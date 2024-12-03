# Lab2

## Mục đích: 
Tiếp tục phân tích ca sử dụng hệ thống "**Payroll System**" và code

## Thực hiện:

**1) Phân tích các ca sử dụng còn lại:**

  **Ca sử dụng: Create Administrative Report**:
  
  a) Các lớp phân tích:
  - ReportGenerator.
  - Payroll.
  - Employee.
    
  b) Biểu đồ:

  ![Diagram](https://www.planttext.com/api/plantuml/png/UhzxlqDnIM9HIMbk3bTYSab-aO9ZIcvc7XUOLD2rKmXABSWlAd5FpKijIWHAMocaGvYf40aDJIuq5I1D0OcLHVavELOAQQaboHbGdajYII9GEPIde8lDyABKajAYF5GDMCntpIt8oQzCJOLQ0ED2DS2u-An0qu9X1r0dE0Yi558oYmjo4YlXtdL8pKi1XXO0003__mC0)

  c) Nhiệm vụ:
  - ReportGenerator: Tạo và hiển thị báo cáo.
  - Payroll: Cung cấp dữ liệu lương cho báo cáo.
  - Employee: Cung cấp thông tin nhân viên cho báo cáo.

  d) Thuộc tính và quan hệ:
  
   *Thuộc tính*:
   - ReportGenerator: reportId, reportType.
   - Payroll: payrollId, totalAmount.
   - Employee: employeeId, name.

   *Quan hệ*:
   - ReportGenerator - Payroll(1-N).
   - ReportGenerator - Employee(1-N).


  **Ca sử dụng: Create Employee Report**:

  a) Các lớp phân tích:
  - ReportGenerator
  - Employee.

  b) Biểu đồ:

  ![Diagram](https://www.planttext.com/api/plantuml/png/UhzxlqDnIM9HIMbk3bTYSab-aO9ZIcvc7XUOLD2rKmXABSWlAd5FpKijIWHAMocaGvYfhha5EVcLgQaG1HgQN6WgGPfXQgmKqb9BaZDWN9V4aaIW1XXNGHURFKMf9QL5UMXQCEm0wWGxrKeX9REu82Un4iDP3gbvAK3V0G000F__0m00)

  c) Nhiệm vụ:
  - ReportGenerator: Tạo và hiển thị báo cáo nhân viên.
  - Employee: Cung cấp thông tin nhân viên cho báo cáo.

  d) Thuộc tính và quan hệ:
  
   *Thuộc tính*:
   - ReportGenerator: reportId, reportType.
   - Employee: employeeId, name, salary.
 
   *Quan hệ*:
   - ReportGenerator - Employee(1-N).

  **Ca sử dụng: Login**:

  a) Các lớp phân tích:
  - User.
  - AuthenticationService.

  b) Biểu đồ:

  ![Diagram](https://www.planttext.com/api/plantuml/png/R8qx3eCm40Lxds9BaC85A13fqo4Ei38hOWdMQ3_9uIXof5m1kwTvrSoy__aRrL3CzorWj2mmAqce0zq0JxStiQM8bZ9F99yKgOSjhuaRBn3ZJWyuKFMRPMd3hG1TITLa3qBcmg_gJuRcshHX95xA_mK00F__0m00)

  c) Nhiệm vụ:
  - User: Cung cấp thông tin đăng nhập.
  - AuthenticationService: Xác thực thông tin và trả về trạng thái đăng nhập.

  d) Thuộc tính và quan hệ:

   *Thuộc tính*:
   - User: username, password.
   - AuthenticationService: status.
 
   *Quan hệ*:
   -  User - AuthenticationService(1-1)

  **Ca sử dụng: Maintain Employee Information**:

  a) Các lớp phân tích:
  - Employee.
  - EmployeeService.

  b) Biểu đồ:

  ![Diagram](https://www.planttext.com/api/plantuml/png/R8z12i8m44NtESKiAzWBP24LTE7Q4uHaWe5aKgOJYsTpuP6yWh4GBDBDmF_yDv__Vhw6IGnBIL4PAvdXw58WjLpe3t1EOymFn2loFLZKK4Pd19jz8PyxRCBjWN3-UZlr1wv_QV0ezjRaYlzXq6-LCqfXQlO9nOGuTHjb5LucQB2PVE1a96IgoG79rR4V0000__y30000)

  c) Nhiệm vụ:
  - Employee: Cung cấp thông tin chi tiết về nhân viên.
  - EmployeeService: Cập nhật thông tin nhân viên và xác nhận thay đổi.

  d) Thuộc tính và quan hệ:

   *Thuộc tính*:
   - Employee: employeeId, name, salary.
   - EmployeeService: serviceId.

   *Quan hệ*:
   - EmployeeService - Employee(1-1)

**2) Code mô phỏng ca Maintain Timecard(Java)**:

  
