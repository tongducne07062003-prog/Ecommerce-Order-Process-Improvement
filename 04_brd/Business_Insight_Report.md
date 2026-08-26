# Business Insight Report & BRD Summary
## E-commerce Order-to-Delivery Process Improvement

**Prepared by:** Tống Anh Đức  
**Email:** tongducne07062003@gmail.com  
**Role:** Business Analyst Intern / Junior  
**Date:** August 2026  
**Version:** 1.0

---

## 1. Executive Summary

Phân tích **400 đơn hàng** mẫu của một shop thời trang online cho thấy:

- Tỷ lệ hủy đơn hiện tại: **~11.4%** (cao hơn mức tốt của ngành 6–8%)
- Thời gian xác nhận đơn trung bình còn cao (nhiều đơn mất 8–24 giờ)
- Kênh Shopee có tỷ lệ hủy cao nhất trong các kênh

**Mục tiêu cải tiến:**  
Giảm tỷ lệ hủy xuống **dưới 7%** và giảm thời gian xử lý đơn trung bình khoảng **35%** thông qua tự động hóa xác nhận + thông báo trạng thái.

---

## 2. Business Problem

Shop đang gặp các vấn đề chính:

1. Quy trình xác nhận đơn còn thủ công → chậm và dễ sai sót
2. Khách hàng không được cập nhật trạng thái kịp thời → tăng hủy và khiếu nại
3. Thiếu quy trình chuẩn (SOP) và tài liệu yêu cầu rõ ràng
4. Không có metric theo dõi hiệu quả từng bước một cách thường xuyên

---

## 3. Current Process (As-Is)

Luồng hiện tại (rút gọn):

1. Khách đặt hàng
2. **Xác nhận đơn thủ công**
3. Kiểm tra tồn kho
4. Đóng gói hàng
5. Bàn giao vận chuyển
6. Giao hàng → Hoàn thành / Hủy

**Điểm nghẽn chính:**
- Bước xác nhận thủ công
- Thiếu thông báo tự động cho khách
- Đồng bộ kho – vận chuyển chưa tốt

*(Xem sơ đồ chi tiết: `02_process/bpmn_as_is.png`)*

---

## 4. Proposed Process (To-Be)

Luồng đề xuất:

1. Khách đặt hàng
2. **Xác nhận đơn tự động** (hệ thống)
3. **Gửi thông báo Zalo/SMS** ngay
4. Đóng gói + cập nhật trạng thái
5. Bàn giao VC + thông báo
6. Giao hàng + Tracking real-time

*(Xem sơ đồ: `02_process/bpmn_to_be.png`)*

---

## 5. Key Findings from Data

| Phân tích | Kết quả chính |
|-----------|---------------|
| Tỷ lệ hủy theo kênh | Shopee cao nhất, Website thấp hơn |
| Thời gian xác nhận | Nhiều đơn mất > 8–12 giờ |
| Ngày giao hàng | Phần lớn đơn thành công giao trong 2–5 ngày |
| Trạng thái nhiều đơn hủy | Tập trung ở giai đoạn chờ xác nhận / đóng gói |

---

## 6. Recommendations & Requirements

### 6.1 Functional Requirements (tóm tắt BRD)
- Hệ thống tự động xác nhận đơn trong < 30 phút (trừ trường hợp ngoại lệ)
- Gửi thông báo Zalo/SMS tại các mốc: Xác nhận – Đóng gói – Bàn giao – Đang giao
- Màn hình Tracking cho khách hàng (xem prototype: `03_prototype/tracking_screens.png`)
- Dashboard nội bộ theo dõi tỷ lệ hủy, thời gian xử lý, theo kênh

### 6.2 Non-functional
- Thông báo gửi thành công > 95%
- Thời gian phản hồi trang tracking < 2 giây
- Dễ sử dụng trên mobile

### 6.3 Expected Impact
| Chỉ số | Hiện tại | Mục tiêu (3–6 tháng) |
|--------|----------|----------------------|
| Tỷ lệ hủy đơn | ~11.4% | < 7% |
| Thời gian xử lý TB | Baseline | -35% |
| Ticket CSKH về tracking | Cao | Giảm 40–50% |

---

## 7. Implementation Roadmap

| Giai đoạn | Thời gian | Công việc chính |
|-----------|-----------|-----------------|
| Phase 1 | 0–45 ngày | Tự động hóa xác nhận + thông báo cơ bản |
| Phase 2 | 45–90 ngày | Prototype Tracking + tích hợp |
| Phase 3 | 90+ ngày | Dashboard vận hành + tối ưu SOP |

---

## 8. Appendix

- Dữ liệu mẫu: `01_data/sample_order_data.xlsx`
- BPMN As-Is / To-Be: `02_process/`
- Prototype Tracking: `03_prototype/tracking_screens.png`
- Dashboard: `03_dashboard/dashboard_preview.png`

---

**Prepared by Tống Anh Đức**  
📧 tongducne07062003@gmail.com  
GitHub: github.com/tongducne07062003-prog
