# Day 5: Phân tích Kênh Phân phối & Hoa hồng (Distribution & Commission)

## ⏱️ Bạn Có 30 Phút Hôm Nay!
- **10 Phút**: Phân biệt Agency vs Bancassurance.
- **10 Phút**: Bài toán tính Hoa hồng (Commission) đau não.
- **10 Phút**: Yêu cầu AI tính Hoa hồng theo cấu trúc Đa cấp (Hierarchy).

---

## 📖 1. Tổng quan 2 Kênh Phân phối Chính
- **Agency (Đội Đại lý)**: Mạng lưới cá nhân tư vấn bán bảo hiểm bán thời gian hoặc toàn thời gian. Bao gồm: Đại lý mới (Agent) -> Trưởng nhóm (Unit Manager) -> Giám đốc khu vực (Branch Manager).
- **Bancassurance (Ngân hàng)**: Bán chéo. Khách hàng đến gửi tiết kiệm tại Vietcombank -> Giao dịch viên giới thiệu Bảo hiểm FWD. Hoa hồng chia lại cho Ngân hàng và nhân viên.

---

## 🚀 2. Bài Toán Tính Hoa Hồng (10 Phút)
Trong hệ thống quản lý Đại lý, **Hoa hồng (Commission & Bonus)** là phần phức tạp nhất. Nó chia ra:
1. **FYC (First Year Commission)**: Thường chiếm 30% - 40% Phí bảo hiểm năm đầu (FYP). Tức là Khách đóng 20 triệu -> Đại lý lấy 8 triệu.
2. **RYC (Renewal Year Commission)**: Phí tái tục năm 2, năm 3 (Tỷ lệ giảm dần còn 10%, 5%, 0%).
3. **Overriding (Hoa hồng quản lý/Thưởng KPI đội nhóm)**: Đại lý A có doanh số 1 tỷ, Quản lý B (tuyến trên của A) được hưởng 5% trên số hoa hồng của A. Mạng lưới này có cấu trúc Cây (Hierarchy C).

> **Lời khuyên BA**: Luôn dùng **Data Hierarchy Table** (bảng chứa Cấp bậc và Quản lý trực tiếp `Manager_ID`).

---

## 🤖 3. Thực hành Tính Hoa Hồng Phức Tạp bằng AI (10 Phút)

**🎯 Bài tập hôm nay:**
Copy đoạn Prompt sau và gửi tôi giải logic giúp bạn nhé:

> *"Tôi đang làm BA Hệ thống Tính thưởng (Commission System) cho Kênh Agency.
> Dữ liệu cho:
> - Cấu trúc cấp bậc: Branch Manager (Quản lý trưởng) -> Unit Manager (Trưởng nhóm) -> Agent (Đại lý bán).
> - Giao dịch tháng 10: Hai Agent (A1 và A2) mỗi người bán được 1 hợp đồng với Phí (FYP) là 20.000.000 VNĐ.
> - Agent được nhận: Hoa hồng FYC là 35% trên FYP. Thưởng năng suất thêm 5% nếu FYP đạt trên 15 triệu.
> - Unit Manager được nhận: Thưởng quản lý bằng 8% tổng FYC của cả đội nhóm bên dưới.
> - Branch Manager được nhận: Thưởng lãnh đạo bằng 2% tổng FYP của toàn văn phòng.
> 
> Hãy 'Suy nghĩ từng bước một' (Chain of Thought), tính toán và in ra Thu nhập Chính xác (Net Income) của 2 Đại lý A, của Unit Manager, và Branch Manager. 
> Sau đó, hãy tạo giúp tôi một Bảng Dữ Liệu (Table Data) mẫu mô tả cấu trúc Cây hoa hồng này."*

**💡 Nâng cao**: "Điều gì xảy ra với Hoa hồng Overriding của Unit Manager nếu Agent A1 quyết định nghỉ việc (Terminate) trước khi khách hàng đóng phí?"
