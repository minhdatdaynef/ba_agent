# Module 2: AI & BA Fundamentals in Life Insurance

## 1. Vai trò của BA Kỷ nguyên AI trong Bảo hiểm
Hệ thống lõi bảo hiểm (Core Insurance System) rất phức tạp với hàng ngàn Medical Rules, Actuarial Formulas, và Distribution Compansations. AI là cầu nối giúp BA giải quyết khối lượng nghiệp vụ đó một cách thông minh, thay vì chỉ "copy-paste" vào tài liệu Phân tích.

### Thay đổi Mindset:
| Truyền thống | BA + AI (Bảo hiểm Đầu bán) |
| :--- | :--- |
| **Phân tích yêu cầu Rule Thẩm định bằng Excel** | Dùng AI/LLM để trích xuất Business Rules từ tài liệu Y khoa (Medical Guidelines) và viết thành Decision Matrix. |
| **Vẽ BPMN e-App thủ công** | Yêu cầu GenAI tạo luồng BPMN cơ bản cho quy trình nộp hồ sơ e-App, sau đó Review và Update các Use Case (AML, FATCA). |
| **Báo cáo Data/Dashboard** | Thiết kế luồng cho **Predictive Analytics (Dự đoán rủi ro/Lead Conversion)** để đề xuất Sản phẩm Bổ sung (Cross-sell Rider). |
| **Test Case cho Bảng minh họa** | Truyền công thức tính Phí (Premium) vào AI để Gen ra hàng trăm Test Scenarios cực nhanh theo độ tuổi/nghề nghiệp. |

## 2. Các ứng dụng AI trọng tâm trong Đầu bán Bảo hiểm (Presales)

### 2.1. Predictive Analytics (Phân tích dự đoán)
- **Lead Scoring (Chấm điểm tiềm năng)**: Khách hàng nào có xác suất mua bảo hiểm cao nhất trên kênh Bancassurance.
- **Next-Best Action (Hành động kế tiếp)**: Tư vấn viên (Agent) nên gọi điện hay nhắn tin? Nên giới thiệu Sản phẩm Tử kỳ hay Liên kết đầu tư?
- **Risk Prediction (Dự đoán Rủi ro Y tế)**: Khả năng rủi ro y khoa của khách hàng dựa trên lịch sử nhân khẩu học cơ bản.

### 2.2. Automated Underwriting (Thẩm định tự động & Sinh học AI)
- **Rule Engine kết hợp NLP**: Dùng Natural Language Processing (NLP) để quét hồ sơ y tế đính kèm của khách hàng trên e-App, nếu phát hiện bệnh lý nghiêm trọng -> đẩy sang Thẩm định Tự động (Automated Underwriting).
- **Computer Vision (Nhận diện hình ảnh/OCR)**: Rút trích thông tin từ CCCD, Bằng lái, Giấy khai sinh tự động điền vào e-App, cải thiện mức độ hài lòng khách hàng (CX).

### 2.3. Generative AI (Hỗ trợ Gen tài liệu/Giao tiếp)
- **Khơi gợi yêu cầu**: Tạo kịch bản phỏng vấn Stakeholder (Bancassurance Sales Head, Underwriting Manager).
- **Viết AI-Powered User Story**: Gen ra các Gherkin Criteria phức tạp cho e-App.
- **Chatbot / Virtual Assistant**: Tạo kịch bản và dữ liệu huấn luyện cho Bot hỗ trợ Tư vấn viên tra cứu quyền lợi bảo hiểm lập tức.

## 3. Quy trình AI-Enhanced SDLC cho Bảo hiểm
1. **Khơi gợi (Elicitation)**: Tạo ma trận câu hỏi cho bộ phận Actuary bằng AI trước khi bước vào cuộc họp.
2. **Đặc tả (Specification)**: Đưa các Rule phức tạp của Đầu bán vào Prompt và nhận về bản nháp BDD (Behavior-Driven Development).
3. **Kiểm thử (UAT / QA)**: Yêu cầu AI quét sơ đồ luồng (BPMN) để tìm ra các Corner Case (Edge case) rớt thanh toán, hoặc lỗi logic tuổi tham gia minh họa (Illustration Issue).

---
### 📝 Bài tập thực hành:
Thử yêu cầu Agent chuyên gia: *"Hãy đóng vai Giám đốc Thẩm định (Chief Underwriter), cho mình biết để cấu hình Rule Engine thẩm định tự động một Hồ sơ sinh mạng thông thường (Term Life), mình cần thu thập những thuộc tính đầu vào (Input) nào từ người dùng trên e-App?"*
