# Lab1

## Mục đích: 
Phân tích ca sử dụng hệ thống "**Payroll System**".

## Thực hiện:
1) Phân tích yêu cầu để **đề xuất kiến trúc phù hợp** cho bài toán, giải thích:
   * **Đề xuất**:
     Multi-tier Architecture (Kiến trúc nhiều tầng):
     
     Các thành phần gồm:
     
     a) Presentation Layer (Tầng trình bày):
        * User Interface: Giao diện người dùng cho sinh viên và giảng viên.
        * API Gateway: Quản lý và điều hướng các request từ client.
          
     b) Business Layer (Tầng nghiệp vụ):
       * Services: Xử lý các yêu cầu nghiệp vụ chính như đăng ký môn học, nhập điểm.
       * Business Logic: Chứa logic nghiệp vụ và các quy tắc.
       * Security: Quản lý xác thực và phân quyền.

     c) Data Access Layer (Tầng truy cập dữ liệu):
       * New Database: Lưu trữ dữ liệu mới (đăng ký, điểm số).
       * Legacy Course Catalog: Database cũ chứa thông tin khóa học.
  
    * **Lý do**:

      a)Phù hợp với yêu cầu tích hợp hệ thống cũ:
      * Tách biệt xử lý.
      * Dễ dàng chuyển đổi dần dần từ hệ thống cũ sang mới.
      * Cache và tối ưu truy cập database cũ.
     
      b)Đảm bảo bảo mật cao:
      * Kiểm soát truy cập ở nhiều lớp.
      * Bảo vệ thông tin nhạy cảm (điểm số).
      * Dễ dàng thêm các cơ chế bảo mật mới.

      c)Khả năng mở rộng và bảo trì tốt:
      * Các tầng độc lập, dễ nâng cấp từng phần.
      * Có thể scale riêng từng tầng khi cần.
      * Giảm sự phụ thuộc giữa các thành phần.
     
      d) Hiệu năng tốt:
      * Cache ở nhiều tầng.
      * Tối ưu truy cập database.


    * **Biểu đồ**:

   ![Diagram](https://www.planttext.com/api/plantuml/png/X5H1IiD05Dtd59-kxHMase88NGXs9rrC9p4PsangEwaMSTL55oBOXIiHAoAYA0gwiOEucEezvWHUmJzDgObDOXP3vh_tt_lp6EPRVfIwWdH4wBSigqreaxWE56fwSijT41trm3reg76_08SMuBUpmKW0DjDoo86xNyzQNZ2mrHjtwn6XhEKPzgvjRTQjesLDxdgckGqzBMyMgXKjZwatgyrbge7BQ98zHzRrv3e0NqyUHQg3w8Hze0YtmTRo2Lf68LnOrLBXkNPDFU8OdfRNRRCEGU0wGb7wUJSpiuaW3TBzTQDVLz3LyZBLgxnTgUAayfpLOmMROAXOlQ7GzDGBCKudT66H5p4KYwl9YEER24racTX5U6goARn4pgbT4IyhqBoMt9Yp5EU7ZsMQBnJZvqLkyK0uq66k9o3O_U-6nz5zfm7K2w3BKBt7r3r7Ga-DmMMO7KuHrHnkW_5OSlfpwwUdqm4sDTKx-EgLHpEk8B0N6Zbe8J0TeVN0DrTkPA03nyyuNBPjVle0SRndWawma92TPioqXB_uglm0003__mC0)
     
     
2) Phân tích yêu cầu để **đề xuất các cơ chế** (phân tích) cần giải quyết trong bài toán:
   
    a) Cơ chế xác thực và phân quyền:
    * Quản lý đăng nhập người dùng.
    * Phân quyền truy cập cho sinh viên/giảng viên.
    * Bảo vệ thông tin nhạy cảm (điểm số).

    b) Cơ chế tích hợp hệ thống:
  
    * Kết nối với CSDL danh mục khóa học cũ.
    * Cache dữ liệu để tối ưu hiệu năng.
    * Đồng bộ dữ liệu giữa 2 hệ thống.
  
    c) Cơ chế thông báo:
  
    * Thông báo khi lớp đầy.
    * Thông báo khi lớp bị hủy (dưới 10 sinh viên).
    * Thông báo cập nhật thời khóa biểu.
  
    d) Cơ chế xử lý giao dịch:
  
    * Đảm bảo tính nhất quán khi đăng ký.
    * Xử lý đồng thời nhiều yêu cầu đăng ký.
    * Rollback khi gặp lỗi.

  3) Tiền hành **phân tích 02 ca sử dụng**: *Select Payment và Maintain Timecard*:

      3.1 **Select Payment**:
      
      a) Phân tích các lớp:
      - SinhVien: Đại diện cho sinh viên chưa các thông tin cá nhân và khóa học đã đăng ký.
      - ThanhToan: Chịu trách nhiệm xử lý các yêu cầu thanh toán.
      - HoaDon: Quán lý hóa đơn và thanh toán.
      
      b) Biểu đồ:
     
     ![Diagram](https://www.planttext.com/api/plantuml/png/UhzxlqDnIM9HIMbk3bTYSab-aK9mPbv6M6Pg7bS1K3WpERCWCQz4GSdbuUxkv0o5ieUxbog4P2JcPIY4v1zUcAUaa5Yi491OcPkQLnASMbIMcPoAgi_ZuUvsXPACXxidvgKhU1pUdAXmPC8ng3wdp9oSpBpquChYajHSBYwOnGgwTcX6MYb47bvLgf3ySDVoKeMImpih5PA19lRc0Gq6kQG4v18kL2qWGr3CjrBmURXhQILExIYAiJaXfEZXhiMW06WamGamFrafU6G-tDsS1mwARfm6EAJcfG1Z0W000F__0m00)

     c) Nhiệm vụ:
     - Sinh viên: Gửi yêu cầu chọn phương thức thanh toán.
     - Dịch vụ Thanh Toán: Xử lý và trả về các tùy chọn thanh toán.
     - Hệ thống Hóa Đơn: Cung cấp các thông tin thanh toán cần thiết.

     d) Thuộc tính và quan hệ:
     
     **SinhVien**:
       - Thuộc tính: studentID, name, registeredCourses.
       - Quan hệ: Một SinhVien có thể có nhiều HoaDon (1:N với HoaDon).

     **ThanhToan**:
       - Thuộc tính: paymentMethods, processPayment().
       - Quan hệ:ThanhToan tương tác với HoaDon để lấy thông tin thanh toán (N:1).

     **HoaDon**:
       - Thuộc tính: billID, amount, dueDate.
       - Quan hệ:
         + Một HoaDon thuộc về một SinhVien (N:1).
         + HoaDon cung cấp thông tin cho ThanhToan (1:N).
                 
 
     3.2) **Maintain Timecard**:
     
     a) Phân tích các lớp:
       - GV: Đại diện cho giảng viên, có thông tin cá nhân và khóa học giảng dạy.
       - Time: Chịu trách nhiệm quản lý và duy trì thẻ thời gian.
       - Data: Lưu trữ thông tin thẻ thời gian.

     b) Biểu đồ:
     
       ![Diagram](https://www.planttext.com/api/plantuml/png/V90n2i8m58RtdEB7tGjq4C621r14nsSCRK1ZQLEluE0PH3k881GN9pCu1Bn7Jk0LJ2iA5d5vG_A-__zu3tFhPffIdI_cZBXUfkXBKj582iKI_owvJ4Xfj49dDZp6ofa3Xh6xccgQhQptMw0CGxaGdDBPGAGhoSKtthiNo9pPmUUSCPVEhFEQ2adJb3B1sASOxKupBC34dd9mTptMiqoWl4IfeMiN_NA9V0Hhe5NQkoH0xp_xNlofCBO5Vw4_Ipx-WJ-DlQW8KriicxPshsBmwfjrXPhvkpy1003__mC0)

     c) Nhiệm vụ:
       - GV: Gửi yêu cầu cập nhật thẻ thời gian.
       - Time: Xử lý yêu cầu và cập nhật thông tin.
       - Data: Lưu trữ và quản lý thông tin thẻ thời gian.

     d) Thuộc tính và quan hệ:
     
     **GV**:
       - Thuộc tính: professorID, name, coursesTaught.
       - Quan hệ: Một GV có thể có nhiều Time (1:N với Time).

     **Time**:
       - Thuộc tính: timecardID, updateTimecard().
       - Quan hệ: Time tương tác với Data để cập nhật thông tin (N:1).

     **Data**:
       - Thuộc tính: recordID, timecardData.
       - Quan hệ:
         + Một bản ghi trong Data thuộc vềTime (1:1).
         + Data cung cấp thông tin cho Time (1:N).





    
