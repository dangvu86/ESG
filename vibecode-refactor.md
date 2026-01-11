---
description: Refactor an toàn với kiểm soát
---

# Refactor - Cải thiện code

> **Khi nào dùng:** Muốn cải thiện code structure mà không thay đổi behavior

## 1. Pre-check
// turbo
```bash
npm run test  # Ghi nhớ số tests pass
npm run build
```

## 2. Load Context
Chạy `/vibecode-context` (nếu chưa trong session)

## 3. Define Scope
Xác định với user:
- Refactor cái gì?
- Files nào bị ảnh hưởng?
- Expected outcome?

## 4. Safety Checklist
- [ ] Tests hiện có cover behavior cần giữ?
- [ ] Có backup / git commit trước refactor?
- [ ] Refactor nhỏ, incremental (không big bang)?

## 5. Execute
// turbo
Thực hiện refactor theo scope đã định

## 6. Verify
// turbo
```bash
npm run test  # Phải = số tests trước đó
npm run build
```

## 7. Document
// turbo
Cập nhật CHANGELOG:
```markdown
### Changed
- Refactored [what] for [reason]
```

## ⚠️ Rules
- Behavior KHÔNG được thay đổi
- Tests số lượng phải = hoặc > trước
- Nếu test fail → Rollback, check lại
