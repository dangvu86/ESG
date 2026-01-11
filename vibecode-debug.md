---
description: Debug có hệ thống (không random fix)
---

# Debug - Xử lý lỗi

> **Khi nào dùng:** Gặp bug hoặc error trong code

## 1. Reproduce
Xác định và ghi lại:
- Error message / stacktrace
- Steps để reproduce
- Expected vs Actual behavior

## 2. Analyze
// turbo
Đọc logs/stacktrace → Xác định file và line gây lỗi

## 3. Find Root Cause
// turbo
Đọc code liên quan, KHÔNG sửa random!
Xác định rõ: Lỗi do logic? Data? Config? Dependency?

## 4. Propose Fix
Giải thích cho user:
- Root cause là gì
- Fix như thế nào
- Tại sao fix này đúng

## 5. Implement & Test
- Apply fix
- Test specific case gây lỗi
- Test regression (không break gì khác)
// turbo
```bash
npm run test
```

## 6. Document
// turbo
Ghi CHANGELOG nếu fix quan trọng

## ⚠️ Rules
- KHÔNG sửa random khi chưa hiểu root cause
- 1 bug = 1 fix (không scope creep)
