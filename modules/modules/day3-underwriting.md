# Day 3: Cấu trúc Thẩm định sơ bộ (Pre-Underwriting) & Rule Engine

## ⏱️ Bạn Có 30 Phút Hôm Nay!
- **10 Phút**: Hiểu thế nào là Underwriting.
- **10 Phút**: Học về BPMN Text Format từ Rule.
- **10 Phút**: Yêu cầu AI chuyển Business Rule thành Sơ đồ.

---

## 📖 1. Thẩm định (Underwriting) là gì?
Khi nộp e-App, Công ty Bảo hiểm (Insurer) phải xem xét Khách hàng này mang lại "tiền" hay mang "rủi ro quá lớn". Quá trình duyệt đó gọi là **Underwriting**.

### Hai dạng Underwriting chính:
1. **Manual / Human Underwriting**: Hồ sơ rớt vào trạng thái Chờ (Pending) -> Underwriter (Bác sĩ/Chuyên viên Thẩm định) tải hồ sơ bệnh án (PDF/JPG) về -> Đọc -> Ra quyết định: (Chấp nhận cấp / Tạm hoãn Postpone / Tăng phí béo phì Loading / Từ chối Decline).
2. **Auto / Pre-Underwriting (STP - Straight Through Processing)**: Hồ sơ chạy qua một bộ luật máy tính (Rule Engine) và "Sạch" -> Tự động Cấp hợp đồng (Approved) trong 10 giây. Tỷ lệ STP càng cao, hệ thống càng thông minh.

---

## 🚀 2. Tư duy thiết kế Rule Engine & AI (10 Phút)

### Rule Engine (Mệnh đề If-Else kinh điển)
Hệ thống sẽ dựa vào Input từ e-App (đặc biệt là bảng *Lời khai Y tế Medical*) để chạy Luật.
*Ví dụ*:
`IF (BMI > 30) AND (Age > 45) THEN -> Trạng thái = Trả về Bác sĩ xem ngay`
`IF (Câu hỏi: "Bạn có mắc bệnh nan y không?" = YES) THEN -> Trạng thái = Decline`

### AI Tương lai trong Thẩm định
Dùng Natural Language Processing (NLP) / Generative AI để "đọc" đống hồ sơ xét nghiệm (Lab Test) tải lên, tự động rà soát chỉ số Men Gan/Mỡ máu, đối chiếu với Cẩm nang Y khoa của Công ty và đề xuất luôn: *"Khách này nên tăng 15% phí bảo vệ sinh mạng."*

---

## 🤖 3. Thực hành Sinh Sơ đồ (BPMN) từ AI (10 Phút)
Một BA thường phải vẽ BPMN (Sơ đồ quy trình nghiệp vụ). AI có thể Gen ra Sơ đồ (PlantUML hoặc Mermaid) chỉ bằng cách bạn cung cấp Mệnh đề Logic (Rule).

**🎯 Bài tập hôm nay:**
Copy đoạn Prompt dưới đây và gửi thẳng cho tôi:

> *"Tôi đang làm hệ thống Thẩm định tự động (Auto-Underwriting) cho sản phẩm Liên kết Đầu tư.
> Bộ Luật (Rule) của phòng Thẩm định đưa xuống như sau:
> 1. Nếu Khách hàng chọn nghề thợ mỏ (Class 4) -> Từ chối ngay.
> 2. Nếu Khách hàng < 50 tuổi VÀ không hút thuốc VÀ trả lời toàn bộ bảng câu hỏi sức khỏe là 'KHÔNG' -> Duyệt tự động (STP).
> 3. Nếu Khách hàng hút thuốc HOẶC BMI > 28 -> Đẩy sang thẩm định tay (Human Underwriting).
> 
> Hãy dùng ngôn ngữ Markdown/PlantUML text format vẽ một biểu đồ quy trình (Flowchart) mô tả luồng luật này."*

**💡 Nâng cao**: Sau khi lấy Sơ đồ, yêu cầu tiếp: *"Tìm giúp tớ trường hợp bị lọt (Missing Case). Chuyện gì xảy ra nếu Khách 55 tuổi, không hút thuốc, và không có BMI > 28?"*
