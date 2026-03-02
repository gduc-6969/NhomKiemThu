# BÁO CÁO KIỂM THỬ (Test Report)

> **Hệ thống:** Website bán hàng online (E-commerce)  
> **Ngày báo cáo:** 28/03/2026  
> **Phiên bản:** v1.0  
> **Người lập:** Lê Minh Đức (Test Lead)

---

## 1. Tổng quan

| Chỉ số | Giá trị |
|--------|---------|
| Tổng số Test Case | 45 |
| Đã thực thi | 43 |
| Chưa thực thi (Blocked) | 2 |
| **Pass** | **33** |
| **Fail** | **10** |
| **Blocked** | **2** |

---

## 2. Kết quả thực thi theo Module

| Module | Tổng TC | Pass | Fail | Blocked | Tỷ lệ Pass |
|--------|---------|------|------|---------|-------------|
| Authentication (Auth) | 15 | 12 | 3 | 0 | 80.0% |
| Product & Cart | 20 | 15 | 4 | 1 | 78.9% |
| Checkout | 10 | 6 | 3 | 1 | 66.7% |
| **Tổng** | **45** | **33** | **10** | **2** | **76.7%** |

---

## 3. Tỷ lệ thực thi test (Test Execution Rate)

Công thức: Execution Rate = (Số TC đã thực thi / Tổng số TC) x 100 = (43 / 45) x 100 = 95.56%

| Chỉ số | Giá trị |
|--------|---------|
| Tỷ lệ thực thi | 95.56% |
| Tỷ lệ Pass | 76.74% (33/43) |
| Tỷ lệ Fail | 23.26% (10/43) |

---

## 4. Chi tiết Test Case Fail

| TC_ID | Tiêu đề | Bug liên quan | Severity |
|-------|---------|---------------|----------|
| TC_AUTH_004 | Đăng ký với email thiếu tên miền | BUG_AUTH_002 | Major |
| TC_AUTH_007 | Đăng nhập thành công (kiểm tra API response) | BUG_AUTH_001 | Critical |
| TC_AUTH_009 | Đăng nhập sai mật khẩu (ngôn ngữ thông báo) | BUG_AUTH_003 | Minor |
| TC_CART_004 | Cập nhật số lượng sản phẩm tăng | BUG_CART_001 | Major |
| TC_CART_009 | Thêm sản phẩm hết hàng vào giỏ | BUG_CART_002 | Major |
| TC_PROD_007 | Xem chi tiết sản phẩm (hình ảnh lỗi) | BUG_PROD_002 | Minor |
| TC_PROD_010 | Lọc giá min > max | BUG_PROD_001 | Major |
| TC_CHECKOUT_002 | Thanh toán không nhập địa chỉ | BUG_CHECKOUT_002 | Major |
| TC_CHECKOUT_005 | Đặt hàng COD (tồn kho không trừ) | BUG_CHECKOUT_001 | Critical |
| TC_CHECKOUT_007 | Xem lịch sử đơn hàng (sắp xếp sai) | BUG_CHECKOUT_003 | Minor |

---

## 5. Chi tiết Test Case Blocked

| TC_ID | Tiêu đề | Lý do Blocked |
|-------|---------|---------------|
| TC_CART_010 | Cập nhật số lượng vượt quá tồn kho | Chức năng kiểm tra tồn kho chưa được triển khai hoàn chỉnh |
| TC_CHECKOUT_009 | Đặt hàng với giỏ hàng trống | Nút "Thanh toán" không hiển thị ở trang giỏ hàng trống, không thể test flow |

---

## 6. Top 5 lỗi nghiêm trọng nhất

| # | Bug ID | Tóm tắt | Severity | Priority |
|---|--------|---------|----------|----------|
| 1 | BUG_CHECKOUT_001 | Đặt hàng thành công nhưng không trừ tồn kho | Critical | High |
| 2 | BUG_AUTH_001 | Mật khẩu hiển thị plaintext trong API response | Critical | High |
| 3 | BUG_CART_001 | Tổng tiền giỏ hàng tính sai khi cập nhật số lượng | Major | High |
| 4 | BUG_CART_002 | Thêm sản phẩm hết hàng vào giỏ không báo lỗi | Major | High |
| 5 | BUG_CHECKOUT_002 | Không validate địa chỉ giao hàng để trống | Major | High |

---

## 7. Nhận xét chất lượng hệ thống

### Điểm mạnh:
- Các chức năng cơ bản (đăng ký, đăng nhập, tìm kiếm, xem sản phẩm) hoạt động ổn định.
- Giao diện người dùng nhìn chung rõ ràng, dễ sử dụng.
- Chức năng đăng xuất, quên mật khẩu hoạt động đúng.
- Bộ lọc danh mục và tìm kiếm cơ bản hoạt động tốt.

### Điểm yếu:
- **Bảo mật:** Mật khẩu bị lộ plaintext trong API response — lỗ hổng nghiêm trọng.
- **Logic nghiệp vụ:** Tồn kho không được trừ khi đặt hàng, dẫn đến dữ liệu không nhất quán.
- **Validation:** Thiếu validation ở nhiều trường (email, địa chỉ giao hàng, tồn kho).
- **Tổng tiền giỏ hàng:** Tính sai khi cập nhật số lượng — ảnh hưởng trực tiếp đến trải nghiệm và doanh thu.
- **Localization:** Một số thông báo lỗi chưa được dịch sang tiếng Việt.

### Đánh giá tổng thể:
Hệ thống còn tồn tại **2 lỗi Critical** và **5 lỗi Major** chưa được xử lý. Các lỗi Critical ảnh hưởng trực tiếp đến bảo mật và tính toàn vẹn dữ liệu của hệ thống.

---

## 8. Quyết định Release

### **NO-RELEASE** (Không cho phép phát hành)

**Lý do:**
1. Còn **2 bug Critical** chưa được xử lý:
   - BUG_CHECKOUT_001: Tồn kho không trừ khi đặt hàng → sai lệch dữ liệu nghiệp vụ
   - BUG_AUTH_001: Mật khẩu plaintext trong API response → lỗ hổng bảo mật nghiêm trọng
2. Còn **5 bug Major** ảnh hưởng đến trải nghiệm người dùng và tính chính xác của hệ thống.
3. Tỷ lệ Pass chỉ đạt **76.7%**, chưa đạt ngưỡng chấp nhận (toi thieu 90%).
4. **2 test case** bị Blocked do chức năng chưa hoàn thiện.

**Khuyến nghị:**
- Fix toàn bộ bug Critical và Major trước khi release.
- Chạy lại vòng Regression Test sau khi fix bug.
- Bổ sung validation cho các trường nhập liệu.
- Kiểm tra lại logic tồn kho và tính toán tổng tiền giỏ hàng.
- Đánh giá lại sau vòng test tiếp theo (Vòng 2).
