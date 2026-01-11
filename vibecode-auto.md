---
description: Đọc trước MỌI task - Tự động áp dụng workflow phù hợp
---

# Auto Workflow - Đọc đầu tiên

## QUAN TRỌNG
File này PHẢI được đọc trước MỌI task coding trong workspace này.

## Quy trình tự động

### Bước 0: Kiểm tra trạng thái dự án ⚠️
// turbo
Kiểm tra trong thư mục dự án:
1. **Có code?** (src/, package.json, requirements.txt, *.py, *.js, etc.)
2. **Có docs?** (docs/BLUEPRINT.md, docs/CONTRACT.md)

**Xử lý:**
- Có code + **CHƯA có docs** → Chạy `/vibecode-adopt` trước!
- Có code + có docs → Tiếp tục Bước 1
- Chưa có code → Chạy `/vibecode` để tạo dự án mới

### Bước 1: Nhận diện loại task
- "thêm", "tạo", "implement" → `/vibecode-add-feature`
- "fix", "sửa", "debug", "lỗi" → `/vibecode-debug`
- "refactor", "cải thiện", "optimize" → `/vibecode-refactor`
- "cài", "install", "thêm package" → `/vibecode-dependency`
- "adopt", "onboard", "tạo docs" → `/vibecode-adopt`

### Bước 2: Load context
// turbo
Đọc `/vibecode-context` trước khi bắt đầu

### Bước 3: Thực hiện workflow tương ứng
Đọc và follow workflow đã nhận diện ở bước 1

### Bước 4: Sau khi hoàn thành
// turbo
- Cập nhật `docs/CHANGELOG.md`
- Cập nhật `docs/DECISIONS.md` nếu cần
- Chạy `/vibecode-review` trước khi báo hoàn thành

## Reminder
> "Nếu không chắc loại task, hỏi user trước khi bắt đầu."
