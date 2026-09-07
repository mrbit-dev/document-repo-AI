# Hướng dẫn cài đặt và sử dụng Obsidian

> **Obsidian** là ứng dụng quản lý ghi chú và xây dựng hệ thống tri thức cá nhân (Personal Knowledge Management - PKM).
>
> Điểm quan trọng nhất: Obsidian lưu ghi chú dưới dạng **file Markdown (`.md`) trên máy tính của bạn**, vì vậy dữ liệu không bị khóa trong một định dạng độc quyền.

---

# 1. Obsidian là gì?

Obsidian là một ứng dụng dùng để:

- Ghi chú cá nhân
- Quản lý kiến thức
- Viết tài liệu
- Quản lý dự án
- Xây dựng Wiki cá nhân
- Quản lý ý tưởng
- Viết nội dung
- Làm Documentation
- Quản lý tài liệu cho lập trình
- Xây dựng hệ thống PKM
- Kết nối kiến thức bằng các liên kết giữa các note

Điểm khác biệt lớn của Obsidian so với nhiều ứng dụng ghi chú truyền thống là:

```text
Note A
   ↓
Note B
   ↓
Note C
   ↓
Note D
```

Các note có thể liên kết với nhau để tạo thành một **Knowledge Graph**.

Obsidian cũng hỗ trợ Graph View để trực quan hóa mối quan hệ giữa các note.

---

# 2. Vì sao Obsidian được nhiều người sử dụng?

## 2.1. Dữ liệu nằm trên máy của bạn

Obsidian lưu note dưới dạng:

```text
Markdown
↓
File .md
↓
Folder trên máy tính
```

Ví dụ:

```text
D:\Obsidian\MyVault\
│
├── README.md
├── Projects\
│   ├── Project-A.md
│   └── Project-B.md
│
├── Notes\
│   ├── AI.md
│   └── Programming.md
│
└── Attachments\
    ├── image.png
    └── document.pdf
```

Bạn có thể mở các file Markdown này bằng nhiều trình soạn thảo khác nhau.

Điều này giúp giảm sự phụ thuộc vào một ứng dụng duy nhất.

---

# 3. Download Obsidian

Website chính thức:

https://obsidian.md/

Trang download:

https://obsidian.md/download

Obsidian có phiên bản cho:

- Windows
- macOS
- Linux
- iOS
- Android

Website chính thức hiện cung cấp phiên bản Desktop và Mobile.

---

# 4. Cài đặt Obsidian trên Windows

## Bước 1: Download

Truy cập:

https://obsidian.md/download

Chọn:

```text
Windows
```

Tải installer về máy.

---

## Bước 2: Cài đặt

Chạy file `.exe`.

Thực hiện các bước cài đặt bình thường.

Sau khi cài xong mở:

```text
Obsidian
```

---

# 5. Vault là gì?

Đây là khái niệm cực kỳ quan trọng.

**Vault = một thư mục chứa toàn bộ hệ thống ghi chú của bạn.**

Ví dụ:

```text
D:\Obsidian\MyVault
```

Bên trong có:

```text
MyVault
│
├── .obsidian
├── Notes
├── Projects
├── Attachments
└── README.md
```

Trong đó:

```text
.obsidian
```

là thư mục cấu hình của Vault.

Các note chủ yếu là:

```text
.md
```

---

# 6. Tạo Vault đầu tiên

Mở Obsidian.

Chọn:

```text
Create new vault
```

Đặt tên:

```text
MyVault
```

Chọn vị trí.

Ví dụ:

```text
D:\Obsidian\MyVault
```

Sau đó chọn:

```text
Create
```

Obsidian sẽ mở Vault.

---

# 7. Nên đặt Vault ở đâu?

Có thể đặt Vault ở:

```text
C:\Users\<username>\Documents\Obsidian
```

hoặc:

```text
D:\Obsidian
```

Nếu có nhiều project và dữ liệu lớn, có thể dùng:

```text
D:\Obsidian
```

Ví dụ:

```text
D:\Obsidian\
│
├── Knowledge
├── Projects
├── AI
├── Programming
└── Personal
```

---

# 8. Cấu trúc Vault khuyên dùng

Một cấu trúc đơn giản:

```text
MyVault
│
├── 00-Inbox
│
├── 01-Projects
│
├── 02-Areas
│
├── 03-Resources
│
├── 04-Archive
│
├── 05-Daily
│
├── 06-Templates
│
└── Attachments
```

Ý nghĩa:

### 00-Inbox

Nơi chứa những thứ mới ghi nhanh.

```text
00-Inbox
```

Ví dụ:

```text
idea-video.md
idea-project.md
todo.md
```

---

### 01-Projects

Các dự án đang thực hiện.

Ví dụ:

```text
01-Projects
│
├── YouTube
├── Claude-Code
├── Obsidian
├── AI-Agent
└── Website
```

---

### 02-Areas

Các lĩnh vực cần duy trì lâu dài.

Ví dụ:

```text
02-Areas
│
├── Programming
├── AI
├── Linux
├── Networking
└── Content
```

---

### 03-Resources

Tài liệu tham khảo.

Ví dụ:

```text
03-Resources
│
├── Books
├── Tutorials
├── Documentation
└── Research
```

---

### 04-Archive

Các project hoặc tài liệu không còn hoạt động.

---

### 05-Daily

Daily Notes.

Ví dụ:

```text
2026-08-12.md
2026-08-13.md
2026-08-14.md
```

---

### 06-Templates

Các template dùng lại nhiều lần.

Ví dụ:

```text
Daily Note.md
Project.md
Meeting.md
Video.md
```

---

# 9. Tạo Note

Có nhiều cách.

Cách đơn giản:

```text
Ctrl + N
```

Sau đó đặt tên:

```text
Claude Code
```

Obsidian sẽ tạo:

```text
Claude Code.md
```

---

# 10. Markdown cơ bản

Obsidian sử dụng Markdown.

## Heading

```markdown
# Tiêu đề 1

## Tiêu đề 2

### Tiêu đề 3
```

---

## Bold

```markdown
**Nội dung**
```

Kết quả:

**Nội dung**

---

## Italic

```markdown
*Nội dung*
```

---

## Code

Inline:

```markdown
`npm install`
```

Code block:

````markdown
```bash
npm install
```
````

---

## Danh sách

```markdown
- Item 1
- Item 2
- Item 3
```

---

## Checklist

```markdown
- [ ] Cài Obsidian
- [ ] Tạo Vault
- [ ] Tạo note
- [ ] Cài plugin
```

---

# 11. Internal Link - tính năng quan trọng nhất

Obsidian cho phép liên kết giữa các note.

Cú pháp:

```markdown
[[Claude Code]]
```

Nếu có note:

```text
Claude Code.md
```

thì:

```markdown
[[Claude Code]]
```

sẽ tạo liên kết tới note đó.

---

# 12. Link tới một Heading

Ví dụ note:

```text
Claude Code.md
```

có:

```markdown
## Installation
```

Có thể link:

```markdown
[[Claude Code#Installation]]
```

---

# 13. Link tới Block

Obsidian cũng hỗ trợ liên kết tới block cụ thể trong note.

Ví dụ:

```markdown
Một đoạn nội dung quan trọng.
^important
```

Có thể link:

```markdown
[[Claude Code#^important]]
```

---

# 14. Backlink

Giả sử:

```text
Obsidian.md
```

link tới:

```text
Claude-Code.md
```

thì Obsidian có thể hiển thị:

```text
Backlinks
```

cho biết note nào đang liên kết tới note hiện tại.

Đây là một trong những cơ chế quan trọng để xây dựng Knowledge Graph.

---

# 15. Graph View

Graph View giúp xem trực quan mối quan hệ giữa các note.

Có thể mở bằng:

```text
Command Palette
→ Graph view
```

Bạn sẽ thấy dạng:

```text
             AI
             │
       ┌─────┴─────┐
       ↓           ↓
Claude Code     Agents
       │           │
       ↓           ↓
   Obsidian      MCP
```

Graph càng lớn thì hệ thống kiến thức càng trở nên liên kết.

---

# 16. Tags

Có thể sử dụng tag:

```markdown
#ai
#programming
#claude-code
#obsidian
```

Ví dụ:

```markdown
# Claude Code

#ai
#programming
#claude-code
```

Có thể tìm kiếm các note theo tag.

---

# 17. Properties

Obsidian hỗ trợ metadata cho note.

Ví dụ:

```yaml
---
title: Claude Code
type: tutorial
status: active
tags:
  - ai
  - programming
created: 2026-08-12
---
```

Properties rất hữu ích khi kết hợp với các plugin như Dataview.

---

# 18. Daily Notes

Daily Notes giúp tạo một note cho từng ngày.

Ví dụ:

```text
2026-08-12.md
```

Nội dung:

```markdown
# 2026-08-12

## Công việc hôm nay

- [ ] Làm video
- [ ] Cập nhật project
- [ ] Nghiên cứu Obsidian

## Ý tưởng

...

## Ghi chú

...
```

Daily Notes có thể được bật trong Core Plugins.

---

# 19. Templates

Template giúp tạo note theo một cấu trúc cố định.

Ví dụ:

```markdown
# {{title}}

## Mục tiêu

## Nội dung

## Todo

- [ ]

## Notes

## Next Steps
```

Có thể tạo:

```text
06-Templates/Project.md
```

Sau đó dùng template này mỗi khi tạo project mới.

---

# 20. Command Palette

Một tính năng cực kỳ hữu ích:

```text
Ctrl + P
```

Command Palette cho phép tìm nhanh các chức năng của Obsidian.

Ví dụ:

```text
Create new note
Open graph view
Search
Toggle reading view
Insert template
Open settings
```

Thay vì nhớ vị trí từng chức năng, chỉ cần:

```text
Ctrl + P
```

và tìm.

---

# 21. Search

Obsidian có hệ thống tìm kiếm toàn bộ Vault.

Có thể tìm:

```text
Claude Code
```

hoặc:

```text
AI Agent
```

Search có thể tìm trong nội dung note.

Đây là một lý do rất lớn khiến việc lưu kiến thức dưới dạng Markdown trở nên hữu ích.

---

# 22. Canvas

Canvas là không gian làm việc trực quan.

Có thể dùng để:

- Brainstorm
- Sơ đồ hóa ý tưởng
- Lập kế hoạch
- Thiết kế workflow
- Nghiên cứu
- Liên kết note
- Làm mind map

Ví dụ:

```text
                  AI
                   │
        ┌──────────┼──────────┐
        ↓          ↓          ↓
    Claude      Gemini      Kimi
        │          │          │
        └──────┬───┴──────────┘
               ↓
            AI Agent
               │
               ↓
             MCP
```

Canvas là một tính năng được tích hợp trong Obsidian.

---

# 23. Attachments

Vault không chỉ chứa Markdown.

Có thể chứa:

```text
.png
.jpg
.jpeg
.gif
.pdf
.mp3
.mp4
```

Ví dụ:

```text
Attachments
│
├── screenshot.png
├── diagram.png
└── document.pdf
```

Các file này có thể được tham chiếu từ Markdown.

Ví dụ:

```markdown
![[screenshot.png]]
```

---

# 24. Community Plugins

Obsidian có hệ thống Community Plugins.

Plugin mở rộng khả năng của Obsidian.

Website plugin:

https://community.obsidian.md/plugins

Một số plugin nổi tiếng:

### Dataview

Dùng để truy vấn dữ liệu trong Vault.

Ví dụ:

```text
Tất cả project có status = active
```

---

### Tasks

Quản lý task trong toàn bộ Vault.

---

### Calendar

Hiển thị Daily Notes theo lịch.

---

### Kanban

Biến note thành Kanban board.

---

### Templater

Tạo template nâng cao.

Obsidian hiện có hàng nghìn plugin và theme cộng đồng.

---

# 25. Cách cài Community Plugin

Vào:

```text
Settings
→ Community plugins
→ Turn on community plugins
→ Browse
```

Tìm plugin cần cài.

Ví dụ:

```text
Dataview
```

Chọn:

```text
Install
```

Sau đó:

```text
Enable
```

---

# 26. Plugin nên cài cho người mới

Không nên cài quá nhiều plugin ngay từ đầu.

Có thể bắt đầu với:

```text
Dataview
Tasks
Calendar
Templater
```

Sau khi quen Obsidian mới mở rộng thêm.

---

# 27. Obsidian và Git

Một lợi thế lớn của Vault là dữ liệu nằm trong filesystem.

Ví dụ:

```text
D:\Obsidian\MyVault
```

Có thể quản lý bằng Git:

```bash
git init
git add .
git commit -m "Initial vault"
```

Sau đó có thể đưa repository lên Git server.

Điều này đặc biệt hữu ích với:

- Developer
- Documentation
- Technical Notes
- Project Knowledge
- AI Agent Knowledge Base

---

# 28. Obsidian và VS Code

Obsidian và VS Code có thể cùng làm việc trên một thư mục.

Ví dụ:

```text
D:\Obsidian\MyVault
```

Obsidian:

```text
→ quản lý kiến thức
```

VS Code:

```text
→ chỉnh sửa file
→ code
→ Git
→ terminal
```

Ví dụ:

```text
D:\Obsidian\MyVault
│
├── AI.md
├── Claude-Code.md
└── Projects
```

VS Code có thể mở trực tiếp thư mục này.

---

# 29. Obsidian và Claude Code

Đây là một workflow rất mạnh.

Có thể sử dụng:

```text
Obsidian
    ↓
Knowledge Base
    ↓
Markdown
    ↓
Claude Code
    ↓
AI Agent
```

Ví dụ:

```text
D:\Obsidian\MyVault
```

chứa:

```text
AI/
├── Claude-Code.md
├── MCP.md
├── Prompt-Engineering.md
└── AI-Agent.md
```

Claude Code có thể làm việc với các file Markdown này như các file thông thường trên filesystem.

Điểm quan trọng:

> Obsidian không phải là database đóng kín. Vault về bản chất là một thư mục chứa dữ liệu mà các công cụ khác có thể truy cập.

---

# 30. Ví dụ workflow Obsidian + Claude Code

Giả sử có project:

```text
D:\www\my-project
```

và Vault:

```text
D:\Obsidian\MyVault
```

Có thể tổ chức:

```text
D:\Obsidian\MyVault
│
├── Projects
│   └── My-Project.md
│
├── AI
│   ├── Claude-Code.md
│   └── MCP.md
│
└── Knowledge
```

Trong:

```text
My-Project.md
```

ghi:

```markdown
# My Project

## Project Path

D:\www\my-project

## Technology

- PHP
- MySQL
- Nginx

## Architecture

...

## TODO

- [ ] Authentication
- [ ] API
- [ ] Dashboard
```

Claude Code có thể sử dụng các file Markdown này làm tài liệu tham khảo khi làm việc với project.

---

# 31. Obsidian có mở được HTML không?

Cần phân biệt:

```text
Obsidian Vault
≠
Obsidian Editor
```

Vault có thể chứa nhiều loại file.

Ví dụ:

```text
.html
.css
.js
.php
.py
.json
.pdf
.png
.md
```

Nhưng Obsidian chủ yếu được thiết kế để **soạn thảo và hiển thị Markdown**.

Vì vậy:

```text
File system
    ↓
Có thể chứa HTML
    ↓
Nhưng Obsidian không phải IDE HTML
```

Nếu cần chỉnh sửa HTML chuyên sâu:

```text
VS Code
```

sẽ phù hợp hơn.

---

# 32. Obsidian Sync

Obsidian Sync là dịch vụ đồng bộ Vault giữa các thiết bị.

Ví dụ:

```text
PC
 │
 ├── Obsidian Sync
 │
 ├── Laptop
 │
 └── Phone
```

Sync hỗ trợ mã hóa end-to-end và version history.

Nếu sử dụng Sync, nên hiểu rằng:

```text
Local Vault
      ↓
Obsidian Sync
      ↓
Remote Vault
      ↓
Other Devices
```

---

# 33. Có nhất thiết phải mua Obsidian Sync không?

Không.

Nếu chỉ sử dụng một máy:

```text
Obsidian
+
Local Vault
```

là đủ.

Nếu muốn đồng bộ nhiều thiết bị có thể lựa chọn:

```text
Obsidian Sync
```

hoặc các phương án đồng bộ khác phù hợp với workflow của bạn.

---

# 34. Backup Vault

Không nên chỉ dựa vào Sync.

Nên backup Vault định kỳ.

Ví dụ:

```text
D:\Obsidian\MyVault
```

backup thành:

```text
E:\Backup\MyVault
```

hoặc:

```text
MyVault-2026-08-12.zip
```

---

# 35. Git Backup

Với người làm kỹ thuật, có thể sử dụng:

```text
Obsidian
+
Git
```

Workflow:

```text
Edit note
   ↓
Git add
   ↓
Git commit
   ↓
Git push
```

Ưu điểm:

- Version control
- Xem lịch sử thay đổi
- Rollback
- Backup
- Đồng bộ repository

---

# 36. Cách tổ chức kiến thức hiệu quả

Không nên biến Obsidian thành một thư mục chứa hàng nghìn note không có liên kết.

Nên xây dựng:

```text
Capture
   ↓
Organize
   ↓
Connect
   ↓
Review
   ↓
Create
```

Ví dụ:

```text
Ý tưởng
  ↓
Inbox
  ↓
Note
  ↓
Link
  ↓
Knowledge
  ↓
Project
  ↓
Content
```

---

# 37. Quy tắc đặt tên file

Nên dùng tên rõ ràng.

Ví dụ tốt:

```text
Claude-Code.md
Obsidian.md
MCP.md
AI-Agent.md
Nginx-Reverse-Proxy.md
```

Không nên:

```text
abc.md
note1.md
new.md
test2.md
```

---

# 38. Không nên lạm dụng Folder

Obsidian mạnh nhờ:

```text
Links
+
Tags
+
Properties
+
Search
+
Graph
```

Không nhất thiết phải tạo cấu trúc folder quá sâu:

```text
AI
└── Programming
    └── Tools
        └── Claude
            └── Code
                └── Notes
```

Có thể đơn giản hơn:

```text
AI
Claude-Code.md
MCP.md
Programming.md
```

và dùng:

```markdown
[[Claude-Code]]
[[MCP]]
[[Programming]]
```

để kết nối.

---

# 39. Mô hình PARA

Một phương pháp tổ chức phổ biến:

```text
Projects
Areas
Resources
Archives
```

Ví dụ:

```text
Projects
├── YouTube
├── Website
└── AI-Agent

Areas
├── Programming
├── AI
└── Content

Resources
├── Tutorials
├── Books
└── Documentation

Archives
└── Old Projects
```

---

# 40. Workflow Obsidian đề xuất

Đối với người làm công nghệ:

```text
00-Inbox
     ↓
Ghi nhanh
     ↓
Review
     ↓
01-Projects
02-Areas
03-Resources
     ↓
Link các note
     ↓
Properties / Tags
     ↓
Dataview
     ↓
Knowledge Base
```

---

# 41. Workflow dành cho YouTube

Có thể xây:

```text
YouTube
│
├── Ideas
├── Research
├── Scripts
├── Published
└── Analytics
```

Ví dụ:

```text
YouTube/Ideas/Obsidian-Claude-Code.md
```

Nội dung:

```markdown
# Obsidian + Claude Code

## Hook

Obsidian có thể trở thành bộ não kiến thức cho Claude Code.

## Problem

...

## Solution

...

## Demo

...

## Script

...

## Thumbnail

...

## Status

idea
```

---

# 42. Workflow dành cho AI

Có thể tạo:

```text
AI
│
├── Models
├── Agents
├── Claude
├── Gemini
├── Kimi
├── MCP
├── Prompt Engineering
└── Tools
```

Ví dụ:

```text
AI/Claude-Code.md
AI/MCP.md
AI/Agents.md
AI/Prompt-Engineering.md
```

Sau đó liên kết:

```markdown
[[Claude-Code]]
[[MCP]]
[[AI-Agents]]
```

---

# 43. Workflow dành cho lập trình

Ví dụ:

```text
Programming
│
├── Linux
├── Windows
├── Docker
├── Nginx
├── NodeJS
├── PHP
├── Python
└── Git
```

Một note:

```text
Nginx-Reverse-Proxy.md
```

có thể link tới:

```markdown
[[Linux]]
[[Nginx]]
[[SSL]]
[[Cloudflare]]
```

Dần dần Vault trở thành một Wiki kỹ thuật cá nhân.

---

# 44. Obsidian + AI

Một trong những workflow đáng chú ý:

```text
Knowledge
      ↓
Markdown
      ↓
Obsidian
      ↓
AI Agent
      ↓
Claude Code
      ↓
Project
```

AI có thể đọc các tài liệu Markdown để hiểu:

- Quy trình
- Kiến trúc
- Quyết định kỹ thuật
- Documentation
- Project requirements
- Coding conventions
- TODO
- Knowledge base

---

# 45. Obsidian không phải là "Word nâng cấp"

Đây là cách hiểu sai phổ biến.

Obsidian không chỉ nhằm mục đích:

```text
Viết note
```

Mà mạnh ở:

```text
Knowledge Graph
+
Markdown
+
Links
+
Properties
+
Plugins
+
Automation
```

---

# 46. Ba cấp độ sử dụng Obsidian

## Level 1 - Beginner

Sử dụng:

```text
Notes
Markdown
Folders
Links
Tags
Search
```

---

## Level 2 - Advanced

Thêm:

```text
Properties
Templates
Daily Notes
Canvas
Dataview
Tasks
Git
```

---

## Level 3 - Power User

Xây dựng:

```text
Obsidian
+
Git
+
Automation
+
AI
+
Claude Code
+
MCP
+
Scripts
+
Knowledge Base
```

Lúc này Obsidian không còn đơn thuần là app ghi chú mà trở thành một **Knowledge Operating System** cho workflow cá nhân.

---

# 47. Bộ cấu hình đề xuất

Nếu mới bắt đầu, nên dùng:

```text
Core Plugins
├── Daily Notes
├── Templates
├── Backlinks
├── Graph View
├── Canvas
├── Search
└── Properties

Community Plugins
├── Dataview
├── Tasks
├── Calendar
└── Templater
```

Không nên cài hàng chục plugin ngay lập tức.

---

# 48. Checklist cài đặt

- [ ] Download Obsidian
- [ ] Cài Obsidian
- [ ] Tạo Vault
- [ ] Chọn vị trí Vault
- [ ] Tạo cấu trúc folder
- [ ] Tạo note đầu tiên
- [ ] Học Markdown
- [ ] Học `[[Internal Links]]`
- [ ] Học Tags
- [ ] Học Properties
- [ ] Bật Daily Notes
- [ ] Tạo Templates
- [ ] Thử Graph View
- [ ] Thử Canvas
- [ ] Cài Dataview
- [ ] Cài Tasks
- [ ] Thiết lập backup
- [ ] Cân nhắc Git
- [ ] Cân nhắc Sync

---

# 49. Cấu trúc Vault hoàn chỉnh đề xuất

```text
D:\Obsidian\MyVault
│
├── 00-Inbox
│
├── 01-Projects
│   ├── YouTube
│   ├── Claude-Code
│   ├── Obsidian
│   └── AI-Agent
│
├── 02-Areas
│   ├── AI
│   ├── Programming
│   ├── Linux
│   ├── Networking
│   └── Content
│
├── 03-Resources
│   ├── Documentation
│   ├── Tutorials
│   ├── Books
│   └── Research
│
├── 04-Archive
│
├── 05-Daily
│
├── 06-Templates
│   ├── Daily.md
│   ├── Project.md
│   ├── Meeting.md
│   └── Video.md
│
└── Attachments
```

---

# 50. Kết luận

Nếu chỉ sử dụng Obsidian như một ứng dụng ghi chú:

```text
Obsidian
=
Note App
```

Nhưng nếu sử dụng đúng cách:

```text
Markdown
      +
Internal Links
      +
Backlinks
      +
Tags
      +
Properties
      +
Graph
      +
Canvas
      +
Plugins
      +
Git
      +
AI
      +
Claude Code
```

thì Obsidian có thể trở thành:

```text
PERSONAL KNOWLEDGE BASE
          +
PROJECT MANAGEMENT
          +
DOCUMENTATION
          +
AI KNOWLEDGE BASE
          +
DEVELOPER WORKSPACE
```

Đặc biệt với workflow lập trình và AI Agent, việc Vault sử dụng các file Markdown cục bộ khiến nó rất phù hợp để kết hợp với các công cụ developer khác. Obsidian cũng có URI scheme để mở Vault, note, search hoặc tạo note từ các ứng dụng khác, giúp mở rộng khả năng automation.

---

# Tài liệu chính thức

- Website: https://obsidian.md/
- Help: https://help.obsidian.md/
- Plugins: https://community.obsidian.md/plugins
- Developer documentation: https://docs.obsidian.md/
- Obsidian Sync: https://obsidian.md/sync