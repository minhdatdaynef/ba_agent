# 📄 Tài liệu Đặc tả Yêu cầu: Tối ưu hóa Hệ thống Auto-Underwriting (Day 3 Outcome)

**Người thực hiện:** Business Analyst & AI Mentor
**Mục tiêu:** Tăng tỷ lệ STP (Straight Through Processing) bằng cách tinh chỉnh các điểm nghẽn (Bottlenecks) và quản trị rủi ro linh hoạt.

---

## 1. Chiến lược Phân loại Nghề nghiệp (Occupation Strategy)
*   **Vấn đề:** Danh mục "Other" và "Worker Class 4" gây nghẽn hệ thống.
*   **Giải pháp:** 
    *   **Linh động hóa:** Không mặc định Class 4 là Decline. Thực hiện đối chiếu thêm với **Môi trường làm việc**.
    *   **Ưu tiên:** Nhóm khách hàng văn phòng (Office-based) là nhóm tiềm năng nhất vì ít yếu tố tác động sức khỏe ngoại cảnh.
    *   **Bộ câu hỏi định danh (Max 5 câu):** Cần làm rõ: Môi trường (Văn phòng/Công trường), Thao tác rủi ro (Hóa chất/Điện), Độ cao/Chiều sâu, Vai trò (Quản lý/Vận hành), Tần suất di chuyển.

## 2. Chiến lược Quản lý Bệnh lý (Medical Grey-zone)
*   **Phân loại:** Chia Rule bệnh lý thành 2 nhóm: **Bắt buộc (Hard)** và **Vùng xám (Grey)**.
*   **Cơ chế Auto-Pass:** 
    *   Đối với bệnh thứ yếu (vặt): Nếu có chứng từ đính kèm xác nhận tình trạng hiện tại ổn định -> Chuyển từ Manual sang **STP (với phí chuẩn hoặc Loading)**.
    *   **Luật 5 năm (Historical Grace Period):** Thiết kế bộ câu hỏi chuyên biệt cho các trường hợp "Đã khỏi bệnh 5 năm trước" để đánh giá rủi ro tái phát. Nếu kết quả tích cực -> Cho phép STP.

## 3. Tối ưu hóa Rule BMI (BMI vs. Lifestyle)
*   **Tư duy mới:** Không dùng BMI làm chỉ số đơn lẻ.
*   **Tham chiếu chéo:** Kết hợp BMI với Nghề nghiệp. 
    *   *Logic:* Nếu BMI trong khoảng 28-30 nhưng thuộc nhóm **Nghề nghiệp Văn phòng** và không có bệnh lý nền -> Cân nhắc cho phép STP (vì mức độ rủi ro tử vong/tai nạn thấp hơn so với lao động chân tay cùng chỉ số).

## 4. Quản trị nhóm Khách hàng Lớn tuổi (>60)
*   **Thay đổi thước đo:** Loại bỏ việc dùng "Số tiền bảo hiểm" (Sum Assured) làm thước đo duy nhất cho nhóm này (vì rủi ro cao).
*   **Tập trung vào Loyalty & Risk History:** 
    *   Ưu tiên **Khách hàng VIP cũ tái tục**.
    *   *Lý do:* Đã có dữ liệu phí đóng đều đặn + Hồ sơ sức khỏe đã được confirm trong quá khứ. Đây là tập khách hàng "Chắc chắn" nhất để nâng ngưỡng STP cho lứa tuổi >60.

---
> [!NOTE]
> **Kết luận từ BA:** Chúng ta đang thực hiện "Đánh đổi có kiểm soát" (Calculated Risk) để lấy sự hài lòng của khách hàng và tốc độ xử lý của hệ thống.
