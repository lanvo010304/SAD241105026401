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
    * Thông báo khi lớp bị hủy (dưới 3 sinh viên).
    * Thông báo cập nhật thời khóa biểu.
  
    d) Cơ chế xử lý giao dịch:
  
    * Đảm bảo tính nhất quán khi đăng ký.
    * Xử lý đồng thời nhiều yêu cầu đăng ký.
    * Rollback khi gặp lỗi.

  3) Tiền hành **phân tích 02 ca sử dụng**: *Select Payment và Maintain Timecard.*:

  * **Select Payment**:
    
     a) Phân tích các lớp:

       ![Diagram](https://www.planttext.com/api/plantuml/png/b9EnQiCm48PtFyNXgHto0XrAXa0xfA6bVW7LCPQf8eT4BWqbG-cGeHJQeNjCo52eQQ2TB4871R-7dg2lq9E7s2GH8He4ulxJ_P_kz2T_cqD11YBfCQTF_5iI1k2UHII6RgJbXBlmu00kdv7X4DmBDUL0rIUd82WnUwpIjQXS5FEUk4UrVFQe-k6X5-49jPwH7XrNIXyrB_oI5eiYHHcUFlpTodkL-Xsgyspxfh4pTYhddT2Kd_JXJilvXlUhHESp3amjRTuRFJMh2fp0jHX4FAp2F5JJKLtG8YAemcAWyn94fT5MCWWCnXOyBREsMbfU2R7x9RpmQWNM-7N4S_LDOFLMR6EPoEgrs4Kbj7mtNTBoqI35oGqBDfcDzmDnLOOmjQiFOQgtjANb5p3JrMIZeUrYaG2wmBXj61bAzZ_hJW7J-Nnad-3IfFK_D1gdre5ph9DOPjLwk4TfuNUQ0U_YV_u7003__mC0)

     b) Mô tả các hành vi:

       ![Diagram](https://www.planttext.com/api/plantuml/png/d5HDIyD05BpdLpnwRx3MxqCfUEcX2e87FQvfI1RRRKmtnHx5etZmB895H1IB1RsO83siv7_iB_0l-BRfjabJHRpaD3DlthpPV4MZQeSJdmUjfa4itlQXiEl4GndTK6Y8T-OKW7GWwDY-uI6CMjGZZ4DXHzmoSCKpSu6xH7tReiyICCr2zm8PtZ5eYeySr2Ezbiru5byJhmG-h-89Xh9kcrfs5bEFXm5mNqOlESqEBa4Ssp2KQIXMq0ziGSc4G_4KW2N3Xo3DKLlJBk6sycqW5XaJMqXRDc5VXlrscW4j6LtJ6KylOMWQAanCeqBPXBeCxtke8DwO0vogtFI6CnMzfcOMCpvMq8UFCK9NHcSfAQDXvnHcFlJogoRKg8pE6J9bT96saauYfJNTAHFYcWdRA739m7FZ8TftneAF5dJ5BPoAlWNCbU60vODSD-50HeFv5lmrnGsSZC9Uei_LwSDalEZJV-IvYNPcTbKhfjg_HrhH_LATMiBRZekuEC-fZAwafcQzb4fPCqsKJ9kO5ZftrvAgPpBxI619ZsKuud2YtjlYOzA4gswAxF9SBNwWuxkesgo1VuXl0000__y30000)

     c) Nhiệm vụ:
        1) Lớp giao diện:
           **Màn hình thanh toán:**
             - Hiển thị thông tin thanh toán cho người dùng.
             - Cho phép chọn phương thức thanh toán.  
             - Thu thập thông tin xác nhận từ người dùng.

        3) Lớp nghiệp vụ:
    
            **Quản lý thanh toán:**
              - Tạo mới giao dịch thanh toán.
              - Xử lý logic thanh toán.
              - Kiểm tra tính hợp lệ của thanh toán.
              - Cập nhật trạng thái thanh toán.
     
            **Hóa đơn:**
              - Quản lý thông tin hóa đơn.
              - Tính toán tổng tiền.
              - Theo dõi trạng thái hóa đơn.
        4) Lớp dữ liệu:
             **Lưu trữ thanh toán**:
                - Lưu trữ thông tin thanh toán.
                - Cập nhật dữ liệu thanh toán.
                - Truy xuất thông tin thanh toán.

     d) Các quan hệ:
      - Màn hình thanh toán -> Quản lý thanh toán: Quan hệ sử dụng.
      - Quản lý thanh toán -> Hóa đơn: Quan hệ kết hợp.
      - Quản lý thanh toán -> Lưu trữ thanh toán: Quan hệ sử dụng.

     e) Giải thích luồng xử lý:

       Người dùng bắt đầu thanh toán -> Hệ thống tạo giao dịch thanh toán mới
       -> Lấy và hiển thị thông tin hóa đơn -> Người dùng chọn phương thức và xác nhận
       -> Hệ thống xử lý thanh toán -> Cập nhật trạng thái hóa đơn -> Lưu thông tin và hiển thị kết quả
               
   * **Maintain Timecard**:
     
     a) Phân tích các lớp:
       ![Diagram]()





    
