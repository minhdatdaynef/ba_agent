# 🧪 Kế hoạch Kiểm thử Chi tiết (Deep-dive Testing Plan) - Day 4

## 1. Phân tích Giá trị Biên (BVA) cho Rule Độ tuổi & BMI
| Thông số | Biên Dưới (Min) | Điểm Giao Thoa | Biên Trên (Max) |
| :--- | :--- | :--- | :--- |
| **Độ tuổi** | 18 (Duyệt) / 17 (Từ chối) | 60 (Duyệt) / 61 (Manual) | 65 (Manual) / 66 (Từ chối) |
| **BMI** | 15 (Manual) / 16 (Duyệt) | 28 (Duyệt) / 28.1 (Manual/STP*) | 35 (Manual) / 36 (Decline) |
*\*Ghi chú: 28.1 sẽ STP nếu thỏa mãn điều kiện Nghề nghiệp Văn phòng.*

## 2. Kịch bản Kiểm thử Sự ưu tiên (Priority Scenarios)
**Scenario ID: SEQ_01**
- **Mục tiêu:** Kiểm tra Rule Nghề nghiệp phải được ưu tiên hàng đầu.
- **Dữ liệu:** Khách hàng VIP, Tuổi 25, BMI 20 (Cực đẹp) NHƯNG Nghề nghiệp = Class 4.
- **Kết quả mong đợi:** Hệ thống phải báo **Decline** ngay lập tức. Không được hiện Approved dù là VIP.

**Scenario ID: SEQ_02**
- **Mục tiêu:** Kiểm tra Logic "Linh động hóa" cho BMI.
- **Dữ liệu:** Tuổi 45, BMI 29, Nghề nghiệp = Office.
- **Kết quả mong đợi:** Hệ thống báo **STP (Approved)**. 
- **Nếu ra kết quả khác:** Lỗi coding logic (Chưa áp dụng ma trận linh động).

## 3. Cải tiến Sản phẩm (Product Enhancement) - Từ góc độ BA
- **Tính năng đề xuất:** Tích hợp **BMI Calculator Function** ngay trên e-App Form.
- **Mục tiêu:** Chặn lỗi "Dirty Data" (Dữ liệu bẩn) do người dùng gõ nhầm hoặc không biết tính. Hệ thống tự tính BMI dựa trên Chiều cao/Cân nặng và Lock trường dữ liệu BMI.
- **Validation:** Thiết kế Range check (Ví dụ: Chiều cao > 100cm và < 250cm) để tránh các ca vô lý.

## 4. Danh sách Mock Data (JSON Format) cho Dev
```json
[
  {
    "desc": "Kiểm tra khách hàng VIP lớn tuổi",
    "input": {"age": 62, "bmi": 24, "occ": "Office", "isVIP": true},
    "expected": "Approved (STP)"
  },
  {
    "desc": "Kiểm tra điểm nghẽn nghề nghiệp",
    "input": {"age": 30, "bmi": 22, "occ": "Class 4", "isVIP": false},
    "expected": "Decline"
  },
  {
    "desc": "Kiểm tra BMI vùng xám cho văn phòng",
    "input": {"age": 35, "bmi": 29.5, "occ": "Office", "isVIP": false},
    "expected": "Approved (STP)"
  }
]
```
