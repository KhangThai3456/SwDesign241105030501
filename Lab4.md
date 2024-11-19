# Lab 4

## 1. Exercise: Use-Case Analysis

## 1.1. Use-Case Realization Interaction Diagram

## 1.1.1. Login

![Sequence Diagram](https://www.planttext.com/api/plantuml/png/X50x3e904Etd51CgBRY0XK4BAZlZ0IRincpO3zaP89pDmYDv1HU2G8o9tRmtxpEPr-DPi52KrbdWslY68ZcaIaAyoc0rifYg1X0Z2Lp2tNZCyKniAYnjw04cBMOdF-2DTSoG61COPqXfoMuQyeBPP2v3T9DaGG2p6lFZoXvGUqbScnQUd4Ro2XjYxaDKk_tOQZeIlLGjpg-OZgnHe_1lqdhH9Yk5pGq7Z9fRAw3q3yk6_5m4XVPg_2ky0G00__y30000)

![Use Case Diagram](https://www.planttext.com/api/plantuml/png/T8z12i9034NtEKNeIXTUm8LK144GN8W729qWeMscpAGjFPiBZ-GLd2bIGN0JyfFtVyZhyIoZKR2-RI3MeXq5Qf4gy-5gKyCOJQeQmCIIEFkxADuYuu5IEQbnIAnunSl0OH0U0MOp5dkTCXaAf8X9v1vIVCgJZjImcDEEFhGpiYY03usRtNUwHSxNi4yBfPQHr657COu-kDKQ5l37DL0ZZep_6g5aTVbzU0C00F__0m00)

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
- **Actor:** Quản trị viên
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

### **Tính bảo mật:**
- Các tính năng đăng nhập, quản lý tài khoản và quên mật khẩu đều được thiết kế để đảm bảo chỉ người dùng hợp lệ có thể truy cập vào hệ thống. Việc bảo vệ tài khoản và thông tin người dùng khỏi các truy cập trái phép là yếu tố quan trọng trong việc bảo mật dữ liệu của tổ chức.

### **Tính minh bạch và tiện lợi:**
- Các tính năng như xem bảng lương cá nhân giúp nhân viên dễ dàng theo dõi quá trình tính lương và các thay đổi liên quan đến tài chính của mình. Điều này tạo ra sự tin tưởng và minh bạch trong quy trình quản lý.

### **Tính tự động hóa và hiệu quả:**
- Việc tự động hóa các quy trình như tính toán bảng lương giúp giảm thiểu các sai sót và tiết kiệm thời gian cho bộ phận nhân sự. Các báo cáo thống kê và thông báo tự động giúp công việc quản lý trở nên đơn giản và hiệu quả hơn.

---

## Các Tính Năng Mở Rộng

### **Báo cáo thống kê (Generate Reports):**
- **Diễn viên:** Quản trị viên
- **Mục đích:** Quản trị viên có thể tạo các báo cáo tổng hợp về chi phí lương, nghỉ phép, và các thông tin tài chính khác để hỗ trợ các quyết định quản lý.
- **Luồng chính:**
  + Quản trị viên truy cập vào phần báo cáo trong hệ thống.
  + Quản trị viên chọn loại báo cáo cần tạo.
  + Hệ thống tạo và xuất báo cáo theo yêu cầu.
- **Tiền điều kiện:** Quản trị viên đã đăng nhập và có quyền truy cập báo cáo.
- **Hậu điều kiện:** Báo cáo được tạo thành công và có sẵn cho người quản lý sử dụng.

---

### **Thông báo tự động (Automated Notifications):**
- **Diễn viên:** Quản trị viên, Nhân viên
- **Mục đích:** Hệ thống gửi thông báo tự động cho người dùng về các thay đổi quan trọng trong hệ thống.
- **Luồng chính:**
  + Hệ thống gửi thông báo cho người dùng khi có thay đổi về bảng lương, thông tin tài khoản, hoặc khi có thông báo quan trọng từ quản trị viên.
- **Tiền điều kiện:** Người dùng đã đăng nhập vào hệ thống.
- **Hậu điều kiện:** Người dùng nhận được thông báo kịp thời về các sự kiện quan trọng.


