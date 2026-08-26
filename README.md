# 🛒 E-commerce Order-to-Delivery Process Improvement

> Business Process Analysis + BA Portfolio Project  
> **Tống Anh Đức** | Business Analyst Intern / Junior  
> 📧 tongducne07062003@gmail.com  
> 🔗 LinkedIn: linkedin.com/in/tong-anh-duc | GitHub: github.com/tongducne

---

## 📊 Project Overview

Phân tích và cải tiến quy trình **Order-to-Delivery** của một shop thời trang online, dựa trên **4.200+ đơn hàng** thực tế.

Xác định điểm nghẽn gây chậm trễ và tỷ lệ hủy đơn cao (11.4%), đề xuất quy trình To-Be, prototype giao diện theo dõi đơn hàng và viết tài liệu yêu cầu (BRD).

### 🎯 Key Highlights

| Metric                        | Value                  | Note                          |
|-------------------------------|------------------------|-------------------------------|
| 📦 Số đơn phân tích           | 4.200+                 | Thời trang online             |
| ❌ Tỷ lệ hủy đơn hiện tại     | 11.4%                  | Cao hơn benchmark ngành       |
| ⏱️ Thời gian xử lý TB         | Cần cải thiện          | Nhiều bước thủ công           |
| 📉 Mục tiêu giảm hủy đơn      | < 7%                   | Sau khi triển khai            |
| 🛠️ Công cụ                    | Excel, Figma, BPMN     | As-Is / To-Be + Prototype     |

---

## 🎯 Business Problem

Shop thời trang online đang gặp các vấn đề:

1. **Quy trình xử lý đơn thủ công nhiều bước** → chậm trễ, sai sót.
2. **Khách hàng không được cập nhật trạng thái** kịp thời → tăng tỷ lệ hủy và khiếu nại.
3. **Thiếu tài liệu quy trình chuẩn** → nhân viên mới khó tiếp cận, khó scale.
4. **Không có metric rõ ràng** để đo lường hiệu quả từng bước.

**Goal:**  
- Vẽ lại As-Is process  
- Thiết kế To-Be process tối ưu  
- Prototype màn hình theo dõi đơn hàng  
- Viết BRD để team Dev / Operations triển khai

---

## 🛠️ Tools & Technologies

| Tool          | Mục đích                                      |
|---------------|-----------------------------------------------|
| **Excel**     | Phân tích dữ liệu đơn hàng, tính KPI          |
| **BPMN**      | Vẽ quy trình As-Is / To-Be (draw.io / Lucidchart / Visio) |
| **Figma**     | Prototype giao diện theo dõi đơn hàng         |
| **Word/PPT**  | Viết BRD & trình bày recommendation           |

**Kỹ thuật chính:**
- Process Mapping (As-Is → To-Be)
- Root Cause Analysis (5 Whys / Fishbone)
- Requirement Gathering & BRD writing
- UX thinking cho màn hình tracking

---

## 📁 Project Structure

```
Ecommerce-Order-Process-Improvement/
├── 01_data/                  # Sample order data + analysis
├── 02_process/               # BPMN diagrams (As-Is / To-Be)
├── 03_prototype/             # Figma link + screenshots
├── 04_brd/                   # Business Requirements Document
└── README.md
```

---

## 📊 Key Insights

### 1️⃣ Điểm nghẽn chính (từ 4.200+ đơn)

1. Xác nhận đơn thủ công (chậm 4–12 giờ)
2. Không có thông báo tự động khi đổi trạng thái
3. Kho và vận chuyển thiếu đồng bộ
4. Khách hàng phải chủ động hỏi → tăng tải CSKH
5. Tỷ lệ hủy cao nhất ở giai đoạn “Chờ xác nhận” và “Đang đóng gói”

### 2️⃣ Tác động

- Tỷ lệ hủy **11.4%** (cao hơn mức tốt của ngành ~6–8%)
- Thời gian trung bình từ đặt hàng đến giao hàng dài hơn mong đợi của khách
- CSKH phải trả lời nhiều câu hỏi “Đơn tôi đến đâu rồi?”

---

## 💡 Strategic Recommendations

### Priority 1: Tự động hóa xác nhận & thông báo (0–45 ngày)
- Tích hợp hệ thống tự động gửi Zalo/SMS khi:
  - Đơn được xác nhận
  - Đơn đang đóng gói
  - Đơn đã bàn giao vận chuyển
- Giảm thời gian xác nhận từ thủ công xuống < 30 phút.

### Priority 2: Prototype màn hình Tracking (Figma)
- Khách hàng xem được trạng thái real-time + ước tính giao hàng.
- Giảm 40–50% ticket CSKH liên quan đến “tracking”.

### Priority 3: Chuẩn hóa quy trình & đào tạo
- Tài liệu BRD + SOP mới.
- Training nhân viên theo To-Be process.

**Ước tính tác động:**
- Giảm thời gian xử lý đơn trung bình **~35%**
- Giảm tỷ lệ hủy đơn xuống **dưới 7%**

---

## 📈 Expected Impact

| Chỉ số                      | Hiện tại     | Mục tiêu (3–6 tháng) | Cải thiện |
|-----------------------------|--------------|----------------------|-----------|
| Tỷ lệ hủy đơn               | 11.4%        | < 7%                 | ↓ ~40%   |
| Thời gian xử lý trung bình  | Baseline     | -35%                 | 📈       |
| Ticket CSKH về tracking     | Cao          | Giảm 40–50%          | 📈       |
| Độ hài lòng khách hàng      | -            | Tăng                 | 📈       |

---

## 🖼️ Deliverables Preview

- **BPMN As-Is / To-Be** – Quy trình hiện tại vs đề xuất
- **Figma Prototype** – Màn hình “Theo dõi đơn hàng” cho khách
- **BRD** – Tài liệu yêu cầu đầy đủ cho Dev & Operations

*(Thêm screenshot Figma và sơ đồ BPMN vào thư mục tương ứng)*

---

## 🚀 How to Use This Project

1. Xem sơ đồ quy trình trong `02_process/`
2. Mở prototype Figma (link sẽ được cập nhật trong `03_prototype/`)
3. Đọc BRD trong `04_brd/` để hiểu rõ yêu cầu chức năng & phi chức năng
4. Dùng file Excel trong `01_data/` để tái hiện phân tích KPI

---

## 📚 Skills Demonstrated

**Business Analysis**
- Process Mapping (BPMN)
- Requirement Elicitation & BRD Writing
- Root Cause Analysis
- Stakeholder Communication

**Tools**
- Figma (UI/UX Prototype)
- Excel (Data Analysis)
- Process Modeling Tools

**Soft Skills**
- Tư duy hệ thống
- Giải quyết vấn đề thực tế
- Viết tài liệu chuyên nghiệp

---

## 👨‍💼 About Me

**Tống Anh Đức** – Business Analyst Intern / Junior  

📧 **Email:** [tongducne07062003@gmail.com](mailto:tongducne07062003@gmail.com)  
💼 **LinkedIn:** [linkedin.com/in/tong-anh-duc](https://linkedin.com/in/tong-anh-duc)  
🐙 **GitHub:** [https://github.com/tongducne07062003-prog](https://github.com/tongducne07062003-prog)  
📍 Hà Nội, Việt Nam

**Background:**  
- Cử nhân Quản trị Kinh doanh (NEU + Dongseo University – GPA 3.92/4.5)  
- Kinh nghiệm Sales & CSKH tại FPT Telecom  
- Đang theo học Thạc sĩ Hệ thống thông tin quản lý – NEU

---

## 📜 License

MIT License – Tự do sử dụng cho mục đích học tập và xây dựng portfolio.

---

**⭐ Nếu project hữu ích, hãy cho một star!**  
**💬 Câu hỏi? Mở Issue hoặc email trực tiếp.**

Built with ❤️ by Tống Anh Đức | Last Updated: August 2026
[README.md](https://github.com/user-attachments/files/31446062/README.md)

