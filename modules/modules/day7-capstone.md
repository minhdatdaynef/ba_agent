# Day 7: Thử thách Capstone - Xây dựng Giải pháp "Số hóa e-App + AI Underwriting" Toàn diện

## ⏱️ Bạn Có 30 Phút Hôm Nay!
- **5 Phút**: Lên ý tưởng Hệ thống Giải pháp (Solution Design).
- **5 Phút**: Tạo Roleplay Prompt cho Capstone.
- **20 Phút**: Tranh luận, phản biện giải pháp với AI (như một buổi bảo vệ nghiệp vụ thực tế).

---

## 📖 1. Tại Sao Lại Cần Capstone?
Trong một dự án thực tế, bạn sẽ không làm từng phần nhỏ giọt (tương tự Day 1 đến Day 6). Sếp sẽ đưa cho bạn một yêu cầu "To Cổ": 
> *"Công ty đang mất 3 ngày rưỡi để Thẩm định một Hồ sơ Tai nạn (Personal Accident Rider). Tỷ lệ khách hàng rớt ngang hợp đồng quá cao. Hãy trình bày thiết kế hệ thống e-App tích hợp Rule Engine (STP) để duyệt hồ sơ này chỉ trong 3 phút!"*

Nhiệm vụ của người BA là kết hợp:
1. Xác định luồng (BPMN) từ Kênh Bancassurance đến Core System.
2. Xây dựng Bảng luật (Decisions Matrix / Rule Engine).
3. Thiết kế trường Dữ liệu (ERD) trên e-App.
4. Ưu tiên hoá (Backlog Prioritization) và Thuyết phục Stackholders (Chuyên gia nghiệp vụ, Tech Lead, Giám đốc khối).

---

## 🚀 2. Đấu Trường Phản Biện (Roleplay) cùng AI
Khả năng đáng sợ nhất của LLM là đóng vai các "Nhân vật Khó Tính" (Stakeholders) trong dự án. 
Đây là cách các BA Senior luyện tập trước khi đối đáp với Client/Tech Lead. Bạn sẽ phải trình bày giải pháp và bảo vệ nó. 

---

## 🤖 3. Bắt Đầu Buổi Bảo Vệ Dự Án Cuối Khóa (20 Phút)

**🎯 Bài tập hôm nay:**
Chuẩn bị tâm lý vững vàng, copy đoạn Prompt này và gửi cho chuyên gia AI:

> *"Tôi là Lead Business Analyst phụ trách dự án số hóa Quy trình nộp Hồ sơ e-App và Thẩm định sơ bộ (Straight Through Processing - STP) cho Sản phẩm Bảo hiểm Liên kết chung (Universal Life). 
> 
> Giải pháp dự kiến của tôi:
> - Sử dụng OCR tích hợp trên Mobile App nội bộ để Agent tự scan CCCD -> Gọi API Cục Cảnh sát QLHC để đối chiếu.
> - Xây dựng một Rule Engine tích hợp vào e-App: Chỉ hỏi 3 câu hỏi Sức khỏe (Bệnh nặng, Kê toa thuốc, BMI). Nếu 'Không' -> Cấp HĐ ngay trong hệ thống Core Insuarance, gửi e-Policy qua Zalo. Nếu có 'Có' -> Đẩy sang Human Underwriting.
> 
> Bạn hãy đóng 2 vai đan xen nhau phản biện Giải pháp của tôi:
> 1. Giám đốc Thẩm định (Chief Underwriter): Hỏi xoáy về Rủi ro trục lợi bảo hiểm nếu luật quá lỏng lẻo. Lời khai sức khỏe khách hàng có thể bị Agent mớm cung.
> 2. Giám đốc Công nghệ (CTO/Tech Lead): Hỏi về khả năng API tắc nghẽn, thời gian chờ Cục Cảnh sát phản hồi quá lâu thì Mobile App bị timeout.
> 
> Hãy đặt cho tôi 2 câu hỏi hóc búa nhất dựa trên giải pháp trên. Tôi sẽ suy nghĩ và rep lại."*

**💡 Chúc Mừng Bạn**: Nếu bạn trả lời trôi chảy và thuyết phục được 2 "Giám đốc" AI này. Chào mừng bạn bước vào hàng ngũ Senior Business Analytst Kỷ Nguyên Mới.
