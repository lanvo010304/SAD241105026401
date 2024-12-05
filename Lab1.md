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
  - Kiểm soát quyền truy cập: Hệ thống cần đảm bảo rằng mỗi nhân viên chỉ có thể truy cập và sửa đổi thông tin của riêng mình.
  - Xử lý dữ liệu kế thừa: Hệ thống cần kết nối và truy cập dữ liệu từ cơ sở dữ liệu kế thừa (Project Management Database) mà không cần sửa đổi cơ sở dữ liệu này.
  - Xử lý tính toán lương: Hệ thống cần tính toán lương cho từng nhân viên dựa trên số giờ làm việc, mức lương, hoa hồng,...
  - Xử lý phương thức thanh toán: Hệ thống cần hỗ trợ nhiều phương thức thanh toán như: nhận lương trực tiếp tại văn phòng, nhận lương qua bưu điện, chuyển khoản ngân hàng.
  - Tạo báo cáo: Hệ thống cần tạo các báo cáo về lương, giờ làm việc, v.v. cho cả quản trị viên và nhân viên.
  - Kiểm tra tính hợp lệ của dữ liệu: Hệ thống cần kiểm tra tính hợp lệ của dữ liệu nhập vào, ví dụ: số giờ làm việc, mã dự án,...
  - Lưu trữ và bảo mật dữ liệu: Hệ thống cần đảm bảo dữ liệu được lưu trữ an toàn và bảo mật.

  b)  **Lý do**:
  - Các cơ chế này là cần thiết để đảm bảo hệ thống Payroll hoạt động hiệu quả, chính xác và an toàn.

  3) Phân tích ca sử dụng *Select Payment*:

     a) Xác định các lớp phân tích:
     - Employee: Lớp đại diện cho nhân viên, chứa thông tin về nhân viên như: tên, mã nhân viên, phương thức thanh toán,..
     - PayrollSystem: Lớp đại diện cho hệ thống Payroll, chứa các phương thức xử lý các yêu cầu của nhân viên về phương thức thanh toán.
     - BankSystem: Lớp đại diện cho hệ thống ngân hàng, chứa các phương thức xử lý các giao dịch chuyển khoản ngân hàng.
      
      b) Biểu đồ:
     
     ![Diagram](https://www.planttext.com/api/plantuml/png/UhzxlsjkGKv-PMgghfrTG69bKNvEJd1bSKbghfL2vE5LfGh93tSj1v8P3tVtvYaKP1pRS6nXNhf22P2_CXb89UPbA9Ja7rwOnvMON99PbbYIge1Y2XSA3sW7p3eh1O_CXxkRyy16TIkaW0mgFhmmEGEl9RWTwqpOXRYT4W6qM24lu-6kjUIQu0pKMm0neWIevV0Ma06P-4rBISKHPeav9Ge1k3Kgv1nU08oHqafm-6Ldv3_SjJYFIm48qDtdb9YN3GiWzuUxrsOgL2B7AHOJu2v2Q0MB8xYOGOySUkcPYVaAAS0O1KOaLWkGF8raHMfU2W000F__0m00)

     c) Nhiệm vụ:
     - Employee: Gửi yêu cầu chọn phương thức thanh toán, cung cấp thông tin cần thiết cho hệ thống.
     - PayrollSystem: Xử lý yêu cầu của nhân viên, hiển thị danh sách phương thức thanh toán, cập nhật thông tin phương thức thanh toán, gửi yêu cầu chuyển khoản ngân hàng (nếu có).
     - BankSystem: Xử lý yêu cầu chuyển khoản, xác nhận giao dịch chuyển khoản.

     d) Thuộc tính và quan hệ:
     
     **Thuộc tính**:
       - Employee: employeeId(Mã nhân viên), name (Tên), paymentMethod(Phương thức thanh toán), bankAccount(Thông tin ngân hàng).
       - PayrollSystem: paymentMethodS(Danh sách phương thức thanh toán), bankConnection(Ngân hàng dùng để kết nối)
       - Payment:  bankAccount(Thông tin ngân hàng), processingMethods(Các phương thức xử lý giao dịch chuyển khoản).

     **Quan hệ**:
       - PayrollSystem 1-N Employee: Một hệ thống Payroll có thể quản lý nhiều nhân viên.
       - PayrollSystem 1-1 BankSystem: Một hệ thống Payroll có thể kết nối với một hệ thống ngân hàng.
       
  4) Phân tích ca sử dụng *Maintain Timecard*:

     a) Xác định các lớp phân tích:
     - Employee: Lớp đại diện cho nhân viên, chứa thông tin về nhân viên như: tên, mã nhân viên,..
     - Timecard: Lớp đại diện cho bảng chấm công, chứa thông tin về giờ làm việc của nhân viên.
     - ProjectManagementDatabase: Lớp đại diện cho cơ sở dữ liệu quản lý dự án, chứa thông tin về các dự án và mã dự án.
     - PayrollSystem: Lớp đại diện cho hệ thống Payroll, chứa các phương thức xử lý các yêu cầu của nhân viên về bảng chấm công.
    
     b) Biểu đồ:
     
       ![Diagram](https://www.planttext.com/api/plantuml/png/b9AnJiCm48RtFCMz02-GeGiWCG2gH0SOhuwL1CMNAZ6HCY861fu1gQL2bIen837L0uEVn4_0At0KHKdQ9cqNnrRaxxlp_J_c-rnDahIKycGm66APfKboK-PQAX_kxF81X5ijrkl712ZYZuQnMyqf1C6dTmN2Vb7eeT1nWLf2Y-6rJcmOnKeAp08VBlbo2JhwkmqwfbrKrfe5ijQ-4HInNLBjgKXUjTckVvGn4Wfd7lTul41kSpTB7sRflHJw2Wb3gIJfCzGunbnMlGH84UHs9Y9GTWw1CvzWPusIEmbUvv_Ufhg4ZMvwb1ljLJ7muI9sveduoPnvsJcLmauxtTrfkexM6MfC8cJHAoHsgdYupZoBdhYSDWFOopWc8RVSm3-KsX6l3GTbetwy8uajq2y0003__mC0)

     c) Nhiệm vụ:
       - Employee: Gửi yêu cầu cập nhật bảng chấm công, nhập thông tin giờ làm việc, xác nhận cập nhật thông tin.
       - Timecard: Lưu trữ thông tin về giờ làm việc của nhân viên, cập nhật thông tin giờ làm việc
       - ProjectManagementDatabase: Cung cấp danh sách mã dự án cho hệ thống.
       - PayrollSystem: Xử lý yêu cầu của nhân viên, lấy thông tin bảng chấm công, lấy danh sách mã dự án, cập nhật thông tin giờ làm việc, xác nhận cập nhật thông tin.

     d) Thuộc tính và quan hệ:
     
     **Thuộc tính**:
       - Employee: name (Tên), employeeId (Mã nhân viên)
       - Timecard: employeeId (Mã nhân viên), date (Ngày), hoursworked (Giờ làm việc), projectId (Mã dự án)
       - ProjectManagementDatabase: projectIdS (Danh sách mã dự án), projectName (Tên dự án)
       - PayrollSystem: employees (Danh sách nhân viên), timecards (Danh sách bảng chấm công), projectdatabase(Thông tin kết nối với cơ sở dữ liệu quản lý dự án)

     **Quan hệ**:
       - Employee 1-N Timecard: Một nhân viên có thể có nhiều bảng chấm công.
       - PayrollSystem 1-N Employee: Một hệ thống Payroll có thể quản lý nhiều nhân viên.
       - PayrollSystem 1-1 ProjectManagementDatabase: Một hệ thống Payroll có thể kết nối với một cơ sở dữ liệu quản lý dự án.





    
