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

  **BankSystem**:
  - Mô tả: Hệ thống con BankSystem chịu trách nhiệm xử lý các giao dịch liên quan đến lương của nhân viên, như thực hiện các khoản thanh toán trực tiếp vào tài khoản ngân hàng của họ.
  - Vai trò: Chịu trách nhiệm xử lý các giao dịch liên quan đến lương của nhân viên, như thực hiện các khoản thanh toán trực tiếp vào tài khoản ngân hàng của họ.
  - Cách hoạt động: Hệ thống Payroll sẽ gửi thông tin về phiếu lương (aPaycheck) và thông tin ngân hàng (intoBank) đến BankSystem. BankSystem sẽ xác nhận và thực hiện các giao dịch chuyển tiền lương vào tài khoản của nhân viên.

  **PrintService**:
  - Mô tả: Hệ thống con PrintService cung cấp dịch vụ in ấn các phiếu lương cho nhân viên.
  - Vai trò: Cung cấp dịch vụ in ấn các phiếu lương cho nhân viên.
  - Cách hoạt động: Hệ thống Payroll sẽ gửi yêu cầu in phiếu lương đến PrintService. PrintService sẽ thực hiện in ấn và cung cấp các phiếu lương đã in cho Hệ thống Payroll.

  **ProjectManagementDatabase**:
  - Mô tả: Hệ thống con ProjectManagementDatabase lưu trữ và cung cấp thông tin về các dự án mà nhân viên tham gia, phục vụ cho việc tính toán lương dựa trên thông tin dự án.
  - Vai trò: Lưu trữ và cung cấp thông tin về các dự án mà nhân viên tham gia, phục vụ cho việc tính toán lương dựa trên thông tin dự án.
  - Cách hoạt động: Hệ thống Payroll sẽ truy cập vào ProjectManagementDatabase để lấy thông tin về các dự án mà nhân viên đang tham gia. ProjectManagementDatabase sẽ cung cấp các thông tin liên quan đến dự án cho Hệ thống Payroll.

1.3. Interface:

**BankSystem**:

![Diagram](https://www.planttext.com/api/plantuml/png/Uhzxlu93SKbYKKbfRWwNGcPUIMfHMc9oge9JObvsS6LnIMgkGZMN0WYaf1Ra5sUMQ2G695OcPwGcPrifm5Ww88tv82rMO8sUUMdvHRc99PdvUPfS2hLS2WwfUIb02m00003__mC0)

**PrintService**:

![Diagram](https://www.planttext.com/api/plantuml/png/Uhzxlm88E1IN91QLbERcS86vcNabgKLfYScf2W55G7PmQb5P9f1J3P45WGAGU41YPN5EPe560OIsKe0AQ4BKrK8eXzIy5A3900000F__0m00)

**ProjectManagementDatabase**:

![Diagram](https://www.planttext.com/api/plantuml/png/Uhzxlm88E1IN91QLbERcS86vcNabgKLfYScf2W55-LcfoIM-YNc9wQcvgNabBeabYKc9nQaArH2b892UMW9LvvcNbg-HcbkGar-PckgPOgKGN5AKcPUkQQM0f02YiHP2EQJcfG3j1G000F__0m00)


**2) Analysis class to design element map:**
  - Lớp Phân Tích | Phần Tử Thiết Kế
  - PayrollSystem | PayrollController
  - Employee | EmployeeEntity, EmployeeService
  - Paycheck | PaycheckEntity, PaycheckService
  - BankAccount | BankAccountEntity, BankAccountService
  - Project | ProjectEntity, ProjectService
  - PayslipGenerator | PayslipGeneratorService
  - PayrollReport | PayrollReportService

**3. Design element to owning package map:**
  - Phần Tử Thiết Kế | Gói
  - PayrollController	| com.company.payroll.controllers
  - EmployeeEntity, EmployeeService |	com.company.payroll.employees
  - PaycheckEntity, PaycheckService	| com.company.payroll.paychecks
  - BankAccountEntity, BankAccountService	| com.company.payroll.bankaccounts
  - ProjectEntity, ProjectService |	com.company.payroll.projects
  - PayslipGeneratorService	| com.company.payroll.payslips
  - PayrollReportService	| com.company.payroll.reports

**4. Architectural layers and their dependencies:**

![Diagram](https://www.planttext.com/api/plantuml/png/T59RJiCm4FpFAQp-zmgeXLO82QIgFS5Y5Z3nI-iDaeKu6HySYIkGf57hH_9bUJmx7i_ux-Tt4nY8EwCR3xA5DnIh0s50oy3AMV484MablXgf8GHnW4XEwpjdULYHck_cEhdrNYivExWtNhk8U4BwL1AlSl8TPPkZjs3RhPIkirpGoNsWB468GIj_ZnO9s55rEXWzedTq6Kmzxvm1jMXtRrbnBDncO68s9v-zJbXwuuDz9GXCdUIEiBnvq3l5m6WkGceXXoUmlQ3fkze1mpE4yMLLHMAzlgdoB_OPP_9Sb3DIYWZgfaPMdKdUt5ag2sYXnOcP931NQAet4ye6xKl_m_y1003__mC0)
