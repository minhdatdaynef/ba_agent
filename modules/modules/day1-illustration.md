# Day 1: Giải mã Bảng minh họa (Illustration) & Phí Bảo Hiểm

## ⏱️ Bạn Có 30 Phút Hôm Nay!
- **10 Phút**: Đọc hiểu thuật ngữ Actuary cơ bản.
- **10 Phút**: Phân tích quan hệ (ERD) giữa Base Plan & Rider.
- **10 Phút**: Thực hành Prompt AI.

---

## 📖 1. Khái niệm Cốt lõi (10 Phút)

### Bảng minh họa (Illustration/Quotation) là gì?
Khi Tư vấn viên (Agent) gặp khách hàng, họ cần tạo một bản **dự kiến dòng tiền**, bao gồm Phí đóng (Premium) và Quyền lợi nhận về (Benefit/Maturity) dựa trên:
1. **Tuổi phát hành (Entry Age)**: Càng cao phí càng đắt (Tỷ lệ tử vong - Mortality Rate lớn).
2. **Giới tính (Gender)**: Nữ thường có tuổi thọ cao hơn Nam -> Phí rẻ hơn (với Tử kỳ).
3. **Nghề nghiệp (Occupation Class)**: NV Văn phòng (Class 1) rẻ hơn Công nhân xưởng (Class 3).

### Cấu trúc 1 Gói Bảo hiểm (Policy Structure)
- **Base Plan (Sản phẩm chính)**: Bắt buộc phải có. Ví dụ: *Bảo hiểm Sinh mạng (Term)*, *Liên kết chung (UL)*. Quyết định Sinh/Tử.
- **Riders (Sản phẩm bổ trợ)**: Mua thêm để bảo vệ toàn diện. Vd: *Tai nạn (PA)*, *Nằm viện (Health)*, *Ung thư (CI)*. Mất đi nếu Base Plan bị Hủy.

---

## 🧠 2. Phương pháp luận BA (10 Phút)

**Thiết kế Dữ liệu (ERD - Logic)**
Khi làm Hệ thống Illustration, bạn phải quy định Mối quan hệ:
- 1 Khách hàng (Client) có thể tạo Nhiều `Illustration`.
- 1 `Illustration` phải có Đúng 1 `Base Plan` (1:1).
- 1 `Illustration` có thể đính kèm Nhiều `Rider` (1:N).
- Tổng Phí (Total Premium) = `Phí Base Plan` + `Tổng Phí Rider 1...N`.

---

## 🤖 3. Thực hành AI & Prompt (10 Phút)

Bạn không cần tự vẽ Data Model (ERD) từ đầu. Hãy để LLM làm việc nặng nhọc.

**🎯 Bài tập hôm nay:**
Copy đoạn Prompt dưới đây và gửi cho tư vấn viên AI (chính là tôi - Antigravity) để xem tôi vẽ hệ thống Data Model cho bạn như thế nào:

> *"Đóng vai Data Architect ngành Bảo hiểm Nhân thọ. Hãy vẽ cho mình Data Model (ERD) bằng định dạng chữ (Mermaid Format) cho một tính năng Tạo Bảng minh họa (Illustration). Các bảng (Tables) cần có: Client, Illustration_Quote, Base_Product, Rider_Product. Hãy giải thích mối nối Primary Key/Foreign Key."*

**💡 Nâng cao**: Sau khi lấy ERD, hãy yêu cầu: *"Bổ sung trường Occupation_Class vào bảng Client. Dùng Rule Engine nào (trong Code) để tính Premium nếu Class = 3?"*
