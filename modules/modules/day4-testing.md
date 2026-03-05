# Day 4: Kiểm thử (QA & Testing) Bảng minh họa Phí Bảo hiểm

## ⏱️ Bạn Có 30 Phút Hôm Nay!
- **10 Phút**: Tại sao Tester và BA lại đau đầu với Phí Bảo hiểm?
- **10 Phút**: Kỹ thuật phân tích Corner Cases (Trường hợp Góc).
- **10 Phút**: Dùng LLM (AI) để tạo tự động Data Test.

---

## 📖 1. Bài toán Đau đầu: Risk Premium (Phí Rủi ro)
Biểu phí của một sản phẩm Bảo hiểm có thể là một ma trận khổng lồ.
*Ví dụ*: `Phí = Tỷ suất cơ bản * Hệ số(Giới tính) * Hệ số(Nghề nghiệp) * Hệ số(Tuổi) * Số tiền bảo hiểm(Sum Assured)`.
Hệ thống tính sai 1 đồng phí cũng dẫn kiện tụng hoặc lỗ tỷ giá.

> **BA & QA làm gì?**: Tạo ra hàng trăm Test Cases bao phủ mọi lứa tuổi và tổ hợp rủi ro để đưa vào công cụ chạy Test Tự động (Automation Test).

---

## 🚀 2. Tư duy Edge Cases (10 Phút)
Khi phân tích BA, luôn tìm điểm Mù (Edge/Corner Cases):
- Tuổi phát hành nhỏ nhất: 30 ngày (Vậy 29 ngày tuổi tính phí sao?)
- Tối đa: 65 tuổi (Vậy 65 tuổi 1 ngày thì Pass hay Fail?)
- Nghề nghiệp Loại 4 (Nguy hiểm) gắn với Sản phẩm Tử kỳ: Allowed?
- Khách hàng mua Sản phẩm bổ trợ (Rider) số tiền bảo vệ LỚN HƠN Sản phẩm chính (Base Plan).

---

## 🤖 3. Thực hành Sinh Test Data tự động (10 Phút)
Tạo test data bằng tay rất chậm (Mở Excel, canh từng ô). Hãy để AI làm điều đó, Output bằng Array JSON để dùng thẳng trên Postman.

**🎯 Bài tập hôm nay:**
Đóng vai BA đi kiểm thử API Tính phí Bảo hiểm (Calculate Premium API). Copy đoạn Prompt gửi cho mình:

> *"Tôi đang cần kiểm thử tính logic của API 'Tính Tỷ lệ phí Bảo hiểm'.
> Quy tắc kinh doanh (Business Rules):
> - Độ tuổi (Age): Từ 1 đến 60.
> - Nếu Age > 55, phí tăng thêm 20%.
> - Giới tính (Gender): Nam (M) phí đắt hơn Nữ (F) 5%.
> - Nghề nghiệp (Occupation): Class 1 (Văn phòng), Class 2 (Công nhân), Class 3 (Nguy hiểm - Từ chối sản phẩm này).
> 
> Hãy dùng tư duy BVA (Boundary Value Analysis - Phân tích giá trị biên) để gen cho tôi một danh sách 5 Scenarios (Test Cases). 
> Output trả về bằng định dạng JSON (Array) bao gồm: 'TestID', 'Age', 'Gender', 'Occ_Class', 'Expected_Status' (Accept hoặc Reject), và 'Expected_Surcharge' (Tức là bị tăng phí bao nhiêu %)."*

**💡 Nâng cao**: "Hãy giải thích tại sao bạn lại chọn độ tuổi 60 và 61 trong Test Data này?"
