# Day 6: Phân tích Dự đoán & Tỷ lệ chuyển đổi (Predictive Analytics)

## ⏱️ Bạn Có 30 Phút Hôm Nay!
- **10 Phút**: AI/Machine Learning trong Bảo hiểm Đầu bán.
- **10 Phút**: Chấm điểm Lead (Lead Scoring) là gì?
- **10 Phút**: Yêu cầu AI chuẩn bị Dữ liệu (Input/Output) cho Mô hình ML.

---

## 📖 1. AI/Machine Learning sinh ra để làm gì?
Khi bạn (BA) xây xong một hệ thống e-App & Kênh phân phối trơn tru, câu hỏi sếp đặt ra là: *"Tháng này MKT đổ về 10,000 Leads (Khách hàng tiềm năng). Làm sao biết nên ưu tiên gọi cho ai để chốt đơn nhanh nhất?"*

Đó là lúc **Phân tích Dự đoán (Predictive Analytics)** vào cuộc. Chúng ta xây dựng các Mô hình Học Máy (Machine Learning Models) để phân tích Dữ liệu Lịch sử và Dự đoán Tương lai.

---

## 🚀 2. Các Bài Toán Dự Đoán Phổ Biến (Presales)
1. **Lead Conversion Scoring (Chấm điểm Khách hàng)**: 
   - Điểm càng cao (VD: 90/100), khả năng mua càng lớn.
   - *Yếu tố quyết định*: Đã có gia đình, thu nhập > 30tr, độ tuổi 30-40, mới sinh con.
2. **Next-Best-Offer / Cross-Sell (Bán chéo)**:
   - Khách hàng vừa giải ngân khoản vay Mua Nhà 3 Tỷ tại Ngân hàng (Bancassurance).
   - *Hệ thống tự động gợi ý*: Chào bán ngay gói Bảo hiểm Tử kỳ (Term Life) bảo vệ khoản vay đó.
3. **Flight Risk / Churn Prediction (Dự đoán Hủy hợp đồng)**:
   - Khách trong 14 ngày dùng thử (Free-look period) có nguy cơ Hủy Hợp đồng trả lại tiền không?

---

## 🤖 3. Thực hành AI: Thiết kế Input/Output cho mô hình (10 Phút)

**🎯 Bài tập hôm nay:**
 Là một BA, bạn không code ra Mô hình ML, nhưng bạn phải là người định nghĩa Đầu vào (Tính năng/Features) và Đầu ra (Label). Hãy gửi Prompt này cho tôi:

> *"Tôi là Data BA cho hệ thống Bancassurance. Ngân hàng đối tác muốn nhờ chúng ta xây một Machine Learning Model để chấm điểm 'Khả năng mua Bảo hiểm Liên kết Đầu tư (ILP)' của tệp khách hàng Ngân hàng.
> 
> Hãy giúp tôi liệt kê 10 Data Features (Trường thông tin Đầu vào) quan trọng nhất cần trích xuất từ Hệ thống Ngân hàng (Core Banking) để đưa vào mô hình này (Ví dụ: Số dư bình quân, Lịch sử giao dịch, v.v.). Giải thích ý nghĩa của từng biến.
> Đầu ra (Output/Target Variable) của mô hình này nên thiết kế như thế nào?"*

**💡 Nâng cao**: "Nếu mô hình dự đoán sai (Tức là điểm mua cao nhưng khách không mua), Data BA nên yêu cầu bắt lại (Log) những lý do từ chối (Reject Reasons) nào từ Giao dịch viên để train lại mô hình?"
