---
description: Load context trước khi làm việc (tránh phá vỡ cấu trúc)
---

# Context - Load trước MỌI task

> **Workflow này là BẮT BUỘC trước khi chạy:** `/vibecode-add-feature`, `/vibecode-build`

## Khi nào chạy?
- Bắt đầu session mới
- Làm việc với module chưa quen
- Thay đổi lớn / refactor

## 1. Đọc Architecture
// turbo
```
docs/BLUEPRINT.md   → Hiểu cấu trúc hệ thống
docs/DECISIONS.md   → Biết lý do thiết kế
docs/CONTRACT.md    → Biết scope hiện tại
```

## 2. Đọc Related Files
// turbo
Xác định files liên quan đến task → Đọc để hiểu patterns đang dùng

## 3. Confirm Understanding
Tóm tắt ngắn gọn cho user:
- Architecture hiện tại
- Patterns đang dùng
- Constraints cần tuân thủ

## ⚠️ Warning Signs
Dừng lại nếu:
- Không tìm thấy BLUEPRINT → Chạy `/vibecode-blueprint` trước
- Không hiểu tại sao decision được chọn → Hỏi user
- Task có thể ảnh hưởng nhiều modules → Cần review kỹ hơn

## ✅ Done
> "Context loaded! Tiếp tục với task của bạn."
