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
   - PayrollAdministrator: name (Tên) ,employeeId (Mã nhân viên).
   - Employee: employeeId (Mã nhân viên), name (Tên), address (Địa chỉ), phone(Số điện thoại), salary (Lương), paymentMethod (Phương thức thanh toán), bankAccount (Thông tin tài khoản ngân hàng)
   - EmployeeManager: employees (Danh sách nhân viên)

   *Quan hệ*:
   - EmployeeManager 1-N PayrollAdministrator: Một chức năng quản lý nhân viên có thể phục vụ nhiều quản trị viên.
   - EmployeeManager 1-N Employee: Một chức năng quản lý nhân viên có thể quản lý nhiều nhân viên.

  **Ca sử dụng: Maintain Purchase Order**:

  a) Các lớp phân tích:
  - OrderEmployee: Lớp đại diện cho nhân viên bán hàng, chứa thông tin về nhân viên bán hàng và các phương thức xử lý các yêu cầu của nhân viên bán hàng về quản lý đơn hàng.
  - PurchaseOrder: Lớp đại diện cho đơn hàng, chứa thông tin về đơn hàng.
  - OrderManager: Lớp đại diện cho chức năng quản lý đơn hàng, chứa các phương thức xử lý các yêu cầu về quản lý thông tin đơn hàng.

  b) Biểu đồ:

  ![Diagram](https://www.planttext.com/api/plantuml/png/UhzxlqDnIM9HIMbk3bTYSab-aO9_KKfgaMjkGKv-PMegLm5GBZCvio0nhmGYuvkObvYUMeGY4L1Qb9oHM9mALi35XMA2WguTYaOh1VU7kzTcAbGUNbMgaFnmr_9IXSBIXxiMvoda7DwhS6JYiOLv2Xc75-IbSo7h0fc2OekLWdDfNZh8WAK52YKPXxS0EIMPUIW6e6Z0T4V4uON92daP3tUjpSDb0heJK7o6QWB2FmG382JZyAfSKhmAqK0LNnAm68y7CJI3H1RaPIWaWvn5qDF1m5XF9CNJ40sKUxgOeCLuF8sXcJHFHnpUJ9AVmUefzt858Mln-1XTBwg77LBpKe151G000F__0m00)

  c) Nhiệm vụ:
  - OrderEmployee: Gửi yêu cầu quản lý đơn hàng, cung cấp thông tin đơn hàng, xác nhận thêm, sửa, xóa đơn hàng.
  - PurchaseOrder: Thêm, sửa, xóa thông tin đơn hàng.
  - OrderManager: Xử lý yêu cầu của nhân viên bán hàng, thêm, sửa, xóa thông tin đơn hàng.

  d) Thuộc tính và quan hệ:

   *Thuộc tính*:
   - OrderEmployee: name (Tên) ,employeeId (Mã nhân viên).
   - PurchaseOrder: purchaseOrderId (Mã đơn hàng), customerName (Tên khách hàng), productName (Tên sản phẩm), quantity (Số lượng), date (Ngày).
   - OrderManager: purchaseOrders (Danh sách đơn hàng).

   *Quan hệ*:
   - OrderManager 1-N CommissionedEmployee: Một chức năng quản lý đơn hàng có thể phục vụ nhiều nhân viên bán hàng.
   - OrderManager 1-N PurchaseOrder: Một chức năng quản lý đơn hàng có thể quản lý nhiều đơn hàng.

 **Ca sử dụng: Run Payroll**:

  a) Các lớp phân tích:
  - PayrollProcessor: Lớp đại diện cho chức năng xử lý lương, chứa các phương thức xử lý các yêu cầu về chạy lương.
  - BankSystem: Lớp đại diện cho hệ thống ngân hàng, chứa các phương thức xử lý các giao dịch chuyển khoản ngân hàng.
  - PaymentManager: Lớp đại diện cho chức năng quản lý thanh toán, chứa các phương thức xử lý các yêu cầu về thanh toán lương cho nhân viên.

  b) Biểu đồ:

  ![Diagram](https://www.planttext.com/api/plantuml/png/Z98zJiD048Lxds8km0LIf0W5GW8f4XIqc_KgQyMP3VOwaciA2YfkW44e8YWYL4ZU8iMYt6DFm1KOvzUs78WhUzVptZVpviSikYoDL1Xs8yL57AlefDsk7xMWu_8F3T-FBfyamANBinJ2vNoPOTzZN0TZfWNKoxoZf2zS_fg2pr12R3Ck0QLzHXW7Teh0oH11o-9MAvlXSPhNThOjs68IjGBjp3kzbXmEw0q5wak6h2z8xOQmYjxD0ucEv4PFIsVUU9cDQCs4DPcKHrIIzbYeeVk7O6YVY3j9dRb364ZbyXVqW9wg3Z5t60wkqbYBOGlEd9a5aDffiffVqYonOzgNhixtduT6WPJ_3A4VC0K-JOKoQtJmHPE726FnRzCRYsrsEdBca_uANBuOGM7nnU4sOT1RpXEA9d3c_i1WwXsS8qLOw2Ix1HReUoNMMaP7BTmfuOxMrBgWpTUzsIoeBWZjO7algguLpLy0003__mC0)

  c) Nhiệm vụ:
  - PayrollProcessor: Chạy lương, tính toán lương, xác định phương thức thanh toán.
  - BankSystem: Xử lý yêu cầu chuyển khoản, xác nhận giao dịch chuyển khoản.
  - PaymentManager: Quản lý thanh toán, xác định phương thức thanh toán, xử lý thanh toán theo từng phương thức.

  d) Thuộc tính và quan hệ:

   *Thuộc tính*:
   - BankSystem: bankAccount (Thông tin tài khoản ngân hàng), processingMethodS (Các phương thức xử lý giao dịch chuyển khoản).
   - PaymentManager: paymentMethods (Danh sách phương thức thanh toán).

   *Quan hệ*:
   - PayrollProcessor 1-1 PaymentManager: Một chức năng xử lý lương cần kết nối với một chức năng quản lý thanh toán.
   - PaymentManager 1-1 BankSystem: Một chức năng quản lý thanh toán có thể kết nối với một hệ thống ngân hàng.
  
  **Code mô phỏng ca Maintain Timecard(Java)**:

  
