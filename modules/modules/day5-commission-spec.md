# 💰 Đặc tả Logic Hoa hồng & Truy thu (Day 5 Outcome)

## 1. Cấu trúc Tính toán (Commission Calculation)
- **FYC (First Year Commission):** Tính trên Phí thực thu (Net FYP).
- **Bonus:** Chỉ tính trên số **Dương** cuối cùng sau khi đã trừ toàn bộ Clawback trong kỳ.
- **Overriding (Thưởng quản lý):** Phải tỉ lệ thuận với kết quả thực tế của cấp dưới (Nếu cấp dưới bị thu hồi, cấp trên cũng bị thu hồi tương ứng).

## 2. Quy tắc Xử lý Truy thu (Clawback Rules)
- **Nguyên tắc:** Thu hồi tại nguồn đã chi trả.
- **Xử lý Thu nhập Âm (Negative Income):** 
    - **UI Payout:** Hiển thị = 0 (Không chi trả âm).
    - **Database Ledger:** Ghi nhận số dư nợ (**Debit Balance**) và tự động cấn trừ vào kỳ lương gần nhất có phát sinh thu nhập dương.
- **Audit Trail:** Mỗi dòng Clawback phải tham chiếu (Reference) đến đúng `Policy_Number` và `Original_Transaction_ID` để đối soát.

## 3. Cấu trúc Cây (Hierarchy)
- Hệ thống hỗ trợ **Moving Structure** (Dịch chuyển nhánh).
- Khi có sự thay đổi cấp bậc, hoa hồng được tính theo Snapshot tại thời điểm chốt kỳ lương (Cut-off date).
