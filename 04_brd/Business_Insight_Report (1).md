# Business Insight Report
## E-commerce Order-to-Delivery Process Improvement

**Prepared by:** Tống Anh Đức  
**Email:** tongducne07062003@gmail.com  
**Role:** Business Analyst Intern / Junior  
**Date:** September 2026  
**Version:** 2.0 (aligned with sample data in repo)

---

## 1. Executive Summary

Phân tích quy trình Order-to-Delivery trên **bộ dữ liệu mô phỏng 400 đơn** (shop thời trang online):

| Finding chính | Giá trị (sample) |
|---------------|------------------|
| Tỷ lệ hủy | **8.0%** (32/400) |
| Thời gian xác nhận TB | **~10.4 giờ** (median 4h, max **36h**) |
| Kênh hủy cao nhất | **Shopee ~16.3%** |
| Đơn còn ở bước giữa pipeline | Chờ xác nhận 32 · Đang đóng gói 69 · … |

**Hướng xử lý:** To-Be ưu tiên **auto confirm + thông báo trạng thái**, màn **tracking**, và **BRD/SOP**.  
Mục tiêu hủy **&lt; 7%** và cải thiện thời gian ~**35%** là **kỳ vọng thiết kế**, chưa đo sau go-live.


---

## 2. Business Context & Objective

### 2.1 Pain chính
1. Nhiều bước xử lý đơn thủ công → chậm, khó chuẩn hóa  
2. Khách thiếu cập nhật trạng thái → hỏi CSKH, dễ hủy  
3. Thiếu tài liệu process/requirement → khó onboard và scale  
4. Thiếu metric theo từng bước → khó biết đơn kẹt ở đâu  

### 2.2 Mục tiêu project
Map **As-Is** → thiết kế **To-Be** → **prototype** tracking → viết **BRD** cho Dev/Ops (không làm thay phần code).

---

## 3. Data & Methodology

| Hạng mục | Chi tiết |
|----------|----------|
| Số đơn mẫu | **400** |
| File | `01_data/sample_order_data.xlsx` |
| Công cụ | Excel (KPI), BPMN, Figma, BRD |
| Chỉ số | `is_cancelled`, `confirm_hours`, `status`, `channel` |

---

## 4. Key Findings

### 4.1 Hủy đơn
- Hủy: **32/400 = 8.0%**

### 4.2 Phân bố status (As-Is snapshot)

| Status | Số đơn |
|--------|--------|
| Đã giao | 93 |
| Đã bàn giao VC | 79 |
| Đang đóng gói | 69 |
| Đang giao | 52 |
| Đã xác nhận | 43 |
| Đã hủy | 32 |
| Chờ xác nhận | 32 |

### 4.3 Confirm hours
| Metric | Giá trị |
|--------|---------|
| Mean | ~10.4 h |
| Median | 4 h |
| P75 | ≤ 12 h |
| Max | 36 h |

→ Đuôi chậm (tới 1.5 ngày) là tín hiệu cần tự động hóa / SLA confirm.

### 4.4 Hủy theo kênh

| Kênh | Tỷ lệ hủy | n |
|------|----------:|---|
| **Shopee** | **16.3%** | 86 |
| TikTok | 8.4% | 107 |
| Website | 4.8% | 104 |
| Facebook | 3.9% | 103 |

→ Ưu tiên soi fulfillment / notify / SLA trên **Shopee** trước khi nhân rộng.

---

## 5. Strategic Recommendations (To-Be)

### Priority 1 (0–45 ngày) — Auto confirm & notify
- Thông báo khi: đã xác nhận / đang đóng gói / đã bàn giao VC  
- Rút đuôi confirm chậm (max 36h trên sample)

### Priority 2 — Prototype màn tracking
- Khách tự xem status + ETA  
- Kỳ vọng minh họa: giảm ticket “đơn đâu rồi?” (hướng 40–50% nếu triển khai tốt)

### Priority 3 — BRD + SOP + training
- Requirement cho Dev/Ops; process không phụ thuộc một người

---

## 6. Expected Impact (minh họa)

| Chỉ số | Hiện trạng (sample) | Mục tiêu nếu triển khai | Loại |
|--------|---------------------|-------------------------|------|
| Tỷ lệ hủy | **8.0%** | **&lt; 7%** | Target |
| Confirm (mean/max) | ~10.4h / 36h | Rút đuôi chậm | Finding → action |
| Hủy Shopee | ~16.3% | Thu hẹp vs kênh khác | Finding → ưu tiên |
| Ticket tracking | Cao (định tính) | Giảm ~40–50% | Target |
| Thời gian xử lý | Baseline | ~−35% | Target thiết kế To-Be |

**Chưa đạt trên production** — project portfolio, chưa go-live.

---

## 7. Deliverables

| Sản phẩm | Thư mục |
|----------|---------|
| BPMN As-Is / To-Be | `02_process/` |
| Prototype tracking | `03_prototype/` |
| BRD | `04_brd/` |
| Data + KPI | `01_data/` |

---

## 8. Next Steps

1. Xác nhận BPMN với Operations  
2. Ưu tiên phase 1: notify + status update  
3. Khi có data thật: đo baseline hủy & confirm hours trước–sau  

---

**Prepared by Tống Anh Đức**  
📧 tongducne07062003@gmail.com · GitHub: github.com/tongducne07062003-prog
