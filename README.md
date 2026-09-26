# 🛒 Cải tiến Quy trình Order-to-Delivery (E-commerce)

> Dự án Portfolio: Phân tích quy trình nghiệp vụ (Business Process Analysis)  
> **Tống Anh Đức** | Business Analyst Intern 
> 📧 tongducne07062003@gmail.com  
> 🔗 LinkedIn: linkedin.com/in/tong-anh-duc | GitHub: github.com/tongducne07062003-prog

---

## 📊 Tổng quan dự án

Phân tích quy trình **Order-to-Delivery** cho bối cảnh shop thời trang online, dựa trên **bộ dữ liệu mô phỏng 400 đơn hàng**.

**Mục tiêu:** Tìm chỗ đơn bị chậm / dễ hủy, đề xuất quy trình **To-Be**, đề xuất quy trình To-Be, prototype giao diện theo dõi đơn hàng và viết tài liệu yêu cầu (BRD).

### ✨ Điểm nổi bật (từ sample 400 đơn)

| 📌 Chỉ số | 📈 Giá trị | 📝 Ghi chú |
|-----------|------------|------------|
| 📦 Số đơn trong sample | **400** | File `sample_order_data.xlsx` |
| ❌ Tỷ lệ hủy (`is_cancelled`) | **8.0%** (32/400) | Finding từ sample |
| ⏱️ Thời gian xác nhận TB | **~10.4 giờ** (median **4 giờ**, max **36 giờ**) | Cột `confirm_hours` |
| 🛒 Kênh hủy cao nhất | **Shopee ~16.3%** | Cao hơn Facebook / Website |
| 🎯 Mục tiêu hủy (nếu triển khai To-Be) | **< 7%** | Kỳ vọng chiến lược, chưa đo sau go-live |
| 🛠️ Công cụ | Excel · BPMN · Figma · BRD | As-Is / To-Be + prototype |


---

## 🎯 Vấn đề nghiệp vụ

Shop thời trang online đang gặp các vấn đề:

1. Quy trình xử lý đơn còn nhiều bước thủ công → chậm, dễ sai sót, khó chuẩn hóa khi đơn tăng.
2. Khách không được cập nhật trạng thái kịp thời → phải chủ động hỏi CSKH; tăng trải nghiệm xấu và dễ dẫn tới hủy đơn.
3. Thiếu tài liệu quy trình / requirement chuẩn → nhân viên mới khó tiếp cận, khó bàn giao và khó scale.
4. Chưa có metric rõ theo từng bước (confirm, đóng gói, bàn giao…) → khó biết đơn đang kẹt ở đâu để ưu tiên sửa.

**Mục tiêu:**
- Vẽ lại quy trình As-Is  
- Thiết kế quy trình To-Be tối ưu  
- Prototype màn hình theo dõi đơn hàng  
- Viết BRD để team Dev / Operations triển khai  

---

## 🛠️ Công cụ & cách làm

| 🔧 Công cụ | 💡 Dùng để |
|------------|------------|
| **Excel** | Đếm hủy, thời gian confirm, cắt theo status / kênh |
| **BPMN** (draw.io / tương đương) | Vẽ As-Is và To-Be |
| **Figma** | Prototype màn “Theo dõi đơn hàng” |
| **Word / Markdown** | BRD (yêu cầu chức năng & phi chức năng) |

**🔍 Hướng phân tích:**

- 📉 KPI: tỷ lệ hủy, `confirm_hours`, phân bố `status`
- 🛒 Cắt theo **kênh** (Shopee / TikTok / Facebook / Website)
- 🧱 Xác định **điểm nghẽn** (chờ xác nhận, đóng gói, thiếu notify)
- 🗺️ As-Is → To-Be → prototype → BRD
- ✂️ Tách **finding từ sample** vs **mục tiêu nếu triển khai**


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

### 1️⃣ Tỷ lệ hủy và phân bố trạng thái

Trên **400** đơn:

| 📌 Chỉ số | 📈 Giá trị |
|-----------|------------|
| Đơn hủy (`is_cancelled = True`) | **32** |
| Tỷ lệ hủy | **8.0%** |

**Phân bố `status`:**

| Status | Số đơn |
|--------|--------|
| Đã giao | 93 |
| Đã bàn giao VC | 79 |
| Đang đóng gói | 69 |
| Đang giao | 52 |
| Đã xác nhận | 43 |
| Đã hủy | 32 |
| Chờ xác nhận | 32 |

💬 **Ý nghĩa:** Vẫn còn lượng đơn ở **Chờ xác nhận** và **Đang đóng gói** — đúng các bước hay phát sinh chậm / thiếu thông tin cho khách. Trên sample, đơn hủy được gắn status **Đã hủy** (32 đơn); phân tích process vẫn ưu tiên các bước trước khi hoàn tất/hủy.


---

### 2️⃣ Thời gian xác nhận — tín hiệu nghẽn

| ⏱️ `confirm_hours` | Giá trị |
|--------------------|---------|
| Trung bình | **~10.4 giờ** |
| Trung vị | **4 giờ** |
| Phần lớn (75%) | ≤ **12 giờ** |
| Max | **36 giờ** (~1.5 ngày) |

💬 **Ý nghĩa:** Nhiều đơn confirm nhanh (median 4h), nhưng **đuôi chậm tới 36h** kéo trải nghiệm xuống và tăng nguy cơ khách hết kiên nhẫn — khớp đề xuất **tự động hóa confirm + notify**.

---

### 3️⃣ Hủy theo kênh (finding rõ trên sample)

| 🛒 Kênh | Tỷ lệ hủy | Số đơn |
|---------|----------:|-------:|
| **Shopee** | **16.3%** | 86 |
| TikTok | 8.4% | 107 |
| Website | 4.8% | 104 |
| Facebook | 3.9% | 103 |

💬 **Ý nghĩa:** **Shopee hủy cao hơn hẳn** các kênh khác trên sample → khi cải tiến process, nên **ưu tiên soi fulfillment / SLA / thông báo** trên kênh này trước (hoặc tách playbook theo kênh).


---


## 🚀 Đề xuất chiến lược

### 🥇 Ưu tiên 1 — Tự động xác nhận & thông báo (0–45 ngày)

- 📲 Gửi Zalo/SMS (hoặc kênh tương đương) khi: **đã xác nhận**, **đang đóng gói**, **đã bàn giao vận chuyển**
- ⏱️ Hướng tới rút phần confirm thủ công (mục tiêu vận hành: nhiều đơn về mức **dưới ~30–60 phút** khi hệ thống ổn)
- Gắn với finding: confirm mean ~10h, max 36h

### 🥈 Ưu tiên 2 — Prototype màn Theo dõi đơn (Figma)

- 👀 Khách xem được trạng thái + ETA cơ bản
- 🎧 Kỳ vọng minh họa: giảm ticket “đơn tôi đâu rồi?” (hướng **40–50%** nếu triển khai tốt — **target**, chưa đo sau go-live)

### 🥉 Ưu tiên 3 — BRD + SOP + training

- 📄 BRD cho Dev/Ops: chức năng notify, tracking, cập nhật status
- 📘 SOP To-Be để process không phụ thuộc một người

**Tác động kỳ vọng (minh họa nếu triển khai):**

- Hủy: từ **8.0%** (sample) hướng **< 7%**
- Thời gian xử lý: hướng cải thiện khoảng **~35%** (target thiết kế To-Be)
- Ticket tracking: giảm rõ (target vận hành)

---

## 📈 Tác động kỳ vọng (minh họa)

| 📌 Chỉ số | 📊 Hiện trạng (sample) | 🎯 Mục tiêu nếu triển khai | 🏷️ Loại |
|-----------|------------------------|----------------------------|---------|
| Tỷ lệ hủy | **8.0%** | **< 7%** | Target chiến lược |
| Confirm hours (mean / max) | **~10.4h / 36h** | Rút đuôi chậm, tăng đơn confirm nhanh | Finding → action |
| Hủy kênh Shopee | **~16.3%** | Thu hẹp vs kênh khác | Finding → ưu tiên |
| Ticket CSKH về tracking | Cao (định tính) | Giảm ~40–50% | Target vận hành |

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
