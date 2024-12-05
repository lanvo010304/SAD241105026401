# Lab4

## Mục đích: 
Thiết kế các ca sử dụng cho hệ thống **Payroll System**.

## Thực hiện:

**1) Ca sử dụng: Login**
- Diễn tả: Người dùng có thể đăng nhập vào hệ thống Payroll bằng cách cung cấp tên đăng nhập và mật khẩu.
- Luồng cơ bản:
  + Người dùng nhập tên đăng nhập và mật khẩu vào form đăng nhập.
  + Hệ thống xác thực thông tin đăng nhập.
  + Nếu thông tin hợp lệ, người dùng được phép đăng nhập vào hệ thống.
  + Nếu thông tin không hợp lệ, hệ thống hiển thị thông báo lỗi.
- Luồng thay thế:
  + Nếu người dùng quên mật khẩu, hệ thống cung cấp chức năng khôi phục mật khẩu.
- Lý do thiết kế:
  + Ca sử dụng này là cần thiết để đảm bảo tính bảo mật của hệ thống.
  + Nó cho phép người dùng xác thực danh tính trước khi truy cập vào các chức năng của hệ thống.
 
**2) Ca sử dụng:  Maintain Timecard**
- Diễn tả: Nhân viên có thể xem, cập nhật và gửi bảng chấm công của mình.
- Luồng cơ bản:
  + Nhân viên truy cập vào chức năng quản lý bảng chấm công.
  + Hệ thống hiển thị thông tin bảng chấm công hiện tại của nhân viên.
  + Nhân viên có thể xem, cập nhật thông tin bảng chấm công.
  + Nhân viên xác nhận gửi bảng chấm công.
  + Hệ thống cập nhật trạng thái bảng chấm công thành "Submitted".
- Luồng thay thế:
  + Nếu nhân viên muốn thêm bảng chấm công mới, hệ thống cung cấp chức năng thêm bảng chấm công mới.
  + Nếu nhân viên muốn xóa bảng chấm công hiện tại, hệ thống cung cấp chức năng xóa bảng chấm công.
- Lý do thiết kế:
  + Ca sử dụng này cho phép nhân viên quản lý bảng chấm công của mình một cách hiệu quả.
  + Nó đảm bảo tính chính xác và kịp thời của thông tin bảng chấm công.

**3) Ca sử dụng:  Run Payroll**
- Diễn tả: Hệ thống tính toán và thanh toán lương cho nhân viên.
- Luồng cơ bản:
  + Hệ thống thời gian xác định ngày thanh toán lương.
  + PayrollProcessor lấy danh sách nhân viên cần thanh toán lương.
  + PayrollProcessor tính toán lương cho từng nhân viên.
  + PayrollProcessor xác định phương thức thanh toán của từng nhân viên.
  + Nếu phương thức thanh toán là chuyển khoản, PayrollProcessor gửi yêu cầu chuyển khoản đến BankSystem.
  + Nếu phương thức thanh toán là nhận lương trực tiếp hoặc qua bưu điện, PayrollProcessor in phiếu lương bằng PrintService.
  + PayrollProcessor cập nhật trạng thái thanh toán cho nhân viên.
- Luồng thay thế:
  + Nếu có lỗi xảy ra trong quá trình tính toán lương, hệ thống hiển thị thông báo lỗi.
  + Nếu có lỗi xảy ra trong quá trình chuyển khoản, hệ thống hiển thị thông báo lỗi.
- Lý do thiết kế:
  + Ca sử dụng này là chức năng chính của hệ thống Payroll, đảm bảo tính toán và thanh toán lương cho nhân viên một cách chính xác và kịp thời.
  + Nó tích hợp với các hệ thống con khác như BankSystem và PrintService để thực hiện các chức năng liên quan.

**4) Ca sử dụng:  Maintain Employee Information**
- Diễn tả: Quản trị viên có thể quản lý thông tin của nhân viên, bao gồm thêm, sửa, xóa thông tin nhân viên.
- Luồng cơ bản:
  + Quản trị viên truy cập vào chức năng quản lý thông tin nhân viên.
  + Quản trị viên chọn chức năng muốn thực hiện (Thêm, Sửa, Xóa).
  + Hệ thống hiển thị thông tin nhân viên tương ứng với chức năng được chọn.
  + Quản trị viên cung cấp thông tin cần thiết để thêm, sửa, xóa thông tin nhân viên.
  + Hệ thống xử lý yêu cầu của quản trị viên và cập nhật thông tin nhân viên.
- Luồng thay thế:
  + Nếu quản trị viên muốn tìm kiếm thông tin nhân viên, hệ thống cung cấp chức năng tìm kiếm.
  + Nếu quản trị viên muốn xem danh sách nhân viên, hệ thống cung cấp chức năng xem danh sách.
- Lý do thiết kế:
  + Ca sử dụng này cho phép quản trị viên quản lý thông tin nhân viên một cách hiệu quả.
  + Nó đảm bảo tính chính xác và cập nhật của thông tin nhân viên trong hệ thống.

**5) Ca sử dụng:  Create Administrative Report**
- Diễn tả: Quản trị viên có thể tạo báo cáo hành chính về thông tin nhân viên, bảng chấm công, lương,...
- Luồng cơ bản:
  + Quản trị viên truy cập vào chức năng tạo báo cáo hành chính.
  + Quản trị viên chọn loại báo cáo muốn tạo.
  + Hệ thống hiển thị thông tin cần thiết để tạo báo cáo.
  + Quản trị viên cung cấp thông tin cần thiết và xác nhận tạo báo cáo.
  + Hệ thống tạo báo cáo và hiển thị báo cáo cho quản trị viên.
- Luồng thay thế:
  + Nếu quản trị viên muốn lưu báo cáo, hệ thống cung cấp chức năng lưu báo cáo.
  + Nếu quản trị viên muốn in báo cáo, hệ thống cung cấp chức năng in báo cáo.
- Lý do thiết kế:
  + Ca sử dụng này cho phép quản trị viên theo dõi và phân tích thông tin của hệ thống Payroll.
  + Nó cung cấp các báo cáo hữu ích để hỗ trợ quản lý và ra quyết định.
 
**6) Ca sử dụng:  Create Administrative Report**
- Diễn tả: Nhân viên có thể tạo báo cáo về thông tin cá nhân, bảng chấm công, lương của mình.
- Luồng cơ bản:
  + Nhân viên truy cập vào chức năng tạo báo cáo.
  + Nhân viên chọn loại báo cáo muốn tạo.
  + Hệ thống hiển thị thông tin cần thiết để tạo báo cáo.
  + Nhân viên xác nhận tạo báo cáo.
  + Hệ thống tạo báo cáo và hiển thị báo cáo cho nhân viên.
- Luồng thay thế:
  + Nếu nhân viên muốn lưu báo cáo, hệ thống cung cấp chức năng lưu báo cáo.
  + Nếu nhân viên muốn in báo cáo, hệ thống cung cấp chức năng in báo cáo.
- Lý do thiết kế:
  + Ca sử dụng này cho phép nhân viên theo dõi và quản lý thông tin cá nhân của mình trong hệ thống Payroll.
  + Nó cung cấp các báo cáo hữu ích để hỗ trợ nhân viên trong việc quản lý tài chính cá nhân.

**7) Ca sử dụng: Maintain Purchase Order**
- Diễn tả: Nhân viên bán hàng có thể quản lý đơn hàng, bao gồm thêm, sửa, xóa đơn hàng.
- Luồng cơ bản:
  + Nhân viên bán hàng truy cập vào chức năng quản lý đơn hàng.
  + Nhân viên bán hàng chọn chức năng muốn thực hiện (Thêm, Sửa, Xóa).
  + Hệ thống hiển thị thông tin đơn hàng tương ứng với chức năng được chọn.
  + Nhân viên bán hàng cung cấp thông tin cần thiết để thêm, sửa, xóa thông tin đơn hàng.
  + Hệ thống xử lý yêu cầu của nhân viên bán hàng và cập nhật thông tin đơn hàng.
- Luồng thay thế:
  + Nếu nhân viên bán hàng muốn tìm kiếm thông tin đơn hàng, hệ thống cung cấp chức năng tìm kiếm.
  + Nếu nhân viên bán hàng muốn xem danh sách đơn hàng, hệ thống cung cấp chức năng xem danh sách.
- Lý do thiết kế:
  + Ca sử dụng này cho phép nhân viên bán hàng quản lý đơn hàng một cách hiệu quả.
  + Nó đảm bảo tính chính xác và cập nhật của thông tin đơn hàng trong hệ thống.

**8) Ca sử dụng: Select Payment**
- Diễn tả: Nhân viên có thể chọn phương thức thanh toán lương của mình.
- Luồng cơ bản:
  + Nhân viên truy cập vào chức năng chọn phương thức thanh toán.
  + Hệ thống hiển thị danh sách các phương thức thanh toán có sẵn.
  + Nhân viên chọn phương thức thanh toán mong muốn.
  + Hệ thống cập nhật thông tin phương thức thanh toán của nhân viên.
- Luồng thay thế:
  + Nếu nhân viên muốn thêm phương thức thanh toán mới, hệ thống cung cấp chức năng thêm phương thức thanh toán mới.
  + Nếu nhân viên muốn xóa phương thức thanh toán hiện tại, hệ thống cung cấp chức năng xóa phương thức thanh toán.
- Lý do thiết kế:
  + Ca sử dụng này cho phép nhân viên lựa chọn phương thức thanh toán phù hợp với nhu cầu của mình.
  + Nó đảm bảo tính linh hoạt và tiện lợi cho nhân viên trong việc nhận lương.
