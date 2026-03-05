# Module 2: Prompt Engineering for BAs

Prompt Engineering (Kỹ thuật đặt câu lệnh) là kỹ năng quan trọng nhất của BA khi làm việc với AI.

## 1. Công thức Prompt chuẩn cho BA (Framework: CREATE)
- **C**haracter: Gán vai (VD: Bạn là một Senior Business Analyst).
- **R**equested Action: Hành động cụ thể (VD: Hãy viết User Story).
- **E**xamples: Đưa ra ví dụ (nếu có).
- **A**udience: Đối tượng đọc (VD: Dành cho đội ngũ Developer).
- **T**erminology: Thuật ngữ chuyên môn muốn sử dụng.
- **E**xtra Constraints: Các ràng buộc (VD: Định dạng Markdown, không quá 500 chữ).

## 2. Ví dụ Prompt thực tế cho BA

### Viết User Story:
> "Bạn là một Senior BA. Hãy viết 5 User Stories cho tính năng 'Thanh toán bằng ví điện tử' cho ứng dụng TMĐT. Mỗi Story phải bao gồm: ID, Title, Description (As a, I want, So that), và Acceptance Criteria."

### Review PRD:
> "Tôi sẽ gửi cho bạn một bản PRD. Hãy đóng vai một Technical Lead, hãy review bản PRD này về tính khả thi và chỉ ra các điểm thiếu hụt (missing cases) hoặc mâu thuẫn trong logic."

## 3. Top Prompt Tips cho BA
- **Chain-of-Thought**: Yêu cầu AI "Think step-by-step" để có logic chặt chẽ hơn.
- **Few-Shot Prompting**: Cung cấp 1-2 ví dụ về cách bạn muốn output trông như thế nào.
- **Iterative Refinement**: Đừng dừng lại ở prompt đầu tiên. Hãy yêu cầu AI "Làm bản thảo này chi tiết hơn về phần bảo mật".

---
### 📝 Bài tập nhỏ:
Hãy thử yêu cầu tôi: *"Hãy viết một Prompt hoàn chỉnh để giúp tôi tóm tắt biên bản họp (meeting minutes) thành các Action Items."*
