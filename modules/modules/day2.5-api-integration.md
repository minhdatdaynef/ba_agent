# Day 2.5: Giao Thức API & Kiến Trúc Ưu Tiên Của Hệ Thống (Dành Cho BA)

## ⏱️ Bạn Có 30 Phút Hôm Nay!
- **10 Phút**: Thế nào là API? Phân biệt Client (App) và Server (Core).
- **10 Phút**: 4 Động từ thần thánh (HTTP Methods) BA phải thuộc nằm lòng.
- **10 Phút**: Đọc hiểu JSON và Cấu hình tham số (Parameters) khi ráp luồng.

---

## 📖 1. Tại Sao BA Cần Hiểu API? 

Ngày xưa, BA chỉ cần vẽ màn hình "Người Dùng bấm nút này, thì hiện ra chữ kia".
Nhưng ở các hệ thống tài chính (Insurance/Banking Core), Logic xử lý 90% **KHÔNG** nằm trên điện thoại của khách (Mobile App / Front-end), mà nằm trên cái Máy Chủ Khổng Lồ ở trụ sở (Core System / Back-end). 

Để Điện thoại "nói chuyện" được với Máy Chủ, chúng cần một người phiên dịch: **API (Application Programming Interface - Giao diện Lập trình Ứng dụng)**.

### Ví dụ Thực tế: Tính Phí Bảng Minh Họa (Calculate Premium)
*   **App (Front-end):** Tư vấn viên nhập "Nam, 30 tuổi, Tử kỳ". Bấm `<TÍNH PHÍ>`.
*   **API (Cái ống nước):** App đóng gói 3 thông tin này vào một hộp quà gọi là `Request`, ném thẳng qua ống nước API gửi đến Máy Chủ.
*   **Core (Back-end):** Nhận được hộp quà, mở ra đọc "Nam, 30 tuổi". Lục tìm bảng Tỷ lệ tử vong, nhân chia cộng trừ rầm rộ, tính ra số tiền `20,000,000 VNĐ`. 
*   **API (Lượt về):** Core đóng gói số 20 triệu vào một hộp quà phản hồi gọi là `Response`, ném trả lại theo ống nước về cho App.
*   **App:** Lấy số 20 triệu hiển thị lên màn hình xanh đỏ chớp chớp cho khách xem.

**=> Nhiệm vụ của BA**: Thiết kế hình dáng của "Cái Ống Nước" và "Món Quà" (Tức là Tài liệu **API Specification / Integration Mapping**). Trả lời câu hỏi: *App cần gửi lên những field gì? Core phải trả về lỗi gì nếu tính thất bại?*

---

## 🚀 2. "Bộ Tứ" HTTP Methods BA Nào Cũng Phải Khắc Ghi (10 Phút)

Khi App gửi 1 `Request` qua API, App phải nói rõ mình muốn **LÀM GÌ** với bộ Data dưới Máy chủ. Có 4 dạng thao tác kinh điển (CRUD - Create, Read, Update, Delete):

1.  **GET (Lấy / Đọc)**: Chỉ giơ tay xin dữ liệu, KHÔNG làm thay đổi bất kỳ cái gì trên Server.
    *   *BA Case:* "GET danh sách lịch sử đóng phí của khách hàng A". (Khách hàng gọi đi gọi lại ngàn lần thì data vẫn y nguyên).
2.  **POST (Tạo mới / Gửi Lên)**: Yêu cầu Server tạo ra một cục dữ liệu mới toanh.
    *   *BA Case:* "POST một bộ hồ sơ e-App mới tinh vào hệ thống".
3.  **PUT (Ghi đè / Cập nhật toàn bộ)**: Sửa 1 dữ liệu đã có.
    *   *BA Case:* "PUT cập nhật lại số điện thoại trên e-App".
4.  **DELETE (Xóa)**: Xóa sổ 1 dòng dữ liệu.
    *   *BA Case:* "DELETE Xóa một Sản phẩm bổ trợ (Rider) ra khỏi giỏ hàng".

*(Bí kíp: Trong tài liệu thiết kế, BA sẽ viết: "Luồng này dùng API POST để tạo Quote, sau đó dùng API GET để render màn hình Detail").*

---

## 🛠️ 3. JSON - Định Dạng Ngôn Ngữ Chung (10 Phút)

Món quà truyền đi trong API phải được đóng gói bằng một ngôn ngữ mà cả App (Android, iOS) và Core (Java, C#) đều đọc được. Ngôn ngữ đỉnh cao nhất hiện nay là **JSON (JavaScript Object Notation)**. Nó như một bảng Key - Value (Trường số liệu - Chữ số đi kèm).

Ví dụ Request lên API Tính phí:
```json
{
  "client_id": "CLI-8899",
  "product_code": "TERM_01",
  "client_info": {
     "gender": "M",
     "age": 30,
     "smoke_status": false
  }
}
```

### Cách BA tư duy khi review API JSON:
1.  **Kiểu Dữ liệu (Data Types)**: BA quyết định `age` bắt buộc phải là số tự nhiên (`Integer`), không được phép là chữ (`String`).
2.  **Bắt buộc hay Không (Mandatory/Optional)**: BA quy định `smoke_status` là trường Mandatory. Nếu App quên truyền trường này xuống, API phải quăng thẳng vào mặt báo lỗi: `400 Bad Request - Missing Smoke Status`.

---

## 🤖 4. Thực hành AI: Dịch Nghĩa API (10 Phút)

**🎯 Bài tập hôm nay:**
Copy đoạn Prompt dưới đây và gửi cho AI (tức mình) để luyện cách đọc API phức tạp:

> *"Tôi là BA phụ trách luồng Gọi API chấm điểm eKYC (Chụp CCCD) gửi cho đối tác VNPT.
> Tài liệu Swagger (API Docs) của Dev đối tác ghi thế này:
> Endpoint: `POST /v1/ekyc/id-card/ocr`
> Request Body (JSON): Cần trường `image_front_base64` (Mandatory), `image_back_base64` (Optional).
> Response Body (JSON): Trả về `status_code` (200, 400, 401, 500) và `data` (Họ tên, ngày sinh, Cảnh báo cắt góc).
> 
> Là một chuyên gia BA hệ thống, hãy dịch ngôn ngữ Dev trên ra thành một **Scenario Text (Kịch bản nghiệp vụ bằng Tiếng Việt)** dễ hiểu dành cho Giám đốc Kinh doanh nghe. Liệt kê rõ App của chúng ta phải làm gì ở lúc Request, Cần xử lý gì khi nhận 4 mã lỗi `status_code` kia?"*

**💡 Nâng cao**: "Tại sao API phía trên lại dùng phương thức POST mà không dùng phương thức GET?"
