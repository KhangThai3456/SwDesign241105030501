# Lab 5

## 1. Exercise: Use-Case Design, Part 1

## 1.1 Run Payroll (with ss interface)

![Use Case Diagram](https://www.planttext.com/api/plantuml/png/T99DJiCm48NtFiN8-wgYFniMgAYj20iab03xKJAfB3bsiIU2274o5Xo9As2diHAXi7EUFxrvR-AVh--TPtJSDbfWoTQ1p78e6EjQ0dh8yYGVcxEs7L4lXu-atrQDChtOduHmL3AQaoQGZzWvgpKKdMTg97m8WDPJYJvSFg314q7oXNjJMzSWAtknUzvVJV4zwhBLo0G5QdJTmAncB9_mVSPjFINlo92BPY6Yr-eyC9ifywBeRHW6cVAXRHgw5Pz2X3qj5ZSn9bp7DLJBOwLuUI1DFDQI8xUAN4wlBNbElgbLZ3cIwqZ-KqRqQnx0JGJ_Tl5IXEa3iOt4N9DnMczIaAcI0R2Tv8_19x76_n2J7QXgoqikiGiMyHtz0W00__y30000)

## Giải thích các Use-Case

### Manage Employee Information
- **Mô tả**: Đây là use-case cho phép nhân viên HR quản lý thông tin nhân viên trong hệ thống. Các chức năng bao gồm thêm mới, chỉnh sửa và xóa thông tin nhân viên.
- **Tác nhân**: HR Staff.
- **Chi tiết**:
  - HR Staff có thể thêm thông tin mới cho nhân viên như tên, chức vụ, lương cơ bản, giờ làm việc, v.v.
  - Chỉnh sửa các thông tin hiện có hoặc xóa nhân viên khỏi hệ thống nếu họ không còn làm việc.

### Calculate Salary
- **Mô tả**: Use-case này cho phép nhân viên HR yêu cầu hệ thống tính toán lương cho các nhân viên. Lương sẽ được tính dựa trên các yếu tố như số giờ làm việc, mức lương cơ bản, phụ cấp, thuế, và các khoản khấu trừ.
- **Tác nhân**: HR Staff.
- **Chi tiết**:
  - HR Staff nhập vào số giờ làm việc, các loại phụ cấp (nếu có), các khoản khấu trừ, và mức thuế áp dụng cho nhân viên.
  - Hệ thống sẽ tính toán lương sau khi trừ thuế và các khoản khác.

### Manage Tax Information
- **Mô tả**: Use-case này cho phép nhân viên HR quản lý thông tin thuế của các nhân viên. Điều này bao gồm việc nhập, chỉnh sửa hoặc xóa thông tin thuế, bao gồm mức thuế suất và các quy định về thuế.
- **Tác nhân**: HR Staff.
- **Chi tiết**:
  - HR Staff có thể thay đổi mức thuế suất dựa trên quy định mới của nhà nước hoặc thông tin thuế cá nhân của nhân viên.
  - Thông tin thuế này được sử dụng trong quá trình tính toán lương.

### Generate Payslip
- **Mô tả**: Use-case này cho phép Admin tạo và gửi phiếu lương cho các nhân viên. Phiếu lương sẽ hiển thị các thông tin về lương cơ bản, các khoản phụ cấp, thuế, và số tiền cuối cùng mà nhân viên nhận được.
- **Tác nhân**: Admin.
- **Chi tiết**:
  - Admin có thể tạo phiếu lương cho từng nhân viên sau khi lương được tính toán.
  - Phiếu lương có thể được tạo dưới dạng PDF hoặc các định dạng khác và gửi cho nhân viên.

### View Salary History
- **Mô tả**: Use-case này cho phép nhân viên xem lịch sử lương của mình, bao gồm các lần trả lương trước đây, số tiền lương đã nhận và các khoản khấu trừ hoặc phụ cấp.
- **Tác nhân**: Employee.
- **Chi tiết**:
  - Nhân viên có thể truy cập và xem các phiếu lương đã được tạo trước đó trong hệ thống.
  - Các thông tin trong lịch sử lương bao gồm số tiền lương cơ bản, các khoản khấu trừ, và các khoản phụ cấp.

### Send Payslip to Employee
- **Mô tả**: Đây là use-case cho phép HR gửi phiếu lương cho nhân viên sau khi đã tính toán xong và tạo phiếu lương. Phiếu lương có thể được gửi qua email hoặc tải xuống dưới dạng tệp.
- **Tác nhân**: HR Staff.
- **Chi tiết**:
  - Sau khi phiếu lương được tạo, HR Staff gửi phiếu lương cho từng nhân viên qua email hoặc cung cấp liên kết tải về.

### Calculate Tax Deduction
- **Mô tả**: Use-case này là một phần trong quá trình tính toán lương, nơi hệ thống sẽ tính toán số tiền thuế phải trả của nhân viên dựa trên các quy định thuế hiện hành.
- **Tác nhân**: HR Staff.
- **Chi tiết**:
  - Hệ thống sẽ tính toán thuế thu nhập cá nhân của nhân viên dựa trên mức thuế suất và các thông tin thuế liên quan.

## Mô tả các tác nhân

### HR Staff
- **Mô tả**: Nhân viên HR là người quản lý thông tin nhân viên và các tác vụ liên quan đến lương và thuế trong hệ thống. Họ sẽ sử dụng hệ thống để thêm, sửa, xóa thông tin nhân viên, tính toán lương, quản lý thuế, tạo và gửi phiếu lương.
- **Vai trò**:
  - Quản lý thông tin nhân viên.
  - Tính toán và cập nhật lương cho nhân viên.
  - Quản lý các thông tin thuế và điều chỉnh mức thuế khi cần thiết.
  - Gửi phiếu lương cho nhân viên.

### Employee
- **Mô tả**: Nhân viên là người sử dụng hệ thống để theo dõi lịch sử lương của mình. Họ có thể xem các phiếu lương đã nhận trong quá khứ và kiểm tra các khoản thuế, khấu trừ, phụ cấp.
- **Vai trò**:
  - Xem lịch sử lương.
  - Nhận thông báo về phiếu lương.

### Admin
- **Mô tả**: Quản trị viên là người chịu trách nhiệm tạo và gửi phiếu lương cho nhân viên. Admin cũng có quyền truy cập vào các chức năng liên quan đến việc tạo phiếu lương và quản lý các quyền truy cập của người dùng khác.
- **Vai trò**:
  - Tạo và gửi phiếu lương.
  - Quản lý quyền truy cập và các tác vụ của nhân viên HR và nhân viên.

## 1.1.2 Run Payroll (with Security)
