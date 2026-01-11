---
description: Kiểm tra Gate trước khi claim hoàn thành
---

# Gate Check - Kiểm tra checkpoint

## 1. Đọc GATES.md
// turbo
Đọc `docs/GATES.md` để biết criteria

## 2. Automated Checks
// turbo
```bash
npm run build
npm run test
npm run lint
npm run type-check  # nếu có TS
```

## 3. Báo cáo
- Build: ✅/❌
- Tests: ✅/❌ (X/Y passed)
- Lint: ✅/❌
- Type Check: ✅/❌

## 4. Manual Checks
Hỏi user từng item từ GATES.md: "Đã hoàn thành [check]? (y/n)"

## 5. Cập nhật GATES.md
// turbo
```markdown
**Trạng thái:** ✅ Passed / ❌ Failed
**Ngày:** [Hôm nay]
```

## 6. Kết luận
- ✅ All pass → "🎉 Gate PASSED! Ready to deploy."
- ❌ Failed → "Cần fix: [liệt kê]. Chạy lại sau khi fix."

## 7. Cập nhật CHANGELOG
// turbo
