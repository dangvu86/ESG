---
description: Nghiên cứu rủi ro ESG công ty từ báo chí - Tự động tìm kiếm và tổng hợp thông tin vi phạm E/S/G
---

// turbo-all

# Workflow: Nghiên cứu Rủi ro ESG từ Báo chí

## Cấu trúc file

```
D:\ESG\
├── esg_data.json          ← Data sự kiện (AI update file này)
├── create_esg_report.py   ← Script tạo Excel (KHÔNG đổi)
└── esg_risk_report_*.xlsx ← Output
```

## Tổng quan Flow

```
Bước 1: Nhập công ty (HPG, VNM...)
    ↓
Bước 2: search_web + after/before filter → Tìm sự kiện vi phạm E/S/G
    ↓
Bước 3: Với mỗi sự kiện → browser search từ khóa cụ thể → Verify link
    ↓
Bước 4: AI update file esg_data.json với data mới
    ↓
Bước 5: Chạy python create_esg_report.py → Excel
```

---

## Đầu vào
- **Danh sách công ty:** Nhập tay (VD: HPG, VNM, FPT)
- **Thời gian:** 5 năm gần nhất (tự động tính)

---

## Bước 1: Chuẩn bị

1. Nhận mã cổ phiếu từ người dùng
2. Chuyển đổi sang tên đầy đủ:
   - `HPG` → `Hòa Phát`
   - `VNM` → `Vinamilk`
   - `FPT` → `FPT`

---

## Bước 2: Tìm kiếm sự kiện (search_web)

> [!IMPORTANT]
> **BẮT BUỘC PHẢI SEARCH 3 LẦN RIÊNG BIỆT** cho mỗi công ty (E, S, G).
> Không được gộp chung hoặc bỏ sót bất kỳ nhóm nào.

### Query mẫu cho từng nhóm:

**Search 1 - Nhóm E (Môi trường):**
```
search_web("[Tên công ty]" vi phạm môi trường ô nhiễm xả thải sự cố hóa chất after:2021-01-01)
```

**Search 2 - Nhóm S (Xã hội):**
```
search_web("[Tên công ty]" tai nạn lao động chết người đình công khiếu nại dân cư after:2021-01-01)
```

**Search 3 - Nhóm G (Quản trị):**
```
search_web("[Tên công ty]" vi phạm chứng khoán bị phạt thuế trốn thuế khởi tố HĐQT after:2021-01-01)
```

### Checklist bắt buộc (phải hoàn thành cả 3):

- [ ] ✅ Đã search E (môi trường)
- [ ] ✅ Đã search S (xã hội)  
- [ ] ✅ Đã search G (quản trị)

### Kết quả từ search_web:
- AI tự động tổng hợp các sự kiện vi phạm
- Mỗi sự kiện có thông tin: thời gian, nội dung, nguồn (domain)
- Danh sách nguồn [1], [2], [3]... kèm theo

---

## Bước 3: Xác nhận link (browser)

> [!IMPORTANT]
> **PHẢI VERIFY TẤT CẢ SỰ KIỆN** tìm được từ Bước 2.
> - Nếu search_web trả về 3 sự kiện → phải gọi browser 3 lần
> - KHÔNG được bỏ qua sự kiện nào mà chưa thử verify
> - KHÔNG được đưa sự kiện vào báo cáo nếu chưa verify link

Với **MỖI sự kiện** tìm được từ Bước 2:

1. **Lấy từ khóa cụ thể** từ kết quả search_web
   - VD: "Hòa Phát Điện lạnh bị phạt 105 triệu xả thải"

2. **Browser search Google** với từ khóa đó
   ```
   browser → google.com.vn → search từ khóa
   ```

3. **Click vào link đầu tiên** từ nguồn uy tín

4. **Xác nhận:**
   - ✅ Link mở được (không 404)
   - ✅ Nội dung đúng sự kiện
   - ✅ Lấy URL đầy đủ

5. **Nếu link không hoạt động:**
   - Thử link tiếp theo từ nguồn khác
   - Nếu tất cả link đều chết → vẫn đưa vào báo cáo với ghi chú "Link không khả dụng"
   - **KHÔNG ĐƯỢC XÓA** sự kiện có thật chỉ vì link không hoạt động

---

## Bước 4: Nguồn tin uy tín

### Ưu tiên cao:
- VnExpress (vnexpress.net)
- Tuổi Trẻ (tuoitre.vn)
- Thanh Niên (thanhnien.vn)
- Lao Động (laodong.vn)
- CafeF (cafef.vn)
- Dân Trí (dantri.com.vn)

### Chấp nhận:
- VietnamNet, Pháp Luật TP.HCM, Báo Đầu tư
- Các báo địa phương (baophutho.vn, baoquangngai.vn...)
- Sức khỏe & Đời sống (suckhoedoisong.vn)

### Loại bỏ:
- Diễn đàn, Facebook, blog cá nhân
- Trang tổng hợp không rõ nguồn

---

## Bước 5: Tổng hợp báo cáo Excel

Tạo file: `D:\ESG\esg_risk_report_[MaCK]_[YYYYMMDD].xlsx`

### Cấu trúc:

| Cột | Mô tả |
|-----|-------|
| Công ty | Tên công ty + mã CK |
| Loại rủi ro | E / S / G |
| Ngày xảy ra | DD/MM/YYYY |
| Tóm tắt | Mô tả ngắn sự kiện |
| Mức độ | Cao / Trung bình / Thấp |
| Link nguồn | **Hyperlink đã verify** |
| Nguồn | Tên báo |

### Hyperlink:
- Cột "Link nguồn" là hyperlink có thể click
- Hiển thị: "Xem bài báo"
- URL: Link đầy đủ đã xác nhận hoạt động

---

## Lưu ý quan trọng

> [!IMPORTANT]
> - Mỗi sự kiện chỉ cần **1 link đại diện** từ nguồn uy tín
> - Link phải được **xác nhận hoạt động** trước khi đưa vào báo cáo
> - Nếu không tìm được link hoạt động → ghi tên nguồn thay vì URL

> [!WARNING]
> - Bài báo cũ (2019-2020) có thể đã bị xóa hoặc đổi URL
> - Một số sự kiện có thể được nhiều báo đưa tin → chỉ lấy 1 link

---

## Ví dụ thực tế

### Input:
```
Công ty: HPG (Hòa Phát)
Thời gian: 2021-2026
```

### Bước 2 - search_web:
```
search_web("Hòa Phát vi phạm môi trường after:2021-01-01 before:2026-01-01")
```
→ Kết quả: "Công ty Điện lạnh Hòa Phát bị phạt 105 triệu đồng xả thải"

### Bước 3 - browser verify:
```
Google: "Điện lạnh Hòa Phát bị phạt 105 triệu xả thải"
Click: giadinh.suckhoedoisong.vn/...
Xác nhận: ✅ Link hoạt động, nội dung đúng
```

### Output Excel:
| Công ty | Loại | Ngày | Tóm tắt | Link |
|---------|------|------|---------|------|
| Hòa Phát (HPG) | E | 07/2019 | Bị phạt 105 triệu đồng xả thải vượt quy chuẩn | [Xem bài báo](url) |
