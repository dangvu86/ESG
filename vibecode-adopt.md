---
description: Tạo docs cho dự án đã có code (reverse-engineering)
---

# Adopt - Onboard dự án có sẵn

> **Khi nào dùng:** Dự án đã có code nhưng chưa có BLUEPRINT/DECISIONS/CONTRACT

## 1. Phân tích Codebase
// turbo
- Đọc cấu trúc thư mục (`src/`, `package.json`, `requirements.txt`, etc.)
- Xác định tech stack đang dùng
- Tìm patterns, conventions, data flows

## 2. Thu thập thông tin bổ sung
Hỏi user:
- Mục tiêu dự án là gì?
- Đối tượng sử dụng?
- Constraints/limitations cần biết?

## 3. Tạo BLUEPRINT.md
// turbo
Reverse-engineer từ code:
```markdown
# BLUEPRINT – [Tên dự án]
## Tech Stack (từ dependencies)
## Modules (từ cấu trúc src/)
## Data Model (từ schema/models)
## User Flows (từ routes/pages)
```

## 4. Tạo DECISIONS.md
// turbo
Ghi lại các quyết định đã thực hiện (suy luận từ code):
```markdown
## ADR-001: Đã dùng [Tech]
**Ngày:** [Ước tính] | **Trạng thái:** Accepted
**Lý do:** [Suy luận từ implementation]
```

## 5. Tạo CONTRACT.md + GATES.md
// turbo
- Scope: Liệt kê features hiện có
- Gates: Dựa trên tests/CI hiện có

## 6. User Review
> "Docs đã tạo từ code. Xem và điều chỉnh?"

## 7. Hoàn thành
Sau khi duyệt → Dùng workflow bình thường (`/vibecode-context` → task)

## ⚠️ Lưu ý
- INTAKE.md có thể bỏ qua (code đã có)
- Docs này document reality, không phải plan
- Sau khi có docs, mọi thay đổi follow workflow bình thường
