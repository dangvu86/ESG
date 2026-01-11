---
description: Tạo dự án mới theo quy trình Vibecode V2 (Intake → Blueprint → Contract → Build)
---

# Vibecode - Tạo dự án mới

## 1. Thu thập yêu cầu
Hỏi: Tên dự án? Mục tiêu? Đối tượng? Deadline? Tech stack?

## 2. Tạo cấu trúc
// turbo
```
{project}/
├── docs/ (INTAKE, BLUEPRINT, CONTRACT, GATES, CHANGELOG, DECISIONS)
├── src/
├── tests/
└── README.md
```

## 3. Tạo INTAKE.md
// turbo
Điền: Mục tiêu, Đối tượng, Ràng buộc, Phạm vi, Yêu cầu kỹ thuật

## 4. Tạo BLUEPRINT.md
Thiết kế: Tech stack, Modules, User flows, Data model, Phases
**→ Phải được user duyệt trước khi tiếp tục!**

## 4.5. UI Design (nếu có UI)
Chạy `/vibecode-ui-design` để tạo wireframe/mockup
**→ User review trước khi code!**

## 5. Tạo CONTRACT.md + GATES.md
// turbo
Scope Phase 1, Out of scope, Definition of Done, Gates criteria

## 6. Bắt đầu Build
Sau khi duyệt: Tạo TEST_PLAN.md → Init project → Code theo BLUEPRINT

## ⚠️ Rules
- **Không build khi chưa duyệt Blueprint**
- Cập nhật CHANGELOG sau mỗi thay đổi
- Chạy `/vibecode-gate-check` trước deploy
