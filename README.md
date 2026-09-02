# 🛒 Cải tiến Quy trình Order-to-Delivery (E-commerce)

> Dự án Portfolio: Phân tích quy trình nghiệp vụ (Business Process Analysis)  
> **Tống Anh Đức** | Business Analyst Intern / Junior  
> 📧 tongducne07062003@gmail.com  
> 🔗 LinkedIn: linkedin.com/in/tong-anh-duc | GitHub: github.com/tongducne07062003-prog

---

## 📊 Tổng quan dự án

Phân tích và cải tiến quy trình **Order-to-Delivery** của một shop thời trang online, dựa trên **4.200+ đơn hàng** (dữ liệu mô phỏng).

Xác định điểm nghẽn gây chậm trễ và tỷ lệ hủy đơn cao (11.4%), đề xuất quy trình To-Be, prototype giao diện theo dõi đơn hàng và viết tài liệu yêu cầu (BRD).

### 🎯 Điểm nổi bật

| Chỉ số | Giá trị | Ghi chú |
|--------|---------|---------|
| 📦 Số đơn phân tích | 4.200+ | Thời trang online |
| ❌ Tỷ lệ hủy đơn hiện tại | 11.4% | Cao hơn benchmark ngành |
| ⏱️ Thời gian xử lý TB | Cần cải thiện | Nhiều bước thủ công |
| 📉 Mục tiêu giảm hủy đơn | < 7% | Sau khi triển khai |
| 🛠️ Công cụ | Excel, Figma, BPMN | As-Is / To-Be + Prototype |

---

## 🎯 Vấn đề nghiệp vụ

Shop thời trang online đang gặp các vấn đề:

1. **Quy trình xử lý đơn thủ công nhiều bước** → chậm trễ, sai sót.
2. **Khách hàng không được cập nhật trạng thái** kịp thời → tăng tỷ lệ hủy và khiếu nại.
3. **Thiếu tài liệu quy trình chuẩn** → nhân viên mới khó tiếp cận, khó scale.
4. **Không có metric rõ ràng** để đo lường hiệu quả từng bước.

**Mục tiêu:**
- Vẽ lại quy trình As-Is  
- Thiết kế quy trình To-Be tối ưu  
- Prototype màn hình theo dõi đơn hàng  
- Viết BRD để team Dev / Operations triển khai  

---

## 🛠️ Công cụ & Công nghệ

| Công cụ | Mục đích |
|---------|----------|
| **Excel** | Phân tích dữ liệu đơn hàng, tính KPI |
| **BPMN** | Vẽ quy trình As-Is / To-Be (draw.io / Lucidchart / Visio) |
| **Figma** | Prototype giao diện theo dõi đơn hàng |
| **Word / PowerPoint** | Viết BRD & trình bày đề xuất |

**Kỹ thuật chính:**
- Lập bản đồ quy trình (As-Is → To-Be)
- Phân tích nguyên nhân gốc (5 Whys / Fishbone)
- Thu thập yêu cầu & viết BRD
- Tư duy UX cho màn hình tracking

---

## 📁 Cấu trúc dự án

```
Ecommerce-Order-Process-Improvement/
├── 01_data/                  # Dữ liệu đơn hàng mẫu + phân tích
├── 02_process/               # Sơ đồ BPMN (As-Is / To-Be)
├── 03_prototype/             # Ảnh / link prototype Figma
├── 04_brd/                   # Tài liệu yêu cầu nghiệp vụ (BRD)
└── README.md
```

---

## 📊 Insight chính

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

## 💡 Đề xuất chiến lược

### Ưu tiên 1: Tự động hóa xác nhận & thông báo (0–45 ngày)
- Tích hợp hệ thống tự động gửi Zalo/SMS khi:
  - Đơn được xác nhận
  - Đơn đang đóng gói
  - Đơn đã bàn giao vận chuyển
- Giảm thời gian xác nhận từ thủ công xuống < 30 phút.

### Ưu tiên 2: Prototype màn hình Theo dõi đơn (Figma)
- Khách hàng xem được trạng thái real-time + ước tính giao hàng.
- Giảm 40–50% ticket CSKH liên quan đến “tracking”.

### Ưu tiên 3: Chuẩn hóa quy trình & đào tạo
- Tài liệu BRD + SOP mới.
- Training nhân viên theo quy trình To-Be.

**Ước tính tác động:**
- Giảm thời gian xử lý đơn trung bình **~35%**
- Giảm tỷ lệ hủy đơn xuống **dưới 7%**

---

## 📈 Tác động kỳ vọng

| Chỉ số | Hiện tại | Mục tiêu (3–6 tháng) | Cải thiện |
|--------|----------|----------------------|-----------|
| Tỷ lệ hủy đơn | 11.4% | < 7% | ↓ ~40% |
| Thời gian xử lý trung bình | Baseline | -35% | 📈 |
| Ticket CSKH về tracking | Cao | Giảm 40–50% | 📈 |
| Độ hài lòng khách hàng | - | Tăng | 📈 |

---

## 🖼️ Sản phẩm bàn giao

- **BPMN As-Is / To-Be** – Quy trình hiện tại so với đề xuất  
- **Prototype Figma** – Màn hình “Theo dõi đơn hàng” cho khách  
- **BRD** – Tài liệu yêu cầu đầy đủ cho Dev & Operations  

<img width="2224" height="1105" alt="tracking_screens" src="https://github.com/user-attachments/assets/956912fb-eda6-45a8-8a11-2adbcdfa57d3" />
<img width="2084" height="1476" alt="dashboard_preview" src="https://github.com/user-attachments/assets/da13e3c5-4b9c-4bf3-80bf-106a45f5723f" />


---

## 🚀 Cách sử dụng dự án

1. Xem sơ đồ quy trình trong `02_process/`
2. Mở prototype Figma (link / ảnh trong `03_prototype/`)
3. Đọc BRD trong `04_brd/` để hiểu yêu cầu chức năng & phi chức năng
4. Dùng file Excel trong `01_data/` để tái hiện phân tích KPI

---

## 📚 Kỹ năng thể hiện

**Business Analysis**
- Lập bản đồ quy trình (BPMN)
- Thu thập yêu cầu & viết BRD
- Phân tích nguyên nhân gốc
- Giao tiếp với stakeholder

**Công cụ**
- Figma (prototype UI/UX)
- Excel (phân tích dữ liệu)
- Công cụ mô hình hóa quy trình

**Kỹ năng mềm**
- Tư duy hệ thống
- Giải quyết vấn đề thực tế
- Viết tài liệu chuyên nghiệp

---

## 👨‍💼 Về tôi

**Tống Anh Đức** – Business Analyst Intern / Junior  

📧 **Email:** [tongducne07062003@gmail.com](mailto:tongducne07062003@gmail.com)  
💼 **LinkedIn:** [linkedin.com/in/tong-anh-duc](https://linkedin.com/in/tong-anh-duc)  
🐙 **GitHub:** [github.com/tongducne07062003-prog](https://github.com/tongducne07062003-prog)  
📍 Hà Nội, Việt Nam

**Nền tảng:**  
- Cử nhân Quản trị Kinh doanh (NEU + Dongseo University – GPA 3.92/4.5)  
- Kinh nghiệm Sales & CSKH tại FPT Telecom  
- Đang theo học Thạc sĩ Hệ thống thông tin quản lý – NEU

---

## 📜 Giấy phép

MIT License – Tự do sử dụng cho mục đích học tập và xây dựng portfolio.

---

**⭐ Nếu project hữu ích, hãy cho một star!**  
**💬 Câu hỏi? Mở Issue hoặc email trực tiếp.**

Xây dựng với ❤️ bởi Tống Anh Đức | Cập nhật: Tháng 8/2026
