---
description: Tạo UI wireframe/mockup trước khi code (giảm rework)
---

# UI Design - Thiết kế giao diện

> **Khi nào dùng:** Sau BLUEPRINT, trước BUILD (cho dự án có UI)

## 1. Xác định màn hình cần thiết kế
// turbo
Đọc BLUEPRINT → Liệt kê các pages/screens chính

## 2. Chọn loại wireframe

### Option A: Quick Preview (Hình ảnh)
Dùng `generate_image` tool:
- Nhanh (~10s/hình)
- Phù hợp khi cần xem ý tưởng nhanh
- Không interactive

### Option B: Detailed Mockup (HTML) ⭐ Recommended
Tạo HTML/CSS/JS files:
```
wireframes/
├── styles.css      # Shared styles
├── index.html      # Dashboard
├── [page].html     # Các trang khác
```

**Tiêu chuẩn HTML Wireframe:**
- ✅ Responsive (mobile-friendly)
- ✅ Navigation liên kết giữa các trang
- ✅ Dummy data thực tế
- ✅ Hotkeys cho thao tác nhanh
- ✅ Dark/Light theme
- ✅ Tối ưu không gian hiển thị

## 3. User review
> "Đây là wireframe cho [màn hình]. Góp ý gì không?"

Lặp lại cho đến khi user hài lòng.

## 4. Lưu wireframes
// turbo
- Hình ảnh: Lưu vào `docs/UI_WIREFRAMES.md`
- HTML: Lưu vào thư mục `wireframes/`

## 5. Cập nhật BLUEPRINT
// turbo
Thêm reference đến wireframes trong BLUEPRINT.md

## ⚠️ Lưu ý
- Wireframe là HƯỚNG DẪN, không phải pixel-perfect
- Focus vào layout và flow, không phải chi tiết nhỏ
- User có thể yêu cầu thay đổi khi code

## ✅ Done
> "UI design hoàn tất! Tiếp tục với `/vibecode-contract` hoặc `/vibecode-build`"

