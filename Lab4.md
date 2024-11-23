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
- Hệ thống hiển thị các mã dự án (charge codes) từ cơ sở dữ liệu.

#### **Tại sao thiết kế như vậy?**
- Tính năng tạo bảng chấm công mới tự động giúp người dùng giảm bớt thao tác thủ công.
- Cách thức hiển thị các mã dự án đảm bảo dữ liệu đồng nhất với cơ sở dữ liệu.

---

## **Enter Hours for Charge Numbers**
### **Mô tả**
Nhân viên nhập số giờ làm việc cho từng mã dự án.

### **Các bước thực hiện**
- Nhân viên chọn mã dự án (charge code).
- Nhập số giờ làm việc vào từng mục tương ứng.
- Hệ thống kiểm tra và cập nhật bảng chấm công.

### **Tại sao thiết kế như vậy?**
- Đảm bảo dữ liệu nhập vào chính xác và gắn liền với từng mã dự án, phù hợp với cấu trúc cơ sở dữ liệu.

---

## **Save Timecard**
### **Mô tả**
Nhân viên lưu thông tin bảng chấm công vào cơ sở dữ liệu.

### **Các bước thực hiện**
- Hệ thống kiểm tra dữ liệu đã nhập.
- Lưu bảng chấm công vào **ProjectManagementDatabase**.
- Xác nhận lưu thành công và thông báo cho người dùng.

### **Tại sao thiết kế như vậy?**
- Quy trình lưu giữ liệu được đảm bảo qua các bước kiểm tra nhằm giảm thiểu lỗi dữ liệu trong cơ sở dữ liệu.

---

### **Lý do thiết kế**
- **Tính rõ ràng và đơn giản:**
   + Các thành phần được chia nhỏ theo chức năng giúp dễ dàng bảo trì và nâng cấp hệ thống.
- **Tính nhất quán:**
   + Dữ liệu liên quan đến bảng chấm công được quản lý tập trung thông qua `TimecardController` và cơ sở dữ liệu.
- **Tăng hiệu suất làm việc:**
   + Tự động hóa các tác vụ (như tạo bảng chấm công mới) giúp tiết kiệm thời gian cho nhân viên.

## 1.1.3. Run Payroll

### **Use Case 1: Xử lý trả lương nhân viên**
- **Mô tả:** 
  - Hệ thống bắt đầu quy trình xử lý trả lương theo chu kỳ lặp lại.
  - Kiểm tra ngày trả lương thông qua `SystemClock`.
- **Diễn viên:** `SystemClock`, `PayrollController`.

### **Use Case 2: Tạo bảng chấm công**
- **Mô tả:**
  - Hệ thống thu thập thông tin chấm công từ nhân viên và lưu vào `Timecard`.
- **Diễn viên:** `Employee`, `PayrollController`, `Timecard`.

### **Use Case 3: Tính toán tiền lương**
- **Mô tả:**
  - Hệ thống sử dụng thông tin từ `Timecard` và `PurchaseOrder` để tính toán tiền lương.
- **Diễn viên:** `PayrollController`, `Timecard`, `PurchaseOrder`.

### **Use Case 4: Gửi lương qua chuyển khoản ngân hàng**
- **Mô tả:**
  - Xác định phương thức thanh toán của nhân viên và thực hiện giao dịch với `BankSystem`.
- **Diễn viên:** `PayrollController`, `BankSystem`.

### **Use Case 5: In phiếu lương**
- **Mô tả:**
  - Nếu phương thức thanh toán là nhận phiếu lương trực tiếp hoặc qua thư, hệ thống sẽ in phiếu qua `PrinterInterface`.
- **Diễn viên:** `PrinterInterface`, `PayrollController`.

---

## Thiết kế chi tiết
### Sơ đồ tuần tự
Hệ thống được mô tả thông qua sơ đồ tuần tự dưới đây:

![Sequence Diagram](https://www.planttext.com/api/plantuml/png/T5DBJiCm4Dtx55ws4hq02rGr0gchMWeNCCwKMl5FzWGfPsF1aRW2CtKIDGMoQ3JllVcycVJxysjVK6SSl1FQOCoo7Gk2RrmqlTH5jirl_1WGybaRg8BZf7ZsoSKHO0fLjgoReeCEVIt1IHm9aQYnDJRfW5BfCKVdcXYGtv1PffgLvjLwC3ftwyGXcuikSChTb7IwBsmkOFerM6TR6L77bUHku5Q8jf6x9_Oh7-LrQPkju8X0rH2MXo1JjK6CQXR25iOxFIxml2eYtm4bJiQa3UT8eeKcwMpwJlfVANNwgmYXD1zWjl0159NRyOnsPd0QGLqddAbfRop8GEn6-pW4N3dZZcJD0otC0ruYpoMqG_b2D_VQEadlP4s_6vAGz4p9lCF4HzZCVRQLhkkivraqMm6kmBLcPpCOt7MGOh5uK_BGybaWTFADBYSnwr3eqxCnoAN7G-LuGRKT9QrIRxAuQUY4sDCl_pj-0000__y30000)

---

### Lý do thiết kế

- **Tách biệt trách nhiệm rõ ràng:**
   + Mỗi thành phần đảm nhiệm một nhiệm vụ riêng, giúp hệ thống dễ bảo trì và phát triển.
- **Hỗ trợ mở rộng:**
   + Có thể dễ dàng thêm các phương thức thanh toán hoặc thay đổi quy trình trả lương.
- **Tự động hóa:**
   + Sử dụng `SystemClock` để tự động kích hoạt quy trình trả lương theo chu kỳ.

---

### Lợi ích của thiết kế

- **Tính linh hoạt:** 
   + Cho phép tích hợp với các hệ thống ngân hàng hoặc phần mềm quản lý nhân sự khác.
- **Tính nhất quán và chính xác:**
   + Các thành phần hoạt động đồng bộ, giảm thiểu sai sót khi tính toán và xử lý trả lương.
- **Khả năng mở rộng:** 
   + Dễ dàng thêm các chức năng mới mà không ảnh hưởng đến các thành phần hiện có.

## Sơ đồ tuần tự

Hệ thống được biểu diễn qua sơ đồ tuần tự sau:

![Use Case Diagram](https://www.planttext.com/api/plantuml/png/Z5GxRiCm3Drr2eu9q5p0GniqwD0f0TeBA19J2z77a6WKFbk77gbNA1L_uYPA4GysABxtz4XH_ldwNYUIaLfdXLGK8hnrYT1jR537OUN5DJPqY4EuYyOJnY5wblxOKuHGmLCCTYxncg47gN1AxcJ77xlfGyj2KwONlgRCzq1FXhgiecfaYqFyRXmg6VMKRwEgPS9jrBo3c3c2rMFHO0MdHYoMefJDh2ld5SJMGzClC_4AS7ilap9Fo-xf5c_iUWKVI413VM3y8J1bp6RaM7iPUOVuRbkI_TF2Is1HjT0W9QrghIJat3-qqraoEY93uTDG3TA5rjDz1N0h7HyyEAGwwFiuUnwgiHeXBMKR9v5z1quQ2ppSZL77LTi8uATi_M9aAsZooc8iQTbJBr0pvaXO2hG9vnwqYQW8D3OX6RfjuNmvU8BHwxumYj8dlg4c-CdCmxdctjUPMXIQQx0_huLOypl_Adu1003__mC0)

---

## Mô tả luồng hoạt động

### **Khởi động hệ thống**
- **Actor:** `SystemClock`.
- **Mô tả:** `SystemClock` khởi động hệ thống và chuyển điều khiển đến `SystemClockInterface`.

### **Kiểm tra ngày trả lương**
- **Actor:** `SystemClockInterface`, `PayrollController`.
- **Mô tả:** `PayrollController` sử dụng `SystemClockInterface` để xác định xem hôm nay có phải ngày trả lương không.

### **Lấy dữ liệu nhân viên**
- **Actor:** `PayrollController`, `Employee`.
- **Mô tả:** `PayrollController` thu thập thông tin chấm công và đơn hàng từ nhân viên thông qua các đối tượng `Timecard` và `PurchaseOrder`.

### **Tính toán lương**
- **Actor** `PayrollController`.
- **Mô tả:** Dựa trên dữ liệu chấm công và đơn hàng, `PayrollController` tính toán tổng lương của nhân viên.

### **Tạo phiếu lương**
- **Actor:** `PayrollController`, `Paycheck`.
- **Mô tả:** Phiếu lương được tạo ra với số tiền tương ứng.

### **Thực hiện thanh toán**
- **Tùy chọn 1:** Gửi lương qua ngân hàng
  - **Actor:** `PayrollController`, `BankSystem`.
  - **Mô tả:** Gửi giao dịch lương đến hệ thống ngân hàng dựa trên thông tin tài khoản của nhân viên.
- **Tùy chọn 2:** In phiếu lương
  - **Actor:** `PayrollController`, `PrinterInterface`.
  - **Mô tả:** In phiếu lương và chuyển đến nhân viên qua bưu điện hoặc nhận trực tiếp.

---

## Lý do thiết kế

- **Phân tách rõ ràng trách nhiệm:**
   + Các thành phần được chia nhỏ, đảm bảo mỗi phần chỉ thực hiện một nhiệm vụ cụ thể.
- **Tích hợp linh hoạt:**
   + Hỗ trợ cả hai phương thức thanh toán (chuyển khoản và in phiếu).
- **Tự động hóa quy trình:**
   + Sử dụng `SystemClock` để tự động khởi động và kiểm tra thời gian.

---

## Lợi ích của thiết kế

- **Tính linh hoạt:**
   + Dễ dàng mở rộng hệ thống bằng cách thêm phương thức thanh toán hoặc sửa đổi quy trình tính lương.
- **Tự động hóa:**
   + Hệ thống tự động kích hoạt và xử lý trả lương mà không cần can thiệp thủ công.
- **Khả năng bảo trì:**
   + Phân tách trách nhiệm giúp dễ dàng sửa lỗi và cải tiến các thành phần riêng lẻ.

## 1.2. Use-Case Realization View of Participating Classes (VOCPs)

## 1.2.1. Login

### Mô tả
Chức năng đăng nhập là một trong những tính năng cơ bản của bất kỳ hệ thống phần mềm nào, giúp xác thực người dùng trước khi cho phép truy cập. Thành phần chính trong chức năng đăng nhập là lớp `LoginForm`, có nhiệm vụ thu thập thông tin từ người dùng và xác thực.

### Mục tiêu
- Bảo mật hệ thống bằng cách cho phép truy cập chỉ những người dùng hợp lệ.
- Đảm bảo trải nghiệm người dùng thân thiện, nhanh chóng.

---

## Sơ đồ lớp LoginForm

Hệ thống được thiết kế với lớp `LoginForm` có vai trò chính trong chức năng đăng nhập. Sơ đồ lớp được thể hiện dưới đây:

![Class Diagram](https://www.planttext.com/api/plantuml/png/UhzxlqDnIM9HIMbk3bToJc9niO9FVdfcdbj-KQv2DPS24DZO9EMNvgKa5bNQsO4551HIyqfIYqABKulo4dDJ7VDI0e3wolEBKZGqeGhA4dCoKn9BKh6hgULoICrB0Ta80000__y30000)

## Luồng hoạt động

### Mô tả luồng chính
- Người dùng truy cập vào giao diện đăng nhập.
- Nhập tên đăng nhập và mật khẩu vào lớp `LoginForm`.
- Gọi phương thức `enterUsernameAndPassword()` để thu thập dữ liệu người dùng.
- Hệ thống gọi phương thức `validateUsernameAndPassword()` để xác thực thông tin:
   + Nếu thông tin hợp lệ: Người dùng được cấp quyền truy cập.
   + Nếu thông tin không hợp lệ: Hiển thị thông báo lỗi và yêu cầu nhập lại.

---

## Lý do thiết kế

- **Phân tách rõ ràng trách nhiệm:**
   + Lớp `LoginForm` tập trung vào giao diện và xử lý đăng nhập cơ bản.
- **Tính bảo trì:**
   + Dễ dàng mở rộng và chỉnh sửa các chức năng liên quan đến đăng nhập.
- **Khả năng tái sử dụng:**
   + Lớp `LoginForm` có thể tái sử dụng trong các ứng dụng khác có chức năng đăng nhập.

---

## Phạm vi mở rộng

- **Tích hợp cơ sở dữ liệu người dùng:**
  + Kết nối lớp `LoginForm` với cơ sở dữ liệu để xác thực thông tin đăng nhập thực tế.
- **Xác thực nâng cao:**
  + Bổ sung chức năng xác thực đa yếu tố (MFA) để tăng cường bảo mật.
- **Ghi nhật ký đăng nhập:**
  + Ghi lại các lần đăng nhập thành công và thất bại để phân tích bảo mật.

## 1.2.2. Maintain Timecard

### Mô tả
Hệ thống quản lý Timecard hỗ trợ việc lưu trữ, cập nhật và xử lý thông tin chấm công của nhân viên. Chức năng này bao gồm việc nhập số giờ làm, lấy mã công việc (charge codes), và lưu thông tin timecard để sử dụng trong tính lương và báo cáo.

### Mục tiêu
- Đơn giản hóa quy trình quản lý timecard của nhân viên.
- Đảm bảo tính chính xác và hiệu quả trong việc ghi nhận thời gian làm việc.
- Hỗ trợ tích hợp dữ liệu với các hệ thống khác như tính lương và quản lý dự án.

---
## Sơ đồ lớp

Hệ thống được biểu diễn qua sơ đồ lớp sau:

![Class Diagram](https://www.planttext.com/api/plantuml/png/b9FDRjGm4CVlUGfhBuLAhU2AgbLX0L6XLYiLYLudzh0nzKSOsqXHnRa7JZrpwXFm03bmA2-I9-0LS7OJRx9Bf19fbUoCP-OtCt__gN-TEW_aWrRP0NjVW6Jvmxrb_E6UCzNKFyeiumgSOn-aHWuatbhIx2PZyJavoMqm0gYQpzS6neHqfOAgF_paQMUt9Phq1ur7UcS3kPXiKG2jy2Be7Ccb8ngayV6tbyZ1LnmOl-tYBQpnP9L2If1yOqgCA_IBG1GfzhAthZNFmWhSqeHIWCV_Paa4iPJqso4LRUiVBLsZw2mbL4iaQSKWyn2gptXcFjbfgWJmHfVALeXJ00OqzhleZfxrfNCmrssPdiHo2UeIUQ2OOREcpWL243hNjr1OWoC_nYMgROCwGfoZBrAJqYsX4b0D6usMbpgAokyOjy53nwkETRI_YTLoK3oeEB3bkcAQrPBiP-J-70oii2tp6Zpau71Qv7igYSaEs5LxPNxVDVLtKp3Tr7UIVGbWMD7Kjsmbc_edZAxLw4BDdi_OqT5y_TwNSlOFTS-U7H_tGPlFoKuU5vvK-uBnyGnJ_6xKuIn9BViB003__mC0)

## Chi tiết thiết kế

### Các lớp và chức năng chính

#### **TimecardForm**
- **Loại:** `<<boundary>>`
- **Vai trò:** Giao diện để người dùng thao tác với timecard.
- **Phương thức:**
  - `displayTimecard()`: Hiển thị thông tin timecard hiện tại.
  - `open()`: Mở form nhập liệu cho timecard.
  - `enterHoursForChargeNumbers()`: Nhập số giờ làm việc dựa trên mã công việc.
  - `maintainTimecard()`: Thực hiện duy trì hoặc chỉnh sửa timecard.
  - `saveTimecard()`: Lưu thông tin timecard sau khi chỉnh sửa.

#### **TimecardController**
- **Loại:** `<<control>>`
- **Vai trò:** Điều khiển logic liên quan đến timecard.
- **Phương thức:**
  - `getCurrentTimecard()`: Lấy thông tin timecard hiện tại.
  - `getChargeCodes()`: Lấy danh sách mã công việc từ cơ sở dữ liệu.
  - `updateTimecard()`: Cập nhật thông tin timecard.
  - `saveTimecard()`: Lưu timecard sau khi chỉnh sửa hoặc thêm mới.

#### **Timecard**
- **Loại:** `<<entity>>`
- **Vai trò:** Lưu trữ thông tin về timecard của nhân viên.
- **Thuộc tính:**
  - `hoursWorked`: Tổng số giờ làm việc.
  - `payPeriod`: Kỳ tính lương liên quan đến timecard.
- **Phương thức:**
  - `save()`: Lưu thông tin timecard vào cơ sở dữ liệu.
  - `getTimecardInfo()`: Lấy dữ liệu timecard.
  - `updateTimecard()`: Cập nhật thông tin trong timecard.

#### **Employee**
- **Loại:** `<<entity>>`
- **Vai trò:** Lưu trữ thông tin của nhân viên liên quan đến timecard.
- **Thuộc tính:**
  - `name`: Tên nhân viên.
  - `employeeId`: Mã nhân viên.
  - `bankInfo`: Thông tin ngân hàng.
  - `socialSecurityNumber`: Số bảo hiểm xã hội.
  - `address`: Địa chỉ nhân viên.
  - `phoneNumber`: Số điện thoại.
  - `email`: Địa chỉ email.
  - `paymentMethod`: Phương thức thanh toán.
- **Phương thức:**
  - `isPayday()`: Xác định ngày trả lương.
  - `getPayAmount()`: Lấy số tiền lương.
  - `getPaymentMethod()`: Lấy phương thức thanh toán.
  - `getBankInfo()`: Lấy thông tin ngân hàng.
  - `getCurrentTimecard()`: Lấy timecard hiện tại.
  - `calculatePay()`: Tính toán lương dựa trên timecard.

#### **ProjectManagementDatabase**
- **Loại:** `<<boundary>>`
- **Vai trò:** Cung cấp dữ liệu mã công việc (charge codes) từ hệ thống quản lý dự án.
- **Phương thức:**
  - `getChargeCodes()`: Lấy danh sách mã công việc.

---

## Lý do thiết kế

- **Phân tách trách nhiệm rõ ràng:**
   + Lớp `TimecardForm` tập trung vào giao diện, trong khi `TimecardController` xử lý logic và tương tác với dữ liệu.
- **Tính tái sử dụng:**
   + Lớp `Timecard` và `Employee` có thể được sử dụng lại trong các module khác (tính lương, báo cáo).
- **Tích hợp dễ dàng:**
   + Lớp `ProjectManagementDatabase` cho phép tích hợp với hệ thống quản lý dự án, đảm bảo sự linh hoạt.

---

## Lợi ích của thiết kế

- **Hiệu quả:** Quản lý thông tin timecard một cách rõ ràng và có tổ chức.
- **Mở rộng:** Dễ dàng bổ sung thêm chức năng, ví dụ: báo cáo timecard, đồng bộ hóa dữ liệu.
- **Bảo trì:** Các thành phần được tách biệt giúp việc sửa lỗi và nâng cấp dễ dàng hơn.

---

## Phạm vi mở rộng

- **Tích hợp API bên thứ ba:** Kết nối với hệ thống quản lý chấm công tự động.
- **Xác thực dữ liệu:** Thêm các bước xác minh thông tin trước khi lưu timecard.
- **Báo cáo:** Tạo báo cáo tổng hợp giờ làm và năng suất dựa trên timecard.

## 1.2.3. Run Payroll

### Mô tả
Hệ thống trả lương được thiết kế để quản lý và xử lý việc tính toán lương cho nhân viên dựa trên thông tin chấm công, hình thức thanh toán và loại nhân viên (lương cố định, theo giờ hoặc hoa hồng). Hệ thống bao gồm các thành phần chính như xử lý phiếu lương, in ấn, và thanh toán qua ngân hàng.

### Mục tiêu
- Đảm bảo việc trả lương chính xác và hiệu quả.
- Hỗ trợ nhiều loại nhân viên với các phương thức thanh toán khác nhau.
- Tích hợp dễ dàng với hệ thống in và ngân hàng.

---

## Sơ đồ lớp

Hệ thống được biểu diễn qua sơ đồ lớp sau:

![Class Diagram](https://www.planttext.com/api/plantuml/png/Z5JBRXCn5DtxAwni6X2fO5j54IL2QeMW4Qa4snlFRSUA7y6FYX6mPi6gQpRqEx9WKNuaNy0luCdCU3oJb2QRUCvzdNjzhl-kVx-q3eppKf0Z-YO7JXVtTvgo-pj6nMRzSqLlxdzHkLdVSlh9WwBvPlsT42R0MZelh4Cv5PejpvL3SmKCwHT2msyyNcYlCZ35PB85ADqM6ZuXtvhm6HH62p7LofN_Q68igw0OQhogdTFurt8bT85jILIEkxQW0edr4MlNywm65g02volTSDECWvWZyoPaUEVb0arjWYmpQ6tzjSgrmeuT9N3HMA6GWSHRTBbkAd4Rg6TG1EOLS8qk8ASopCVrm3OuDRogkQROr1iJd2-vH0QcTMSWc1VWSBQj66VLE3uqgrnxOpzeiyIixMM6XiS-BDnWog39s67cLrcedR1ABvlbo9OF4O3jF9ek38OqmmfBanXUwkm0iQrApxH-ESHAh_zHAAgizBiqe2mmnxKQkXmZzPFOnJCQyEPU0ZvteTvrojGRbeF52vCbkkxrN5xwHJs_67aMRa8KKTlusGLMEsAlRamKxyESscnd4Kippa60uPWzdXEKyc4DIl-YpNgQe6dUgPQIMnkcT4Xk5hsxdASTlBCGwGnjLVc8VYoVfZ-tc_KFbLVlLFzrslii3LuCw6WqeOFdnyVXkFFsaDtNg7PjefuEObEFEuTZNBaJohhRUb2jH7NNgD24uMGDPWyYqD-MWuBQFI4atk6WIots4Ht6NqUZdd9xnhu8U-PzMY9ahy9wP3eg8N7ejNNFGCa_0000__y30000)

---

## Chi tiết thiết kế

### Các lớp và chức năng chính

#### **SystemClockInterface**
- **Loại:** `<<boundary>>`
- **Vai trò:** Khởi động quy trình xử lý bảng lương.
- **Phương thức:**
  - `start()`: Bắt đầu quy trình xử lý bảng lương.

#### **PayrollController**
- **Loại:** `<<control>>`
- **Vai trò:** Điều phối toàn bộ quy trình xử lý bảng lương.
- **Phương thức:**
  - `runPayroll()`: Chạy quy trình xử lý bảng lương, bao gồm tính toán và phát lương.

#### **Employee**
- **Loại:** `<<entity>>`
- **Vai trò:** Lưu trữ thông tin nhân viên.
- **Thuộc tính:**
  - `name`: Tên nhân viên.
  - `employeeId`: Mã nhân viên.
  - `bankInfo`: Thông tin ngân hàng.
  - `socialSecurityNumber`: Số bảo hiểm xã hội.
  - `address`: Địa chỉ nhân viên.
  - `phoneNumber`: Số điện thoại.
  - `email`: Địa chỉ email.
  - `paymentMethod`: Phương thức thanh toán.
- **Phương thức:**
  - `isPayday()`: Kiểm tra ngày trả lương.
  - `getPayAmount()`: Lấy số tiền lương.
  - `getPaymentMethod()`: Lấy phương thức thanh toán.
  - `getBankInfo()`: Lấy thông tin ngân hàng.
  - `getCurrentTimecard()`: Lấy thông tin timecard hiện tại.
  - `calculatePay()`: Tính lương dựa trên thông tin timecard.

#### **Timecard**
- **Loại:** `<<entity>>`
- **Vai trò:** Lưu trữ thông tin chấm công.
- **Thuộc tính:**
  - `hoursWorked`: Số giờ làm việc.
  - `payPeriod`: Kỳ lương.
- **Phương thức:**
  - `save()`: Lưu thông tin timecard.
  - `getTimecardInfo()`: Lấy thông tin từ timecard.
  - `updateTimecard()`: Cập nhật thông tin timecard.

#### **Paycheck**
- **Loại:** `<<entity>>`
- **Vai trò:** Đại diện cho phiếu lương.
- **Thuộc tính:**
  - `amount`: Số tiền lương.
- **Phương thức:**
  - `create(amount)`: Tạo phiếu lương với số tiền lương cụ thể.

#### **PrinterInterface**
- **Loại:** `<<boundary>>`
- **Vai trò:** In phiếu lương.
- **Phương thức:**
  - `print()`: In phiếu lương cho nhân viên.

#### **BankSystem**
- **Loại:** `<<boundary>>`
- **Vai trò:** Xử lý thanh toán qua ngân hàng.
- **Phương thức:**
  - `sendBankTransaction(thePaycheck : Paycheck, theBankInfo : String)`: Gửi giao dịch thanh toán lương qua ngân hàng.

#### **PurchaseOrder**
- **Loại:** `<<entity>>`
- **Vai trò:** Đại diện cho các đơn hàng, liên quan đến nhân viên hưởng hoa hồng.
- **Phương thức:**
  - `getPOInfo()`: Lấy thông tin đơn hàng.

#### **Các lớp kế thừa từ Employee**
- **HourlyEmployee**
  - **Thuộc tính:** `hourlyRate` - Lương theo giờ.
  - **Phương thức:** `getHourlyRate()`: Lấy mức lương theo giờ.
- **SalariedEmployee**
  - **Thuộc tính:** `annualSalary` - Lương cố định hàng năm.
  - **Phương thức:** `getAnnualSalary()`: Lấy mức lương cố định hàng năm.
- **CommissionedEmployee**
  - **Thuộc tính:** `commissionRate` - Tỷ lệ hoa hồng.
  - **Phương thức:**
    - `getCommissionRate()`: Lấy tỷ lệ hoa hồng.
    - `getPurchaseOrders()`: Lấy danh sách đơn hàng.

---

## Lý do thiết kế

- **Phân tách trách nhiệm rõ ràng:**
   + Lớp `PayrollController` chịu trách nhiệm điều phối các hoạt động, trong khi các lớp khác tập trung vào nhiệm vụ cụ thể.
- **Hỗ trợ đa dạng nhân viên:**
   + Các lớp con của `Employee` cho phép hệ thống xử lý nhiều loại nhân viên (lương cố định, theo giờ, hoa hồng).
- **Tích hợp dễ dàng:**
   + Các lớp biên giới (`PrinterInterface`, `BankSystem`) hỗ trợ tích hợp với hệ thống in và ngân hàng.

---

## Phạm vi mở rộng

- **Báo cáo lương:** Tích hợp thêm lớp xử lý báo cáo tổng hợp về lương.
- **Xác thực nhân viên:** Bổ sung chức năng xác thực danh tính trước khi tạo phiếu lương.
- **API ngân hàng:** Hỗ trợ nhiều giao diện API để kết nối với các ngân hàng khác nhau.

## 1.3. Analysis-Class-To-Analysis-Mechanism Map

## 3. Giải thích cơ chế phân tích

### 3.1. Persistency
- **Định nghĩa:** Lưu trữ và quản lý dữ liệu dài hạn để đảm bảo tính nhất quán và khôi phục dữ liệu khi cần.
- **Áp dụng cho:** 
  - `CommissionedEmployee`, `Employee`, `HourlyEmployee`, `SalariedEmployee`: Lưu trữ thông tin nhân viên và dữ liệu liên quan.
  - `Paycheck`, `PurchaseOrder`, `Timecard`: Lưu trữ phiếu lương, đơn hàng và thông tin chấm công.

### 3.2. Security
- **Định nghĩa:** Bảo vệ dữ liệu nhạy cảm và đảm bảo quyền truy cập.
- **Áp dụng cho:**
  - `CommissionedEmployee`, `Employee`, `HourlyEmployee`, `SalariedEmployee`: Đảm bảo an toàn dữ liệu nhân viên, bao gồm thông tin cá nhân và tài khoản ngân hàng.

### 3.3. Distribution
- **Định nghĩa:** Hỗ trợ phân tán chức năng hoặc dữ liệu trên nhiều thành phần trong hệ thống.
- **Áp dụng cho:**
  - `PayrollController`: Điều phối quá trình xử lý lương giữa các thành phần.
  - `TimecardController`: Phân phối thông tin chấm công và liên kết với các thành phần khác.

### 3.4. Legacy Interface
- **Định nghĩa:** Tích hợp với hệ thống cũ để kế thừa dữ liệu và chức năng.
- **Áp dụng cho:**
  - `BankSystem`: Tích hợp với hệ thống ngân hàng hiện có.
  - `ProjectManagementDatabase`: Tích hợp với hệ thống quản lý dự án cũ.

### 3.5. None
- **Định nghĩa:** Không yêu cầu cơ chế phân tích đặc biệt.
- **Áp dụng cho:**
  - `LoginForm`, `PrinterInterface`, `TimecardForm`, `SystemClockInterface`: Các thành phần này thực hiện nhiệm vụ đơn giản, không liên quan đến lưu trữ, bảo mật hoặc phân tán.

---

## 4. Lợi ích của phân tích

- **Tính rõ ràng:** Mỗi lớp được gắn cơ chế phù hợp, giúp dễ hiểu và dễ bảo trì.
- **Tính bảo mật:** Các lớp liên quan đến dữ liệu nhạy cảm đều được đảm bảo an toàn.
- **Khả năng mở rộng:** Cơ chế phân tích như `Persistency` và `Distribution` đảm bảo hệ thống dễ dàng mở rộng khi cần.
- **Tích hợp liền mạch:** Các lớp như `BankSystem` và `ProjectManagementDatabase` hỗ trợ tích hợp với hệ thống cũ, giảm thiểu rủi ro chuyển đổi.
