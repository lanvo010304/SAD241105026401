# Lab1

## Mục đích: 
Phân tích ca sử dụng hệ thống "**Payroll System**".

## Thực hiện:
1) Phân tích kiến trúc:

   a) **Đề xuất**:
   
     - Multi-tier Architecture (Kiến trúc nhiều tầng- Cụ thể em dùng 3 tầng):
     
     - Các thành phần gồm:
       - Presentation Layer (Tầng trình bày): Giao diện mà người dùng tương tác với hệ thống.
       - Business Layer (Tầng nghiệp vụ): Chứa các quy tắc và logic xử lý của hệ thống.
       - Data Access Layer (Tầng truy cập dữ liệu): Lưu trữ và truy xuất dữ liệu từ cơ sở dữ liệu.
  
    b) **Lý do**:
      - Tách biệt rõ ràng: Giúp dễ dàng bảo trì và mở rộng hệ thống.
      - Khả năng mở rộng: Mỗi lớp có thể được mở rộng độc lập mà không ảnh hưởng đến các lớp khác.
      - Bảo mật: Dữ liệu nhạy cảm được bảo vệ tốt hơn khi có sự phân chia rõ ràng giữa các lớp.

    c) **Ý nghĩa**:
      - Giao diện người dùng: Cung cấp một trải nghiệm người dùng thân thiện.
      - Xử lý nghiệp vụ: Đảm bảo rằng tất cả các quy trình tính lương được thực hiện chính xác.
      - Dữ liệu: Quản lý hiệu quả thông tin về nhân viên, thời gian làm việc và lương.

    d) **Biểu đồ**:

   ![Diagram](https://www.planttext.com/api/plantuml/png/UhzxlqDnIM9HIMbk3bT1Od9sOdggWb90OcLHVawEGd1bSKbghf92DPS244G75AKMf-QL99PavkSf-2HMfXR5AjZOA6W4w2YxkJa2WQQ2dHr4gLDfSMPUQd6nWaz-UcOoic8d7ML7Hv1oX6ANn994P2Kk82KWHN0bkEtNrRN3OHi-Xu1r8LdBLSlba9gN0Wm400000F__0m00)
     
     
2) Phân tích cơ chế:

  a) **Đề xuất**:
  - Quản lý nhân viên.
  - Tính lương.
  - Quản lý thời gian làm việc.
  - Báo cáo.

  b)  **Lý do**:
  - Quản lý nhân viên: Quản lý thông tin nhân viên(User) là rất quan trọng trong bất kỳ hệ thống tính nào. Đối với hệ thống Payroll này đảm bảo rằng tất cả thông tin đều được lưu trữ và cập nhật chính xác.
  - Tính lương: Chức năng cốt lõi của hệ thống Payroll.
  - Quản lý thời gian làm việc: Chức năng này cần phải có vì chức năng Tính lương phụ thuộc vào chức năng này.
  - Báo cáo: Cơ chế tạo báo cáo là cần thiết để cung cấp thông tin tổng hợp về lương, thời gian làm việc,... Các báo cáo này có thể hỗ trợ trong việc ra quyết định, lập kế hoạch, đánh giá.

  3) Phân tích ca sử dụng *Select Payment*:

     a) Xác định các lớp phân tích:
     - Employee: Đại diện cho nhân viên.
     - Payroll: Chịu trách nhiệm tính toán và xử lý lương.
     - Payment: Quản lý thông tin thanh toán.
      
      b) Biểu đồ:
     
     ![Diagram](https://www.planttext.com/api/plantuml/png/R90n3i8m34NtdC8Z3Br01jG1TXOEOAKMgkGanN66d8s18t454YaLL7InRF-d_sM_dwynAOfcpmQTHe5R8Z6jm722AnQ9p1Q47fcIrjbJqCFHTAL15xzmB4GMxgJhS2R5cLCbrmqCMqFD4hxKZryFiU2GNMPKsiIsRi-hIpkMbMq7MPZcj32MFtAaCDKFV0000F__0m00)

     c) Nhiệm vụ:
     - Employee: Cung cấp thông tin chi tiết về nhân viên.
     - Payroll: Tính toán lương và xử lý thông tin thanh toán.
     - Payment: Lưu trữ và quản lý thông tin thanh toán.

     d) Thuộc tính và quan hệ:
     
     **Employee**:
       - Thuộc tính: employeeId, name, salary.
       - Quan hệ:
            + Employee - Payroll(1-1).
            + Employee - Payment(1-N).

     **Payroll**:
       - Thuộc tính: payrollId, date.
       - Quan hệ:
            + Payroll - Employee(1-N)
            + Payroll - Payment(1-N).

     **Payment**:
       - Thuộc tính: paymentId, amount.
       - Quan hệ:
            + Payment - Employee(1-N)
            + Payment - Payroll(1-1)

  4) Phân tích ca sử dụng *Maintain Timecard*:

     a) Xác định các lớp phân tích:
     - Timecard: Quản lý thông tin thời gian làm việc.
     - Employee: Đại diện cho nhân viên.
     - Payroll: Cập nhật thông tin thời gian vào hệ thống.
    
     b) Biểu đồ:
     
       ![Diagram](https://www.planttext.com/api/plantuml/png/N8-z3G8n34RxJE4IYbiW1Je9w2bW02inA5B-vFYAcus2aLY1HBe8GcDzd_NqBB-Vhxa8iYp1ApII66w5MBK1qm6kBf11jXgMR56ezzrUzTYmSyW-hKGQ7YIzd4ZG-LBHle5fK3B9ml6B_Helk7Bolj_TQeMszASoATuT1nINuc2gLFj5WtKbUroF8pXJjFNr3m000F__0m00)

     c) Nhiệm vụ:
       - Timecard: Cập nhật và quản lý thông tin thời gian làm việc.
       - Employee: Cung cấp thông tin nhân viên.
       - Payroll: Đảm bảo rằng thông tin thời gian được cập nhật đúng cách.

     d) Thuộc tính và quan hệ:
     
     **Timecard**:
       - Thuộc tính: timecardId, hoursWorked.
       - Quan hệ:
            + Timecard - Employee(1-1)
            + Timecard - Payroll(1-1)

     **Employee**:
       - Thuộc tính: employeeId, name.
       - Quan hệ:
            + Employee - Timecard(1-1)
            + Employee - Payroll(1-1)

     **Payroll**:
       - Thuộc tính: payrollId, date.
       - Quan hệ:
         + Payroll - Timecard(1-N)
         + Payroll - Employee(1-N)





    
