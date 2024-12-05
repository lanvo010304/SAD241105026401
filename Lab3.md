# Lab3

## Mục đích: 
Xác định các phần tử thiết kế của hệ thống "*Payroll System*".

## Thực hiện:
**1) Subsystem context diagrams:**

  1.1. Biểu đồ:
  
  **BankSystem**:
   
   ![Diagram](https://www.planttext.com/api/plantuml/png/UhzxVtH0OcLHVawEGd1bSKbgRgo2hgwTGhHJObusL80BGuMU7geA1Ii5zyp4V8MKXxkxapCKaZDAAn_kRivJoCx8VxXhSHu0003__mC0)

   **PrintService**:

   ![Diagram](https://www.planttext.com/api/plantuml/png/UhzxVtH0OcLHVawEGd1bSKbgRgo2hgwTGdH0KMPUIN1gKLbcScei5uOQFJrqDGfM2fvv2WKPcGztxIzLo3csuTZ2l7G00000__y30000)

   **ProjectManagementDatabase**:

   ![Diagram](https://www.planttext.com/api/plantuml/png/UhzxVtH0OcLHVawEGd1bSKbgRgo2hgwTGdH0KNvMQdA9Rs9UOdfgRcfUYKjYIM9IOd5gB1U61Zqzl1eKh1H2Yaeh5SeUxbgQfr2ISNXBNhf2IMQUGih3tHiL3Y_C0m000F__0m00)

1.2. Mô tả, giải thích:

  **a) BankSystem**:
  
  *Mô tả:*
  - Hệ thống ngân hàng, xử lý các giao dịch chuyển khoản.

  *Interface:*
  - transferMoney(accountFrom, accountTo, amount): Chuyển tiền từ tài khoản này sang tài khoản khác.
  - getBankAccountInfo(accountNumber): Lấy thông tin tài khoản ngân hàng.

  **b) PrintService**:
  
  *Mô tả:*
  - Dịch vụ in ấn, xử lý các yêu cầu in ấn từ các hệ thống khác.

  *Interface:*
  - printDocument(document): In tài liệu.
  - printReport(report): In báo cáo.
    
  **c) ProjectManagementDatabase**:
  
  *Mô tả:*
  - Cơ sở dữ liệu quản lý dự án, lưu trữ thông tin về các dự án, mã dự án,...

  *Interface:*
  - getProjectInfo(projectId): Lấy thông tin về dự án.
  - getProjectList(): Lấy danh sách các dự án.
    
**2) Analysis class to design element map:**
  - Lớp phân tích	| Phần tử thiết kế
  - PayrollAdministrator | PayrollAdministrator
  - Employee | Employee
  - PaymentManage | PaymentManage
  - Timecard	| Timecard
  - PurchaseOrder	| PurchaseOrder
  - Report	| Report
  - ReportGenerator	| ReportGenerator
  - User	| User
  - AuthenticationManager	| AuthenticationManager
  - EmployeeManager	| EmployeeManager
  - OrderManager	| OrderManager
  - TimecardManager	| TimecardManager
  - PayrollProcessor	| PayrollProcessor
  - BankSystem	| BankSystem
  - PrintService	| PrintService
  - ProjectManagementDatabase	| ProjectManagementDatabase

**3. Design element to owning package map:**
  - Gói | Phần tử thiết kế
  - com.payroll.admin	| PayrollAdministrator
  - com.payroll.employee	| Employee
  - com.payroll.payment | PaymentManager
  - com.payroll.timecard	| Timecard
  - com.payroll.purchaseorder	| PurchaseOrder
  - com.payroll.report	| Report
  - com.payroll.reportgenerator	| ReportGenerator
  - com.payroll.user	| User
  - com.payroll.authentication	| AuthenticationManager
  - com.payroll.employee.manager	| EmployeeManager
  - com.payroll.order.manager	| OrderManager
  - com.payroll.timecard.manager	| TimecardManager
  - com.payroll.processor	| PayrollProcessor
  - com.payroll.bank	| BankSystem
  - com.payroll.print	| PrintService
  - com.payroll.project	| ProjectManagementDatabase

**4. Architectural layers and their dependencies:**

![Diagram](https://www.planttext.com/api/plantuml/png/UhzxVtH0KMfnQbv9OabcVbwiWgwkdKAqKsbnPbvgSN4i5vgidXwoh8ALGkJXLQKAoGztBI_LKKXvk7kzGaxcmztjfLn8Yi0ckYIM9COYYu9D0elYCmMY06n2G55-LcfoYMzYNc9wQYxGII2vfCJYr5YOCh2Hk9K1xGafAgrKA7kuQscUZaBEiGsb2YL5GDjGh75ApCiEhYmkISr5DHT9d3Y30eeoyqg2KulACfCnd8WaWzCm00000F__0m00)
