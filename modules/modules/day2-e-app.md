# Day 2: Hệ sinh thái e-App & Thu thập Dữ liệu (OCR/AI)

## ⏱️ Bạn Có 30 Phút Hôm Nay!
- **10 Phút**: Nắm chắc luồng nộp Hồ sơ e-App.
- **10 Phút**: Tìm hiểu luồng tích hợp AI OCR vào CCCD.
- **10 Phút**: Viết User Story với Gherkin bằng AI.

---

## 📖 1. Khái niệm Cốt lõi (10 Phút)

### Vậy e-App (Electronic Application) là mớ gì?
Nếu Bảng minh họa (Illustration) là lúc *Dụ dỗ & Tính toán phí dự kiến*, thì e-App là lúc **Chốt đơn (Đồng ý mua)**. e-App là một siêu ứng dụng web hoặc iPad để Đại lý giúp Khách điền thông tin và ký tên.

1 e-App bắt buộc chứa các Khối thông tin (Blocks) sau:
1. **Thông tin Cá nhân cơ bản (PII)**: CMND/CCCD, Tên, Ngày sinh.
2. **Khai báo FATCA/CRS**: Khai thuế (bạn có quốc tịch Mỹ hay nộp thuế ở nước ngoài không?).
3. **Khai báo Y tế (Medical Declaration)**: Bộ câu hỏi "Có/Không".
4. **Khai báo Thu nhập (Financial Questionnaire)**: Mua hợp đồng 500 triệu mà lương 5 triệu/tháng -> Nguy cơ trục lợi bảo hiểm/Rửa tiền.

---

## 🚀 2. Ứng dụng AI/OCR vào e-App (10 Phút)
Lúc xưa: Agent gõ tay 20 trường thông tin CCCD -> Nhầm lẫn -> Hợp đồng bị trả về (Pended).
Bây giờ (AI Era): Camera -> Chụp CCCD -> AI/OCR quét mã QR & Text -> Điền thẳng vào 20 trường -> Khoá sửa đổi.

**Luồng hệ thống thiết kế (System Flow):**
[Client App] --(Gửi ảnh/Base64)--> [API Gateway] --(Gọi 3rd Party OCR: VNPT/FPT)--> [Trả về JSON Name/DOB/ID] --(Client App auto-fill).

---

## 🤖 3. Thực hành AI & Prompt (10 Phút)

Khi làm BA, bạn phải viết User Story cho cái "Luồng OCR" bên trên. Thay vì hì hục ngồi tự nghĩ, hãy yêu cầu AI.

**🎯 Bài tập hôm nay:**
Copy đoạn Prompt dưới đây và gửi cho tôi để tôi soạn ngay User Story chuẩn Agile cho bạn:

> *"Bạn là BA Manager cấp cao của một công ty Life Insurance. Hãy viết giúp tôi một User Story cho tính năng 'Tự động trích xuất thông tin CCCD gắn chip bằng OCR' trên hệ thống e-App. 
> Yêu cầu:
> 1. Viết theo chuẩn 'As a... I want to... So that...'
> 2. Viết Acceptance Criteria (Tiêu chí nghiệm thu) sử dụng cấu trúc Gherkin (Given, When, Then). Hãy chia làm 2 kịch bản (Scenario): (a) Ảnh CCCD rõ nét trả về đúng JSON, (b) Báo lỗi nếu ảnh CCCD bị chói sáng hoặc sai định dạng"*

**💡 Nâng cao**: Sau khi tôi trả lời, hãy bảo tôi: *"Bổ sung thêm Scenario (c): Khách hàng tải ảnh bằng lái xe máy thay vì CCCD, hệ thống sẽ từ chối như thế nào?"*
