# Lab 3

## 1. Subsystem context diagram

    a) Sơ đồ hệ thống con của [banksystem](//https://www.planttext.com/api/plantuml/png/f58zJiCm5DvzYhUrIBG7gAAeWga3KYLEu3fkRJMnW-rKHC3Cm08tA0D28274MWyCxKLy0gw0dJIGjcnuyC_tllVUzzd-ifz3RR0oHPQY3cpkdRqJ3CICRLumaFKZ0SFMIm_bpAsU1IpMou2yPdLG6wgeD6LEOU9M7s9MmGoqis-GEFlaaIX29CLQmnYNIgRfgHGch5Jv4AaFSGnN2C9GXTZokaVe1Y4kV8if9XH69rZCpqlVCcl82SsbvgQBVGfXbCm7qEoEmMVAa3A0C8_4LAeC6ov5LVT7KiNsIgWmt9Hnl8tivRG9BKOjPwpaPUaPkfZeMbyUa5zJ_z3PWJDd7pXS55W0S_OMPjpPzxyU1nrUSAyNxzpR01AkA36D8Wsr_GN7gCsBhllzVOCxX52uiN0GsFE1XbGa_eDz0m00__y30000)
  
    b) Giải thích
      - PayrollController: Được biểu diễn là một lớp control, có phương thức runPayroll().
      - IBankSystem: Được biểu diễn là một interface có phương thức deposit(aPaycheck: Paycheck, intoBank: BankInformation), mô tả chức năng nạp tiền.
      - BankSystemProxy: Biểu diễn một hệ thống con BankSystem dưới dạng subsystem, thể hiện hành động deposit.
      - Paycheck và BankInformation: Được biểu diễn là các thực thể (entity), đóng vai trò là các đối tượng dữ liệu được truyền vào trong quá trình xử lý của BankSystem.
      - Mối quan hệ:
        -  **PayrollController**: liên kết với IBankSystem để thực hiện hành động deposit.
        -  **BankSystemProxy**: thực hiện IBankSystem.
        -  **IBankSystem**: phụ thuộc vào Paycheck và BankInformation trong quá trình hoạt động. 