# Lab2

## Mục đích: 
Tiếp tục phân tích ca sử dụng hệ thống "**Payroll System**" và code

## Thực hiện:

**1) Phân tích các ca sử dụng còn lại:**

  **Ca sử dụng: Select Payment**:
  
  a) Các lớp phân tích:
  - DịchVụThanhToan: Xử lý các yêu cầu thanh toán.
  - NgườiDùng: Đại diện cho người dùng (sinh viên/giảng viên).
  - CổngThanhToan: Kết nối với hệ thống thanh toán bên ngoài.
  - DịchVụThôngBáo: Gửi thông báo cho người dùng về trạng thái thanh toán.
    
  b) Biểu đồ:

  ![Diagram](https://www.planttext.com/api/plantuml/png/UhzxlqDnIM9HIMbk3bS1aCvCpYn8p2jHy4i_jk7XxhcPBeTtvgMZoBWytDsTd17sSFVIa8p4l8oG_CGy57ddXxkdvgLZbqFMUtXBNhhJuONvN5meTYdesc6pmaeXyl2gKeNaXxkMbogKW4GLIl8FBypZmg8MP0IQAwmK8XxkNgkGStWlYcOqLGgwk2oFEBmmMI4lu-6kjNc4RGSQWk8bAuMGeeUx5WBzLf9nU64cCSx75b1M2kv0Fu2qWqGKaa1XXqqTLWSWzA1Oxv2QbmAAUW00003__mC0)

  c) Nhiệm vụ:
  - DịchVụThanhToan: Xử lý logic thanh toán, gọi đến CổngThanhToan để thực hiện thanh toán, gửi thông báo cho người dùng.
  - NgườiDùng: Gửi yêu cầu thanh toán, nhận thông báo về trạng thái thanh toán.
  - CổngThanhToan: Kết nối với hệ thống thanh toán bên ngoài, xác thực và xử lý giao dịch thanh toán.
  - DịchVụThôngBáo: Gửi thông báo đến người dùng về trạng thái thanh toán.

  **Ca sử dụng: Maintain Timecard**:

  a) Các lớp phân tích:
  - DịchVụThẻThờiGian: Xử lý các yêu cầu liên quan đến thời gian làm việc.
  - NgườiDùng: Đại diện cho nhân viên.
  - CơSởDữLiệu: Lưu trữ thông tin thời gian làm việc.
  - DịchVụThôngBáo: Gửi thông báo cho người dùng về trạng thái cập nhật.

  b) Biểu đồ:

  ![Diagram](https://www.planttext.com/api/plantuml/png/UhzxlqDnIM9HIMbk3bS1aCvCpYn8p2jHy4i_jk7XxhcPBeTtvgMZoBWytDsTd17sSFVIa8o7ktO32Q0ozyp4F1HLpiSM1Z_SFH-eUBrFviFTxQKupJYy9I_TwV32V2uk53iLTErmMsMbuFvmzzfCXHAGC8W4YYkaWzo0Kml8F0n7MIdu7DjGYiKO39KAklZT4t5uOR927b1qBLut00r1yQMLGaZHmrqBWTujoJYyC5CX6MX00SIS4ln-mHQ4Y601YIWaWK8Lcpgixa3eGN45bi1nICrB0QKN00000F__0m00)

  c) Nhiệm vụ:
  - DịchVụThẻThờiGian: Xử lý logic lưu trữ thời gian làm việc, gọi đến CơSởDữLiệu để lưu thông tin, gửi thông báo cho người dùng.
  - NgườiDùng: Gửi yêu cầu cập nhật thời gian làm việc, nhận thông báo về trạng thái cập nhật.
  - CơSởDữLiệu: Lưu trữ thông tin thời gian làm việc, xác nhận thông tin đã được lưu trữ.
  - DịchVụThôngBáo: Gửi thông báo đến người dùng về trạng thái cập nhật thời gian làm việc.

**2) Code mô phỏng ca Maintain Timecard(Java)**:

  
