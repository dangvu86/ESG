---
description: Self-review code trước khi commit
---

# Review - Kiểm tra code

> **Chạy sau:** `/vibecode-add-feature`, `/vibecode-build`
> **Chạy trước:** commit code hoặc `/vibecode-gate-check`

## 1. Code Quality Checklist
- [ ] Không có duplicate code (extract helper nếu cần)
- [ ] Error handling đầy đủ
- [ ] Không hardcode values (move ra config)
- [ ] Comments cho logic phức tạp
- [ ] Types/interfaces rõ ràng

## 2. Structure Check
- [ ] Code đặt đúng module (theo BLUEPRINT)
- [ ] Không tạo circular imports
- [ ] Follow naming convention
- [ ] Không break existing APIs

## 3. Tests
- [ ] Unit tests cho logic mới
- [ ] Existing tests vẫn pass
// turbo
```bash
npm run test
```

## 4. Final Check
- [ ] CHANGELOG đã cập nhật
- [ ] Docs cập nhật (nếu cần)

## ✅ Ready to Commit
> "Code đã review! Có thể commit. Chạy `/vibecode-gate-check` nếu ready deploy."
</Parameter>
<parameter name="Complexity">3
