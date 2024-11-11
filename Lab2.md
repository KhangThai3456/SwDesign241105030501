# Tài liệu Phân tích Hệ thống Payroll System - Lab 1

## 1. Phân tích ca sử dụng Create Employee
- **Mô tả**: Quản trị viên hoặc người có thẩm quyền có thể tạo hồ sơ cho nhân viên mới trong hệ thống.
- **Chi tiết**: Nhập thông tin cơ bản của nhân viên như tên, địa chỉ, số ID, thông tin liên lạc, chức danh công việc, mức lương, và các thông tin khác.
- **Kết quả mong đợi**: Thông tin của nhân viên mới được lưu vào hệ thống và có thể được truy cập khi cần thiết.

## 2. Phân tích ca sử dụng Maintain Purchase Order
- **Mô tả**: Quản lý các đơn mua hàng liên quan đến hệ thống Payroll (có thể là các chi phí mua vật tư liên quan đến nhân viên hoặc hệ thống).
- **Chi tiết**: Thêm, sửa đổi hoặc xoá các đơn mua hàng, ghi nhận các chi tiết liên quan như mã đơn hàng, ngày tạo đơn, người yêu cầu, chi phí, nhà cung cấp, v.v.
- **Kết quả mong đợi**: Đảm bảo các đơn mua hàng được lưu trữ và quản lý chính xác để có thể theo dõi ngân sách và chi phí.

## 3. Phân tích ca sử dụng Login
- **Mô tả**: Người dùng đăng nhập vào hệ thống Payroll System.
- **Chi tiết**: Người dùng nhập thông tin xác thực như tên đăng nhập và mật khẩu, sau đó hệ thống kiểm tra quyền truy cập.
- **Kết quả mong đợi**: Nếu thông tin đúng, người dùng được cấp quyền truy cập vào hệ thống. Nếu sai, hiển thị thông báo lỗi hoặc từ chối truy cập.

## 4. Phân tích ca sử dụng Create Administrative Report
- **Mô tả**: Tạo các báo cáo quản lý liên quan đến nhân viên và các hoạt động tài chính.
- **Chi tiết**: Người dùng có thể tạo báo cáo dựa trên các dữ liệu như lương thưởng, số giờ làm việc, chi phí quản lý, và các thông tin khác để phục vụ cho việc quản trị và ra quyết định.
- **Kết quả mong đợi**: Báo cáo hoàn chỉnh và có thể xem lại, in ra, hoặc lưu trữ.

## 5. Phân tích ca sử dụng Maintain Employee Info
- **Mô tả**: Quản lý thông tin của các nhân viên hiện tại.
- **Chi tiết**: Cập nhật thông tin nhân viên như địa chỉ, vị trí, mức lương, tình trạng công việc, và các thông tin khác khi có thay đổi.
- **Kết quả mong đợi**: Thông tin nhân viên luôn được cập nhật chính xác trong hệ thống.

## 6. Phân tích ca sử dụng Run Payroll
- **Mô tả**: Quản lý thông tin của các nhân viên hiện tại.
- **Chi tiết**: Cập nhật thông tin nhân viên như địa chỉ, vị trí, mức lương, tình trạng công việc, và các thông tin khác khi có thay đổi.
- **Kết quả mong đợi**: Thông tin nhân viên luôn được cập nhật chính xác trong hệ thống.

## 7. Viết code Java mô phỏng ca sử dụng Maintain Timecard.
import java.util.ArrayList;
import java.util.Date;
import java.util.List;

/**
 * Class Timecard
 * Represents an individual timecard entry with date and hours worked.
 */
class Timecard {
    private Date date;
    private double hoursWorked;

    public Timecard(Date date, double hoursWorked) {
        this.date = date;
        this.hoursWorked = hoursWorked;
    }

    public Date getDate() {
        return date;
    }

    public double getHoursWorked() {
        return hoursWorked;
    }

    public void setHoursWorked(double hoursWorked) {
        this.hoursWorked = hoursWorked;
    }

    @Override
    public String toString() {
        return "Timecard{" +
                "date=" + date +
                ", hoursWorked=" + hoursWorked +
                '}';
    }
}

/**
 * Class Employee
 * Manages a list of timecards for a specific employee.
 */
class Employee {
    private int id;
    private String name;
    private List<Timecard> timecards;

    public Employee(int id, String name) {
        this.id = id;
        this.name = name;
        this.timecards = new ArrayList<>();
    }

    public void addTimecard(Date date, double hoursWorked) {
        Timecard timecard = new Timecard(date, hoursWorked);
        timecards.add(timecard);
        System.out.println("Added: " + timecard);
    }

    public void updateTimecard(Date date, double newHoursWorked) {
        for (Timecard timecard : timecards) {
            if (timecard.getDate().equals(date)) {
                timecard.setHoursWorked(newHoursWorked);
                System.out.println("Updated: " + timecard);
                return;
            }
        }
        System.out.println("Timecard not found for date: " + date);
    }

    public void deleteTimecard(Date date) {
        timecards.removeIf(timecard -> timecard.getDate().equals(date));
        System.out.println("Deleted timecard for date: " + date);
    }

    public void displayTimecards() {
        System.out.println("Timecards for " + name + ":");
        for (Timecard timecard : timecards) {
            System.out.println(timecard);
        }
    }
}

/**
 * Main class PayrollSystem
 * Demonstrates the use of Employee and Timecard classes.
 */
public class PayrollSystem {
    public static void main(String[] args) {
        Employee employee = new Employee(1, "John Doe");

        // Sample dates for demonstration purposes
        Date date1 = new Date(2024, 10, 1); // Adjust the date as per your needs
        Date date2 = new Date(2024, 10, 2);

        // Adding timecards
        employee.addTimecard(date1, 8);
        employee.addTimecard(date2, 7.5);

        // Displaying timecards
        employee.displayTimecards();

        // Updating a timecard
        employee.updateTimecard(date1, 8.5);

        // Deleting a timecard
        employee.deleteTimecard(date2);

        // Displaying timecards after updates
        employee.displayTimecards();
    }
}
