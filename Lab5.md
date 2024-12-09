# Lab3

## Mục đích: 
Thiết kế các hệ thống con trong "*Payroll System*".

## Thực hiện:
**1. Hệ thống con: AuthenticationManager:**
- Chức năng: Xác thực thông tin đăng nhập của người dùng.
- Interface:
  + authenticate(username, password): Xác thực tên đăng nhập và mật khẩu.
  + getUser(userId): Lấy thông tin người dùng dựa trên ID.
- Ca sử dụng liên quan: Login.

**2. Hệ thống con: EmployeeManager**:
- Chức năng: Quản lý thông tin nhân viên, bao gồm thêm, sửa, xóa, tìm kiếm, xem danh sách nhân viên.
- Interface:
  + addEmployee(employee): Thêm nhân viên mới.
  + updateEmployee(employeeId, employee): Cập nhật thông tin nhân viên.
  + deleteEmployee(employeeId): Xóa thông tin nhân viên.
  + getEmployee(employeeId): Lấy thông tin nhân viên dựa trên ID.
  + getEmployees(): Lấy danh sách tất cả nhân viên.
  + searchEmployee(criteria): Tìm kiếm nhân viên dựa trên tiêu chí.
- Ca sử dụng liên quan: Maintain Employee Information.

**3. Hệ thống con: TimecardManager**:
- Chức năng: Quản lý bảng chấm công, bao gồm thêm, sửa, xóa, xem, gửi bảng chấm công.
- Interface:
  + addTimecard(timecard): Thêm bảng chấm công mới.
  + updateTimecard(timecardId, timecard): Cập nhật thông tin bảng chấm công.
  + deleteTimecard(timecardId): Xóa bảng chấm công.
  + getTimecard(timecardId): Lấy thông tin bảng chấm công dựa trên ID.
  + getTimecards(employeeId): Lấy danh sách bảng chấm công của nhân viên.
  + submitTimecard(timecardId): Gửi bảng chấm công.
- Ca sử dụng liên quan: Maintain Timecard.

**4. Hệ thống con: PayrollProcessor**:
- Chức năng: Xử lý tính toán và thanh toán lương cho nhân viên.
- Interface:
  + calculatePayroll(): Tính toán lương cho tất cả nhân viên.
  + processPayment(employeeId, paymentMethod): Xử lý thanh toán lương cho nhân viên theo phương thức đã chọn.
- Ca sử dụng liên quan: Run Payroll.

**5. Hệ thống con: PaymentManager**:
- Chức năng: Quản lý phương thức thanh toán lương của nhân viên.
- Interface:
  + getPaymentMethods(): Lấy danh sách các phương thức thanh toán.
  + setPaymentMethod(employeeId, paymentMethod): Cập nhật phương thức thanh toán cho nhân viên.
- Ca sử dụng liên quan: Select Payment.
  
**6. Hệ thống con: ReportGenerator**:
-Chức năng: Tạo báo cáo hành chính và báo cáo cho nhân viên.
- Interface:
  + generateAdministrativeReport(reportType): Tạo báo cáo hành chính theo loại báo cáo đã chọn.
  + generateEmployeeReport(employeeId, reportType): Tạo báo cáo cho nhân viên theo loại báo cáo đã chọn.
- Ca sử dụng liên quan: Create Administrative Report, Create Employee Report.
  
**7. Hệ thống con: BankSystem**:
- Chức năng: Xử lý các giao dịch chuyển khoản.
- Interface:
  + transferMoney(accountFrom, accountTo, amount): Chuyển tiền từ tài khoản này sang tài khoản khác.
  + getBankAccountInfo(accountNumber): Lấy thông tin tài khoản ngân hàng.
- Ca sử dụng liên quan: Run Payroll.
  
**8. Hệ thống con: PrintService**:
- Chức năng: In phiếu lương, báo cáo, tài liệu.
- Interface:
  + printDocument(document): In tài liệu.
  + printReport(report): In báo cáo.
- Ca sử dụng liên quan: Run Payroll, Create Administrative Report, Create Employee Report.
  
**9. Hệ thống con: ProjectManagementDatabase**:
- Chức năng: Lưu trữ và cung cấp thông tin về các dự án.
- Interface:
  + getProjectInfo(projectId): Lấy thông tin về dự án.
  + getProjectList(): Lấy danh sách các dự án.
- Ca sử dụng liên quan: Maintain Timecard.
  
**10. Hệ thống con: OrderManager**
- Chức năng: Quản lý đơn hàng, bao gồm thêm, sửa, xóa, tìm kiếm, xem danh sách đơn hàng.
- Interface:
  + addOrder(order): Thêm đơn hàng mới.
  + updateOrder(orderId, order): Cập nhật thông tin đơn hàng.
  + deleteOrder(orderId): Xóa thông tin đơn hàng.
  + getOrder(orderId): Lấy thông tin đơn hàng dựa trên ID.
  + getOrders(): Lấy danh sách tất cả đơn hàng.
  + searchOrder(criteria): Tìm kiếm đơn hàng dựa trên tiêu chí.
- Ca sử dụng liên quan: Maintain Purchase Order.
