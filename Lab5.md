# Lab 5

## 1. Exercise: Use-Case Design, Part 1

## 1.1 Use-Case Realization - Run Payroll

### 1.1.1 Run Payroll (with ss interface)
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

![Use Case Diagram](https://www.planttext.com/api/plantuml/png/X9DBJiCm48RtFiKe-wg2lbcWLcr5MI2XXB8V9TCgakE4s154Y9Enu4XSWTXncjGDi7Cyd_z_Nld-_5fAXRag4iumL6aEtiw7GE7Xu05AsFdDzIfAOc7kpAcvtYOPJqiY4wa-6CifL2YEdDeWFA308oKa50IbL9HuyCu02aaXIjBYqN0RnMgu8KwAu4nrlxxgiiynlPu0k1U7D4zGnQcmy3NxE4iYG8vv2MlaOS4Ds9z30n3KBwpSg9zvmZVOK5I47UUnuwoP_ogluqRkifH9bzndKMFiLmUBJ1tFHombZpEu8q7v7zNQE85zOELcNIOW4JLnKAaxbNb_etUnh3QZxBSrmpi7hTf2grMxDnZSwed3pQat9zisFD9XdruAaWek1zmX9nqXjydCRB85Pnfqko8zLhbROg69lW9Qjxb6VcqRqudNu5Y3gopZfRD9JATSCrFDk5DdoqfT_wti1m00__y30000)

## Giải thích các Use-Case

### Employee Management System

#### **Add/Edit/Delete Employee**
- **Mô tả**: Quản lý thông tin nhân viên, bao gồm thêm, chỉnh sửa hoặc xóa nhân viên khỏi hệ thống.
- **Tác nhân**: HR Staff.
- **Chi tiết**:
  - HR Staff có thể thêm nhân viên mới vào hệ thống, sửa thông tin của nhân viên đã có hoặc xóa nhân viên khi họ nghỉ việc hoặc chuyển công tác.
  - Các thông tin như tên, chức vụ, ngày vào làm, mức lương, giờ làm việc sẽ được cập nhật.

#### **View Employee Information**
- **Mô tả**: Xem thông tin chi tiết về nhân viên.
- **Tác nhân**: HR Staff.
- **Chi tiết**:
  - HR Staff có thể tra cứu thông tin cá nhân, thông tin công việc, lịch sử công tác của nhân viên để hỗ trợ các quyết định về nhân sự.

### Salary Calculation System

#### **Calculate Salary**
- **Mô tả**: Tính toán lương cho nhân viên dựa trên các yếu tố như số giờ làm việc, mức lương cơ bản, phụ cấp, khấu trừ và thuế.
- **Tác nhân**: HR Staff.
- **Chi tiết**:
  - HR Staff nhập các thông tin về số giờ làm việc, các khoản phụ cấp, các khoản khấu trừ thuế và bảo hiểm.
  - Hệ thống tính toán tổng lương phải trả cho nhân viên sau khi áp dụng các khoản khấu trừ.

#### **Calculate Tax Deduction**
- **Mô tả**: Tính toán các khoản thuế cần khấu trừ từ lương nhân viên.
- **Tác nhân**: HR Staff.
- **Chi tiết**:
  - Hệ thống sẽ tự động tính toán số tiền thuế thu nhập cá nhân cần khấu trừ từ lương nhân viên dựa trên mức thuế suất và thông tin thuế hiện tại.

### Tax Management System

#### **Manage Tax Information**
- **Mô tả**: Quản lý thông tin thuế của nhân viên, bao gồm việc nhập, chỉnh sửa các thông tin về thuế, mức thuế suất, v.v.
- **Tác nhân**: HR Staff.
- **Chi tiết**:
  - HR Staff sẽ nhập thông tin thuế của nhân viên khi họ gia nhập công ty, cập nhật thay đổi thuế suất hoặc điều chỉnh mức thuế trong trường hợp có thay đổi pháp luật.

#### **Update Tax Rate**
- **Mô tả**: Cập nhật mức thuế suất khi có sự thay đổi từ nhà nước hoặc tổ chức liên quan.
- **Tác nhân**: HR Staff.
- **Chi tiết**:
  - HR Staff sẽ điều chỉnh mức thuế suất cho nhân viên theo các quy định thuế mới của nhà nước hoặc các quy định pháp lý khác.

### Payslip Generation System

#### **Generate Payslip**
- **Mô tả**: Tạo phiếu lương cho nhân viên, bao gồm các thông tin như lương cơ bản, phụ cấp, thuế và các khoản khấu trừ.
- **Tác nhân**: Admin.
- **Chi tiết**:
  - Admin sẽ tạo phiếu lương cho nhân viên sau khi tính toán xong lương và các khoản khấu trừ.
  - Phiếu lương sẽ được xuất dưới dạng tài liệu điện tử (ví dụ: PDF) và gửi tới nhân viên.

#### **Send Payslip to Employee**
- **Mô tả**: Gửi phiếu lương cho nhân viên qua email hoặc hệ thống nội bộ.
- **Tác nhân**: HR Staff.
- **Chi tiết**:
  - Sau khi phiếu lương được tạo, HR Staff sẽ gửi phiếu lương qua email cho nhân viên hoặc cung cấp liên kết để nhân viên tải về từ hệ thống.

### Salary History System

#### **View Salary History**
- **Mô tả**: Nhân viên có thể xem lại lịch sử lương của mình, bao gồm các lần trả lương trước đây.
- **Tác nhân**: Employee.
- **Chi tiết**:
  - Nhân viên có thể kiểm tra các phiếu lương đã nhận trong quá khứ, xem các khoản phụ cấp, thuế, khấu trừ và tổng số tiền đã nhận.

## Mô tả các tác nhân

### HR Staff
- **Mô tả**: Nhân viên HR là người quản lý thông tin nhân viên, tính toán lương và xử lý các tác vụ liên quan đến thuế và phiếu lương trong hệ thống.
- **Vai trò**:
  - Quản lý thông tin nhân viên (thêm, sửa, xóa).
  - Tính toán lương và quản lý các thông tin thuế của nhân viên.
  - Tạo và gửi phiếu lương cho nhân viên.

### Admin
- **Mô tả**: Quản trị viên chịu trách nhiệm tạo và gửi phiếu lương cho nhân viên, quản lý các quyền truy cập và giám sát các tác vụ của hệ thống.
- **Vai trò**:
  - Quản lý quyền truy cập của HR Staff và nhân viên.
  - Tạo và gửi phiếu lương cho nhân viên.

### Employee
- **Mô tả**: Nhân viên là người sử dụng hệ thống để theo dõi và xem lịch sử lương của mình, nhận phiếu lương và cập nhật thông tin cá nhân khi cần thiết.
- **Vai trò**:
  - Xem lịch sử lương và các phiếu lương đã nhận.
  - Nhận thông báo về phiếu lương qua email hoặc hệ thống nội bộ.

## 1.1.3 Run Payroll (with Distribution)

![Use Case Diagram](https://www.planttext.com/api/plantuml/png/T9DBJiCm54NdNiLJvfMQ_ii05GgY32gXGZj_IjmgmdKYsn54Y9KnO4bi0Tj9MZkVp7BloRt-lFpz_AwaGg7oCoC48vKA23Oxs2B74nK1e8JDRbixZ-UCfGMbLjSlX6GOlMloQbMVdYbN0NmHq4ykQOHICtTn35x4VXtwn3wBKT4B1C_yc5Rao2SF2VtevCRasrdM2nOYPGpMoAASeKfItbfMxL5uHOQYg88cFlL4EHK6qf6I9Lb5JRswUmqT4oK1UGmFDCuZqoXRbUKXGOrNMRDEo8snsBovGtFOi4calgEYLMKFgWNPe4N_3YszeragL0KllTRIIlYfrUUcsAFtKi9X3_s6dmqoD8Lw-60mk3NlS6CdA72qaT7AcN7biP7DlbrnOiJBLRlEr3ZrGbnZPepo5bnvtYqlkbgNVTdXiDS9VOVeAMzNNCL61LbH7flV-Hy00F__0m00)

## Giải Thích:
- HR Manager (Quản lý nhân sự) có thể thực hiện các chức năng như Thêm nhân viên, Cập nhật thông tin nhân viên, Tính lương, Quản lý phụ cấp và Tạo báo cáo.
- Employee (Nhân viên) có thể xem Lịch sử thanh toán và Tạo báo cáo thanh toán.
- Các chức năng khác như tính lương, quản lý phụ cấp, khấu trừ được thực hiện bởi quản lý nhân sự.

## Các hệ thống con

Trong hệ thống Payroll System, các hệ thống con chính bao gồm:

### Quản lý nhân viên (Employee Management)
- **Add Employee**: Quản lý nhân sự thêm mới nhân viên.
- **Update Employee Info**: Cập nhật thông tin nhân viên.
- **View Employee Info**: Xem thông tin nhân viên.

### Tính lương (Payroll Calculation)
- **Calculate Salary**: Tính toán lương cho nhân viên.
- **Generate Payslip**: Tạo phiếu lương cho nhân viên.

### Quản lý phụ cấp và khấu trừ (Benefits and Deductions)
- **Manage Benefits**: Quản lý các khoản phụ cấp của nhân viên.
- **Manage Deductions**: Quản lý các khoản khấu trừ như thuế, bảo hiểm.

### Lịch sử thanh toán (Payment History)
- **View Payment History**: Xem lịch sử thanh toán của nhân viên.
- **Generate Payment Report**: Tạo báo cáo thanh toán.

### Báo cáo (Reporting)
- **Generate Payroll Report**: Tạo báo cáo chi tiết về chi trả lương.
- **Generate Tax Report**: Tạo báo cáo thuế cho nhân viên hoặc công ty.

## 1.1.4 Run Payroll (with OODBMS Persistency)

![Use Case Diagram](https://www.planttext.com/api/plantuml/png/R9BDYi8m483lUOgXTm-srkEYYEXbOQcx3p34GOBv8qaFHNmo3_j8-mgRQYmXz3PVycLcCidVutVZ0xhGAycG1-DWUrP2f_ZOfM2lh3G3KS9Fr7WXnvX5VeqHL5yuE2Cbd0OVI5LmOm2z9uu-RhxqAOcl03tyx9QvSqA9Re0TIjvB3CBePDKpcROXa3wZvfIaPaRw5egkH5ReIx9MkNKWJGu3GMpTIs6Jqyuw7LdZmhlnDOlISqwmM7oac-HS5zmKl2guBVXPuDXbsIUeSsXoQCT3xnbdYOkbvQYb1vpAtHdRn8cElu3z0m00__y30000)

## Giải thích
- Admin có quyền truy cập vào tất cả các chức năng trong hệ thống, từ quản lý nhân viên, tính lương, quản lý ngày công, đến việc tạo báo cáo.
- HR chủ yếu xử lý các tác vụ liên quan đến nhân viên, tính lương, chấm công và phát hành bảng lương.
- Employee có thể truy cập và xem bảng lương của mình, cũng như chỉnh sửa thông tin cá nhân.
- Manager chỉ có quyền xem báo cáo tổng hợp về lương và các chỉ số khác của nhân viên.

## Các chức năng chính trong hệ thống

Hệ thống Payroll System bao gồm các chức năng chính sau đây để quản lý thông tin nhân viên, tính lương và tạo các báo cáo:

### Quản lý nhân viên (Employee Management)
- **Chức năng**: Thêm, sửa, xóa thông tin nhân viên trong hệ thống.
- **Mô tả**: Quản lý thông tin cá nhân của nhân viên, bao gồm tên, vị trí công việc, mức lương, ngày vào làm, và các dữ liệu liên quan khác.
- **Các tác vụ**:
  - Thêm mới nhân viên.
  - Cập nhật thông tin nhân viên.
  - Xóa nhân viên khỏi hệ thống.
  
### Tính lương (Salary Calculation)
- **Chức năng**: Tính toán lương cơ bản, lương thêm giờ, lương thưởng, và các khoản khấu trừ.
- **Mô tả**: Hệ thống tính toán lương cho từng nhân viên dựa trên các yếu tố như mức lương cơ bản, số giờ làm thêm, các khoản thuế, bảo hiểm và các khoản khấu trừ khác.
- **Các tác vụ**:
  - Tính lương cơ bản.
  - Tính lương thưởng và các khoản phụ cấp.
  - Tính các khoản khấu trừ như thuế, bảo hiểm xã hội.

### Quản lý ngày công (Attendance Management)
- **Chức năng**: Theo dõi và quản lý ngày công của nhân viên.
- **Mô tả**: Quản lý các ngày vắng mặt, phép năm, nghỉ lễ và ngày công của nhân viên để tính toán các yếu tố liên quan đến lương.
- **Các tác vụ**:
  - Cập nhật ngày vắng mặt.
  - Quản lý phép năm.
  - Theo dõi tình trạng làm việc của nhân viên.

### Quản lý chấm công (Timekeeping)
- **Chức năng**: Theo dõi giờ làm việc của nhân viên, bao gồm giờ vào và giờ ra.
- **Mô tả**: Hệ thống ghi lại thời gian vào làm, thời gian nghỉ và thời gian kết thúc ca làm việc của nhân viên.
- **Các tác vụ**:
  - Đăng ký giờ vào làm.
  - Đăng ký giờ ra về.
  - Quản lý giờ làm thêm.

### Quản lý bảng lương (Payslip Management)
- **Chức năng**: Tạo và phát hành bảng lương cho nhân viên.
- **Mô tả**: Hệ thống tạo bảng lương định kỳ cho nhân viên dựa trên kết quả tính lương, sau đó phát hành và lưu trữ bảng lương.
- **Các tác vụ**:
  - Tạo bảng lương cho nhân viên.
  - Phát hành bảng lương.
  - Lưu trữ bảng lương.

### Quản lý báo cáo (Report Management)
- **Chức năng**: Xuất các báo cáo tổng hợp liên quan đến lương, thuế, bảo hiểm và các khoản chi phí khác.
- **Mô tả**: Hệ thống cung cấp các báo cáo chi tiết về chi phí lương, thuế, bảo hiểm, v.v. cho các bộ phận quản lý.
- **Các tác vụ**:
  - Xuất báo cáo tổng lương.
  - Xuất báo cáo thuế và bảo hiểm.
  - Xuất báo cáo chi phí nhân sự.

---

## Các Actor trong hệ thống

Các actor trong hệ thống Payroll System đại diện cho những người hoặc hệ thống tương tác với hệ thống và thực hiện các chức năng cụ thể.

### Admin
- **Vai trò**: Quản trị viên hệ thống, có quyền truy cập vào tất cả các chức năng và thông tin trong hệ thống.
- **Tác vụ chính**:
  - Quản lý thông tin nhân viên.
  - Quản lý tính lương, bảng lương và các báo cáo.
  - Quản lý quyền truy cập và cài đặt hệ thống.

### HR (Human Resources)
- **Vai trò**: Nhân viên bộ phận nhân sự, chịu trách nhiệm quản lý thông tin nhân viên, tính toán lương và phát hành bảng lương.
- **Tác vụ chính**:
  - Thêm, sửa và xóa thông tin nhân viên.
  - Tính toán và phê duyệt lương.
  - Quản lý bảng lương và các thông tin liên quan đến nhân viên.

### Employee
- **Vai trò**: Nhân viên trong công ty, có quyền truy cập vào các thông tin cá nhân và bảng lương của mình.
- **Tác vụ chính**:
  - Xem thông tin cá nhân và bảng lương.
  - Cập nhật các thông tin cá nhân nếu cần thiết.

### Manager
- **Vai trò**: Quản lý của các bộ phận, có quyền xem các báo cáo tổng hợp về lương và hiệu suất của nhân viên.
- **Tác vụ chính**:
  - Xem báo cáo tổng hợp về lương, thuế, và bảo hiểm.
  - Đánh giá hiệu suất nhân viên dựa trên các báo cáo.
 
## 1.1.5 Run Payroll (with OODBMS Persistency)

![Use Case Diagram](https://www.planttext.com/api/plantuml/png/Z9J1Rk8m48RlUOeHzweDa02NLIbTBKXTTKMfzknDfYZ2iIFRGOrMVR8Uzf7s5TQ0dJeJgFP0b7_oUVu_W-E_xtzkjM7Ar2MFM6QaWdbU5iBTBzVkvcjPSTaWElcT2RP55KKLotRs3WO_MACav_3KQ8Fb07v70Er3lzgjAr6O4m5GQyoOjimyprkN0J0DpukuIpnNEJFOGh0IBzAHmowvnbBkaRORMUZD_i9aJumprS22yQpcp1HIz8BvPmWds7KRNwBkfAYrWv9BqECUbIbA7oqbiwWgti0zvdLsYEIxJSwymDmO53aJsQV3tIZBmmVh6awxrAa1F23Re_US7Jr3nusDlKEi2h7j-Jp8BVoKQWTBMIlV8huv5sR1fRsknFLZRJmOzypijjAyg3vxjsyeK1rcwbZVZEo9-q8RLVog--2evxh6IYhpNwPk0vrM-8xZ2_26lH8okK2kXAxLyL_jygdFUlnAuUhgY_jEGZqaUaJqcEY4w9Je2T5JecSqpmqjq8GnZHZJZ34D6TEKTXQsibm7GsZ5C1IZK8n3aOGY3SKa5DDGp3gc7IFx4bQsvzF7ObAQzKl7aT5QVAOsF5YuupSS5Iab_L8QsOrpQm-0mr4V_GC00F__0m00)

### Các chức năng chính trong hệ thống bao gồm:
- **Quản lý nhân viên (Employee Management)**
- **Tính lương (Salary Calculation)**
- **Quản lý ngày công (Attendance Management)**
- **Quản lý chấm công (Timekeeping)**
- **Quản lý bảng lương (Payslip Management)**
- **Quản lý báo cáo (Report Management)**

---

## Phân tích các hệ thống con

Dựa trên các chức năng trên, chúng ta có thể phân chia hệ thống thành các hệ thống con, mỗi hệ thống con sẽ đảm nhiệm một số tác vụ và quản lý một phần dữ liệu của hệ thống Payroll.

### Quản lý nhân viên (Employee Management)
- **Chức năng**: Thêm, sửa, xóa thông tin nhân viên.
- **Các tác vụ**:
  - Thêm nhân viên mới.
  - Cập nhật thông tin nhân viên.
  - Xóa nhân viên khỏi hệ thống.

### Tính lương (Salary Calculation)
- **Chức năng**: Tính lương cơ bản, lương thưởng, lương thêm giờ và các khoản khấu trừ.
- **Các tác vụ**:
  - Tính lương cơ bản.
  - Tính lương thưởng và các khoản phụ cấp.
  - Tính các khoản khấu trừ như thuế, bảo hiểm xã hội.

### Quản lý ngày công (Attendance Management)
- **Chức năng**: Theo dõi và quản lý ngày công của nhân viên.
- **Các tác vụ**:
  - Cập nhật ngày vắng mặt, phép năm, nghỉ lễ.
  - Theo dõi số ngày làm việc của nhân viên.

### Quản lý chấm công (Timekeeping)
- **Chức năng**: Ghi nhận thời gian vào làm và ra về của nhân viên.
- **Các tác vụ**:
  - Đăng ký giờ vào làm.
  - Đăng ký giờ ra về.
  - Quản lý giờ làm thêm.

### Quản lý bảng lương (Payslip Management)
- **Chức năng**: Tạo và phát hành bảng lương cho nhân viên.
- **Các tác vụ**:
  - Tạo bảng lương cho nhân viên.
  - Phát hành bảng lương.
  - Lưu trữ bảng lương.

### Quản lý báo cáo (Report Management)
- **Chức năng**: Tạo các báo cáo tổng hợp liên quan đến lương, bảo hiểm và thuế.
- **Các tác vụ**:
  - Xuất báo cáo tổng lương.
  - Xuất báo cáo thuế và bảo hiểm.
  - Xuất báo cáo chi phí nhân sự.

---

## Các Actor trong hệ thống

Các **Actor** trong hệ thống Payroll System đại diện cho những người hoặc hệ thống tương tác với hệ thống và thực hiện các chức năng cụ thể.

### **Admin**
- **Vai trò**: Quản trị viên hệ thống, có quyền truy cập vào tất cả các chức năng và thông tin trong hệ thống.
- **Các tác vụ chính**:
  - Quản lý thông tin nhân viên.
  - Quản lý tính lương, bảng lương và các báo cáo.
  - Quản lý quyền truy cập và cài đặt hệ thống.

### **HR (Human Resources)**
- **Vai trò**: Nhân viên bộ phận nhân sự, chịu trách nhiệm quản lý thông tin nhân viên, tính toán lương và phát hành bảng lương.
- **Các tác vụ chính**:
  - Thêm, sửa và xóa thông tin nhân viên.
  - Tính toán và phê duyệt lương.
  - Quản lý bảng lương và các thông tin liên quan đến nhân viên.

### **Employee**
- **Vai trò**: Nhân viên trong công ty, có quyền truy cập vào các thông tin cá nhân và bảng lương của mình.
- **Các tác vụ chính**:
  - Xem thông tin cá nhân và bảng lương.
  - Cập nhật các thông tin cá nhân nếu cần thiết.

### **Manager**
- **Vai trò**: Quản lý của các bộ phận, có quyền xem các báo cáo tổng hợp về lương và hiệu suất của nhân viên.
- **Các tác vụ chính**:
  - Xem báo cáo tổng hợp về lương, thuế, và bảo hiểm.
  - Đánh giá hiệu suất nhân viên dựa trên các báo cáo.
