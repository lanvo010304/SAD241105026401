# Lab2

## Mục đích: 
Tiếp tục phân tích ca sử dụng hệ thống "**Payroll System**" và code

## Thực hiện:

**1) Phân tích các ca sử dụng còn lại:**

  **Ca sử dụng: Create Administrative Report**:
  
  a) Các lớp phân tích:
  - PayrollAdministrator: Lớp đại diện cho quản trị viên Payroll, chứa thông tin về quản trị viên và các phương thức xử lý các yêu cầu của quản trị viên về báo cáo.
  - Report: Lớp đại diện cho báo cáo, chứa thông tin về loại báo cáo, dữ liệu báo cáo,...
  - ReportGenerator1: Lớp đại diện cho hệ thống Payroll, chứa các phương thức xử lý các yêu cầu của quản trị viên về báo cáo.
    
  b) Biểu đồ:

  ![Diagram](https://www.planttext.com/api/plantuml/png/UhzxVq1YPL5-JevZIcvcNcPnIL5YINwHhfrTK6f1Vb69UsfUAbZ4q4eXyl2gKeNaXxkMbogKFDorC5yXwJ2GI0OIN8d99PbbYIMf2kYwkD05W2PZin35zBoCXxlM5YYKP1pUafUkK9APXsGJqQvrBWNg1Pgt58T1M1m64R9I2C7lEwXMhBQ653tSjLYXxE7kHYJzAQdOJI0YL3mo7-vkpWFwuE7kRd920IbKSuvjACNlVw8Zvl2gF8MommiKZamyjk7Xxhd0i4rvk6jr7heLPCKLaMRZYJuVL9KOeO_G10000F__0m00)

  c) Nhiệm vụ:
  - PayrollAdministrator: Gửi yêu cầu tạo báo cáo, cung cấp thông tin về báo cáo, xác nhận lưu báo cáo.
  - Report: Tạo báo cáo, lưu báo cáo.
  - ReportGenerator1: Xử lý yêu cầu của quản trị viên, tạo báo cáo, lưu báo cáo.

  d) Thuộc tính và quan hệ:
  
   *Thuộc tính*:
   - PayrollAdministrator: name (Tên), employeeId (Mã nhân viên).
   - Report: reportType (Loại báo cáo), data (Dữ liệu báo cáo), reportName (Tên báo cáo), filepath (Đường dẫn lưu báo cáo).
   - ReportGenerator1: reports (Danh sách báo cáo).

   *Quan hệ*:
   - ReportGenerator1 1-N PayrollAdministrator: Một hệ thống Payroll có thể quản lý nhiều quản trị viên.
   - ReportGenerator1 1-N Report: Một hệ thống Payroll có thể tạo nhiều báo cáo.


  **Ca sử dụng: Create Employee Report**:

  a) Các lớp phân tích:
  - Employee: Lớp đại diện cho nhân viên, chứa thông tin về nhân viên và các phương thức xử lý các yêu cầu của nhân viên về báo cáo.
  - Report: Lớp đại diện cho báo cáo, chứa thông tin về loại báo cáo, dữ liệu báo cáo,...
  - ReportGenerator2: Lớp đại diện cho hệ thống Payroll, chứa các phương thức xử lý các yêu cầu của nhân viên về báo cáo.

  b) Biểu đồ:

  ![Diagram](https://www.planttext.com/api/plantuml/png/UhzxlsjkGKv-PMgghfrTK6f1Vb69UsfUQb5YINwHaPL2vE5LfGh93tSjBrKeURXhORv2qc4WaGmak1AJIpBB4ajI5T1rSQ4B04s6MO9YObx6mrrh2nHACWvloKjNACdCGp8ThwkSIu7gWMOinQ4PYmCWGbOA8VXz0TMArTQGeeUx5YkKFTpTYAG_9HMx2JXyxv7vS7Tp7j3L3tTt4-jRf13BERQX5By_yGRquLLv2cM75oWScNXimyFTSu7Xbl9mr-eyT6E93diYpSCJ7JweAZ524w490000__y30000)

  c) Nhiệm vụ:
  - Employee: Gửi yêu cầu tạo báo cáo, cung cấp thông tin về báo cáo, xác nhận lưu báo cáo.
  - Report: Tạo báo cáo, lưu báo cáo.
  - ReportGenerator2: Xử lý yêu cầu của nhân viên, tạo báo cáo, lưu báo cáo.

  d) Thuộc tính và quan hệ:
  
   *Thuộc tính*:
   - Employee: name (Tên), employeeId (Mã nhân viên)
   - Report: reportType (Loại báo cáo), data (Dữ liệu báo cáo), reportName (Tên báo cáo), filepath (Đường dẫn lưu báo cáo).
   - ReportGenerator2: reports (Danh sách báo cáo).

 
   *Quan hệ*:
   - ReportGenerator2 1-N Employee: Một hệ thống Payroll có thể quản lý nhiều nhân viên.
   - ReportGenerator2 1-N Report: Một hệ thống Payroll có thể tạo nhiều báo cáo.

  **Ca sử dụng: Login**:

  a) Các lớp phân tích:
  - User: Lớp đại diện cho người dùng, chứa thông tin về người dùng và các phương thức xử lý các yêu cầu của người dùng về đăng nhập.
  - AuthenticationManager: LLớp đại diện cho chức năng xác thực, chứa các phương thức xử lý các yêu cầu về xác thực.

  b) Biểu đồ:

  ![Diagram](https://www.planttext.com/api/plantuml/png/UhzxVsXnQf6kdPrZQKb6Qbv9Pd9YIMP-dczYNc9wQf6LGkJXLQKAoGztBIzLE3BnI7DUka9UniDTQmku4fDBCiiIIr8Li6hamYeAj0Pa6ugf4ECKIWwloaErGQ7iy0A5N22hH24RAB2ob0k_IvrBWLg1PYubpZ3y3emul31PeIJZuUwD8Ehm5g119PbvN8av9GeXSAu2K7vnWKBEmztjN0f0WDz8vunyXOACmoiBq08o9PL0KARc5ASYsveDOP9akKVcmztDUM0VTSCyb7HuOJv8__HC8joGbm80003__mC0)

  c) Nhiệm vụ:
  - User: Cung cấp thông tin đăng nhập.
  - AuthenticationManager: Xử lý yêu cầu đăng nhập, xác thực thông tin, cho phép hoặc từ chối đăng nhập.

  d) Thuộc tính và quan hệ:

   *Thuộc tính*:
   - User: username, password.
   - AuthenticationManager: status.
 
   *Quan hệ*:
   -  AuthenticationManager 1-N User: Hệ thống có thể xác thực nhiều người dùng.

  **Ca sử dụng: Maintain Employee Information**:

  a) Các lớp phân tích:
  - PayrollAdministrator: Lớp đại diện cho quản trị viên Payroll, chứa thông tin về quản trị viên và các phương thức xử lý các yêu cầu của quản trị viên về quản lý thông tin nhân viên.
  - Employee: Lớp đại diện cho nhân viên, chứa thông tin về nhân viên.
  - EmployeeManager: Lớp đại diện cho chức năng quản lý nhân viên, chứa các phương thức xử lý các yêu cầu về quản lý thông tin nhân viên.
    
  b) Biểu đồ:

  ![Diagram](https://www.planttext.com/api/plantuml/png/l9MzJiCm58NtFCKTGIelqA4IGaWC824rGnbDQZKMZbDIfsf7r14nCB1JAeI8r0ccMAY3-o9-0bu19m544pVzfLcYECftxhd7r_aKatFK3tnA3viUOQJ30yJzuA1ME_RQrEzZV8OOQk6W2XSo2i5HyKi8rw6AHmoe_03kodVM0auOC5S-CUWI6J4BEPnq4SUGmrYvPoraqfzHSrmbxbXwUtM0JGTQRyzsPUHLeAx465MW8T_GlhMiawCYq4AKf-k_2bG-9kOYRyONw6iD2ynLyRWzhra9TEdQGmtGqETIMh74dvKgs4PJXS1cEAPA6dBePCROd4OrSJbrKGFjpE2b7FfmfU89ppQUXMa75yFg95jXjQOicvidHtzfwKkM2QuRNWwvCBLJ_LM_pDtg0Tg1RYPqbRWfusuQuWbHOf3i42LkjvnEFl4j35A6dDuhyK0MPb8twMysI4PBkvsZdZvBTpb6YTwkfYZvJspvwEkPaF-M66jQ1lOtxWi00F__0m00)

  c) Nhiệm vụ:
  - PayrollAdministrator: Gửi yêu cầu quản lý thông tin nhân viên, cung cấp thông tin nhân viên, xác nhận thêm, sửa, xóa nhân viên.
  - Employee: Thêm, sửa, xóa thông tin nhân viên.
  - EmployeeService: Xử lý yêu cầu của quản trị viên, thêm, sửa, xóa thông tin nhân viên.

  d) Thuộc tính và quan hệ:

   *Thuộc tính*:
   - PayrollAdministrator: name (Tên) ,employee_id (Mã nhân viên).
   - Employee: employeeId, name, salary.
   - EmployeeService: serviceId.

   *Quan hệ*:
   - EmployeeService - Employee(1-1)

  **Ca sử dụng: Maintain Purchase Order**:

  a) Các lớp phân tích:
  - OrderService.
  - PurchaseOrder.

  b) Biểu đồ:

  ![Diagram](
**2) Code mô phỏng ca Maintain Timecard(Java)**:

  
