# Lab 6: Thiết kế lớp hệ thống Payroll System
--


## 1. Xác định các operations

## Maintain Timecard

![Class Diagram](https://www.planttext.com/api/plantuml/png/V9EnJiCm48PtFyMf2orgArWZX2fK993Q2IHcDpwb5evTRATIXPYPcPbu0XuW0mDFqYVW5R1JEqtImfBeVltvVF-TyrD-JOobsXQv8EG4PjloVGNN-Kge3I991JMcBk6P08m0GtaxJO1BMscIvfZ0dTLSPfN0SEMeEKhRa04oj94sHKkvCFr1or2i6BNOzJJnmoDinrWhpiZBFiCzpp6bceKCiGmPR2YR6MAkP9_VoqjLQFEWz2Eo19Wg5cAd-puJcBfdJ1RFE9wCCkOfDnxNhw0Hzq_tSoffXheJ8gYTB8utuyPUHDTbF3OA_UXCQb8ysZirvcgD1-OmegQpaVLg4uVLxzoBmK4xZNn-4enkGgvGXJojmOwWkfuUikjwjoh9MWf0IaLQ2FUDPqqBJIrNqc-WtXY0KDb-0ntiiCrihMI-BTyuF1LKmd9RlaB6j-KdXVJx8mNXuv3w3-cTzs0qWjxPU7pQsr-w15ADhZb3QYawtQl-Ee452YKp0rQHxhB_HEULmP0unGQvuTAOAdT729cueFvl_mK00F__0m00)

## Lớp **Employee** (Nhân viên)
Lớp `Employee` lưu trữ thông tin của nhân viên trong hệ thống. Mỗi nhân viên có các thuộc tính như ID nhân viên, tên và phòng ban làm việc.

### Thuộc tính:
- `employeeID` (int): ID duy nhất của nhân viên.
- `name` (String): Tên của nhân viên.
- `department` (String): Phòng ban làm việc của nhân viên.

### Phương thức (Operations):
- `getEmployeeDetails()` (String): Trả về thông tin chi tiết của nhân viên, bao gồm ID, tên và phòng ban.
- `updateEmployeeDetails(name: String, department: String)` (void): Cập nhật thông tin tên và phòng ban của nhân viên.

## Lớp **Timecard** (Thẻ Chấm Công)
Lớp `Timecard` đại diện cho một thẻ chấm công của nhân viên, chứa thông tin về số giờ làm việc và ngày làm việc.

### Thuộc tính:
- `timecardID` (int): ID của thẻ chấm công.
- `employee` (Employee): Tham chiếu đến nhân viên sở hữu thẻ chấm công.
- `hoursWorked` (double): Số giờ làm việc được ghi nhận trong thẻ chấm công.
- `date` (Date): Ngày làm việc.

### Phương thức (Operations):
- `getTimecardDetails()` (String): Trả về chi tiết về thẻ chấm công, bao gồm ID, số giờ làm việc và ngày làm việc.
- `addWorkHours(hours: double)` (void): Thêm số giờ làm việc vào thẻ chấm công.

## Lớp **TimecardManager** (Quản lý Thẻ Chấm Công)
Lớp `TimecardManager` quản lý tất cả các thẻ chấm công trong hệ thống. Nó cung cấp các phương thức để thêm, xóa hoặc lấy thông tin về thẻ chấm công của nhân viên.

### Thuộc tính:
- `timecards` (List<Timecard>): Danh sách các thẻ chấm công trong hệ thống.

### Phương thức (Operations):
- `addTimecard(timecard: Timecard)` (void): Thêm một thẻ chấm công mới vào danh sách.
- `removeTimecard(timecardID: int)` (void): Xóa một thẻ chấm công khỏi hệ thống dựa trên ID của thẻ.
- `getTimecardByEmployee(employeeID: int)` (List<Timecard>): Lấy danh sách các thẻ chấm công của nhân viên theo ID nhân viên.

## Lớp **Workday** (Ngày Làm Việc)
Lớp `Workday` lưu trữ thông tin về một ngày làm việc cụ thể của nhân viên, bao gồm giờ vào và giờ ra.

### Thuộc tính:
- `date` (Date): Ngày làm việc.
- `startTime` (Time): Giờ vào làm.
- `endTime` (Time): Giờ ra làm.

### Phương thức (Operations):
- `calculateWorkDuration()` (double): Tính tổng số giờ làm việc trong một ngày dựa trên giờ vào và giờ ra.
- `logWorkHours(startTime: Time, endTime: Time)` (void): Ghi lại giờ vào và giờ ra của nhân viên trong ngày làm việc.

---

# Tính toán các quan hệ giữa các lớp

## Quan hệ giữa **Employee** và **Timecard**
- Mỗi nhân viên có thể có nhiều thẻ chấm công, nhưng mỗi thẻ chấm công chỉ thuộc về một nhân viên duy nhất.
- Mối quan hệ này là **1:N** (Một nhân viên có thể có nhiều thẻ chấm công).

**Mô tả**: 
Một nhân viên (`Employee`) có thể tạo ra nhiều thẻ chấm công (`Timecard`) trong suốt quá trình làm việc. Các thẻ chấm công sẽ lưu trữ thông tin về số giờ làm việc của nhân viên vào các ngày cụ thể.

## Quan hệ giữa **TimecardManager** và **Timecard**
- `TimecardManager` quản lý nhiều thẻ chấm công trong hệ thống. 
- Mối quan hệ này là **1:N** (Một `TimecardManager` có thể quản lý nhiều `Timecard`).

**Mô tả**:
Lớp `TimecardManager` lưu trữ và quản lý tất cả các thẻ chấm công (`Timecard`) trong hệ thống. Nó cung cấp các phương thức để thêm, xóa hoặc lấy thông tin thẻ chấm công theo yêu cầu.

## Quan hệ giữa **Workday** và **Timecard**
- Mỗi thẻ chấm công có thể có một đối tượng `Workday` ghi lại giờ vào và giờ ra trong một ngày cụ thể.
- Mối quan hệ này là **1:1** (Mỗi thẻ chấm công có một ngày làm việc tương ứng).

**Mô tả**:
Lớp `Workday` ghi lại thông tin về một ngày làm việc của nhân viên, bao gồm thời gian bắt đầu và kết thúc. Một `Timecard` sẽ liên kết với một `Workday` để lưu trữ các thông tin này.

## BankSystem

![Class Diagram](https://www.planttext.com/api/plantuml/png/X9N1RXiX48Rl-nGZN-9KTjHShSfAd3tKKjL3upm0tYKswYwiW8rbLNco7F98VOK22-p0EgalDiFmp_3nW_--lTyfJQJkswOehk2X8Kh1awAogE9F-5E0-IoXDuDj2Ijur9BnWuzoqj8yHkfQKhCy2tT7mUdFljqRqMoAjeGrOz150GvKsmws_5dChzCb07rN4qtZlEqZP2n21sF0rHw7hbuOMkaNmUgiQebhlevyxgjAz5nxH7uKAP5XV7cRUz8GNbbUjUZt3KLaJSo1JrHsvuvUeh8PT5o3I0cWffrGJCz9QvU7oMo39wQFjIIdpxDCcNkyb-a9Q4cuUZOpgSx2TA4quqGpmRt4Ad2AHH3GdTKXbKttK54aWjLZREf2QmKJAyrN8EXwoaaZaPHjWXrYkuWvwgcasjX7JObqKbJ6TYXrFgMwmnlvm6CRmdy_dfMchISo1dAdsMlsWodzpRUyHgQASzPQwoc3E8zwMeSzLv8Qd5vrRkK6YowmE_4T2ino_spEta79tVXuvL0OGoIPYnQGMouxM2oExNNf4BuR04AU9qMkBy8P5CpxOb4WAjavIzgA5nfpjkNaiN6d_Oisxfge8-jKuPxRsUqCbakOVRsv-JABpyiAn8ch8WpJ97nTLi64L1N8DEc2f-71QGadXy_onkh_JKrx2Ed57UMr_NVv1m00__y30000)

## **Lớp `User`**

### Thuộc tính:
- **userID**: Mã định danh của người dùng (String).
- **name**: Tên của người dùng (String).
- **address**: Địa chỉ của người dùng (String).
- **phoneNumber**: Số điện thoại của người dùng (String).
- **email**: Địa chỉ email của người dùng (String).

### Các phép toán (Operations):
- **getUserInfo()**: 
  - Trả về thông tin chi tiết của người dùng dưới dạng một chuỗi.
  - **Trả về**: String (Thông tin người dùng).
  
- **updateUserInfo(name: String, address: String, phone: String, email: String)**: 
  - Cập nhật thông tin của người dùng.
  - **Tham số**: 
    - `name`: Tên mới của người dùng.
    - `address`: Địa chỉ mới của người dùng.
    - `phone`: Số điện thoại mới.
    - `email`: Địa chỉ email mới.
  - **Trả về**: void (Không có giá trị trả về).
  
- **getUserID()**: 
  - Trả về mã định danh của người dùng.
  - **Trả về**: String (Mã ID của người dùng).

## **Lớp `Account`**

### Thuộc tính:
- **accountNumber**: Số tài khoản của người dùng (String).
- **balance**: Số dư tài khoản (double).
- **user**: Tham chiếu đến đối tượng `User` mà tài khoản thuộc về.
- **accountType**: Loại tài khoản (String) ví dụ: tiết kiệm, thanh toán.

### Các phép toán (Operations):
- **getBalance()**:
  - Trả về số dư hiện tại của tài khoản.
  - **Trả về**: double (Số dư tài khoản).
  
- **deposit(amount: double)**:
  - Nạp tiền vào tài khoản.
  - **Tham số**: 
    - `amount`: Số tiền muốn nạp vào tài khoản.
  - **Trả về**: void (Không có giá trị trả về).
  
- **withdraw(amount: double)**:
  - Rút tiền từ tài khoản.
  - **Tham số**: 
    - `amount`: Số tiền muốn rút từ tài khoản.
  - **Trả về**: void (Không có giá trị trả về).
  
- **getAccountNumber()**:
  - Trả về số tài khoản của người dùng.
  - **Trả về**: String (Số tài khoản).
  
- **transfer(amount: double, destinationAccount: Account)**:
  - Chuyển tiền từ tài khoản này sang tài khoản khác.
  - **Tham số**: 
    - `amount`: Số tiền muốn chuyển.
    - `destinationAccount`: Tài khoản đích nhận tiền.
  - **Trả về**: void (Không có giá trị trả về).

## **Lớp `Transaction`**

### Thuộc tính:
- **transactionID**: Mã giao dịch (String).
- **date**: Ngày thực hiện giao dịch (Date).
- **amount**: Số tiền trong giao dịch (double).
- **transactionType**: Loại giao dịch (String), ví dụ: rút tiền, chuyển khoản, nạp tiền.
- **account**: Tham chiếu đến tài khoản mà giao dịch liên quan.

### Các phép toán (Operations):
- **getTransactionDetails()**:
  - Trả về chi tiết về giao dịch.
  - **Trả về**: String (Thông tin giao dịch).
  
- **processTransaction()**:
  - Xử lý giao dịch và thực hiện thao tác tương ứng (rút tiền, nạp tiền, chuyển khoản).
  - **Trả về**: void (Không có giá trị trả về).
  
- **getTransactionID()**:
  - Trả về mã định danh của giao dịch.
  - **Trả về**: String (Mã giao dịch).

## **Lớp `BankSystem`**

### Thuộc tính:
- **accounts**: Danh sách các tài khoản trong hệ thống (List<Account>).
- **users**: Danh sách các người dùng trong hệ thống (List<User>).
- **transactions**: Danh sách các giao dịch trong hệ thống (List<Transaction>).

### Các phép toán (Operations):
- **createAccount(user: User, accountType: String)**:
  - Tạo một tài khoản mới cho người dùng.
  - **Tham số**: 
    - `user`: Người dùng sở hữu tài khoản.
    - `accountType`: Loại tài khoản (ví dụ: tiết kiệm, thanh toán).
  - **Trả về**: Account (Tài khoản mới được tạo).

- **getAccountByNumber(accountNumber: String)**:
  - Trả về tài khoản dựa trên số tài khoản.
  - **Tham số**: 
    - `accountNumber`: Số tài khoản cần tìm.
  - **Trả về**: Account (Tài khoản tương ứng với số tài khoản).
  
- **createTransaction(account: Account, amount: double, transactionType: String)**:
  - Tạo một giao dịch mới cho tài khoản.
  - **Tham số**: 
    - `account`: Tài khoản thực hiện giao dịch.
    - `amount`: Số tiền trong giao dịch.
    - `transactionType`: Loại giao dịch (ví dụ: chuyển khoản, nạp tiền).
  - **Trả về**: Transaction (Giao dịch được tạo).
  
- **getTransactionHistory(account: Account)**:
  - Lấy lịch sử giao dịch của tài khoản.
  - **Tham số**: 
    - `account`: Tài khoản cần lấy lịch sử giao dịch.
  - **Trả về**: List<Transaction> (Danh sách giao dịch của tài khoản).
  
- **addUser(user: User)**:
  - Thêm người dùng vào hệ thống.
  - **Tham số**: 
    - `user`: Người dùng muốn thêm vào hệ thống.
  - **Trả về**: void (Không có giá trị trả về).
  
- **removeUser(userID: String)**:
  - Xóa người dùng khỏi hệ thống.
  - **Tham số**: 
    - `userID`: Mã ID của người dùng cần xóa.
  - **Trả về**: void (Không có giá trị trả về).

## Quan hệ Giữa Các Lớp

- Một người dùng (`User`) có thể sở hữu nhiều tài khoản (`Account`).
- Mỗi tài khoản có thể có nhiều giao dịch (`Transaction`).
- Hệ thống ngân hàng (`BankSystem`) quản lý người dùng, tài khoản và giao dịch.

---

## Xác định các trạng thái

