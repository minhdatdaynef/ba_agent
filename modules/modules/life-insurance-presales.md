# Module 1: Life Insurance Presales Fundamentals
*(Nền tảng nghiệp vụ Đầu bán Bảo hiểm nhân thọ)*

Business Analyst (BA) trong lĩnh vực Life Insurance có cơ hội thiết kế các hệ thống phức tạp, giúp Tư vấn viên và Khách hàng hoàn tất bộ hồ sơ (HĐBH) một cách minh bạch, an toàn và nhanh chóng. Giai đoạn này gọi là **Presales** hoặc **New Business (Khai thác mới) - Front Office**.

## 1. Hành trình Khách hàng Cơ bản (Customer Journey)
Quy trình Đầu bán tiêu chuẩn bao gồm:
1. **Tìm kiếm khách hàng (Lead Generation)**: Marketing, phân bổ Lead.
2. **Khơi gợi nhu cầu (Fact-Find/FNA)**: Financial Needs Analysis - Đánh giá nhu cầu tài chính của Khách hàng để thiết kế gói Bảo hiểm phù hợp.
3. **Bảng minh họa (Illustration/Quotation)**: Chạy thử chi phí và dòng tiền dựa trên độ tuổi, thu nhập, rủi ro.
4. **Kê khai Hồ sơ điện tử (e-App/Application)**: Khách hàng đồng ý, điền form, khai báo Y tế.
5. **Thẩm định (Underwriting)**:
   - *Pre-Underwriting/STP*: Hệ thống tự động duyệt (Rule Engine).
   - *Human Underwriting/Manual*: Chuyên viên Y tế xem xét (Nếu BMI bất thường, có bệnh lý nền...).
6. **Thanh toán (Payment)**: Thu phí Ban đầu.
7. **Phát hành Hợp đồng (Policy Issuance/e-Policy)**: Đẩy data sang hệ thống lõi (Core System) và phát hành e-Policy gửi cho Khách hàng.

## 2. Giải mã các Khái niệm Cốt lõi cho Hệ thống

### 2.1. Illustration (Quotation / Bảng minh họa quyền lợi)
Đây là "bài toán" hóc búa nhất của một BA hệ thống Đầu bán.
- **Sản phẩm chính (Base Plan)**: Ví dụ *Tử kỳ (Term)*, *Trọn đời (Whole Life)*, *Liên kết đầu tư (ILP/UL)*.
- **Sản phẩm bổ trợ (Riders)**: Gắn lồng vào Base Plan, ví dụ *Chăm sóc y tế (Health)*, *Tai nạn (Accident)*, *Bệnh hiểm nghèo (Critical Illness)*.
- **Tính toán Phí (Premium Calculation)**: Dựa vào Tỷ lệ Tử vong (Mortality Rate), Nghề nghiệp (Occupational Class), Giới tính, Tuổi.
**=> Bài toán AI**: *Sử dụng AI/Recommendation Engine gợi ý mức phí Phù hợp năng lực tài chính (Affordability) dựa trên thu nhập thực.*

### 2.2. e-App (Electronic Application / Hồ sơ điện tử)
Là Form số hóa thu thập lời khai Trung thực Tuyệt đối của Khách hàng.
- **AML / FATCA / CRS**: Các chuẩn phòng chống rửa tiền hoặc tuân thủ thuế (đặc biệt khách hàng nước ngoài).
- **Medical Declaration (Lời khai Y tế)**: Danh sách câu hỏi Cây (Tree-logic questions). Ví dụ: "Bạn có hút thuốc không?" -> CÓ -> Hiển thị "Bao nhiêu điếu/ngày?".
**=> Bài toán AI**: *Sử dụng OCR nhận diện CCCD auto-fill thông tin rút ngắn thời gian (Frictionless Onboarding).*

### 2.3. Underwriting (Thẩm định)
Đánh giá mức độ Rủi ro (Risk Assessment) xem Công ty Bảo hiểm có nên bán cho người này không, với mức bảo vệ là bao nhiêu.
- **STP (Straight-Through Processing)**: Chấm dứt triệt để bằng Rule Engine (Nếu tuổi < 30 + không bệnh = Cấp tự động).
- **Postpone / Decline**: Tạm hoãn (ví dụ đang mang thai) hoặc Từ chối (Bệnh ung thư giai đoạn cuối).
- **Loading / Exclusions**: Tăng phí (Loading) hoặc Loại trừ bảo hiểm (Không đền nếu chết vì môn thể thao mạo hiểm đã khai báo).
**=> Bài toán AI**: *Sử dụng NLP để đọc Hồ sơ bệnh án đính kèm và kết luận sơ bộ, tiết kiệm tối đa thời gian cho Underwriter.*

### 3. Kênh phân phối chính (Distribution Channels)

- **Đại lý truyền thống (Agency)**: Hệ thống Sales quản lý cấp bậc nhiều tầng (Hierarchy). BA chú ý bài toán **Hoa hồng đội nhóm (Overriding Commission)**.
- **Bancassurance (Banca - Ngân hàng)**: Bán chéo qua Mạng lưới Ngân hàng. BA phải tích hợp (API) API từ Nhân viên Ngân hàng (FSA) sang Hệ thống Core Bảo hiểm. Yêu cầu tính Liên thông Data (Data integration) cao.
- **Direct Sales / Kênh số**: Khách hàng tự lên App/Web mua trực tiếp (D2C). Yêu cầu UX/UI đỉnh cao và quy tắc Thẩm định (STP) cực đơn giản.

---
### 📝 Bài tập thực hành:
Thử yêu cầu Agent chuyên gia: *"Hãy dùng sơ đồ BPMN (Text Format) chỉ để vẽ quy trình xử lý Khách hàng nộp Hồ sơ e-App, bao gồm cả rẽ nhánh Thẩm định tự động STP đậu và rớt."*
