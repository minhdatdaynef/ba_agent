# 📊 Ma trận Quyết định Underwriting (Day 3 Actionable)

Tài liệu này hệ thống hóa các logic "Linh động hóa" dựa trên 4 chiến lược của BA.

## 1. Logic Phối hợp (Combined Logic)
Hệ thống không đánh giá các tiêu chí đơn lẻ mà phối hợp chúng để ra quyết định:
- **BMI (28-30) + Văn phòng** = **STP** (Thay vì Manual).
- **Tuổi (>60) + VIP Tái tục** = **STP** (Thay vì Manual).
- **Bệnh (YES) + Chứng từ ổn định** = **STP with Loading** (Thay vì Manual).

## 2. Bảng quyết định chi tiết (Decision Table)

| Điều kiện 1: Tuổi | Điều kiện 2: BMI | Điều kiện 3: Nghề | Điều kiện 4: Medical | Điều kiện 5: Type | KẾT QUẢ |
| :--- | :--- | :--- | :--- | :--- | :--- |
| < 60 | <= 28 | Standard | NO | All | **STP** |
| < 60 | 28 - 30 | Office | NO | All | **STP** |
| > 60 | <= 28 | Office | NO | **VIP Loyal** | **STP** |
| All | All | All | YES (Stable) | With Docs | **STP (Loading)** |
| All | All | Class 4 | All | All | **Decline** |
| Mixed | High | Other | YES | New | **Manual** |

## 3. Ghi chú cho Developer
- Sử dụng mô hình **Rule-Engine-as-a-Service**.
- Cho phép Config các ngưỡng (30, 28, 5 năm) trên UI Admin.
- Tích hợp Module AI-OCR để quét cụm từ "Stable/Ổn định" trong chứng từ Y tế.
