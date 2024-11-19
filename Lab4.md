# Lab 4

## 1. Exercise: Use-Case Analysis

![Sequence Diagram](https://www.planttext.com/api/plantuml/png/X50x3e904Etd51CgBRY0XK4BAZlZ0IRincpO3zaP89pDmYDv1HU2G8o9tRmtxpEPr-DPi52KrbdWslY68ZcaIaAyoc0rifYg1X0Z2Lp2tNZCyKniAYnjw04cBMOdF-2DTSoG61COPqXfoMuQyeBPP2v3T9DaGG2p6lFZoXvGUqbScnQUd4Ro2XjYxaDKk_tOQZeIlLGjpg-OZgnHe_1lqdhH9Yk5pGq7Z9fRAw3q3yk6_5m4XVPg_2ky0G00__y30000)

## Các Ca Sử Dụng Chính

### **Đăng nhập (Login)**
- **Actor:** Người dùng (Nhân viên, Quản trị viên)
- **Mục đích:** Người dùng đăng nhập vào hệ thống thông qua tên đăng nhập và mật khẩu hợp lệ.
- **Luồng chính:**
  + Người dùng nhập tên đăng nhập và mật khẩu.
  + Hệ thống xác thực thông tin.
  + Nếu thông tin hợp lệ, người dùng được phép truy cập hệ thống.
  + Nếu thông tin không hợp lệ, hệ thống thông báo lỗi.
- **Tiền điều kiện:** Người dùng đã có tài khoản hợp lệ.
- **Hậu điều kiện:** Người dùng đăng nhập thành công hoặc nhận thông báo lỗi.

---
### **Quản lý tài khoản (Account Management)**
- **Actor:** Quản trị viên
- **Mục đích:** Quản trị viên có thể tạo, sửa, hoặc đặt lại mật khẩu cho tài khoản người dùng.
- **Luồng chính:**
  + Quản trị viên chọn "Quản lý tài khoản".
  + Tạo tài khoản mới hoặc cập nhật thông tin tài khoản.
  + Cung cấp tính năng đặt lại mật khẩu cho người dùng.
  + Hệ thống lưu các thay đổi.
- **Tiền điều kiện:** Quản trị viên phải có quyền truy cập vào phần quản lý tài khoản.
- **Hậu điều kiện:** Tài khoản người dùng được tạo mới hoặc cập nhật thành công.

---

### **Quản lý nhân viên (Manage Employees)**
- **Diễn viên:** Quản trị viên
- **Mục đích:** Quản lý thông tin nhân viên như thêm mới, sửa thông tin hoặc xóa nhân viên khỏi hệ thống.
- **Luồng chính:**
  + Quản trị viên nhập thông tin nhân viên mới.
  + Hệ thống lưu thông tin vào cơ sở dữ liệu.
  + Quản trị viên có thể sửa hoặc xóa thông tin nhân viên khi cần thiết.
- **Tiền điều kiện:** Người dùng phải có quyền quản trị để thực hiện thao tác này.
- **Hậu điều kiện:** Danh sách nhân viên được cập nhật chính xác.

## Lý Do Thiết Kế Các Ca Sử Dụng

- **Tính bảo mật:** Đăng nhập và quản lý tài khoản giúp đảm bảo rằng chỉ người dùng hợp lệ có thể truy cập vào hệ thống, từ đó bảo vệ dữ liệu của tổ chức.
- **Tự động hóa quy trình tính lương:** Các tính toán lương tự động giúp giảm thiểu sai sót và tiết kiệm thời gian cho bộ phận nhân sự.
- **Minh bạch trong quản lý bảng lương:** Nhân viên có thể dễ dàng tra cứu lịch sử lương của mình, tạo ra sự tin tưởng và minh bạch.
- **Tối ưu hóa công việc quản lý nhân sự:** Quản lý nhân viên và tài khoản giúp cho việc theo dõi thông tin nhân sự được dễ dàng và hiệu quả hơn.

---

## Các Tính Năng Phụ Trợ

- **Báo cáo thống kê (Generate Reports):** Quản trị viên có thể tạo các báo cáo về chi phí lương, nghỉ phép, và các thông tin liên quan để phục vụ cho các báo cáo tài chính và quyết định lãnh đạo.
- **Thông báo tự động:** Hệ thống có thể gửi thông báo cho người dùng khi có các thay đổi quan trọng trong hệ thống, chẳng hạn như khi lương đã được tính toán hoặc khi có thông tin mới từ quản trị viên.



