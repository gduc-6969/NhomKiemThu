# MA TRẬN TRUY VẾT YÊU CẦU (Requirement Traceability Matrix – RTM)

> **Hệ thống:** Website bán hàng online (E-commerce)  
> **Tổng số yêu cầu:** 16  
> **Độ bao phủ (Coverage):** 100% (16/16 yêu cầu được bao phủ)

---

## Bảng RTM

| Requirement ID | Mô tả yêu cầu | Test Case ID | Trạng thái |
|:-:|---|---|:-:|
| R1 | Người dùng đăng ký bằng email hợp lệ | TC_AUTH_001, TC_AUTH_002 | Covered |
| R2 | Không cho đăng ký khi email sai định dạng | TC_AUTH_003, TC_AUTH_004, TC_AUTH_014 | Covered |
| R3 | Mật khẩu tối thiểu 8 ký tự | TC_AUTH_005, TC_AUTH_006 | Covered |
| R4 | Đăng nhập thành công với thông tin hợp lệ | TC_AUTH_007, TC_AUTH_008 | Covered |
| R5 | Đăng nhập thất bại khi sai mật khẩu | TC_AUTH_009, TC_AUTH_010, TC_AUTH_015 | Covered |
| R6 | Quên mật khẩu gửi email đặt lại | TC_AUTH_011, TC_AUTH_012 | Covered |
| R7 | Tìm kiếm hiển thị đúng kết quả | TC_PROD_001, TC_PROD_002, TC_PROD_003, TC_PROD_009 | Covered |
| R8 | Lọc theo giá hoạt động đúng | TC_PROD_004, TC_PROD_005, TC_PROD_006, TC_PROD_010 | Covered |
| R9 | Xem chi tiết sản phẩm | TC_PROD_007, TC_PROD_008 | Covered |
| R10 | Thêm sản phẩm vào giỏ thành công | TC_CART_001, TC_CART_002, TC_CART_003, TC_CART_009 | Covered |
| R11 | Cập nhật số lượng trong giỏ | TC_CART_004, TC_CART_005, TC_CART_006, TC_CART_010 | Covered |
| R12 | Xoá sản phẩm khỏi giỏ | TC_CART_007, TC_CART_008 | Covered |
| R13 | Thanh toán bắt buộc nhập địa chỉ | TC_CHECKOUT_001, TC_CHECKOUT_002 | Covered |
| R14 | Chọn phương thức thanh toán | TC_CHECKOUT_003, TC_CHECKOUT_004, TC_CHECKOUT_010 | Covered |
| R15 | Đặt hàng thành công | TC_CHECKOUT_005, TC_CHECKOUT_006, TC_CHECKOUT_009 | Covered |
| R16 | Lưu lịch sử đơn hàng | TC_CHECKOUT_007, TC_CHECKOUT_008 | Covered |

---

## Thống kê bao phủ

| Chỉ số | Giá trị |
|--------|---------|
| Tổng số yêu cầu | 16 |
| Số yêu cầu được bao phủ | 16 |
| Số yêu cầu chưa bao phủ | 0 |
| **Tỷ lệ bao phủ (Coverage)** | **100%** |
| Tổng số Test Case | 45 |
| Trung bình TC / Requirement | 2.81 |
| Requirement có nhiều TC nhất | R7, R8, R10, R11 (4 TC mỗi yêu cầu) |
| Requirement có ít TC nhất | R1, R3, R4, R6, R9, R12, R13, R16 (2 TC mỗi yêu cầu) |

---

## Ghi chú

- Mỗi yêu cầu (Requirement) đều được map với tối thiểu **2 test case** (đạt yêu cầu).
- Các yêu cầu quan trọng (R7, R8, R10, R11) được bao phủ bởi **4 test case** bao gồm cả positive, negative và boundary.
- Tỷ lệ bao phủ **100%** đạt yêu cầu toi thieu 90%.
- TC_AUTH_013 (Đăng xuất) không map trực tiếp với R1–R16 nhưng thuộc chức năng Authentication trong phạm vi kiểm thử.
