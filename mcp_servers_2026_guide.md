# MCP Servers 2026 – Hướng dẫn chi tiết cho Developer

> Dành cho DEVKIT AI / Brian. Mỗi mục gồm: tổng quan, setup, demo thực tế, shortcut/tips.

> **MCP (Model Context Protocol)** là chuẩn mở để kết nối AI models với external tools/data. Nó giúp AI vượt ra ngoài chat — có thể đọc file, query database, browse web, quản lý repo, gửi message... thay vì chỉ trả lời. Được Anthropic đề xuất, hiện đang trở thành standard trong Claude Code, Antigravity, OpenCode và nhiều AI coding tools khác. MCP Server là thành phần chạy độc lập, lắng nghe tool calls từ AI và thực thi trên hệ thống của bạn.

---

## 1. Sequential Thinking

**Tổng quan:** MCP server này cung cấp khả năng chain-of-thought có cấu trúc cho AI. Thay vì AI tự suy luận ngầm, nó chia bài toán thành các bước tư duy rõ ràng, có thể kiểm tra, chỉnh sửa hoặc retry từng bước. Nó không thực thi code — chỉ hỗ trợ reasoning.

**Use case:** Chain-of-thought, debug phức tạp, multi-step reasoning.

### Setup
```bash
# Cài dependency (nếu thiếu)
npm install -g @modelcontextprotocol/server-sequential-thinking
# Chạy
npx @modelcontextprotocol/server-sequential-thinking
```

### Demo
```
Prompt: "Tôi có API timeout production. Hãy liệt kê từng bước debug theo thứ tự ưu tiên."
→ MCP sẽ chia nhỏ thành:
1. Kiểm tra health endpoint
2. Check DB connection pool
3. Xem error log chi tiết
4. Đo latency từng hop
5. Rollback deployment gần nhất
```

### Shortcut
- Dùng khi bạn **không muốn nghĩ hết flow** mà muốn AI thao tác từng bước có logic
- Có thể kết hợp với `Filesystem MCP` để vừa suy nghĩ vừa đọc code

---

## 2. Filesystem

**Tổng quan:** Server này cho phép AI đọc, ghi, di chuyển và quản lý file/folder trên hệ thống local. Nó mở quyền truy cập vào toàn bộ codebase, giúp AI review code, tạo file mới, refactor hàng loạt file — trở thành "coding partner" thực thụ.

**Use case:** Đọc/ghi file, review codebase, di chuyển folder.

### Setup
```bash
npx @modelcontextprotocol/server-filesystem /path/to/project
```

### Demo
```
Prompt: "Đọc file src/auth.ts và tìm lỗi JWT expiration"
→ MCP tự navigate, mở file, highlight lỗi trả về

Prompt: "Tạo file src/utils/date.ts export formatDate()"
→ Tạo file mới, ghi code, xác nhận
```

### Shortcut
- Set quyền read-only nếu chỉ review: thêm flag `--read-only` (nếu server hỗ trợ)
- Dùng với `Claude Code` / `Antigravity` để code thật nhanh

---

## 3. Brave Search

**Tổng quan:** MCP server này wrap API tìm kiếm của Brave Search, cho phép AI thực thi web search trực tiếp từ chat mà không cần mở browser. Kết quả trả về đã được parse sẵn (title, URL, snippet) — nhanh hơn và gọn hơn scraping.

**Use case:** Tìm kiếm web trong chat, real-time.

### Setup
```bash
# Tạo Brave Search API key (miễn phí 2000 req/tháng)
export BRAVE_API_KEY="..."
npx @modelcontextprotocol/server-brave-search
```

### Demo
```
Prompt: "Tìm video YouTube 'Best MCP servers 2026' đang có view cao nhất"
→ Trả về: tiêu đề, view count, channel, URL

Prompt: "So sánh Antigravity 2.0 vs Claude Code 4.8"
→ Tổng hợp từ nhiều nguồn khác nhau
```

### Shortcut
- Combine với `youtube-channel-strategy` skill để auto-find trending
- Tốc độ nhanh hơn browser search vì không cần render page

---

## 4. GitHub MCP

**Tổng quan:** Server này expose GitHub API qua MCP, biến chat thành GitHub client. AI có thể đọc repo, tạo PR, comment issue, check CI status — mọi thao tác Git thông thường đều có thể làm qua prompt.

**Use case:** Manage repo, PR, issues không cần rời khỏi chat.

### Setup
```bash
export GITHUB_TOKEN="ghp_..."
npx @modelcontextprotocol/server-github
```

### Demo
```
Prompt: "Tạo PR từ branch feature/add-login sang main"
→ Tự tạo title, body, base/head branch

Prompt: "Đọc 5 issues gần nhất trong repo backend"
→ List tiêu đề, status, assignee

Prompt: "Review PR #42: chỉ ra lỗi tiềm ẩn"
→ Đọc diff, comment trực tiếp lên GitHub
```

### Shortcut
- Dùng trong workflow code review: chạy 1 prompt → MCP tự check CI, linter, security
- Tích hợp với `Slack MCP` để notify team khi PR merge

---

## 5. SQLite / PostgreSQL MCP

**Tổng quan:** 2 server này kết nối AI trực tiếp với database. AI có thể viết và chạy SQL query, lấy kết quả dạng JSON/table, thậm chí tạo table, migrate schema — tất cả qua chat. Rất mạnh cho data analysis và debugging DB.

**Use case:** Query DB trực tiếp từ chat, không cần mở client.

### Setup SQLite
```bash
npx @modelcontextprotocol/server-sqlite --db-path /path/to/app.db
```

### Setup PostgreSQL
```bash
export DATABASE_URL="postgres://user:pass@localhost:5432/mydb"
npx @modelcontextprotocol/server-postgres
```

### Demo
```
Prompt SQLite: "Liệt kê top 10 users mua hàng nhiều nhất tháng 6"
→ Trả về JSON sẵn, có thể export CSV hoặc visualize

Prompt PostgreSQL: "Kiểm tra connection pool status"
→ SELECT * FROM pg_stat_activity
```

### Shortcut
- Kết hợp với `Filesystem MCP`: đọc CSV → import vào SQLite → query ngay
- Hữu ích khi demo sinh dữ liệu fake cho video (seed data nhanh)

---

## 6. Puppeteer / Playwright

**Tổng quan:** Server này điều khiển Chromium browser headless qua MCP. AI có thể navigate page, click, fill form, chụp screenshot, extract DOM — tự động hóa bất cứ thao tác browser nào mà không cần mở UI. Playwright thay thế Puppeteer nếu cần cross-browser (Firefox/WebKit).

**Use case:** Automate browser, scrape, test UI end-to-end.

### Setup
```bash
npx @modelcontextprotocol/server-puppeteer
# Hoặc Playwright
npx @modelcontextprotocol/server-playwright
```

### Demo
```
Prompt: "Vào https://devkit.vn, chụp screenshot homepage"
→ Chụp ảnh trả về

Prompt: "Login devkit.vn với account test, check xem dashboard load không"
→ Điền form, submit, check element, báo PASS/FAIL
```

### Shortcut
- Dùng để **record bug** khi QA: prompt 1 câu → chụp screenshot + log network
- Tự động test form / checkout page cho WooCommerce

---

## 7. Docker MCP

**Tổng quan:** Server này expose Docker Daemon API, cho phép AI quản lý container trực tiếp từ chat: list, start/stop, xem log, exec, check health. Nó biến terminal docker thành conversation — hữu ích khi deploy hoặc debug microservice.

**Use case:** Quản lý container, logs, exec, health-check.

### Setup
```bash
# Cài docker CLI (đã có rồi thì thôi)
npx @modelcontextprotocol/server-docker
```

### Demo
```
Prompt: "List containers đang chạy, báo status từng cái"
→ Trả về: name, status, uptime, port mapping

Prompt: "Xem log container backend-api, tìm lỗi 'connection refused'"
→ grep log, highlight dòng lỗi, suggest fix

Prompt: "Restart container nginx"
→ docker restart nginx → xác nhận thành công
```

### Shortcut
- Dùng trong dev workflow: build → run → check log → restart đều qua chat
- Combine với `Slack MCP` để gửi alert khi container down

---

## 8. Google Drive MCP

**Tổng quan:** Server này tích hợp Google Drive/ Docs/ Sheets API vào MCP. AI có thể đọc spreadsheet, tạo doc, upload file, quản lý folder — tất cả mà không cần mở Google UI. Rất phù hợp khi dùng Sheets làm CMS hoặc dashboard.

**Use case:** Đọc/ghi/spreadsheet/docs trực tiếp từ chat.

### Setup
```bash
export GOOGLE_APPLICATION_CREDENTIALS="service_account.json"
npx @modelcontextprotocol/server-gdrive
```

### Demo
```
Prompt: "Đọc file Google Sheet 'content-calendar' sheet 6, trả về 5 hàng đầu"
→ Parse trực tiếp, trả JSON/table

Prompt: "Tạo Google Doc 'DEVKIT AI - July Plan' và copy draft vào"
→ Tạo file, ghi content, trả về URL

Prompt: "Upload ảnh thumbnail vào folder 'DEVKIT Thumbnails'"
→ Upload → lấy share link
```

### Shortcut
- Dùng làm **CMS nội dung** cho kênh YouTube: ghi chude, script, schedule từ Sheets
- Tự động backup báo cáo GA4/GSC lên Drive hàng ngày

---

## 📌 Góc nhìn chung

| Nhóm | Server phù hợp | Công dụng chính |
|------|----------------|-----------------|
| **Code** | Filesystem, Sequential Thinking, Docker | Viết code nhanh, debug, quản lý môi trường |
| **Data** | SQLite/PostgreSQL, Google Drive | Query DB, quản lý tài liệu |
| **Ops** | GitHub, Puppeteer, Docker | Deploy, test, monitor |
| **Research** | Brave Search, YouTube (qua browser) | Tìm trend, phân tích đối thủ |
