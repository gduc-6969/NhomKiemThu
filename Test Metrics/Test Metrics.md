# CHỈ SỐ KIỂM THỬ (Test Metrics)

> **Hệ thống:** Website bán hàng online (E-commerce)  
> **Ngày báo cáo:** 28/03/2026  
> **Phiên bản:** v1.0

---

## 1. Tỷ lệ thực thi test (Test Execution Rate)

Công thức: Test Execution Rate = (Số TC đã thực thi / Tổng số TC) x 100

| Chỉ số | Giá trị |
|--------|---------|
| Tổng số Test Case | 45 |
| Số TC đã thực thi (Pass + Fail) | 43 |
| Số TC chưa thực thi (Blocked) | 2 |
| **Tỷ lệ thực thi** | **95.56%** |

### Chi tiết theo Module:

| Module | Tổng TC | Đã thực thi | Tỷ lệ thực thi |
|--------|---------|-------------|-----------------|
| Authentication | 15 | 15 | 100.00% |
| Product & Cart | 20 | 19 | 95.00% |
| Checkout | 10 | 9 | 90.00% |
| **Tổng** | **45** | **43** | **95.56%** |

---

## 2. Mật độ lỗi theo Module (Defect Density per Module)

Công thức: Defect Density = Số bug phát hiện / Số test case thực thi

| Module | Số Test Case thực thi | Số Bug phát hiện | Mật độ lỗi |
|--------|----------------------|------------------|------------|
| Authentication | 15 | 3 | 0.20 |
| Product & Cart | 19 | 4 | 0.21 |
| Checkout | 9 | 3 | 0.33 |
| **Tổng / Trung bình** | **43** | **10** | **0.23** |

### Nhận xét:
- Module **Checkout** có mật độ lỗi cao nhất (**0.33**) — cần được ưu tiên fix và test lại.
- Module **Authentication** và **Product & Cart** có mật độ lỗi tương đương (~0.20).
- Mật độ lỗi trung bình toàn hệ thống: **0.23 bug/test case**.

---

## 3. Phân bố mức độ nghiêm trọng (Severity Distribution)

| Severity | Số lượng | Tỷ lệ (%) |
|----------|----------|----------|
| Critical | 2 | 20% |
| Major | 5 | 50% |
| Minor | 3 | 30% |
| **Tổng** | **10** | **100%** |

### Phân bố Severity theo Module:

| Module | Critical | Major | Minor | Tổng |
|--------|----------|-------|-------|------|
| Authentication | 1 | 1 | 1 | 3 |
| Product & Cart | 0 | 2 | 1 | 3 |
| Checkout | 1 | 1 | 1 | 3 |
| Product (UI) | 0 | 1 | 0 | 1 |
| **Tổng** | **2** | **5** | **3** | **10** |

### Nhận xét:
- **20% bug là Critical** — tỷ lệ nghiêm trọng, cần xử lý ngay trước khi release.
- **50% bug là Major** — ảnh hưởng lớn đến trải nghiệm người dùng.
- Bug phân bố đều giữa 3 module, không có module nào đặc biệt nhiều lỗi hơn.

---

## 4. Độ bao phủ yêu cầu (Requirement Coverage)

Công thức: Requirement Coverage = (Số Requirement được bao phủ bởi TC / Tổng số Requirement) x 100

| Chỉ số | Giá trị |
|--------|---------|
| Tổng số Requirement (R1–R16) | 16 |
| Số Requirement được bao phủ | 16 |
| **Độ bao phủ** | **100%** |

### Chi tiết bao phủ theo Requirement:

| Requirement | Số TC bao phủ | Pass | Fail |
|:-----------:|:-------------:|:----:|:----:|
| R1 | 2 | 2 | 0 |
| R2 | 3 | 2 | 1 |
| R3 | 2 | 2 | 0 |
| R4 | 2 | 1 | 1 |
| R5 | 3 | 2 | 1 |
| R6 | 2 | 2 | 0 |
| R7 | 4 | 4 | 0 |
| R8 | 4 | 3 | 1 |
| R9 | 2 | 1 | 1 |
| R10 | 4 | 3 | 1 |
| R11 | 4 | 3 | 1 |
| R12 | 2 | 2 | 0 |
| R13 | 2 | 1 | 1 |
| R14 | 3 | 3 | 0 |
| R15 | 3 | 2 | 1 |
| R16 | 2 | 1 | 1 |

### Nhận xét:
- Tất cả 16 yêu cầu đều được bao phủ bởi ít nhất 2 test case (**100% coverage**).
- Có **10 yêu cầu** có ít nhất 1 TC Fail → cần xem xét lại chức năng liên quan.

---

## 5. Tổng hợp chỉ số

| # | Chỉ số (Metric) | Giá trị | Ngưỡng mong đợi | Đánh giá |
|---|-----------------|---------|-----------------|----------|
| 1 | Tỷ lệ thực thi test (Execution Rate) | 95.56% | >= 90% | Dat |
| 2 | Mật độ lỗi trung bình (Avg Defect Density) | 0.23 | <= 0.15 | Chua dat |
| 3 | Tỷ lệ bug Critical | 20% | 0% | Chua dat |
| 4 | Độ bao phủ yêu cầu (Requirement Coverage) | 100% | >= 95% | Dat |
| 5 | Tỷ lệ Pass | 76.74% | >= 90% | Chua dat |

### Kết luận:
- Hệ thống đạt yêu cầu về **tỷ lệ thực thi test** và **độ bao phủ yêu cầu**.
- Tuy nhiên, **mật độ lỗi cao**, **tỷ lệ Pass thấp**, và **còn bug Critical** cho thấy hệ thống chưa đủ chất lượng để release.
- **Khuyến nghị:** Fix toàn bộ bug Critical và Major, sau đó chạy Regression Test vòng 2 trước khi đánh giá lại.
