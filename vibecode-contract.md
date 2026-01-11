---
description: Tạo Contract (phạm vi & tiêu chuẩn) từ Blueprint
---

# Contract - Chốt phạm vi

## 1. Đọc Blueprint
// turbo
Đọc `docs/BLUEPRINT.md`

## 2. Xác định với user
- **Scope Phase 1**: Tính năng nào làm?
- **Out of Scope**: Để Phase sau?
- **Definition of Done**: Khi nào xong?

## 3. Tạo CONTRACT.md
// turbo
```markdown
# CONTRACT – Phase 1
## Scope: [Liệt kê]
## Out of Scope: [Liệt kê]
## Definition of Done: [Criteria]
## Testing: Unit >80%, Integration
## Gates: [Checkpoints]
```

## 4. Tạo GATES.md
// turbo
```markdown
# GATES
## Gate 1 – [Tên]
### Manual: [ ] Check 1, [ ] Check 2
### Automated: npm run build/test/lint
### Trạng thái: ⏳ Pending
```

## 5. Thông báo
> "Contract ready! Chạy `/vibecode-build` để bắt đầu."
