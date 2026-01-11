---
description: Bắt đầu Build theo Blueprint và Contract
---

# Build - Bắt đầu xây dựng

## 1. Prerequisites Check
// turbo
Verify có: INTAKE.md, BLUEPRINT.md (đã duyệt), CONTRACT.md, GATES.md
Thiếu → Chạy workflow tương ứng

## 2. Load Context
Chạy `/vibecode-context` để hiểu architecture trước khi code

## 3. Tạo TEST_PLAN.md
// turbo
Unit tests, Integration tests, Commands

## 4. Tạo SECURITY.md (nếu cần auth/data nhạy cảm)
// turbo

## 5. Init Project
Hỏi framework → Chạy init
// turbo
```bash
npm create vite@latest . -- --template react-ts
npm install
```

## 6. Tạo cấu trúc
// turbo
```
src/ → components/, pages/, services/, utils/, types/
```

## 7. Code theo BLUEPRINT
1. Setup core modules trước
2. Implement features theo priority
3. Viết tests song song
4. Cập nhật CHANGELOG

## ⚠️ Rules
- Chạy `/vibecode-context` đầu mỗi session
- Chạy `/vibecode-review` trước mỗi commit
- Chạy `/vibecode-gate-check` trước deploy
