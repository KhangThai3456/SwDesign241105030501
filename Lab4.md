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

## 1.1.2. Maintain Timecard

![Sequence Diagram](https://www.planttext.com/api/plantuml/png/h9HDJiCm48NtFiM83R2ekky2LL3O1MN11QRnj3MAxMey0N8s5Xo9A-2eAKdR_26noCBs-_ncNYRv_lnQ1a6MmkOAC_4CZtQV-vAeNbwbx5yf4qZGuPOiERa2390cQkqBfv5BU36MCcJzvDcgp3jXd_zkFXpMER6Ah956VbpN3et12WNN6EZWixfNwbWKpEvEt1PWqJY93qYzVNEhseesqPIoWFaSjYIG5SpHiOjkrEqxff2LlgfxI5kTm-paucTw1-y8CYOKqc0sO0Iqf-2k1UZ3186If6NpBxrTHDgFzoPx0BK9-npBIKHNlJlaRMpVQmgzxo5D-lHfCXh8k45l6AVem436oE95ErzmW4tyW6hI5NPD7APFPx7NSGh-E9Zzq50sqwowehaa1v89-DPfCX947pOGGuLCxFrCEjRmUJ5BShhwTohr0m00__y30000)

![Use Case Diagram](https://www.planttext.com/api/plantuml/png/b9IzRi8m481tFyM9gHqe0hOE5MffDoI6li3X725LRAEptOfdwz17wYiqnlahO1I634xkkpj_Tyhlzy_2EcJdLIbGEiFmglQbEH3Lnz6QpGT91olKc9CYxKQ05jOhiJ5UPyW7U2yKIUJipR0IqcZ7fcnVliHpIImgjd1TU7EkAtG5bkXmWvPYdUMp44rJC7xwL-qHfWymcO32Ghlg0LT_lBiN_RW-rpKKwCZdv41wvghufHGTqayKyK49O9neu9I1IhbaGaUWwUjY0sSAJdCaRzuOcnrRpWgxB_5mkx9vT-CTSauWJKOsgIjCC6BJ51X2qefwiGE5z8ahknCzLEggB3lZsS8sw8-qzcf3R0TQcTMNy_iipEw67PgrEvHcasxQjObiDipF6NN5KHosnS-BZLrJqimxnQQ4p5iXWHnYuLZ1UYd9sgqlXqauXHQai_0N_0C00F__0m00)

## **Tổng quan hệ thống**
Hệ thống quản lý bảng chấm công (Timecard System) được thiết kế để hỗ trợ nhân viên nhập liệu, chỉnh sửa và lưu trữ dữ liệu về số giờ làm việc. Các chức năng chính được thực hiện thông qua các thành phần hệ thống như:
- **TimecardForm:** Giao diện để nhân viên tương tác, nhập thông tin.
- **TimecardController:** Bộ điều khiển xử lý logic nghiệp vụ.
- **ProjectManagementDatabase:** Cơ sở dữ liệu quản lý thông tin dự án.

---

## **Biểu đồ**
### **Sequence Diagram**
Biểu đồ trình tự dưới đây mô tả luồng hoạt động chính trong hệ thống khi nhân viên duy trì bảng chấm công.

![Sequence Diagram](https://www.planttext.com/api/plantuml/png/h9HDJiCm48NtFiM83R2ekky2LL3O1MN11QRnj3MAxMey0N8s5Xo9A-2eAKdR_26noCBs-_ncNYRv_lnQ1a6MmkOAC_4CZtQV-vAeNbwbx5yf4qZGuPOiERa2390cQkqBfv5BU36MCcJzvDcgp3jXd_zkFXpMER6Ah956VbpN3et12WNN6EZWixfNwbWKpEvEt1PWqJY93qYzVNEhseesqPIoWFaSjYIG5SpHiOjkrEqxff2LlgfxI5kTm-paucTw1-y8CYOKqc0sO0Iqf-2k1UZ3186If6NpBxrTHDgFzoPx0BK9-npBIKHNlJlaRMpVQmgzxo5D-lHfCXh8k45l6AVem436oE95ErzmW4tyW6hI5NPD7APFPx7NSGh-E9Zzq50sqwowehaa1v89-DPfCX947pOGGuLCxFrCEjRmUJ5BShhwTohr0m00__y30000)

### **Mô tả luồng trình tự**
- Nhân viên chọn chức năng "Maintain Timecard".
- Hệ thống kiểm tra và hiển thị bảng chấm công hiện tại (nếu chưa có thì tạo mới).
- Nhân viên nhập số giờ làm việc theo từng mã dự án (charge codes).
- Dữ liệu được lưu trữ vào cơ sở dữ liệu thông qua bộ điều khiển.

---

## **Use Case Diagram**
Biểu đồ ca sử dụng dưới đây mô tả các tác vụ chính trong hệ thống.

![Use Case Diagram](https://www.planttext.com/api/plantuml/png/b9IzRi8m481tFyM9gHqe0hOE5MffDoI6li3X725LRAEptOfdwz17wYiqnlahO1I634xkkpj_Tyhlzy_2EcJdLIbGEiFmglQbEH3Lnz6QpGT91olKc9CYxKQ05jOhiJ5UPyW7U2yKIUJipR0IqcZ7fcnVliHpIImgjd1TU7EkAtG5bkXmWvPYdUMp44rJC7xwL-qHfWymcO32Ghlg0LT_lBiN_RW-rpKKwCZdv41wvghufHGTqayKyK49O9neu9I1IhbaGaUWwUjY0sSAJdCaRzuOcnrRpWgxB_5mkx9vT-CTSauWJKOsgIjCC6BJ51X2qefwiGE5z8ahknCzLEggB3lZsS8sw8-qzcf3R0TQcTMNy_iipEw67PgrEvHcasxQjObiDipF6NN5KHosnS-BZLrJqimxnQQ4p5iXWHnYuLZ1UYd9sgqlXqauXHQai_0N_0C00F__0m00)

### **Mô tả các ca sử dụng**
- **Maintain Timecard:** Nhân viên có thể tạo, sửa đổi và lưu bảng chấm công.
- **Enter Hours for Charge Numbers:** Nhập số giờ làm việc ứng với từng mã dự án.
- **Save Timecard:** Lưu thông tin bảng chấm công vào cơ sở dữ liệu.

---

## **Mô tả chi tiết các ca sử dụng**
### **Maintain Timecard**
#### **Mô tả**
Chức năng cho phép nhân viên duy trì bảng chấm công của họ, bao gồm tạo mới, hiển thị hoặc chỉnh sửa bảng chấm công hiện tại.

#### **Các bước thực hiện**
- Nhân viên truy cập giao diện bảng chấm công (TimecardForm).
- Hệ thống kiểm tra bảng chấm công hiện tại:
   + Nếu có, hiển thị bảng chấm công.
   + Nếu chưa có, tạo bảng chấm công mới.
3. Hệ thống hiển thị các mã dự án (charge codes) từ cơ sở dữ liệu.

#### **Tại sao thiết kế như vậy?**
- Tính năng tạo bảng chấm công mới tự động giúp người dùng giảm bớt thao tác thủ công.
- Cách thức hiển thị các mã dự án đảm bảo dữ liệu đồng nhất với cơ sở dữ liệu.

---

## **Enter Hours for Charge Numbers**
### **Mô tả**
Nhân viên nhập số giờ làm việc cho từng mã dự án.

### **Các bước thực hiện**
1. Nhân viên chọn mã dự án (charge code).
2. Nhập số giờ làm việc vào từng mục tương ứng.
3. Hệ thống kiểm tra và cập nhật bảng chấm công.

### **Tại sao thiết kế như vậy?**
- Đảm bảo dữ liệu nhập vào chính xác và gắn liền với từng mã dự án, phù hợp với cấu trúc cơ sở dữ liệu.

---

## **3.3. Save Timecard**
### **Mô tả**
Nhân viên lưu thông tin bảng chấm công vào cơ sở dữ liệu.

### **Các bước thực hiện**
1. Hệ thống kiểm tra dữ liệu đã nhập.
2. Lưu bảng chấm công vào **ProjectManagementDatabase**.
3. Xác nhận lưu thành công và thông báo cho người dùng.

### **Tại sao thiết kế như vậy?**
- Quy trình lưu giữ liệu được đảm bảo qua các bước kiểm tra nhằm giảm thiểu lỗi dữ liệu trong cơ sở dữ liệu.

---

## **Lý do thiết kế**
- **Tính rõ ràng và đơn giản:**
   + Các thành phần được chia nhỏ theo chức năng giúp dễ dàng bảo trì và nâng cấp hệ thống.
- **Tính nhất quán:**
   + Dữ liệu liên quan đến bảng chấm công được quản lý tập trung thông qua `TimecardController` và cơ sở dữ liệu.
- **Tăng hiệu suất làm việc:**
   + Tự động hóa các tác vụ (như tạo bảng chấm công mới) giúp tiết kiệm thời gian cho nhân viên.

## 1.1.3. Run Payroll

![Sequence Diagram](https://www.planttext.com/api/plantuml/png/T5DBJiCm4Dtx55ws4hq02rGr0gchMWeNCCwKMl5FzWGfPsF1aRW2CtKIDGMoQ3JllVcycVJxysjVK6SSl1FQOCoo7Gk2RrmqlTH5jirl_1WGybaRg8BZf7ZsoSKHO0fLjgoReeCEVIt1IHm9aQYnDJRfW5BfCKVdcXYGtv1PffgLvjLwC3ftwyGXcuikSChTb7IwBsmkOFerM6TR6L77bUHku5Q8jf6x9_Oh7-LrQPkju8X0rH2MXo1JjK6CQXR25iOxFIxml2eYtm4bJiQa3UT8eeKcwMpwJlfVANNwgmYXD1zWjl0159NRyOnsPd0QGLqddAbfRop8GEn6-pW4N3dZZcJD0otC0ruYpoMqG_b2D_VQEadlP4s_6vAGz4p9lCF4HzZCVRQLhkkivraqMm6kmBLcPpCOt7MGOh5uK_BGybaWTFADBYSnwr3eqxCnoAN7G-LuGRKT9QrIRxAuQUY4sDCl_pj-0000__y30000)
