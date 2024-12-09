# Lab3

## Mục đích: 
Thiết kế các hệ thống con trong "*Payroll System*".

## Thực hiện:
**1) Hệ thống con: AuthenticationManager:**

- Chức năng: Xác thực thông tin đăng nhập của người dùng.
- Interface:
  + authenticate(username, password): Xác thực tên đăng nhập và mật khẩu.
  + getUser(userId): Lấy thông tin người dùng dựa trên ID.
- Ca sử dụng liên quan: Login

**2) Hệ thống con: EmployeeManager**:

- Chức năng: Quản lý thông tin nhân viên, bao gồm thêm, sửa, xóa, tìm kiếm, xem danh sách nhân viên.
- Interface:
  + addEmployee(employee): Thêm nhân viên mới.
  + updateEmployee(employeeId, employee): Cập nhật thông tin nhân viên.
  + deleteEmployee(employeeId): Xóa thông tin nhân viên.
  + getEmployee(employeeId): Lấy thông tin nhân viên dựa trên ID.
  + getEmployees(): Lấy danh sách tất cả nhân viên.
  + searchEmployee(criteria): Tìm kiếm nhân viên dựa trên tiêu chí.
- Ca sử dụng liên quan: Maintain Employee Information
