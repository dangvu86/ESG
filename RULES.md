# Vibecode Rules - AUTO APPLY

> Đây là file quy tắc bắt buộc. Khi có yêu cầu coding trong workspace này, AI PHẢI tuân thủ.

## Quy tắc bắt buộc

### 1. Trước MỌI task coding
- Đọc `/vibecode-context` để load context
- Kiểm tra BLUEPRINT.md và DECISIONS.md

### 2. Khi thêm tính năng
- Follow `/vibecode-add-feature`
- Không code trước khi check scope

### 3. Khi fix lỗi
- Follow `/vibecode-debug`
- Tạo test script trước khi fix

### 4. Khi refactor
- Follow `/vibecode-refactor`
- Chạy tests trước và sau

### 5. Sau MỌI thay đổi
- Cập nhật CHANGELOG.md
- Ghi DECISIONS.md nếu có quyết định quan trọng

## Code Quality Guidelines

> Đây là HƯỚNG DẪN, không phải luật cứng. AI nên cố gắng tuân theo, nhưng có thể linh hoạt nếu có lý do hợp lý.

### 1. Function Length
- Ưu tiên function ngắn (~50 lines hoặc ít hơn)
- Nếu cần dài hơn → Cân nhắc tách thành functions nhỏ hơn
- Nếu vẫn cần dài → Thêm comment giải thích

### 2. File Length
- Ưu tiên file ngắn (~300 lines hoặc ít hơn)
- File dài → Cân nhắc tách thành modules riêng
- Ngoại lệ: Config files, test files, generated code

### 3. Code Complexity
- Hạn chế nested if/else quá sâu (>3 levels)
- Ưu tiên early return thay vì nested conditions
- Logic phức tạp → Tách thành helper functions

### 4. Code Clarity
- Tên biến/function rõ ràng, mô tả đúng mục đích
- Comment cho logic phức tạp hoặc "magic numbers"
- Không hardcode values → Dùng constants/config

### 5. Error Handling
- Mọi async call cần try/catch hoặc error handling
- Error messages rõ ràng, hữu ích cho debug
- Không swallow errors (catch rồi không làm gì)

### 6. Security (Bắt buộc ⚠️)
- KHÔNG hardcode secrets, API keys, passwords
- Validate input từ user
- Escape output để tránh XSS/SQL injection

## Nhắc nhở
AI: Nếu bạn đọc file này, hãy tuân thủ các quy tắc trên cho MỌI task trong workspace này.
