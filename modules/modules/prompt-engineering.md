# Module 3: Prompt Engineering cho BA (Bảo hiểm - Đầu bán)

Prompt Engineering (Kỹ thuật đặt câu lệnh) là chiếc "chìa khóa vàng" giúp BA tận dụng tối đa LLM để gỡ rối các rủi ro phức tạp trong sản phẩm Bảo hiểm, và thiết kế Luồng Front-Office thông minh hơn.

## 1. Công thức Prompt chuẩn cho BA (Framework: CREATE)
- **C**haracter: Gán vai (VD: Bạn là một Senior BA ngành Bảo hiểm nhân thọ / Chuyên gia Thẩm định).
- **R**equested Action: Hành động mong muốn (VD: Hãy phân tích BPMN, tính tỷ lệ).
- **E**xamples: Đưa ra ví dụ mẫu (VD: Đây là cách tính phí bảo hiểm Tử kỳ...).
- **A**udience: Đối tượng đọc (VD: Dành cho đội Dev hoặc Actuary).
- **T**erminology: Yêu cầu AI dùng đúng thuật ngữ (e-App, Illustration, Premium, Rider, Surrender Value).
- **E**xtra Constraints: Ràng buộc độ dài, định dạng (VD: Trả về bảng Markdown).

## 2. Thư viện Prompt mẫu cho Nghiệp vụ Bảo hiểm

### 2.1. Gen User Story cho e-App
> "Bạn là một Senior Business Analyst chuyên làm hệ thống Đầu bán (Presales - Life Insurance). Hãy viết 5 User Stories cho tính năng 'Kê khai bệnh lý (Medical Declaration)' trên Hồ sơ e-App. Hãy đảm bảo User Story phải nhắc đến quá trình Rule Engine kiểm tra BMI (Chỉ số Cơ thể) và hút thuốc (Smoking Status).
> Mỗi Story phải bao gồm: ID, Title, Description (As a, I want, So that), và Acceptance Criteria (Gherkin format: Given, When, Then)."

### 2.2. Review Bảng minh họa (Illustration) Logic
> "Tôi sẽ cung cấp Data Dictionary và Use Case cho một sản phẩm Bổ trợ Chăm sóc Sức khỏe (Health Rider). Đóng vai trò là Technical/Domain Lead, hãy chỉ ra các Corner Cases (Trường hợp Góc) mà tôi còn thiếu. Đặc biệt tập trung vào các quy tắc liên kết: Nếu Hợp đồng chính (Base Plan) bị từ chối/hủy, thì Rider sẽ bị ảnh hưởng thế nào?"

### 2.3. Tạo Mock Data cho Test Kịch bản Thẩm định
> "Dùng ngôn ngữ JSON, tạo cho tôi 5 hồ sơ Mock Data của khách hàng độ tuổi từ 30 đến 45. Hãy cung cấp trường 'BMI' (Cân nặng, Chiều cao), trường 'Bệnh lý trước' (Pre-existing Condition: Tiểu đường, Huyết áp) sao cho 2 hồ sơ bị Đẩy qua Human Underwriting, và 3 hồ sơ được duyệt STP (Straight-Through Processing)."

## 3. Các Tip Prompt Cấp cao cho Kỹ sư Phân tích (BA Engineer)
- **Chain-of-Thought (Tư duy theo chuỗi)**: Đối với các quy tắc Bảo hiểm lồng nhau (VD: Logic Hoa hồng Agency, Hoa hồng Bancassurance), hãy yêu cầu AI "Suy nghĩ từng bước một" trước khi in ra kết luận.
- **Iterative Refinement (Tinh chỉnh Dần)**: Đừng trông đợi 1 prompt hoàn hảo. Nếu AI làm sai logic Phí bảo hiểm, hãy nói: *"Nhận định này sai so với Công thức Phí chuẩn, vì Lãi suất kỹ thuật chưa được cộng dồn. Hãy làm lại."*

---
### 📝 Bài tập thực hành:
Thử yêu cầu Agent: *"Để một đại lý (Agency) nộp e-App thành công, công thức tính điểm Hoa hồng Khai thác năm đầu (FYPR) là gì? Hãy viết cho mình 1 Prompt để AI tự động gen Test Case cho tính năng tính Hoa hồng này."*
