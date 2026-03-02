# KẾ HOẠCH KIỂM THỬ (Test Plan)

## 1.1. Giới thiệu (Introduction)

Tài liệu này mô tả kế hoạch kiểm thử thủ công (Manual Testing) cho **Hệ thống Website bán hàng online (E-commerce)** do Nhóm Kiểm Thử thực hiện. Hệ thống bao gồm 3 phân hệ (module) chính: Xác thực người dùng (Authentication), Sản phẩm & Giỏ hàng (Product & Cart), và Thanh toán (Checkout).

Mục tiêu của bản kế hoạch kiểm thử là đảm bảo tất cả các chức năng chính của hệ thống hoạt động đúng theo yêu cầu đặc tả, phát hiện các lỗi tiềm ẩn trước khi release, và đánh giá chất lượng tổng thể của hệ thống.

---

## 1.2. Phạm vi kiểm thử (Scope)

### Trong phạm vi (In-scope):

| Module | Chức năng |
|--------|-----------|
| **Module 1 – Xác thực người dùng (Authentication)** | Đăng ký tài khoản, Đăng nhập, Quên mật khẩu, Đăng xuất |
| **Module 2 – Sản phẩm & Giỏ hàng (Product & Cart)** | Tìm kiếm sản phẩm, Lọc theo giá/danh mục, Xem chi tiết sản phẩm, Thêm sản phẩm vào giỏ, Cập nhật số lượng, Xoá sản phẩm khỏi giỏ |
| **Module 3 – Thanh toán (Checkout)** | Nhập địa chỉ giao hàng, Chọn phương thức thanh toán (COD/Visa giả lập), Đặt hàng, Xem lịch sử đơn hàng |

### Ngoài phạm vi (Out-of-scope):

- Kiểm thử hiệu năng (Performance testing)
- Kiểm thử tự động (Automation testing)
- Kiểm thử bảo mật nâng cao (Advanced security testing)
- Kiểm thử tích hợp cổng thanh toán thực tế
- Kiểm thử trên thiết bị di động (Mobile testing)

---

## 1.3. Phương pháp kiểm thử (Test Approach)

| Phương pháp | Mô tả |
|-------------|-------|
| **Kiểm thử chức năng (Functional Testing)** | Kiểm tra tất cả các chức năng từ R1 đến R16 theo danh sách yêu cầu. Bao gồm kiểm thử dương (Positive), kiểm thử âm (Negative) và kiểm thử biên (Boundary). |
| **Kiểm thử giao diện cơ bản (UI Testing – Basic)** | Kiểm tra bố cục trang, hiển thị thông báo lỗi, hiển thị nút bấm và form nhập liệu trên trình duyệt Chrome. |
| **Kiểm thử hồi quy (Regression – Smoke)** | Chạy lại các test case quan trọng (Critical/High priority) sau mỗi lần sửa lỗi để đảm bảo không phát sinh lỗi mới. |

---

## 1.4. Môi trường kiểm thử (Test Environment)

| Thành phần | Chi tiết |
|------------|----------|
| Trình duyệt | Google Chrome (phiên bản mới nhất) |
| Hệ điều hành | Windows 10/11 |
| URL hệ thống | http://localhost:3000 (môi trường test giả lập) |
| Dữ liệu test | Tài khoản giả lập, sản phẩm mẫu, đơn hàng mẫu |
| Công cụ quản lý test | Markdown + GitHub Repository |

**Dữ liệu test mẫu:**

| Loại | Giá trị |
|------|---------|
| Email hợp lệ | testuser@gmail.com |
| Mật khẩu hợp lệ | Test@1234 |
| Email sai định dạng | testuser, test@, @gmail.com |
| Mật khẩu < 8 ký tự | Test123 |
| Sản phẩm mẫu | Áo thun nam (200.000đ), Quần jean (450.000đ), Giày thể thao (800.000đ) |

---

## 1.5. Điều kiện vào / ra (Entry / Exit Criteria)

| Loại | Điều kiện |
|------|-----------|
| **Entry Criteria** | - Bản build ổn định trên môi trường test |
| | - Database đã được seed dữ liệu mẫu (sản phẩm, tài khoản) |
| | - Tài liệu yêu cầu (R1–R16) đã được review và phê duyệt |
| | - Môi trường test (Chrome, Windows) đã sẵn sàng |
| **Exit Criteria** | - Tất cả test case có Priority = High đã được thực thi |
| | - Không còn bug mức Critical chưa được xử lý |
| | - Tỷ lệ bao phủ yêu cầu (Requirement Coverage) dat toi thieu 95% |
| | - Tỷ lệ thực thi test (Execution Rate) dat toi thieu 90% |

---

## 1.6. Rủi ro & Biện pháp giảm thiểu (Risks & Mitigation)

| Rủi ro | Mức độ | Biện pháp giảm thiểu |
|--------|--------|----------------------|
| Database test bị reset mất dữ liệu mẫu | Cao | Backup database trước mỗi phiên test; chuẩn bị script seed data |
| Yêu cầu thay đổi giữa chừng | Cao | Freeze requirement trước khi test; cập nhật RTM nếu có thay đổi |
| Thiếu dữ liệu test đa dạng (edge case) | Trung bình | Chuẩn bị bộ dữ liệu test bao gồm positive, negative, boundary |
| Hệ thống giả lập không ổn định | Trung bình | Restart server trước mỗi phiên test; ghi nhận lỗi môi trường riêng |
| Thành viên nhóm chưa có kinh nghiệm QA | Thấp | Tổ chức buổi hướng dẫn viết test case; review chéo giữa các thành viên |

---

## 1.7. Vai trò & Trách nhiệm (Roles & Responsibilities)

| Vai trò | Người đảm nhận | Trách nhiệm |
|---------|----------------|-------------|
| Test Lead | Lê Minh Đức | Lập kế hoạch, phân công, tổng hợp báo cáo, review test case |
| Tester 1 | Phạm Gia Đức | Test Module 1 – Xác thực người dùng (Authentication) |
| Tester 2 | Phạm Quang Đạt | Test Module 2 – Sản phẩm & Giỏ hàng (Product & Cart) |
| Tester 3 | Nguyễn Hoàng Sơn | Test Module 3 – Thanh toán (Checkout) |
| Tester 4 | Nguyễn Đình Vũ | Test hồi quy (Regression) + Xác minh bug (Bug Verification) |

---

## 1.8. Lịch trình kiểm thử (Test Schedule)

| Giai đoạn | Thời gian | Nội dung |
|-----------|-----------|----------|
| Chuẩn bị | Tuần 1 (01/03 – 07/03) | Thiết kế test case, lập RTM, chuẩn bị môi trường & dữ liệu test |
| Vòng 1 – Thực thi | Tuần 2–3 (08/03 – 21/03) | Chạy toàn bộ 45 test case trên 3 module |
| Phân tích & Fix bug | Tuần 3 (15/03 – 21/03) | Ghi nhận bug, phối hợp Dev sửa lỗi |
| Vòng 2 – Regression | Tuần 4 (22/03 – 28/03) | Chạy lại test case regression, verify bug đã fix |
| Tổng hợp & Báo cáo | Tuần 4 (28/03 – 31/03) | Tổng hợp Test Report, Test Metrics, ra quyết định Release/No-Release |