# BÁO CÁO LỖI (Bug Reports) 🐞

> **Hệ thống:** Website bán hàng online (E-commerce)  
> **Tổng số bug:** 10  
> **Phân bố:** Critical (2) | Major (5) | Minor (3)

---

## BUG_CHECKOUT_001 – Đặt hàng thành công nhưng không trừ tồn kho

| Trường | Nội dung |
|--------|----------|
| **Bug ID** | BUG_CHECKOUT_001 |
| **Tóm tắt (Summary)** | Sau khi đặt hàng thành công, số lượng tồn kho của sản phẩm không bị trừ |
| **Test Case liên quan** | TC_CHECKOUT_005 |
| **Các bước tái hiện** | 1. Đăng nhập vào hệ thống <br> 2. Thêm sản phẩm "Áo thun nam" (tồn kho = 10) vào giỏ, số lượng = 2 <br> 3. Tiến hành thanh toán bằng COD <br> 4. Đặt hàng thành công <br> 5. Quay lại trang chi tiết sản phẩm "Áo thun nam", kiểm tra tồn kho |
| **Kết quả mong đợi (Expected)** | Tồn kho = 8 (10 − 2) |
| **Kết quả thực tế (Actual)** | Tồn kho vẫn = 10, không bị trừ |
| **Mức độ nghiêm trọng (Severity)** | 🔴 **Critical** |
| **Độ ưu tiên (Priority)** | **High** |
| **Môi trường (Environment)** | Chrome 120, Windows 11 |

---

## BUG_AUTH_001 – Mật khẩu hiển thị dạng plaintext trong response API

| Trường | Nội dung |
|--------|----------|
| **Bug ID** | BUG_AUTH_001 |
| **Tóm tắt (Summary)** | Khi đăng nhập, password được trả về dạng plaintext trong response body của API |
| **Test Case liên quan** | TC_AUTH_007 |
| **Các bước tái hiện** | 1. Mở DevTools (F12) → Tab Network <br> 2. Đăng nhập với thông tin hợp lệ <br> 3. Kiểm tra response body của request POST /api/login |
| **Kết quả mong đợi (Expected)** | Response không chứa mật khẩu hoặc chỉ trả về token |
| **Kết quả thực tế (Actual)** | Response chứa trường "password": "Test@1234" dạng plaintext |
| **Mức độ nghiêm trọng (Severity)** | 🔴 **Critical** |
| **Độ ưu tiên (Priority)** | **High** |
| **Môi trường (Environment)** | Chrome 120, Windows 11 |

---

## BUG_CART_001 – Tổng tiền giỏ hàng tính sai khi cập nhật số lượng

| Trường | Nội dung |
|--------|----------|
| **Bug ID** | BUG_CART_001 |
| **Tóm tắt (Summary)** | Tổng tiền giỏ hàng không cập nhật đúng khi thay đổi số lượng sản phẩm |
| **Test Case liên quan** | TC_CART_004 |
| **Các bước tái hiện** | 1. Thêm "Áo thun nam" (200.000đ) vào giỏ, số lượng = 1 <br> 2. Mở trang giỏ hàng <br> 3. Sửa số lượng thành 3 <br> 4. Kiểm tra tổng tiền |
| **Kết quả mong đợi (Expected)** | Tổng tiền = 600.000đ (200.000 × 3) |
| **Kết quả thực tế (Actual)** | Tổng tiền = 200.000đ (vẫn giữ giá trị cũ, không nhân với số lượng mới) |
| **Mức độ nghiêm trọng (Severity)** | 🟠 **Major** |
| **Độ ưu tiên (Priority)** | **High** |
| **Môi trường (Environment)** | Chrome 120, Windows 11 |

---

## BUG_CART_002 – Thêm sản phẩm hết hàng vào giỏ không báo lỗi

| Trường | Nội dung |
|--------|----------|
| **Bug ID** | BUG_CART_002 |
| **Tóm tắt (Summary)** | Hệ thống cho phép thêm sản phẩm đã hết hàng (tồn kho = 0) vào giỏ mà không hiển thị cảnh báo |
| **Test Case liên quan** | TC_CART_009 |
| **Các bước tái hiện** | 1. Tìm sản phẩm "Túi xách X" (tồn kho = 0) <br> 2. Mở trang chi tiết <br> 3. Nhấn "Thêm vào giỏ hàng" |
| **Kết quả mong đợi (Expected)** | Nút "Thêm vào giỏ" bị disable hoặc hiển thị thông báo "Sản phẩm đã hết hàng" |
| **Kết quả thực tế (Actual)** | Sản phẩm được thêm vào giỏ bình thường, không có cảnh báo |
| **Mức độ nghiêm trọng (Severity)** | 🟠 **Major** |
| **Độ ưu tiên (Priority)** | **High** |
| **Môi trường (Environment)** | Chrome 120, Windows 11 |

---

## BUG_CHECKOUT_002 – Không validate trường địa chỉ giao hàng để trống

| Trường | Nội dung |
|--------|----------|
| **Bug ID** | BUG_CHECKOUT_002 |
| **Tóm tắt (Summary)** | Hệ thống cho phép tiến hành thanh toán khi trường địa chỉ giao hàng bị để trống |
| **Test Case liên quan** | TC_CHECKOUT_002 |
| **Các bước tái hiện** | 1. Thêm sản phẩm vào giỏ hàng <br> 2. Nhấn "Thanh toán" <br> 3. Để trống trường "Địa chỉ giao hàng" <br> 4. Nhấn "Tiếp tục" |
| **Kết quả mong đợi (Expected)** | Hiển thị thông báo "Vui lòng nhập địa chỉ giao hàng", không cho tiếp tục |
| **Kết quả thực tế (Actual)** | Hệ thống vẫn cho tiếp tục sang bước chọn phương thức thanh toán |
| **Mức độ nghiêm trọng (Severity)** | 🟠 **Major** |
| **Độ ưu tiên (Priority)** | **High** |
| **Môi trường (Environment)** | Chrome 120, Windows 11 |

---

## BUG_AUTH_002 – Cho phép đăng ký với email sai định dạng trong một số trường hợp

| Trường | Nội dung |
|--------|----------|
| **Bug ID** | BUG_AUTH_002 |
| **Tóm tắt (Summary)** | Hệ thống cho phép đăng ký tài khoản với email thiếu tên miền (vd: user@) |
| **Test Case liên quan** | TC_AUTH_004 |
| **Các bước tái hiện** | 1. Mở trang đăng ký <br> 2. Nhập email: testuser@ <br> 3. Nhập mật khẩu: Test@1234 <br> 4. Nhấn "Đăng ký" |
| **Kết quả mong đợi (Expected)** | Hiển thị thông báo "Email không hợp lệ", không cho đăng ký |
| **Kết quả thực tế (Actual)** | Đăng ký thành công với email "testuser@", không có validation |
| **Mức độ nghiêm trọng (Severity)** | 🟠 **Major** |
| **Độ ưu tiên (Priority)** | **Medium** |
| **Môi trường (Environment)** | Chrome 120, Windows 11 |

---

## BUG_PROD_001 – Bộ lọc giá không xử lý khi giá min > giá max

| Trường | Nội dung |
|--------|----------|
| **Bug ID** | BUG_PROD_001 |
| **Tóm tắt (Summary)** | Khi nhập giá tối thiểu lớn hơn giá tối đa, hệ thống không hiển thị lỗi và trả về kết quả rỗng không rõ ràng |
| **Test Case liên quan** | TC_PROD_010 |
| **Các bước tái hiện** | 1. Mở trang danh sách sản phẩm <br> 2. Nhập giá tối thiểu: 500000 <br> 3. Nhập giá tối đa: 100000 <br> 4. Nhấn "Lọc" |
| **Kết quả mong đợi (Expected)** | Hiển thị thông báo "Giá tối thiểu không được lớn hơn giá tối đa" hoặc tự hoán đổi giá trị |
| **Kết quả thực tế (Actual)** | Hiển thị trang trống không có sản phẩm, không có thông báo giải thích |
| **Mức độ nghiêm trọng (Severity)** | 🟠 **Major** |
| **Độ ưu tiên (Priority)** | **Medium** |
| **Môi trường (Environment)** | Chrome 120, Windows 11 |

---

## BUG_PROD_002 – Hình ảnh sản phẩm không hiển thị placeholder khi load lỗi

| Trường | Nội dung |
|--------|----------|
| **Bug ID** | BUG_PROD_002 |
| **Tóm tắt (Summary)** | Khi hình ảnh sản phẩm không load được, hiển thị icon broken image thay vì placeholder mặc định |
| **Test Case liên quan** | TC_PROD_007 |
| **Các bước tái hiện** | 1. Mở trang chi tiết sản phẩm có hình ảnh URL bị lỗi (404) <br> 2. Quan sát vùng hiển thị hình ảnh |
| **Kết quả mong đợi (Expected)** | Hiển thị hình placeholder mặc định (ảnh "No Image Available") |
| **Kết quả thực tế (Actual)** | Hiển thị icon broken image (hình vỡ) của trình duyệt, giao diện bị xấu |
| **Mức độ nghiêm trọng (Severity)** | 🟡 **Minor** |
| **Độ ưu tiên (Priority)** | **Low** |
| **Môi trường (Environment)** | Chrome 120, Windows 11 |

---

## BUG_AUTH_003 – Thông báo lỗi đăng nhập hiển thị bằng tiếng Anh

| Trường | Nội dung |
|--------|----------|
| **Bug ID** | BUG_AUTH_003 |
| **Tóm tắt (Summary)** | Khi đăng nhập sai mật khẩu, thông báo lỗi hiển thị bằng tiếng Anh thay vì tiếng Việt |
| **Test Case liên quan** | TC_AUTH_009 |
| **Các bước tái hiện** | 1. Mở trang đăng nhập <br> 2. Nhập email hợp lệ <br> 3. Nhập mật khẩu sai <br> 4. Nhấn "Đăng nhập" |
| **Kết quả mong đợi (Expected)** | Hiển thị thông báo "Sai email hoặc mật khẩu" (tiếng Việt) |
| **Kết quả thực tế (Actual)** | Hiển thị "Invalid email or password" (tiếng Anh) |
| **Mức độ nghiêm trọng (Severity)** | 🟡 **Minor** |
| **Độ ưu tiên (Priority)** | **Low** |
| **Môi trường (Environment)** | Chrome 120, Windows 11 |

---

## BUG_CHECKOUT_003 – Lịch sử đơn hàng không sắp xếp theo thời gian mới nhất

| Trường | Nội dung |
|--------|----------|
| **Bug ID** | BUG_CHECKOUT_003 |
| **Tóm tắt (Summary)** | Danh sách lịch sử đơn hàng hiển thị không theo thứ tự thời gian |
| **Test Case liên quan** | TC_CHECKOUT_007 |
| **Các bước tái hiện** | 1. Đặt 3 đơn hàng vào các thời điểm khác nhau <br> 2. Mở trang "Lịch sử đơn hàng" <br> 3. Kiểm tra thứ tự hiển thị |
| **Kết quả mong đợi (Expected)** | Đơn hàng mới nhất hiển thị ở trên cùng (sắp xếp giảm dần theo thời gian) |
| **Kết quả thực tế (Actual)** | Đơn hàng hiển thị theo thứ tự ngẫu nhiên, không theo thời gian |
| **Mức độ nghiêm trọng (Severity)** | 🟡 **Minor** |
| **Độ ưu tiên (Priority)** | **Low** |
| **Môi trường (Environment)** | Chrome 120, Windows 11 |

---

## TỔNG KẾT BUG

| Severity | Số lượng | Bug IDs |
|----------|----------|---------|
| 🔴 Critical | 2 | BUG_CHECKOUT_001, BUG_AUTH_001 |
| 🟠 Major | 5 | BUG_CART_001, BUG_CART_002, BUG_CHECKOUT_002, BUG_AUTH_002, BUG_PROD_001 |
| 🟡 Minor | 3 | BUG_PROD_002, BUG_AUTH_003, BUG_CHECKOUT_003 |
| **Tổng** | **10** | |

| Module | Số bug |
|--------|--------|
| Authentication | 3 (BUG_AUTH_001, BUG_AUTH_002, BUG_AUTH_003) |
| Product & Cart | 3 (BUG_CART_001, BUG_CART_002, BUG_PROD_001) |
| Checkout | 3 (BUG_CHECKOUT_001, BUG_CHECKOUT_002, BUG_CHECKOUT_003) |
| Product (UI) | 1 (BUG_PROD_002) |    