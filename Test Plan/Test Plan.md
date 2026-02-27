1. KẾ HOẠCH KIỂM THỬ (Test Plan) 📄
1.1. Giới thiệu
Tài liệu này mô tả kế hoạch kiểm thử thủ công cho Hệ thống Quản lý Nhà hàng (RMS) do Nhóm 8 - 23IT-SOFT1 phát triển. Hệ thống bao gồm các chức năng: quản lý bàn, gọi món, thanh toán, quản lý kho, đặt bàn online và báo cáo doanh thu.

1.2. Phạm vi kiểm thử
Trong phạm vi (In-scope):

Module 1: Xác thực người dùng (Đăng nhập, Đăng ký, Phân quyền)
Module 2: Quản lý bàn & Gọi món (Mở bàn, Gọi món, Cập nhật trạng thái)
Module 3: Thanh toán (Tạo hóa đơn, Áp dụng giảm giá, Xác nhận thanh toán)
Module 4: Đặt bàn online (Đặt bàn, Xác nhận, Hủy đặt bàn)
Ngoài phạm vi (Out-of-scope):

Kiểm thử hiệu năng (Performance testing)
Kiểm thử tự động (Automation testing)
Kiểm thử tích hợp cổng thanh toán thực (MoMo, VNPay)
Kiểm thử Kitchen Display System (KDS)
1.3. Phương pháp kiểm thử
Kiểm thử chức năng (Functional testing): Kiểm tra các UC từ UC-01 đến UC-21
Kiểm thử giao diện cơ bản (UI testing): Kiểm tra bố cục, responsive trên PC và tablet
Kiểm thử hồi quy (Regression - smoke): Chạy lại test case quan trọng sau mỗi bản build
1.4. Môi trường kiểm thử
Trình duyệt: Google Chrome (phiên bản mới nhất)
Hệ điều hành: Windows 10/11
Backend: ASP.NET Core 8, Kestrel (port 5000) - theo 4.1_Kien_Truc_He_Thong.md
Frontend: Angular CLI dev server (port 4200)
Database: MySQL 8.0+ (test environment)
Dữ liệu test: Tài khoản giả lập cho 4 role: QUAN_LY, NHAN_VIEN, THU_NGAN, KHACH_HANG
1.5. Điều kiện vào / ra
Loại	Điều kiện
Entry Criteria	- Bản build ổn định trên môi trường test<br>- Database đã seed dữ liệu mẫu<br>- Tài liệu SRS đã được review
Exit Criteria	- Tất cả test case Critical/High đã Pass<br>- Không còn bug Critical mở<br>- Coverage ≥ 95%
1.6. Rủi ro & Biện pháp giảm thiểu
Rủi ro	Mức độ	Biện pháp
Database test bị reset	Cao	Backup data trước mỗi phiên test
API backend chưa hoàn thiện	Cao	Mock API, test UI trước
Thiếu dữ liệu test đa dạng	TB	Chuẩn bị script seed data
Xung đột real-time (SignalR)	TB	Test trên nhiều tab/trình duyệt
1.7. Vai trò & Trách nhiệm
Vai trò	Người đảm nhận	Trách nhiệm
Test Lead	Lê Minh Đức	Lập kế hoạch, phân công, tổng hợp báo cáo
Tester 1	Phạm Gia Đức	Test Module 1 (Auth) + Module 4 (Đặt bàn)
Tester 2	Phạm Quang Đạt	Test Module 2 (Bàn & Gọi món)
Tester 3	Nguyễn Hoàng Sơn	Test Module 3 (Thanh toán)
Tester 4	Nguyễn Đình Vũ	Test regression + bug verification
1.8. Lịch trình kiểm thử
Giai đoạn	Thời gian	Nội dung
Chuẩn bị	Tuần 1	Thiết kế test case, chuẩn bị môi trường
Vòng 1	Tuần 2-3	Chạy toàn bộ test case
Fix bug	Tuần 3	Dev sửa lỗi
Vòng 2	Tuần 4	Regression test + verify bug
Báo cáo	Tuần 4	Tổng hợp kết quả, ra quyết định