# Lab 3

## 1. Subsystem context diagram

a) Sơ đồ hệ thống con của [banksystem](https://www.planttext.com/api/plantuml/png/f58zJiCm5DvzYhUrIBG7gAAeWga3KYLEu3fkRJMnW-rKHC3Cm08tA0D28274MWyCxKLy0gw0dJIGjcnuyC_tllVUzzd-ifz3RR0oHPQY3cpkdRqJ3CICRLumaFKZ0SFMIm_bpAsU1IpMou2yPdLG6wgeD6LEOU9M7s9MmGoqis-GEFlaaIX29CLQmnYNIgRfgHGch5Jv4AaFSGnN2C9GXTZokaVe1Y4kV8if9XH69rZCpqlVCcl82SsbvgQBVGfXbCm7qEoEmMVAa3A0C8_4LAeC6ov5LVT7KiNsIgWmt9Hnl8tivRG9BKOjPwpaPUaPkfZeMbyUa5zJ_z3PWJDd7pXS55W0S_OMPjpPzxyU1nrUSAyNxzpR01AkA36D8Wsr_GN7gCsBhllzVOCxX52uiN0GsFE1XbGa_eDz0m00__y30000)
  
b) Giải thích
   - PayrollController: Được biểu diễn là một lớp control, có phương thức runPayroll().
   - IBankSystem: Được biểu diễn là một interface có phương thức deposit(aPaycheck: Paycheck, intoBank: BankInformation), mô tả chức năng nạp tiền.
   - BankSystemProxy: Biểu diễn một hệ thống con BankSystem dưới dạng subsystem, thể hiện hành động deposit.
   - Paycheck và BankInformation: Được biểu diễn là các thực thể (entity), đóng vai trò là các đối tượng dữ liệu được truyền vào trong quá trình xử lý của BankSystem.
   - Mối quan hệ:
     - **PayrollController**: liên kết với IBankSystem để thực hiện hành động deposit.
     -  **BankSystemProxy**: thực hiện IBankSystem.
     -  **IBankSystem**: phụ thuộc vào Paycheck và BankInformation trong quá trình hoạt động.
c) Mô tả hệ thống con, interface của hệ thống con
   - Hệ Thống Con BankSystem:
     - **Chức năng**: Hệ thống con BankSystem chịu trách nhiệm thực hiện các giao dịch ngân hàng, đặc biệt là gửi tiền trực tiếp vào tài khoản ngân hàng của nhân viên. Nó được triển khai để xử lý việc nộp tiền lương vào các tài khoản được chỉ định.
     - **Mục đích**: Cung cấp dịch vụ nộp tiền tự động cho hệ thống trả lương, đảm bảo rằng các khoản lương được gửi đúng vào tài khoản ngân hàng của từng nhân viên.
   - Giao Diện IBankSystem:
     - **Tên Giao Diện**: IBankSystem
     - **Mô Tả**: Đây là giao diện mà hệ thống trả lương (PayrollController) sẽ sử dụng để thực hiện nộp tiền vào tài khoản ngân hàng.
     - **Phương Thức Chính**:
          - **deposit(aPaycheck : Paycheck, intoBank : BankInformation)**: Phương thức này nhận vào một đối tượng Paycheck và thông tin tài khoản ngân hàng (BankInformation). Khi được gọi, nó sẽ thực hiện việc nộp tiền vào tài khoản ngân hàng tương ứng dựa trên thông tin đã cung cấp.
   - Các Thành Phần Liên Quan:
     - **PayrollController**: Đây là thành phần kiểm soát quá trình trả lương và là thành phần gọi phương thức deposit của giao diện IBankSystem để gửi tiền lương vào tài khoản ngân hàng của nhân viên.
     - **Paycheck**: Đối tượng này chứa thông tin về tiền lương của nhân viên, bao gồm số tiền và các thông tin chi tiết khác liên quan đến kỳ lương.
     - **BankInformation**: Đối tượng này lưu trữ thông tin tài khoản ngân hàng của nhân viên, bao gồm số tài khoản, chi nhánh và các thông tin cần thiết để thực hiện giao dịch ngân hàng.

## 2. Analysis class to design element map

   - Ánh xạ từ lớp phân tích (Analysis Class) sang phần tử thiết kế (Design Element) là cách chuyển đổi các khái niệm logic trong phân tích thành các phần tử cụ thể trong thiết kế, nhằm hiện thực hóa yêu cầu chức năng và phi chức năng của hệ thống.

   - Ví dụ
     - **LoginForm** (lớp phân tích) sang LoginForm (phần tử thiết kế)


