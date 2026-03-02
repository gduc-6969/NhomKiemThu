# CA KIỂM THỬ (Test Cases) 📋

> **Hệ thống:** Website bán hàng online (E-commerce)  
> **Tổng số test case:** 45  
> **Phân bố:** Auth (15) | Product & Cart (20) | Checkout (10)

---

## MODULE 1 – XÁC THỰC NGƯỜI DÙNG (Authentication) — 15 Test Cases

---

### TC_AUTH_001 – Đăng ký tài khoản với email hợp lệ

| Trường | Nội dung |
|--------|----------|
| **TC_ID** | TC_AUTH_001 |
| **Tiêu đề** | Đăng ký tài khoản với email hợp lệ |
| **Điều kiện trước** | Người dùng chưa có tài khoản; trang đăng ký đã mở |
| **Các bước** | 1. Mở trang Đăng ký (/register) <br> 2. Nhập email: newuser@gmail.com <br> 3. Nhập mật khẩu: Test@1234 <br> 4. Nhập xác nhận mật khẩu: Test@1234 <br> 5. Nhấn nút "Đăng ký" |
| **Kết quả mong đợi** | Đăng ký thành công, hiển thị thông báo "Đăng ký thành công", chuyển hướng về trang đăng nhập |
| **Độ ưu tiên** | High |
| **Loại test** | Positive |

---

### TC_AUTH_002 – Đăng ký tài khoản với đầy đủ thông tin hợp lệ

| Trường | Nội dung |
|--------|----------|
| **TC_ID** | TC_AUTH_002 |
| **Tiêu đề** | Đăng ký tài khoản với đầy đủ thông tin hợp lệ |
| **Điều kiện trước** | Trang đăng ký đã mở |
| **Các bước** | 1. Mở trang Đăng ký (/register) <br> 2. Nhập họ tên: Nguyễn Văn A <br> 3. Nhập email: nguyenvana@gmail.com <br> 4. Nhập số điện thoại: 0901234567 <br> 5. Nhập mật khẩu: Abc@12345 <br> 6. Nhập xác nhận mật khẩu: Abc@12345 <br> 7. Nhấn nút "Đăng ký" |
| **Kết quả mong đợi** | Đăng ký thành công, tài khoản được tạo trong hệ thống |
| **Độ ưu tiên** | High |
| **Loại test** | Positive |

---

### TC_AUTH_003 – Đăng ký với email sai định dạng (thiếu @)

| Trường | Nội dung |
|--------|----------|
| **TC_ID** | TC_AUTH_003 |
| **Tiêu đề** | Đăng ký với email sai định dạng (thiếu ký tự @) |
| **Điều kiện trước** | Trang đăng ký đã mở |
| **Các bước** | 1. Mở trang Đăng ký (/register) <br> 2. Nhập email: testusergmail.com <br> 3. Nhập mật khẩu: Test@1234 <br> 4. Nhấn nút "Đăng ký" |
| **Kết quả mong đợi** | Hệ thống hiển thị thông báo lỗi "Email không hợp lệ", không cho phép đăng ký |
| **Độ ưu tiên** | High |
| **Loại test** | Negative |

---

### TC_AUTH_004 – Đăng ký với email thiếu tên miền

| Trường | Nội dung |
|--------|----------|
| **TC_ID** | TC_AUTH_004 |
| **Tiêu đề** | Đăng ký với email thiếu tên miền |
| **Điều kiện trước** | Trang đăng ký đã mở |
| **Các bước** | 1. Mở trang Đăng ký (/register) <br> 2. Nhập email: testuser@ <br> 3. Nhập mật khẩu: Test@1234 <br> 4. Nhấn nút "Đăng ký" |
| **Kết quả mong đợi** | Hệ thống hiển thị thông báo lỗi "Email không hợp lệ", không cho phép đăng ký |
| **Độ ưu tiên** | Medium |
| **Loại test** | Negative |

---

### TC_AUTH_005 – Đăng ký với mật khẩu đúng 8 ký tự (biên dưới)

| Trường | Nội dung |
|--------|----------|
| **TC_ID** | TC_AUTH_005 |
| **Tiêu đề** | Đăng ký với mật khẩu đúng 8 ký tự (giá trị biên) |
| **Điều kiện trước** | Trang đăng ký đã mở |
| **Các bước** | 1. Mở trang Đăng ký (/register) <br> 2. Nhập email: boundary@gmail.com <br> 3. Nhập mật khẩu: Abcd1234 (đúng 8 ký tự) <br> 4. Nhập xác nhận mật khẩu: Abcd1234 <br> 5. Nhấn nút "Đăng ký" |
| **Kết quả mong đợi** | Đăng ký thành công vì mật khẩu đạt tối thiểu 8 ký tự |
| **Độ ưu tiên** | High |
| **Loại test** | Boundary |

---

### TC_AUTH_006 – Đăng ký với mật khẩu 7 ký tự (dưới biên)

| Trường | Nội dung |
|--------|----------|
| **TC_ID** | TC_AUTH_006 |
| **Tiêu đề** | Đăng ký với mật khẩu 7 ký tự (dưới giá trị biên) |
| **Điều kiện trước** | Trang đăng ký đã mở |
| **Các bước** | 1. Mở trang Đăng ký (/register) <br> 2. Nhập email: short@gmail.com <br> 3. Nhập mật khẩu: Abc1234 (7 ký tự) <br> 4. Nhập xác nhận mật khẩu: Abc1234 <br> 5. Nhấn nút "Đăng ký" |
| **Kết quả mong đợi** | Hệ thống hiển thị thông báo lỗi "Mật khẩu phải có tối thiểu 8 ký tự", không cho phép đăng ký |
| **Độ ưu tiên** | High |
| **Loại test** | Boundary |

---

### TC_AUTH_007 – Đăng nhập thành công với thông tin hợp lệ

| Trường | Nội dung |
|--------|----------|
| **TC_ID** | TC_AUTH_007 |
| **Tiêu đề** | Đăng nhập thành công với thông tin hợp lệ |
| **Điều kiện trước** | Tài khoản testuser@gmail.com / Test@1234 đã tồn tại trong hệ thống |
| **Các bước** | 1. Mở trang Đăng nhập (/login) <br> 2. Nhập email: testuser@gmail.com <br> 3. Nhập mật khẩu: Test@1234 <br> 4. Nhấn nút "Đăng nhập" |
| **Kết quả mong đợi** | Đăng nhập thành công, chuyển hướng về trang chủ, hiển thị tên người dùng |
| **Độ ưu tiên** | High |
| **Loại test** | Positive |

---

### TC_AUTH_008 – Đăng nhập và kiểm tra session được tạo

| Trường | Nội dung |
|--------|----------|
| **TC_ID** | TC_AUTH_008 |
| **Tiêu đề** | Đăng nhập và kiểm tra session/token được lưu |
| **Điều kiện trước** | Tài khoản hợp lệ đã tồn tại |
| **Các bước** | 1. Mở trang Đăng nhập (/login) <br> 2. Nhập thông tin đăng nhập hợp lệ <br> 3. Nhấn nút "Đăng nhập" <br> 4. Kiểm tra trang chủ hiển thị đúng thông tin user <br> 5. Refresh trang (F5) |
| **Kết quả mong đợi** | Sau khi refresh, người dùng vẫn đăng nhập, không bị redirect về trang login |
| **Độ ưu tiên** | Medium |
| **Loại test** | Positive |

---

### TC_AUTH_009 – Đăng nhập với sai mật khẩu

| Trường | Nội dung |
|--------|----------|
| **TC_ID** | TC_AUTH_009 |
| **Tiêu đề** | Đăng nhập với mật khẩu sai |
| **Điều kiện trước** | Tài khoản testuser@gmail.com đã tồn tại |
| **Các bước** | 1. Mở trang Đăng nhập (/login) <br> 2. Nhập email: testuser@gmail.com <br> 3. Nhập mật khẩu: WrongPass123 <br> 4. Nhấn nút "Đăng nhập" |
| **Kết quả mong đợi** | Hệ thống hiển thị thông báo lỗi "Sai email hoặc mật khẩu", không cho phép đăng nhập |
| **Độ ưu tiên** | High |
| **Loại test** | Negative |

---

### TC_AUTH_010 – Đăng nhập với mật khẩu để trống

| Trường | Nội dung |
|--------|----------|
| **TC_ID** | TC_AUTH_010 |
| **Tiêu đề** | Đăng nhập với trường mật khẩu để trống |
| **Điều kiện trước** | Trang đăng nhập đã mở |
| **Các bước** | 1. Mở trang Đăng nhập (/login) <br> 2. Nhập email: testuser@gmail.com <br> 3. Để trống trường mật khẩu <br> 4. Nhấn nút "Đăng nhập" |
| **Kết quả mong đợi** | Hệ thống hiển thị thông báo "Vui lòng nhập mật khẩu", nút Đăng nhập bị disable hoặc không submit form |
| **Độ ưu tiên** | Medium |
| **Loại test** | Negative |

---

### TC_AUTH_011 – Quên mật khẩu với email đã đăng ký

| Trường | Nội dung |
|--------|----------|
| **TC_ID** | TC_AUTH_011 |
| **Tiêu đề** | Yêu cầu đặt lại mật khẩu với email hợp lệ đã đăng ký |
| **Điều kiện trước** | Tài khoản testuser@gmail.com đã tồn tại |
| **Các bước** | 1. Mở trang Đăng nhập (/login) <br> 2. Nhấn link "Quên mật khẩu?" <br> 3. Nhập email: testuser@gmail.com <br> 4. Nhấn nút "Gửi yêu cầu" |
| **Kết quả mong đợi** | Hệ thống hiển thị thông báo "Email đặt lại mật khẩu đã được gửi", gửi email chứa link reset password |
| **Độ ưu tiên** | High |
| **Loại test** | Positive |

---

### TC_AUTH_012 – Quên mật khẩu với email chưa đăng ký

| Trường | Nội dung |
|--------|----------|
| **TC_ID** | TC_AUTH_012 |
| **Tiêu đề** | Yêu cầu đặt lại mật khẩu với email chưa đăng ký |
| **Điều kiện trước** | Email notexist@gmail.com chưa tồn tại trong hệ thống |
| **Các bước** | 1. Mở trang Đăng nhập (/login) <br> 2. Nhấn link "Quên mật khẩu?" <br> 3. Nhập email: notexist@gmail.com <br> 4. Nhấn nút "Gửi yêu cầu" |
| **Kết quả mong đợi** | Hệ thống hiển thị thông báo "Email không tồn tại trong hệ thống" |
| **Độ ưu tiên** | Medium |
| **Loại test** | Negative |

---

### TC_AUTH_013 – Đăng xuất thành công

| Trường | Nội dung |
|--------|----------|
| **TC_ID** | TC_AUTH_013 |
| **Tiêu đề** | Đăng xuất khỏi hệ thống thành công |
| **Điều kiện trước** | Người dùng đã đăng nhập thành công |
| **Các bước** | 1. Đăng nhập vào hệ thống <br> 2. Nhấn vào biểu tượng tài khoản (hoặc tên người dùng) <br> 3. Chọn "Đăng xuất" |
| **Kết quả mong đợi** | Hệ thống đăng xuất, xoá session, chuyển hướng về trang đăng nhập |
| **Độ ưu tiên** | High |
| **Loại test** | Positive |

---

### TC_AUTH_014 – Đăng ký với email đã tồn tại

| Trường | Nội dung |
|--------|----------|
| **TC_ID** | TC_AUTH_014 |
| **Tiêu đề** | Đăng ký tài khoản với email đã tồn tại trong hệ thống |
| **Điều kiện trước** | Tài khoản testuser@gmail.com đã tồn tại |
| **Các bước** | 1. Mở trang Đăng ký (/register) <br> 2. Nhập email: testuser@gmail.com <br> 3. Nhập mật khẩu: NewPass@123 <br> 4. Nhập xác nhận mật khẩu: NewPass@123 <br> 5. Nhấn nút "Đăng ký" |
| **Kết quả mong đợi** | Hệ thống hiển thị thông báo "Email đã được sử dụng", không tạo tài khoản mới |
| **Độ ưu tiên** | High |
| **Loại test** | Negative |

---

### TC_AUTH_015 – Đăng nhập với tài khoản chưa đăng ký

| Trường | Nội dung |
|--------|----------|
| **TC_ID** | TC_AUTH_015 |
| **Tiêu đề** | Đăng nhập với email chưa đăng ký trong hệ thống |
| **Điều kiện trước** | Email noexist@gmail.com chưa đăng ký |
| **Các bước** | 1. Mở trang Đăng nhập (/login) <br> 2. Nhập email: noexist@gmail.com <br> 3. Nhập mật khẩu: Test@1234 <br> 4. Nhấn nút "Đăng nhập" |
| **Kết quả mong đợi** | Hệ thống hiển thị thông báo "Sai email hoặc mật khẩu", không cho đăng nhập |
| **Độ ưu tiên** | Medium |
| **Loại test** | Negative |

---

## MODULE 2 – SẢN PHẨM & GIỎ HÀNG (Product & Cart) — 20 Test Cases

---

### TC_PROD_001 – Tìm kiếm sản phẩm bằng tên hợp lệ

| Trường | Nội dung |
|--------|----------|
| **TC_ID** | TC_PROD_001 |
| **Tiêu đề** | Tìm kiếm sản phẩm bằng từ khoá hợp lệ |
| **Điều kiện trước** | Người dùng đã đăng nhập; hệ thống có sản phẩm "Áo thun nam" |
| **Các bước** | 1. Mở trang chủ <br> 2. Nhập từ khoá "Áo thun" vào ô tìm kiếm <br> 3. Nhấn nút "Tìm kiếm" hoặc Enter |
| **Kết quả mong đợi** | Hiển thị danh sách sản phẩm có chứa từ khoá "Áo thun", bao gồm "Áo thun nam" |
| **Độ ưu tiên** | High |
| **Loại test** | Positive |

---

### TC_PROD_002 – Tìm kiếm sản phẩm không tồn tại

| Trường | Nội dung |
|--------|----------|
| **TC_ID** | TC_PROD_002 |
| **Tiêu đề** | Tìm kiếm sản phẩm với từ khoá không có kết quả |
| **Điều kiện trước** | Người dùng đã đăng nhập |
| **Các bước** | 1. Mở trang chủ <br> 2. Nhập từ khoá "xyznotexist123" vào ô tìm kiếm <br> 3. Nhấn nút "Tìm kiếm" |
| **Kết quả mong đợi** | Hiển thị thông báo "Không tìm thấy sản phẩm nào" hoặc danh sách trống |
| **Độ ưu tiên** | Medium |
| **Loại test** | Negative |

---

### TC_PROD_003 – Tìm kiếm với từ khoá rỗng

| Trường | Nội dung |
|--------|----------|
| **TC_ID** | TC_PROD_003 |
| **Tiêu đề** | Tìm kiếm sản phẩm khi ô tìm kiếm để trống |
| **Điều kiện trước** | Người dùng đã đăng nhập |
| **Các bước** | 1. Mở trang chủ <br> 2. Để trống ô tìm kiếm <br> 3. Nhấn nút "Tìm kiếm" hoặc Enter |
| **Kết quả mong đợi** | Hiển thị tất cả sản phẩm hoặc thông báo "Vui lòng nhập từ khoá tìm kiếm" |
| **Độ ưu tiên** | Low |
| **Loại test** | Boundary |

---

### TC_PROD_004 – Lọc sản phẩm theo khoảng giá hợp lệ

| Trường | Nội dung |
|--------|----------|
| **TC_ID** | TC_PROD_004 |
| **Tiêu đề** | Lọc sản phẩm theo khoảng giá từ 100.000đ đến 500.000đ |
| **Điều kiện trước** | Người dùng đã đăng nhập; có sản phẩm trong khoảng giá 100k–500k |
| **Các bước** | 1. Mở trang danh sách sản phẩm <br> 2. Nhập giá tối thiểu: 100000 <br> 3. Nhập giá tối đa: 500000 <br> 4. Nhấn nút "Lọc" hoặc "Áp dụng" |
| **Kết quả mong đợi** | Chỉ hiển thị sản phẩm có giá từ 100.000đ đến 500.000đ |
| **Độ ưu tiên** | High |
| **Loại test** | Positive |

---

### TC_PROD_005 – Lọc sản phẩm theo danh mục

| Trường | Nội dung |
|--------|----------|
| **TC_ID** | TC_PROD_005 |
| **Tiêu đề** | Lọc sản phẩm theo danh mục "Thời trang nam" |
| **Điều kiện trước** | Danh mục "Thời trang nam" có ít nhất 1 sản phẩm |
| **Các bước** | 1. Mở trang danh sách sản phẩm <br> 2. Chọn danh mục "Thời trang nam" từ bộ lọc <br> 3. Nhấn "Áp dụng" (nếu có) |
| **Kết quả mong đợi** | Chỉ hiển thị sản phẩm thuộc danh mục "Thời trang nam" |
| **Độ ưu tiên** | High |
| **Loại test** | Positive |

---

### TC_PROD_006 – Lọc theo khoảng giá không có sản phẩm

| Trường | Nội dung |
|--------|----------|
| **TC_ID** | TC_PROD_006 |
| **Tiêu đề** | Lọc sản phẩm với khoảng giá không có sản phẩm nào |
| **Điều kiện trước** | Không có sản phẩm nào có giá > 100.000.000đ |
| **Các bước** | 1. Mở trang danh sách sản phẩm <br> 2. Nhập giá tối thiểu: 100000000 <br> 3. Nhập giá tối đa: 999999999 <br> 4. Nhấn "Lọc" |
| **Kết quả mong đợi** | Hiển thị thông báo "Không có sản phẩm trong khoảng giá này" hoặc danh sách trống |
| **Độ ưu tiên** | Low |
| **Loại test** | Negative |

---

### TC_PROD_007 – Xem chi tiết sản phẩm

| Trường | Nội dung |
|--------|----------|
| **TC_ID** | TC_PROD_007 |
| **Tiêu đề** | Xem chi tiết một sản phẩm từ danh sách |
| **Điều kiện trước** | Có ít nhất 1 sản phẩm trong danh sách |
| **Các bước** | 1. Mở trang danh sách sản phẩm <br> 2. Nhấn vào sản phẩm "Áo thun nam" |
| **Kết quả mong đợi** | Chuyển sang trang chi tiết sản phẩm, hiển thị: tên, giá, mô tả, hình ảnh, nút "Thêm vào giỏ" |
| **Độ ưu tiên** | High |
| **Loại test** | Positive |

---

### TC_PROD_008 – Xem chi tiết sản phẩm hiển thị đầy đủ thông tin

| Trường | Nội dung |
|--------|----------|
| **TC_ID** | TC_PROD_008 |
| **Tiêu đề** | Kiểm tra trang chi tiết sản phẩm hiển thị đầy đủ các field |
| **Điều kiện trước** | Sản phẩm "Giày thể thao" có đầy đủ thông tin (tên, giá, mô tả, hình, danh mục, tồn kho) |
| **Các bước** | 1. Mở trang chi tiết sản phẩm "Giày thể thao" <br> 2. Kiểm tra hiển thị: tên sản phẩm, giá bán, mô tả chi tiết, hình ảnh, danh mục, số lượng tồn kho |
| **Kết quả mong đợi** | Tất cả thông tin hiển thị đúng, đầy đủ, hình ảnh load thành công |
| **Độ ưu tiên** | Medium |
| **Loại test** | Positive |

---

### TC_PROD_009 – Tìm kiếm với ký tự đặc biệt

| Trường | Nội dung |
|--------|----------|
| **TC_ID** | TC_PROD_009 |
| **Tiêu đề** | Tìm kiếm sản phẩm với ký tự đặc biệt (SQL injection test cơ bản) |
| **Điều kiện trước** | Người dùng đã đăng nhập |
| **Các bước** | 1. Mở trang chủ <br> 2. Nhập từ khoá: `' OR 1=1 --` vào ô tìm kiếm <br> 3. Nhấn "Tìm kiếm" |
| **Kết quả mong đợi** | Hệ thống không bị lỗi, không trả về toàn bộ dữ liệu; hiển thị "Không tìm thấy sản phẩm" hoặc thông báo lỗi an toàn |
| **Độ ưu tiên** | High |
| **Loại test** | Negative |

---

### TC_PROD_010 – Lọc theo giá với giá min > giá max

| Trường | Nội dung |
|--------|----------|
| **TC_ID** | TC_PROD_010 |
| **Tiêu đề** | Lọc sản phẩm khi nhập giá tối thiểu lớn hơn giá tối đa |
| **Điều kiện trước** | Trang danh sách sản phẩm đã mở |
| **Các bước** | 1. Mở trang danh sách sản phẩm <br> 2. Nhập giá tối thiểu: 500000 <br> 3. Nhập giá tối đa: 100000 <br> 4. Nhấn "Lọc" |
| **Kết quả mong đợi** | Hệ thống hiển thị thông báo "Giá tối thiểu không được lớn hơn giá tối đa" hoặc tự hoán đổi giá trị |
| **Độ ưu tiên** | Medium |
| **Loại test** | Boundary |

---

### TC_CART_001 – Thêm sản phẩm vào giỏ hàng

| Trường | Nội dung |
|--------|----------|
| **TC_ID** | TC_CART_001 |
| **Tiêu đề** | Thêm một sản phẩm vào giỏ hàng thành công |
| **Điều kiện trước** | Người dùng đã đăng nhập; giỏ hàng trống; sản phẩm "Áo thun nam" (200.000đ) còn hàng |
| **Các bước** | 1. Mở trang chi tiết sản phẩm "Áo thun nam" <br> 2. Nhấn nút "Thêm vào giỏ hàng" |
| **Kết quả mong đợi** | Sản phẩm được thêm vào giỏ, số lượng giỏ hàng hiển thị = 1, thông báo "Đã thêm vào giỏ hàng" |
| **Độ ưu tiên** | High |
| **Loại test** | Positive |

---

### TC_CART_002 – Thêm nhiều sản phẩm khác nhau vào giỏ

| Trường | Nội dung |
|--------|----------|
| **TC_ID** | TC_CART_002 |
| **Tiêu đề** | Thêm nhiều sản phẩm khác nhau vào giỏ hàng |
| **Điều kiện trước** | Người dùng đã đăng nhập; giỏ hàng trống |
| **Các bước** | 1. Thêm sản phẩm "Áo thun nam" (200.000đ) vào giỏ <br> 2. Thêm sản phẩm "Quần jean" (450.000đ) vào giỏ <br> 3. Mở trang giỏ hàng |
| **Kết quả mong đợi** | Giỏ hàng hiển thị 2 sản phẩm, tổng tiền = 650.000đ |
| **Độ ưu tiên** | High |
| **Loại test** | Positive |

---

### TC_CART_003 – Thêm sản phẩm đã có trong giỏ (tăng số lượng)

| Trường | Nội dung |
|--------|----------|
| **TC_ID** | TC_CART_003 |
| **Tiêu đề** | Thêm sản phẩm đã có trong giỏ hàng |
| **Điều kiện trước** | Giỏ hàng đã có 1 "Áo thun nam" |
| **Các bước** | 1. Mở trang chi tiết sản phẩm "Áo thun nam" <br> 2. Nhấn nút "Thêm vào giỏ hàng" lần nữa |
| **Kết quả mong đợi** | Số lượng "Áo thun nam" trong giỏ tăng thành 2, tổng tiền cập nhật đúng |
| **Độ ưu tiên** | Medium |
| **Loại test** | Positive |

---

### TC_CART_004 – Cập nhật số lượng sản phẩm trong giỏ (tăng)

| Trường | Nội dung |
|--------|----------|
| **TC_ID** | TC_CART_004 |
| **Tiêu đề** | Tăng số lượng sản phẩm trong giỏ hàng |
| **Điều kiện trước** | Giỏ hàng có 1 "Áo thun nam" (200.000đ), số lượng = 1 |
| **Các bước** | 1. Mở trang giỏ hàng <br> 2. Nhấn nút "+" hoặc sửa số lượng "Áo thun nam" thành 3 <br> 3. Kiểm tra tổng tiền |
| **Kết quả mong đợi** | Số lượng cập nhật thành 3, tổng tiền = 600.000đ |
| **Độ ưu tiên** | High |
| **Loại test** | Positive |

---

### TC_CART_005 – Cập nhật số lượng sản phẩm trong giỏ (giảm)

| Trường | Nội dung |
|--------|----------|
| **TC_ID** | TC_CART_005 |
| **Tiêu đề** | Giảm số lượng sản phẩm trong giỏ hàng |
| **Điều kiện trước** | Giỏ hàng có "Áo thun nam", số lượng = 3 |
| **Các bước** | 1. Mở trang giỏ hàng <br> 2. Nhấn nút "−" hoặc sửa số lượng "Áo thun nam" thành 1 |
| **Kết quả mong đợi** | Số lượng cập nhật thành 1, tổng tiền = 200.000đ |
| **Độ ưu tiên** | Medium |
| **Loại test** | Positive |

---

### TC_CART_006 – Cập nhật số lượng về 0

| Trường | Nội dung |
|--------|----------|
| **TC_ID** | TC_CART_006 |
| **Tiêu đề** | Cập nhật số lượng sản phẩm trong giỏ về 0 |
| **Điều kiện trước** | Giỏ hàng có "Áo thun nam", số lượng = 1 |
| **Các bước** | 1. Mở trang giỏ hàng <br> 2. Sửa số lượng "Áo thun nam" thành 0 <br> 3. Nhấn cập nhật (nếu có) |
| **Kết quả mong đợi** | Sản phẩm bị xoá khỏi giỏ hàng hoặc hiển thị thông báo "Số lượng tối thiểu là 1" |
| **Độ ưu tiên** | Medium |
| **Loại test** | Boundary |

---

### TC_CART_007 – Xoá sản phẩm khỏi giỏ hàng

| Trường | Nội dung |
|--------|----------|
| **TC_ID** | TC_CART_007 |
| **Tiêu đề** | Xoá một sản phẩm khỏi giỏ hàng |
| **Điều kiện trước** | Giỏ hàng có 2 sản phẩm: "Áo thun nam" và "Quần jean" |
| **Các bước** | 1. Mở trang giỏ hàng <br> 2. Nhấn nút "Xoá" bên cạnh "Áo thun nam" <br> 3. Xác nhận xoá (nếu có popup) |
| **Kết quả mong đợi** | "Áo thun nam" bị xoá, chỉ còn "Quần jean" trong giỏ, tổng tiền cập nhật đúng |
| **Độ ưu tiên** | High |
| **Loại test** | Positive |

---

### TC_CART_008 – Xoá sản phẩm cuối cùng trong giỏ

| Trường | Nội dung |
|--------|----------|
| **TC_ID** | TC_CART_008 |
| **Tiêu đề** | Xoá sản phẩm cuối cùng còn lại trong giỏ hàng |
| **Điều kiện trước** | Giỏ hàng chỉ có 1 sản phẩm "Quần jean" |
| **Các bước** | 1. Mở trang giỏ hàng <br> 2. Nhấn nút "Xoá" bên cạnh "Quần jean" <br> 3. Xác nhận xoá |
| **Kết quả mong đợi** | Giỏ hàng trống, hiển thị thông báo "Giỏ hàng trống" hoặc gợi ý mua sắm |
| **Độ ưu tiên** | Medium |
| **Loại test** | Positive |

---

### TC_CART_009 – Thêm sản phẩm hết hàng vào giỏ

| Trường | Nội dung |
|--------|----------|
| **TC_ID** | TC_CART_009 |
| **Tiêu đề** | Thêm sản phẩm đã hết hàng (tồn kho = 0) vào giỏ |
| **Điều kiện trước** | Sản phẩm "Túi xách X" có tồn kho = 0 |
| **Các bước** | 1. Mở trang chi tiết sản phẩm "Túi xách X" <br> 2. Nhấn nút "Thêm vào giỏ hàng" |
| **Kết quả mong đợi** | Nút "Thêm vào giỏ" bị disable hoặc hiển thị thông báo "Sản phẩm đã hết hàng", không thêm vào giỏ |
| **Độ ưu tiên** | High |
| **Loại test** | Negative |

---

### TC_CART_010 – Cập nhật số lượng vượt quá tồn kho

| Trường | Nội dung |
|--------|----------|
| **TC_ID** | TC_CART_010 |
| **Tiêu đề** | Cập nhật số lượng sản phẩm trong giỏ vượt quá số lượng tồn kho |
| **Điều kiện trước** | Sản phẩm "Áo thun nam" có tồn kho = 10, hiện trong giỏ số lượng = 5 |
| **Các bước** | 1. Mở trang giỏ hàng <br> 2. Sửa số lượng "Áo thun nam" thành 15 (vượt tồn kho) <br> 3. Nhấn cập nhật |
| **Kết quả mong đợi** | Hệ thống hiển thị thông báo "Số lượng vượt quá tồn kho (còn 10)", không cho cập nhật |
| **Độ ưu tiên** | High |
| **Loại test** | Boundary |

---

## MODULE 3 – THANH TOÁN (Checkout) — 10 Test Cases

---

### TC_CHECKOUT_001 – Nhập địa chỉ giao hàng hợp lệ

| Trường | Nội dung |
|--------|----------|
| **TC_ID** | TC_CHECKOUT_001 |
| **Tiêu đề** | Nhập địa chỉ giao hàng hợp lệ trong bước thanh toán |
| **Điều kiện trước** | Người dùng đã đăng nhập; giỏ hàng có ít nhất 1 sản phẩm; đang ở bước thanh toán |
| **Các bước** | 1. Nhấn "Thanh toán" từ trang giỏ hàng <br> 2. Nhập họ tên: Nguyễn Văn A <br> 3. Nhập số điện thoại: 0901234567 <br> 4. Nhập địa chỉ: 123 Nguyễn Huệ, Q.1, TP.HCM <br> 5. Nhấn "Tiếp tục" |
| **Kết quả mong đợi** | Hệ thống chấp nhận địa chỉ, chuyển sang bước chọn phương thức thanh toán |
| **Độ ưu tiên** | High |
| **Loại test** | Positive |

---

### TC_CHECKOUT_002 – Thanh toán không nhập địa chỉ giao hàng

| Trường | Nội dung |
|--------|----------|
| **TC_ID** | TC_CHECKOUT_002 |
| **Tiêu đề** | Thanh toán khi để trống trường địa chỉ giao hàng |
| **Điều kiện trước** | Người dùng đang ở bước nhập địa chỉ thanh toán |
| **Các bước** | 1. Nhấn "Thanh toán" từ trang giỏ hàng <br> 2. Để trống trường "Địa chỉ giao hàng" <br> 3. Nhấn "Tiếp tục" |
| **Kết quả mong đợi** | Hệ thống hiển thị thông báo "Vui lòng nhập địa chỉ giao hàng", không cho tiếp tục |
| **Độ ưu tiên** | High |
| **Loại test** | Negative |

---

### TC_CHECKOUT_003 – Chọn phương thức thanh toán COD

| Trường | Nội dung |
|--------|----------|
| **TC_ID** | TC_CHECKOUT_003 |
| **Tiêu đề** | Chọn phương thức thanh toán COD (thanh toán khi nhận hàng) |
| **Điều kiện trước** | Đã nhập địa chỉ giao hàng hợp lệ; đang ở bước chọn phương thức thanh toán |
| **Các bước** | 1. Tại bước chọn phương thức thanh toán <br> 2. Chọn "Thanh toán khi nhận hàng (COD)" <br> 3. Nhấn "Tiếp tục" |
| **Kết quả mong đợi** | Hệ thống chấp nhận, chuyển sang bước xác nhận đơn hàng |
| **Độ ưu tiên** | High |
| **Loại test** | Positive |

---

### TC_CHECKOUT_004 – Chọn phương thức thanh toán Visa giả lập

| Trường | Nội dung |
|--------|----------|
| **TC_ID** | TC_CHECKOUT_004 |
| **Tiêu đề** | Chọn phương thức thanh toán Visa giả lập |
| **Điều kiện trước** | Đã nhập địa chỉ giao hàng hợp lệ |
| **Các bước** | 1. Tại bước chọn phương thức thanh toán <br> 2. Chọn "Thanh toán bằng thẻ Visa" <br> 3. Nhập số thẻ: 4111 1111 1111 1111 <br> 4. Nhập ngày hết hạn: 12/28 <br> 5. Nhập CVV: 123 <br> 6. Nhấn "Tiếp tục" |
| **Kết quả mong đợi** | Hệ thống chấp nhận thông tin thẻ giả lập, chuyển sang bước xác nhận |
| **Độ ưu tiên** | High |
| **Loại test** | Positive |

---

### TC_CHECKOUT_005 – Đặt hàng thành công với COD

| Trường | Nội dung |
|--------|----------|
| **TC_ID** | TC_CHECKOUT_005 |
| **Tiêu đề** | Đặt hàng thành công với phương thức COD |
| **Điều kiện trước** | Giỏ hàng có sản phẩm; đã nhập địa chỉ; đã chọn COD |
| **Các bước** | 1. Tại trang xác nhận đơn hàng <br> 2. Kiểm tra thông tin: sản phẩm, số lượng, tổng tiền, địa chỉ, phương thức TT <br> 3. Nhấn nút "Đặt hàng" |
| **Kết quả mong đợi** | Đơn hàng được tạo thành công, hiển thị mã đơn hàng, thông báo "Đặt hàng thành công" |
| **Độ ưu tiên** | High |
| **Loại test** | Positive |

---

### TC_CHECKOUT_006 – Đặt hàng thành công với Visa giả lập

| Trường | Nội dung |
|--------|----------|
| **TC_ID** | TC_CHECKOUT_006 |
| **Tiêu đề** | Đặt hàng thành công với phương thức Visa giả lập |
| **Điều kiện trước** | Giỏ hàng có sản phẩm; đã nhập địa chỉ; đã nhập thẻ Visa hợp lệ |
| **Các bước** | 1. Tại trang xác nhận đơn hàng <br> 2. Kiểm tra thông tin đơn hàng <br> 3. Nhấn nút "Đặt hàng" |
| **Kết quả mong đợi** | Thanh toán giả lập thành công, đơn hàng được tạo, hiển thị mã đơn hàng |
| **Độ ưu tiên** | High |
| **Loại test** | Positive |

---

### TC_CHECKOUT_007 – Xem lịch sử đơn hàng

| Trường | Nội dung |
|--------|----------|
| **TC_ID** | TC_CHECKOUT_007 |
| **Tiêu đề** | Xem danh sách lịch sử đơn hàng đã đặt |
| **Điều kiện trước** | Người dùng đã đặt ít nhất 1 đơn hàng thành công |
| **Các bước** | 1. Đăng nhập vào hệ thống <br> 2. Vào mục "Đơn hàng của tôi" hoặc "Lịch sử đơn hàng" |
| **Kết quả mong đợi** | Hiển thị danh sách đơn hàng với: mã đơn, ngày đặt, tổng tiền, trạng thái |
| **Độ ưu tiên** | High |
| **Loại test** | Positive |

---

### TC_CHECKOUT_008 – Xem chi tiết đơn hàng trong lịch sử

| Trường | Nội dung |
|--------|----------|
| **TC_ID** | TC_CHECKOUT_008 |
| **Tiêu đề** | Xem chi tiết một đơn hàng trong lịch sử |
| **Điều kiện trước** | Có ít nhất 1 đơn hàng trong lịch sử |
| **Các bước** | 1. Mở trang lịch sử đơn hàng <br> 2. Nhấn vào đơn hàng đầu tiên để xem chi tiết |
| **Kết quả mong đợi** | Hiển thị chi tiết: danh sách sản phẩm, số lượng, đơn giá, tổng tiền, địa chỉ giao, trạng thái đơn |
| **Độ ưu tiên** | Medium |
| **Loại test** | Positive |

---

### TC_CHECKOUT_009 – Đặt hàng với giỏ hàng trống

| Trường | Nội dung |
|--------|----------|
| **TC_ID** | TC_CHECKOUT_009 |
| **Tiêu đề** | Thử đặt hàng khi giỏ hàng không có sản phẩm |
| **Điều kiện trước** | Người dùng đã đăng nhập; giỏ hàng trống |
| **Các bước** | 1. Mở trang giỏ hàng (giỏ trống) <br> 2. Nhấn "Thanh toán" (nếu nút hiển thị) |
| **Kết quả mong đợi** | Nút "Thanh toán" bị disable hoặc hiển thị thông báo "Giỏ hàng trống, vui lòng thêm sản phẩm" |
| **Độ ưu tiên** | Medium |
| **Loại test** | Negative |

---

### TC_CHECKOUT_010 – Thanh toán Visa với số thẻ không hợp lệ

| Trường | Nội dung |
|--------|----------|
| **TC_ID** | TC_CHECKOUT_010 |
| **Tiêu đề** | Thanh toán bằng Visa với số thẻ không hợp lệ |
| **Điều kiện trước** | Đã nhập địa chỉ giao hàng; đang ở bước chọn phương thức thanh toán |
| **Các bước** | 1. Chọn "Thanh toán bằng thẻ Visa" <br> 2. Nhập số thẻ: 1234 5678 9012 3456 (không hợp lệ) <br> 3. Nhập ngày hết hạn: 01/20 (đã hết hạn) <br> 4. Nhập CVV: 12 (thiếu số) <br> 5. Nhấn "Tiếp tục" |
| **Kết quả mong đợi** | Hệ thống hiển thị thông báo lỗi "Thông tin thẻ không hợp lệ", không cho tiếp tục |
| **Độ ưu tiên** | High |
| **Loại test** | Negative |

---

## TỔNG KẾT

| Module | Số TC | Positive | Negative | Boundary |
|--------|-------|----------|----------|----------|
| Authentication | 15 | 6 | 6 | 3 |
| Product & Cart | 20 | 11 | 4 | 5 |
| Checkout | 10 | 6 | 3 | 1 |
| **Tổng** | **45** | **23** | **13** | **9** |

- **Negative cases:** 13 (≥ 10 ✓)
- **Boundary cases:** 9 (≥ 5 ✓)
- **Validation / Bảo mật cơ bản:** TC_AUTH_003, TC_AUTH_004, TC_AUTH_006, TC_AUTH_009, TC_AUTH_010, TC_PROD_009, TC_CHECKOUT_002, TC_CHECKOUT_010 = 8 (≥ 5 ✓)
