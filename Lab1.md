# Tài liệu Phân tích Hệ thống Payroll System - Lab 1

## 1. Mô tả Yêu cầu Ca Sử Dụng

### Select Payment Method
- **Mô tả**: Cho phép nhân viên lựa chọn phương thức thanh toán (nhận trực tiếp, gửi qua bưu điện, hoặc chuyển khoản).
- **Quy trình**: Hệ thống yêu cầu người dùng chọn phương thức thanh toán và cung cấp thông tin bổ sung nếu cần thiết. Sau đó, hệ thống sẽ cập nhật thông tin thanh toán của nhân viên.

### Maintain Timecard
- **Mô tả**: Cho phép nhân viên cập nhật thông tin giờ làm việc hàng tuần. Nhân viên có thể thêm giờ làm và chọn mã dự án cho từng ngày trong tuần.
- **Quy trình**: Hệ thống hiển thị thẻ thời gian hiện tại hoặc tạo thẻ mới cho kỳ lương nếu chưa có. Nhân viên nhập giờ làm việc và chọn mã dự án. Khi hoàn tất, hệ thống xác thực và lưu lại thông tin.

## 2. Các Lớp Phân Tích và Quan Hệ Giữa Các Lớp

### Lớp `Employee`
- **Thuộc tính**: `name`, `employeeID`, `paymentMethod`, `timecards`.
- **Nhiệm vụ**: Lưu trữ thông tin cá nhân, thực hiện thao tác chọn phương thức thanh toán và cập nhật giờ làm việc.

### Lớp `PaymentMethod` (Lớp trừu tượng)
- **Phương thức**: `selectMethod()`
- **Nhiệm vụ**: Đóng vai trò là lớp cha cho các lớp kế thừa cung cấp thông tin chi tiết từng phương thức thanh toán (`DirectDeposit`, `Mail`, `Pickup`).

### Lớp `DirectDeposit`, `Mail`, `Pickup` (Kế thừa từ `PaymentMethod`)
- **Thuộc tính `DirectDeposit`**: `bankName`, `accountNumber`
- **Thuộc tính `Mail`**: `mailingAddress`
- **Nhiệm vụ**: Cung cấp thông tin và phương thức xác thực phù hợp cho từng loại thanh toán.

### Lớp `Timecard`
- **Thuộc tính**: `startDate`, `endDate`, `hoursWorked`, `chargeNumber`, `status`.
- **Phương thức**: `submitTimecard()`, `validateHours()`.
- **Nhiệm vụ**: Lưu trữ thông tin thời gian làm việc, xác thực số giờ làm việc và tình trạng thẻ chấm công.

### Lớp `TimecardService`
- **Phương thức**: `createOrRetrieveTimecard(employeeID)`, `submitTimecard(timecard)`.
- **Nhiệm vụ**: Quản lý tạo mới hoặc lấy thẻ chấm công hiện tại, xác thực giờ làm việc và lưu trữ thông tin.

### Lớp `ProjectManagementDB`
- **Phương thức**: `getChargeNumbers()`.
- **Nhiệm vụ**: Tương tác với hệ thống quản lý dự án để lấy mã dự án (không cập nhật).

### Lớp `PaymentService`
- **Phương thức**: `updatePaymentMethod(Employee, PaymentMethod)`.
- **Nhiệm vụ**: Cập nhật phương thức thanh toán được chọn cho nhân viên.

## 3. Biểu đồ Sequence

![Sequence Diagram](https://www.planttext.com/api/plantuml/png/T91D3e8m48NtFSM4bIoy00a63Iv9JFG23HrZOmjDEv3qR2uyabUm_8YeEBkPUUzxcNdSxfaZRgdHYksrKRL7XFK63jnhhEY8jfKbGW8E5POqZWkaIorMPkXEtc3ClXnlnY2U4ACtPbmHo3FC892c4ENI1bMEfdQI8WQXVj4Vee1kkPA24-vuTSsHk5Gk9A1ok1HHXFq_ShUR0RT2M7Gzh18BDqu_Iw0ndU4L1hg_asN15vxx1000__y30000)

### Maintain Timecard

![Sequence Diagram](https://www.planttext.com/api/plantuml/png/X99DJiCm48NtESMegtJH2tI1AYWIBFWHS07NUKqD_gd6uqBFne8ZSGKc9Oq01TKBoxRytdppxC_tZqKMmrA2hox3rgSzGBCpUd81rd3p2Duv2vgJPHZ17Jz0s667uuqQlUnwEQt-oduugKN4wx2jfvIOk3SZlBaiBhPZ3lUSdc7bnaJJ8Y3AybpDMiZ5nd2Bsn9Mu5nFHnlGcsNRA3bjKk5CQwrg3pgA1-69jdDP1IS3jVIBKwtkZ7TTrQkkgA8PB-JMnsEN8hcitjOYvtNn5UaOvECW4DAdaf994as-kGJDv9Tsd2QO5sZMffcbwFSLVCP_gY6DEO5PmmfAgBbNY4srqAdxALy0003__mC0)

## 4. Biểu đồ phân tích hợp nhất

![Class Diagram](https://www.planttext.com/api/plantuml/png/X5HBRjim4Dth50El4Y2wW64OIQe0AH0dGHEWQueQsAn5KU37gD7cP5tqIBr2XoQfI3A3U1Ddvirxd9at_lVdxxMnJ5idsuAtp1YuatshZeZmgm3wbD0nYR245wj5juqnZA2lrJnZXKJET6CeyI2CNRt6mFe4033O8hVFx2YninkqEzLSzE6_rsF_hdGPyLmZivXOBbBOzSqq_5OKh3PMCsuXT3BHYEqa_IXyAWleIcYALzWh8opWJujTa-SeeMRT_Z4p5iQvSfrzTB96FKq275Wh_9jlgRX2oqHhnleR2dmYAmb2V3TDez6OZ_XZUipzBFZUzH-n3x0qpK7mP8sAE4dB_qdRxvhpu4uvRRuhlSU64XlMhtpo2YhbwXRN4SLtJ6ynDw2JcdLdRHbNIs7Fzf-wlVUouruJyWNrGN0SzXvyzAI_8R7ZuTqw6IzVqhUKppyZsNm47Cyx37Z-XE3PgVL9dJZIqLs134jPJfSqvjRgXpSmwzWMFQAw7GIsQB-C1XpdCbnqMQvdkr_28jm3BOsPHJ7DhdwNvVGkSW1lt5myc6wgFb_E4fn1attX33Al7BFvDi9w3IWTnqpTv6fouwDokbow6QeF1eKk371HN9FP_O_ZVm000F__0m00)

## 5. Giải thích Các Quan Hệ và Thuộc Tính

- **Employee** tương tác với **PaymentService** để chọn và cập nhật **PaymentMethod**, và với **TimecardService** để quản lý thông tin chấm công.
- **PaymentMethod** là lớp trừu tượng, chứa các lớp con là **DirectDeposit**, **Mail**, và **Pickup** với các chi tiết thanh toán khác nhau.
- **TimecardService** chịu trách nhiệm tương tác với **ProjectManagementDB** để lấy thông tin mã dự án cho thẻ chấm công.
