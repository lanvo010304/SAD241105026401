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
      
     
     

