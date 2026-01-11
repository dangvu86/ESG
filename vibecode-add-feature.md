---
description: Thêm tính năng mới vào dự án đang có
---

# Add Feature - Thêm tính năng

## 1. Load Context (BẮT BUỘC)
Chạy `/vibecode-context` trước (nếu chưa chạy trong session này)

## 2. Kiểm tra Scope
- **Trong scope** → Bước 4
- **Ngoài scope** → Bước 3

## 3. Nếu ngoài scope
Hỏi user: Thêm vào Phase hiện tại hay để sau?
// turbo
Nếu thêm: Cập nhật CONTRACT.md, BLUEPRINT.md, ghi DECISIONS.md

## 4. Code Structure Check ⚠️
Trước khi code, verify:
- [ ] Đặt đúng module (theo BLUEPRINT)
- [ ] Không tạo circular imports
- [ ] Follow naming convention hiện có
- [ ] Không duplicate logic

## 5. Implement
Xác định module → Viết code → Viết tests → Update docs

## 6. Cập nhật CHANGELOG
// turbo
```markdown
### Added
- [Tên tính năng]: [Mô tả ngắn]
```

## 7. Review & Finish
Chạy `/vibecode-review` → Sau đó `/vibecode-gate-check` nếu ready deploy
