---
description: Thêm dependency an toàn
---

# Dependency - Thêm thư viện mới

> **Khi nào dùng:** Cần cài thêm npm package / library mới

## 1. Justify
Trả lời trước khi install:
- Thư viện này giải quyết vấn đề gì?
- Có thể tự implement không? (nếu đơn giản)
- Có alternative nhẹ hơn không?

## 2. Check Compatibility
// turbo
```bash
npm info [package-name]
```
- Version stable?
- Last update gần đây?
- Weekly downloads hợp lý?
- License phù hợp? (MIT, Apache, etc.)

## 3. Check Conflicts
- Có conflict với packages hiện có?
- Có cùng chức năng với package đã có?

## 4. Install
// turbo
```bash
npm install [package-name]
# hoặc
npm install -D [package-name]  # nếu devDependency
```

## 5. Document
// turbo
Ghi vào DECISIONS.md:
```markdown
## ADR-XXX: Thêm [package-name]
**Ngày:** [Hôm nay]
**Lý do:** [Giải quyết vấn đề gì]
**Alternatives xem xét:** [Nếu có]
```

## 6. Update CHANGELOG
// turbo
```markdown
### Added
- Added [package-name] for [purpose]
```

## ⚠️ Rules
- KHÔNG install nếu chưa justify được
- Prefer packages với stars > 1000, recent updates
- Check bundle size nếu frontend
