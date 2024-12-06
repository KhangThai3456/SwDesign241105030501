# Lab 6: Thiết kế lớp hệ thống Payroll System
--


## 1. Xác định các operations

## 1.1. Maintain Timecard

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

---

## 1.2. BankSystem

![Class Diagram](https://www.planttext.com/api/plantuml/png/V98xRiCm38PtdOBmv1J8qDLJacRfaYMv02qHgL5B2YIwWL7qP1rwf5wXiYCxiXrKWmN_fCYFZz_ldurdTDpe6dPete-jPz92o1gzxvMjbBOn39y2mba3tluFZIx95N1aLvbpj9LOev5KmDusPKrHjLVJURuqdgqcrwi0YYxMLvoZxi8DJrO5VDXAHPzhnM_AuVLVfpFnxfOtNqqozwPjYjivHE2leSO1QonGHk5LpQepg6acaSQgdcW0qX4onRpvmtO5ZAIr2zXyPXzPJmwDHycLDICktxK5yRHjKLI1BaZXkunmQY_p4iixo2FgYxEIl4_8yiLu4kEUE7JCJmUHhbdsdC7JUjtVusWAoBebKb2scKYRa7gdKS83HtKeKG7RJ8WD6HLMNFm1003__mC0)

## Thiết kế hệ thống

### Lớp `BankAccount`
Lớp `BankAccount` đại diện cho một tài khoản ngân hàng và bao gồm các thuộc tính sau:
- `accountNumber`: Số tài khoản (kiểu String)
- `balance`: Số dư tài khoản (kiểu Double)
- `owner`: Chủ sở hữu tài khoản (kiểu `Customer`)

Các phương thức (operations) trong lớp:
- `deposit(amount: Double)`: Nạp tiền vào tài khoản.
- `withdraw(amount: Double)`: Rút tiền từ tài khoản.
- `getBalance()`: Lấy số dư tài khoản.
- `getAccountNumber()`: Lấy số tài khoản.

### Lớp `Customer`
Lớp `Customer` đại diện cho khách hàng của ngân hàng, với các thuộc tính:
- `customerId`: ID của khách hàng (kiểu String)
- `name`: Tên khách hàng (kiểu String)
- `email`: Email khách hàng (kiểu String)

Các phương thức trong lớp:
- `createAccount(accountNumber: String)`: Tạo tài khoản mới cho khách hàng.
- `getAccount()`: Lấy thông tin tài khoản của khách hàng.

### Lớp `Transaction`
Lớp `Transaction` đại diện cho giao dịch ngân hàng, bao gồm các thuộc tính:
- `transactionId`: ID giao dịch (kiểu String)
- `amount`: Số tiền giao dịch (kiểu Double)
- `date`: Ngày thực hiện giao dịch (kiểu Date)
- `transactionType`: Loại giao dịch ("Deposit" hoặc "Withdraw")
- `bankAccount`: Tài khoản liên quan đến giao dịch (kiểu `BankAccount`)

Các phương thức trong lớp:
- `processTransaction()`: Thực hiện giao dịch.
- `getTransactionDetails()`: Lấy thông tin chi tiết về giao dịch.

## Các Phương Thức (Operations) Đã Xác Định

### Lớp `BankAccount`
Lớp `BankAccount` quản lý các tài khoản ngân hàng và các nghiệp vụ tài chính cơ bản. Dưới đây là các phương thức (operations) đã xác định:

#### **`deposit(amount: Double)`**  
- **Mô tả**: Nạp tiền vào tài khoản.
- **Tham số**: `amount`: Số tiền muốn nạp vào tài khoản (kiểu `Double`).
- **Trả về**: Không có giá trị trả về (`void`).
- **Ví dụ**:
    ```java
    account.deposit(1000.0); // Nạp 1000 vào tài khoản
    ```

#### **`withdraw(amount: Double)`**  
- **Mô tả**: Rút tiền từ tài khoản.
- **Tham số**: `amount`: Số tiền muốn rút khỏi tài khoản (kiểu `Double`).
- **Trả về**: Không có giá trị trả về (`void`).
- **Ví dụ**:
    ```java
    account.withdraw(500.0); // Rút 500 từ tài khoản
    ```

#### **`getBalance()`**  
- **Mô tả**: Lấy số dư hiện tại của tài khoản.
- **Trả về**: `Double`: Số dư tài khoản.
- **Ví dụ**:
    ```java
    double balance = account.getBalance(); // Lấy số dư tài khoản
    ```

#### **`getAccountNumber()`**  
- **Mô tả**: Lấy số tài khoản của khách hàng.
- **Trả về**: `String`: Số tài khoản.
- **Ví dụ**:
    ```java
    String accountNumber = account.getAccountNumber(); // Lấy số tài khoản
    ```

### Lớp `Customer`
Lớp `Customer` đại diện cho một khách hàng và có các phương thức sau:

#### **`createAccount(accountNumber: String)`**  
- **Mô tả**: Tạo một tài khoản mới cho khách hàng.
- **Tham số**: `accountNumber`: Số tài khoản (kiểu `String`).
- **Trả về**: Một đối tượng `BankAccount` đại diện cho tài khoản vừa tạo.
- **Ví dụ**:
    ```java
    BankAccount account = customer.createAccount("123456789"); // Tạo tài khoản mới
    ```

#### **`getAccount()`**  
- **Mô tả**: Lấy tài khoản của khách hàng.
- **Trả về**: `BankAccount`: Đối tượng tài khoản của khách hàng.
- **Ví dụ**:
    ```java
    BankAccount account = customer.getAccount(); // Lấy tài khoản của khách hàng
    ```

### Lớp `Transaction`
Lớp `Transaction` đại diện cho các giao dịch ngân hàng. Các phương thức bao gồm:

#### **`processTransaction()`**  
- **Mô tả**: Thực hiện giao dịch (nạp tiền hoặc rút tiền).
- **Trả về**: Không có giá trị trả về (`void`).
- **Ví dụ**:
    ```java
    transaction.processTransaction(); // Xử lý giao dịch
    ```

#### **`getTransactionDetails()`**  
- **Mô tả**: Lấy chi tiết thông tin giao dịch.
- **Trả về**: `String`: Thông tin chi tiết về giao dịch (ví dụ: ID, số tiền, loại giao dịch).
- **Ví dụ**:
    ```java
    String details = transaction.getTransactionDetails(); // Lấy thông tin giao dịch
    ```

## Cài đặt Hệ thống

### Lớp `BankAccount` (Java)
    public class BankAccount {
        private String accountNumber;
        private double balance;
        private Customer owner;
    
        public BankAccount(String accountNumber, Customer owner) {
            this.accountNumber = accountNumber;
            this.owner = owner;
            this.balance = 0.0;
        }
    
        // Nạp tiền vào tài khoản
        public void deposit(double amount) {
            balance += amount;
        }
    
        // Rút tiền từ tài khoản
        public void withdraw(double amount) {
            if (balance >= amount) {
                balance -= amount;
            } else {
                System.out.println("Không đủ số dư.");
            }
        }
    
        // Lấy số dư tài khoản
        public double getBalance() {
            return balance;
        }
    
        // Lấy số tài khoản
        public String getAccountNumber() {
            return accountNumber;
        }
    }

### Lớp `Customer` (Java)

    public class Customer {
        private String customerId;
        private String name;
        private String email;
    
        public Customer(String customerId, String name, String email) {
            this.customerId = customerId;
            this.name = name;
            this.email = email;
        }
    
        // Tạo tài khoản mới cho khách hàng
        public BankAccount createAccount(String accountNumber) {
            return new BankAccount(accountNumber, this);
        }
    
        // Lấy tài khoản của khách hàng
        public BankAccount getAccount() {
            return new BankAccount("12345", this); // Giả sử khách hàng đã có tài khoản
        }
    }

### Lớp `Transaction` (Java)

    public class Transaction {
        private String transactionId;
        private double amount;
        private Date date;
        private String transactionType;
        private BankAccount bankAccount;
    
        public Transaction(String transactionId, double amount, String transactionType, BankAccount bankAccount) {
            this.transactionId = transactionId;
            this.amount = amount;
            this.transactionType = transactionType;
            this.bankAccount = bankAccount;
            this.date = new Date();
        }
    
        // Xử lý giao dịch
        public void processTransaction() {
            if (transactionType.equals("Deposit")) {
                bankAccount.deposit(amount);
            } else if (transactionType.equals("Withdraw")) {
                bankAccount.withdraw(amount);
            }
        }
    
        // Lấy thông tin chi tiết giao dịch
        public String getTransactionDetails() {
            return "Transaction ID: " + transactionId + ", Amount: " + amount + ", Type: " + transactionType;
        }
    }

---

## 1.3. PrintService

![Class Diagram](https://www.planttext.com/api/plantuml/png/Z59BQiCm4Dth5C8h9pI1RaqfsJQKq98JoD8G72oFqSSKIa_MHO_KArJoIDGARLDlF7hlpRoPaJxVFtRM2UEyxXcJlR2MFvbkS4SmKoU1lp8UlsSF7lWPspaWJ2YrnxOUepm43IM6Q4NyQ522jGTuYM2zQlY4dM9lXG-OR75quNpY8w47ePDDYzY368YepuLHazcBge6xA1lo7bI1A9HUm-2-dH8Hzk6y9IXNg-Vy9abkYkICfh7dTIu7db69Ukp1mO-ReEscXXyxw-woxtrit5xRzzB8WCO9_Y4yWLjSJPR4fee7KDrMVBtPXFzskwwerJyLwLglQw8RJVuRotOmgFWolm000F__0m00)

## Các Operations đã xác định

### Lớp `PrintService`

#### `addJob(printJob: PrintJob)`
- **Mô tả**: Thêm một công việc in mới vào hàng đợi.
- **Tham số**: 
  - `printJob`: Đối tượng `PrintJob` đại diện cho công việc in.
- **Trả về**: Không trả về giá trị.
- **Ví dụ**:
    ```java
    printService.addJob(new PrintJob("job001", "Document1"));
    ```

#### `processNextJob()`
- **Mô tả**: Xử lý công việc in tiếp theo trong hàng đợi.
- **Trả về**: Không trả về giá trị.
- **Ví dụ**:
    ```java
    printService.processNextJob();
    ```

---

### Lớp `Printer`

#### `print(job: PrintJob): boolean`
- **Mô tả**: In một công việc in.
- **Tham số**: 
  - `job`: Đối tượng `PrintJob` chứa thông tin công việc cần in.
- **Trả về**: 
  - `boolean`: Trả về `true` nếu in thành công, `false` nếu thất bại.
- **Ví dụ**:
    ```java
    printer.print(printJob);
    ```

---

### Lớp `PrintJob`

#### `startJob()`
- **Mô tả**: Bắt đầu công việc in.
- **Trả về**: Không trả về giá trị.
- **Ví dụ**:
    ```java
    printJob.startJob();
    ```

#### `completeJob()`
- **Mô tả**: Hoàn thành công việc in.
- **Trả về**: Không trả về giá trị.
- **Ví dụ**:
    ```java
    printJob.completeJob();
    ```

---

### Lớp `Queue`

#### `addJob(printJob: PrintJob)`
- **Mô tả**: Thêm một công việc in vào hàng đợi.
- **Tham số**: 
  - `printJob`: Đối tượng `PrintJob`.
- **Trả về**: Không trả về giá trị.
- **Ví dụ**:
    ```java
    queue.addJob(new PrintJob("job002", "Document2"));
    ```

#### `removeJob(printJob: PrintJob)`
- **Mô tả**: Xóa một công việc in khỏi hàng đợi.
- **Tham số**: 
  - `printJob`: Đối tượng `PrintJob` cần xóa.
- **Trả về**: Không trả về giá trị.
- **Ví dụ**:
    ```java
    queue.removeJob(printJob);
    ```

#### `getNextJob()`
- **Mô tả**: Lấy công việc in tiếp theo từ hàng đợi.
- **Trả về**: 
  - `PrintJob`: Công việc in tiếp theo.
- **Ví dụ**:
    ```java
    PrintJob nextJob = queue.getNextJob();
    ```

## Cài đặt Hệ thống

### Lớp `PrintService`

    public class PrintService {
        private Queue jobQueue;
        private Printer printer;
    
        public PrintService(Printer printer) {
            this.jobQueue = new Queue();
            this.printer = printer;
        }
    
        // Thêm công việc vào hàng đợi
        public void addJob(PrintJob printJob) {
            jobQueue.addJob(printJob);
        }
    
        // Xử lý công việc in tiếp theo
        public void processNextJob() {
            PrintJob nextJob = jobQueue.getNextJob();
            if (nextJob != null) {
                nextJob.startJob();
                if (printer.print(nextJob)) {
                    nextJob.completeJob();
                    jobQueue.removeJob(nextJob);
                }
            }
        }
    }

### Lớp `Printer`

    public class Printer {
        private String printerName;
    
        public Printer(String printerName) {
            this.printerName = printerName;
        }
    
        // In một công việc
        public boolean print(PrintJob job) {
            System.out.println("In công việc: " + job.getJobId());
            // Giả lập in thành công
            return true;
        }
    }

### Lớp `PrintJob`

    public class PrintJob {
        private String jobId;
        private String documentName;
        private String status;
    
        public PrintJob(String jobId, String documentName) {
            this.jobId = jobId;
            this.documentName = documentName;
            this.status = "Pending";
        }
    
        // Bắt đầu công việc in
        public void startJob() {
            this.status = "In Progress";
        }
    
        // Hoàn thành công việc in
        public void completeJob() {
            this.status = "Completed";
        }
    
        // Lấy ID công việc
        public String getJobId() {
            return jobId;
        }
    
        // Lấy tên tài liệu
        public String getDocumentName() {
            return documentName;
        }
    }

## 1.4. ProjectManagementDatabase

![Class Diagram](https://www.planttext.com/api/plantuml/png/Z9J1JeD048RlFCM4YzIq1w_4c1fxCQc9jV41LdQ2QvQ5iajZOppx49wCyMYyIuo7FWbFu2kuq2rbeHWvG3B_D_3FFy1F_ZsMYgGgYxZZ7C2qo9yJk4pZEmpK1H4an0Y5cX15ReX49-14oduT7XpGnmYI3I5zc3AfZat3IQK244fDnJEWlxtdm8TbpAW1KupY9RROS-h3NALCX3OSelgBD9g1iuGIrRvpZmkkHpZbt6ZI6xIdUkn4PmVLZcNdozG5YR1LeYY3b2MAnQAbLFlIYUkEycogA6YdfacLIQkz6TC45M6yciSYh6osKDFYS9-xOTlOqFPaPofh5_FAf6TxxTkiWNUE6z5lNyApM0YDQcjc2rsXNaXGbtnez6qUQqJFDaEPt2_WFGQPmbc6wSfRbEV6D5SeCwxcg6pukegwGpEXDfFDCYBWjiYV86H5_a4WMBy4mCjvdVwlq3rouN0q0ZSYOkNMRw4FYwpuV1N0rr__wTRNFT7v88ly7MYHl-dydR5USldp-0K00F__0m00)

## Các operations đã xác định

## Lớp `ProjectManagementDatabase`

Lớp `ProjectManagementDatabase` chịu trách nhiệm quản lý các dự án trong hệ thống. Các phương thức trong lớp này sẽ thao tác với danh sách các dự án và cơ sở dữ liệu.

### Các Operations

- **`addProject(project: Project): void`**
    - **Mô tả**: Thêm một dự án mới vào cơ sở dữ liệu.
    - **Tham số**:
        - `project`: Đối tượng `Project` đại diện cho dự án cần thêm.
    - **Trả về**: Không có giá trị trả về.
  
- **`removeProject(projectId: String): void`**
    - **Mô tả**: Xóa một dự án khỏi cơ sở dữ liệu dựa trên `projectId`.
    - **Tham số**:
        - `projectId`: ID của dự án cần xóa.
    - **Trả về**: Không có giá trị trả về.

- **`getProject(projectId: String): Project`**
    - **Mô tả**: Truy xuất thông tin của một dự án dựa trên `projectId`.
    - **Tham số**:
        - `projectId`: ID của dự án cần lấy thông tin.
    - **Trả về**: Đối tượng `Project` chứa thông tin của dự án.

- **`updateProject(project: Project): void`**
    - **Mô tả**: Cập nhật thông tin của một dự án trong cơ sở dữ liệu.
    - **Tham số**:
        - `project`: Đối tượng `Project` chứa thông tin cập nhật của dự án.
    - **Trả về**: Không có giá trị trả về.

- **`listAllProjects(): List<Project>`**
    - **Mô tả**: Lấy danh sách tất cả các dự án trong cơ sở dữ liệu.
    - **Trả về**: Một danh sách (`List<Project>`) chứa tất cả các dự án.

## Lớp `Project`

Lớp `Project` đại diện cho một dự án trong hệ thống. Các phương thức của lớp này cho phép truy xuất và cập nhật thông tin dự án.

### Các Operations

- **`getProjectDetails(): String`**
    - **Mô tả**: Trả về thông tin chi tiết của dự án dưới dạng chuỗi.
    - **Trả về**: Một chuỗi (`String`) chứa các thông tin về dự án như tên, mô tả, ngày bắt đầu, ngày kết thúc, và trạng thái.

- **`updateProjectDetails(name: String, description: String, startDate: Date, endDate: Date): void`**
    - **Mô tả**: Cập nhật các chi tiết của dự án, bao gồm tên, mô tả, ngày bắt đầu và ngày kết thúc.
    - **Tham số**:
        - `name`: Tên của dự án.
        - `description`: Mô tả của dự án.
        - `startDate`: Ngày bắt đầu của dự án.
        - `endDate`: Ngày kết thúc của dự án.
    - **Trả về**: Không có giá trị trả về.

- **`setProjectStatus(status: String): void`**
    - **Mô tả**: Cập nhật trạng thái của dự án (ví dụ: "hoàn thành", "đang tiến hành", "đã hủy").
    - **Tham số**:
        - `status`: Trạng thái của dự án (chuỗi).
    - **Trả về**: Không có giá trị trả về.

- **`getProjectStatus(): String`**
    - **Mô tả**: Lấy trạng thái hiện tại của dự án.
    - **Trả về**: Một chuỗi (`String`) đại diện cho trạng thái của dự án.

## Lớp `DatabaseConnection`

Lớp `DatabaseConnection` chịu trách nhiệm kết nối và tương tác với cơ sở dữ liệu. Các phương thức trong lớp này sẽ giúp thực hiện các câu truy vấn và cập nhật trong cơ sở dữ liệu.

### Các Operations

- **`connect(): void`**
    - **Mô tả**: Thiết lập kết nối đến cơ sở dữ liệu.
    - **Trả về**: Không có giá trị trả về.

- **`disconnect(): void`**
    - **Mô tả**: Ngắt kết nối khỏi cơ sở dữ liệu.
    - **Trả về**: Không có giá trị trả về.

- **`executeQuery(query: String): ResultSet`**
    - **Mô tả**: Thực thi một câu truy vấn SQL và trả về kết quả.
    - **Tham số**:
        - `query`: Câu truy vấn SQL cần thực thi.
    - **Trả về**: Đối tượng `ResultSet` chứa kết quả truy vấn.

- **`executeUpdate(query: String): int`**
    - **Mô tả**: Thực thi một câu truy vấn SQL như `INSERT`, `UPDATE`, hoặc `DELETE` và trả về số lượng bản ghi bị ảnh hưởng.
    - **Tham số**:
        - `query`: Câu truy vấn SQL cần thực thi.
    - **Trả về**: Số lượng bản ghi bị ảnh hưởng bởi câu truy vấn (dạng `int`).

---

## 2. Xác định các trạng thái

![Sequence Diagram](https://www.planttext.com/api/plantuml/png/UhzxlqDnIM9HIMbk3bUqLgo2hgwTmf493tTjBudFEBmWBvsB2va7bKxCIu-lUBXxRNpEuRqALWeXcGztxSzJ0Ad8K029Am35kT2KGNGUNXoVaGzK5ry2KMsbu07YAfGytBMq1BUMXxkNLuBKWkaZ4uyjXDYMpeLf8aWJq2DSI1fXGbmEgNaf88y20000__y30000)

## Biểu đồ trạng thái cho lớp `Order`

### Giải thích

Biểu đồ trạng thái là một công cụ hữu ích trong UML để mô tả sự thay đổi trạng thái của một đối tượng trong suốt vòng đời của nó. Các trạng thái trong biểu đồ thể hiện các giai đoạn khác nhau mà đối tượng có thể trải qua và các sự kiện (hoặc hành vi) có thể làm thay đổi trạng thái của đối tượng.

Dưới đây là các trạng thái trong biểu đồ trạng thái của lớp `Order`:

1. **Đặt_hàng (Order)**: 
   - Đây là trạng thái ban đầu của đối tượng `Order`, khi người dùng thực hiện yêu cầu đặt hàng. Đơn hàng sẽ bắt đầu ở trạng thái này sau khi người dùng tạo đơn hàng.

2. **Đang_xử_lý (Processing)**: 
   - Sau khi đơn hàng được đặt, nó sẽ chuyển sang trạng thái "Đang xử lý". Trong trạng thái này, hệ thống thực hiện các công đoạn xử lý đơn hàng, ví dụ như xác minh thông tin và chuẩn bị hàng hóa.

3. **Đã_hoàn_thành (Completed)**: 
   - Đây là trạng thái khi đơn hàng đã được hoàn tất và giao hàng thành công cho khách hàng. Sau khi đơn hàng hoàn thành, hệ thống có thể chuyển sang trạng thái "Đã hoàn thành" và kết thúc vòng đời của đơn hàng.

4. **Đã_hủy (Cancelled)**: 
   - Trạng thái này được kích hoạt khi đơn hàng bị hủy vì một lý do nào đó, chẳng hạn như người dùng yêu cầu hủy hoặc có sự cố trong quá trình xử lý đơn hàng.

5. **[*]**: 
   - Biểu tượng này đại diện cho điểm bắt đầu và kết thúc của chuỗi trạng thái trong biểu đồ. Đơn hàng sẽ bắt đầu từ trạng thái "Đặt hàng" và có thể kết thúc ở trạng thái "Đã hoàn thành" hoặc "Đã hủy".

### Cách sử dụng trong thực tế

Biểu đồ trạng thái rất hữu ích khi bạn cần mô tả các trạng thái khác nhau mà một đối tượng có thể trải qua trong suốt vòng đời của nó, đặc biệt là đối với các lớp có trạng thái phức tạp như `Order`.

### Ví dụ về cách sử dụng:
1. **Đặt hàng** (Order): 
   - Khi người dùng tạo một đơn hàng, hệ thống sẽ tạo đối tượng `Order` và chuyển nó vào trạng thái "Đặt hàng". Đây là trạng thái khởi tạo cho đơn hàng.

2. **Đang xử lý** (Processing):
   - Sau khi đơn hàng được xác nhận và thanh toán thành công, đơn hàng sẽ chuyển sang trạng thái "Đang xử lý". Trong giai đoạn này, hệ thống sẽ chuẩn bị hàng hóa và giao hàng.

3. **Đã hoàn thành** (Completed):
   - Khi đơn hàng đã được giao thành công và hoàn tất, trạng thái của đơn hàng sẽ chuyển sang "Đã hoàn thành". Lúc này, người dùng có thể xem thông tin đơn hàng đã giao.

4. **Đã hủy** (Cancelled):
   - Nếu có bất kỳ lý do nào khiến đơn hàng không thể tiếp tục, ví dụ như người dùng hủy đơn hoặc gặp sự cố trong quá trình xử lý, đơn hàng sẽ chuyển sang trạng thái "Đã hủy". Điều này sẽ kết thúc vòng đời của đơn hàng.
  
---

## 3. Xác định các thuộc tính

![Class Diagram](https://www.planttext.com/api/plantuml/png/X571QiCm3BtxAqHEtQKVa4CfD9SUHWSRxTcpjSpKYOCb5qgxB-jXdxHVc5AIPKjJ9h2DzEndlQUlo-UIM4TEbLUgqMQlIuHiktbQPN1I8E5gnlYcZPI9rdtIezSWv1TNeT7HpXuWXqDmTa3B4TedmutKMCquJV6XheVncWYoHotjoFeX-TC7TyLraSCpHrUN0uPLuyCHSGfhVy-Xa7selOSKQHVY7gr08RtwNw1OnebkYKp4kqB-LJesgq1HwkdMiywIAJFcy_DYDASSd4Z72cic9K-NMDjssjy0003__mC0)

# Giải thích về "Maintain Timecard" và Giao diện "ssInterface"

## Tổng Quan

Đoạn code PlantUML mô tả hệ thống quản lý **Timecard** trong môi trường **VOPC** (Virtual Office Process Control). Trong đó, lớp `Maintain Timecard` giữ vai trò quan trọng trong việc quản lý các bảng chấm công của nhân viên, trong khi `ssInterface` là giao diện giúp tương tác với các chức năng liên quan đến Timecard.

## Lớp "Maintain Timecard"

Lớp `Maintain Timecard` đại diện cho một bảng chấm công của nhân viên và có các thuộc tính cũng như phương thức sau:

### Thuộc Tính:
- **`timecardID`**: Mã định danh duy nhất của bảng chấm công (String).
- **`employeeID`**: Mã nhân viên (String).
- **`date`**: Ngày chấm công (Date).
- **`hoursWorked`**: Số giờ làm việc của nhân viên trong ngày (Double).
- **`status`**: Trạng thái của bảng chấm công (String) – có thể là "Đã duyệt", "Chưa duyệt", v.v.

### Phương Thức:
- **`createTimecard()`**: Phương thức để tạo bảng chấm công mới.
- **`updateTimecard()`**: Phương thức để cập nhật bảng chấm công hiện tại.
- **`getTimecardDetails()`**: Phương thức để lấy chi tiết của bảng chấm công.

Lớp này cung cấp các phương thức cho phép tạo mới, cập nhật và truy xuất thông tin bảng chấm công của nhân viên, phục vụ cho các nhu cầu về báo cáo và quản lý.

## Giao Diện "ssInterface"

Giao diện `ssInterface` chứa các phương thức cần thiết để tương tác với các bảng chấm công:

### Phương Thức:
- **`setTimecard()`**: Phương thức để thiết lập thông tin bảng chấm công (Void).
- **`getTimecard()`**: Phương thức để lấy thông tin bảng chấm công (Trả về đối tượng `Timecard`).
- **`updateTimecard()`**: Phương thức để cập nhật bảng chấm công (Void).

### Mối Quan Hệ:
- Lớp `Maintain Timecard` **implements** giao diện `ssInterface`, có nghĩa là `Maintain Timecard` sẽ thực hiện tất cả các phương thức trong `ssInterface`.

## Mối Quan Hệ Giữa Các Thành Phần

Lớp `Maintain Timecard` và giao diện `ssInterface` có mối quan hệ kế thừa (implements), nghĩa là lớp `Maintain Timecard` phải cài đặt tất cả các phương thức từ giao diện `ssInterface`. Điều này đảm bảo rằng tất cả các chức năng cơ bản của Timecard đều được cung cấp thông qua giao diện này.

## 4. Xác định các phụ thuộc, quan hệ kết hợp

![Class Diagram](https://www.planttext.com/api/plantuml/png/X5J1RXCn4BtlLunoAI0r4jSSK85mGcc2KhYxtY6sih4NpsmgG9mvSqHSMY74gUBUFVImNx9Vm2zWrvkjspJai5hlyyppl9dd_LjV7n4BnzMgoB83UAs4XjFcme9iBYGKRVsZ1AcQIwCoMGWYc0Xjs3ydUeLIk1m-Pm2mIj17ZmEo5eNE1UCjGcmTZWMB-Bb03diTy2Nh-DzDPoyZfxJ6eEGJUunyPjto7gyJXeHaRKtSA9sLI7IVRuwoSfe_HavHiKB3Mdg6juGkfWRKElq9dyj04S72BZQvhzO-9oKTQsAdJwjmUYJEDqYYaD3anvRr-t1SNsTLXlBdBBYYb7Cw7R-Op6Veo5EXaLt59DO9fKD_2gP8ZWLoqiK3U5C90wgjlyAolRhciFnPmhevXz8lVm6hggs_osnhaeEd0pWyzA_XyCaW3c845I7j2-rxFFBbb5urWJNxakxqS0G-5fsV9y6PPhKlURjPe-Wl0jzT4TemIyN2GhVr7n5TpQevDofqu-gtoMvq3eVFjfqzwir6MIznHsHgBChkQDkHOMwSuOEtjUp8s0oVG9YyankKJjhwcuOF_TXJhV46zzK75oJuKldrhRO73K1XD-t0VyUu9_h1kNKfsP5tJlWF_GC00F__0m00)

## Các Thành Phần Chính

### **MaintainTimecard**
- **Chức năng chính**: 
  - Duy trì và quản lý thông tin thời gian của người dùng.
  - Kiểm tra tính hợp lệ của thời gian và lưu trữ dữ liệu.
  - Các phương thức chính:
    - `maintainTime()`: Duy trì dữ liệu thời gian.
    - `validateTime()`: Kiểm tra tính hợp lệ của dữ liệu thời gian.
    - `storeData()`: Lưu trữ thông tin thời gian vào hệ thống.
    - `getTimeData()`: Truy xuất dữ liệu thời gian.
  
### **VOPC (Virtual Online Payment Connector)**
- **Chức năng chính**: 
  - Kết nối mạng và xử lý các giao dịch.
  - Phương thức chính:
    - `connectToNetwork()`: Kết nối tới mạng để truyền tải dữ liệu.
    - `validateTransaction()`: Kiểm tra tính hợp lệ của các giao dịch.
    - `processData()`: Xử lý dữ liệu giao dịch.

### **Security**
- **Chức năng chính**: 
  - Cung cấp các chức năng bảo mật như xác thực người dùng và cấp quyền truy cập.
  - Phương thức chính:
    - `authenticateUser()`: Xác thực người dùng.
    - `authorizeAccess()`: Cấp quyền truy cập cho người dùng.
    - `logSecurityEvent()`: Ghi lại các sự kiện bảo mật.

### **Distribution**
- **Chức năng chính**: 
  - Phân phối dữ liệu và thông báo đến các bên liên quan.
  - Phương thức chính:
    - `distributeData()`: Phân phối dữ liệu.
    - `sendNotification()`: Gửi thông báo đến người dùng.
    - `updateStatus()`: Cập nhật trạng thái của dữ liệu.

### **OODBMSPersistency**
- **Chức năng chính**: 
  - Quản lý tính bền vững của dữ liệu thông qua việc lưu trữ vào cơ sở dữ liệu OODBMS (Object-Oriented Database Management System).
  - Phương thức chính:
    - `saveData()`: Lưu dữ liệu vào hệ thống OODBMS.
    - `retrieveData()`: Truy xuất dữ liệu từ hệ thống OODBMS.
    - `deleteData()`: Xóa dữ liệu khỏi hệ thống OODBMS.

## Mối Quan Hệ Giữa Các Thành Phần

### **MaintainTimecard và VOPC**
- **Mối quan hệ**: `MaintainTimecard` **sử dụng** `VOPC`.
  - `MaintainTimecard` gọi đến các phương thức của `VOPC` để xử lý các giao dịch và xác thực dữ liệu.
  - **Mối quan hệ**: **has-a** (MaintainTimecard sử dụng VOPC như một dịch vụ hỗ trợ).
  
### **MaintainTimecard và Security**
- **Mối quan hệ**: `MaintainTimecard` **phụ thuộc vào** `Security`.
  - `MaintainTimecard` dựa vào `Security` để xác thực người dùng và bảo vệ các giao dịch dữ liệu.
  - **Mối quan hệ**: **depends-on** (MaintainTimecard phụ thuộc vào Security để thực hiện các chức năng bảo mật).

### **MaintainTimecard và Distribution**
- **Mối quan hệ**: `MaintainTimecard` **tương tác với** `Distribution`.
  - `MaintainTimecard` sử dụng `Distribution` để phân phối dữ liệu và gửi thông báo đến người dùng.
  - **Mối quan hệ**: **interacts with** (MaintainTimecard tương tác với Distribution để gửi thông tin).

### **MaintainTimecard và OODBMSPersistency**
- **Mối quan hệ**: `MaintainTimecard` **lưu trữ dữ liệu** trong `OODBMSPersistency`.
  - `MaintainTimecard` sử dụng `OODBMSPersistency` để lưu trữ và truy xuất thông tin thời gian.
  - **Mối quan hệ**: **stores data** (MaintainTimecard lưu trữ dữ liệu vào OODBMSPersistency).

### **Security và các Thành Phần Khác**
- **Mối quan hệ**: 
  - `Security` **bảo mật** và **xác thực** các yêu cầu từ `VOPC`, `Distribution`, và `OODBMSPersistency`.
  - Các mối quan hệ chi tiết:
    - `Security` bảo mật và xác thực `VOPC`.
    - `Security` bảo mật và xác thực `Distribution`.
    - `Security` bảo mật và xác thực `OODBMSPersistency`.

## Phụ Thuộc và Quan Hệ
- **Phụ thuộc**:
  - `MaintainTimecard` phụ thuộc vào `VOPC`, `Security`, `Distribution`, và `OODBMSPersistency` để thực hiện các chức năng của mình.
  
- **Quan hệ kết hợp**:
  - `MaintainTimecard` có quan hệ kết hợp với `VOPC`, `Security`, `Distribution`, và `OODBMSPersistency`, khi nó sử dụng hoặc tương tác với các lớp này để thực hiện các tác vụ cụ thể.
