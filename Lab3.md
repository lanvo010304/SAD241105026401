# Lab3

## Mục đích: 
Xác định các phần tử thiết kế của hệ thống "*Payroll System*".

## Thực hiện:
**1) Subsystem context diagrams:**

  1.1. Biểu đồ:
  
  **BankSystem**:
   
   ![Diagram](https://www.planttext.com/api/plantuml/png/V90zZi8m48Lxd-A9QbU22r2WY8eA8T7GMevbMuHnH2O5DGK5LSG5zgVO2j7ZOejm4P-0As0YaAXePaRpllT6cclupogMQwvNXM37XSROnR2jSMbYE81C32UeUFubcrhuax0nxC2fDcIWF64iQJdVLAnNGfGfoYbNIcBq9g_aJ6xMlYXwaDLpVaDFJVj3iEqNcSvnlo74muV1g5jWY5oNldBy8PEah5RBFXonlwkVecCI-xGDiMY_5SZ6yv5WdFJ8OzWhAp9DUVh03G00__y30000)

   **PrintService**:

   ![Diagram](https://www.planttext.com/api/plantuml/png/P90n2i9044NxdE9ZxmLIYAY5TW4hosKDoS8wXhWhM5jOM8ad40a16wspHGh5Uym9l889HZ3Op0pC-_DdvkNA_ig8rDY5zemoEiH0iTjQF0xiZg28tHMIYpF5LNAvGCnk1rF50qMGIqAGAZBJC5qh6NfUKWrJKYM233hZNpOGctIfTGTYzQtRz8ZTNiPOiyim8N2HqGTk6JHIT7kj1dpCxXTRxvfRA48IAovA2_syFKyKUIsu5ZTpV0njVKbbb_o9-Y7DwzUy0G00__y30000)

   **ProjectManagementDatabase**:

   ![Diagram](https://www.planttext.com/api/plantuml/png/L90nRW8n44Lxd-ABFXUWY11iGHE9I5nWibYBaPbTxOuBwXJKA0U8K1IbYY8aAYn4iL7kuHFa2h4326WyjlN_dpVpwm-zHgWMDxTAZ5YDlWd-sU5x5VmBk0Z-2tdOlV4q5lz1c0Q_XCHpnGNoaZ6govdEvO6O2ZtNB1a9FL6ZbQfYiibDHIpe3A-D8rhKfRKTK7E-twe7FsiqmRzYaWXiX5ewFBf40jlkaGM_GRlcOy8H8UihTGh3tVtb5rsCQxT8StnMru7g8adwaxMBWKkpXTrx5O7RRNo8uMJyRwbwcYTfONy0003__mC0)

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
