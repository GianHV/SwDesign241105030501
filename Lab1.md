# 1. Phân tích kiến trúc
## a. Đề xuất kiến trúc
Kiến trúc đề xuất cho hệ thống này là kiến trúc Clean Architecture của Unclude Bob. Kiến trúc này bao gồm các lớp chính sau:

- Infrastructure Presentation Layer: ánh xạ tới các lớp khác.
- Use Case Layer: là phần core của hệ thống, nó chứa tất cả các business logic code và chỉ phụ thuộc vào entities layer.
- Infrastructure Data Layer: làm việc với hệ thống bên ngoài.
- Entities Layer: là trái tim của kiến trúc.

## b. Giải thích lý do lựa chọn và ý nghĩa từng thành phần trong kiến trúc
- Infrastructure Presentation Layer:
  - Lý do lựa chọn: Tách biệt giao diện người dùng khỏi logic nghiệp vụ giúp dễ dàng thay đổi giao diện mà không ảnh hưởng đến các phần khác của hệ thống.
  - Ý nghĩa: Cung cấp giao diện để nhân viên chọn và nhập thông tin phương thức thanh toán.
- Use Case Layer:
  - Lý do lựa chọn: Tách biệt logic nghiệp vụ giúp dễ dàng bảo trì và mở rộng hệ thống.
  - Ý nghĩa: Xử lý các quy tắc kinh doanh, tính toán lương, xác thực dữ liệu, tương tác với cơ sở dữ liệu. 
- Infrastructure Data Layer:
  - Lý do lựa chọn: Tách biệt logic làm việc với dữ liệu với tần.
  - Ý nghĩa: Quản lý việc truy xuất và cập nhật dữ liệu từ cơ sở dữ liệu.
- Entities Layer:
  - Lý do lựa chọn: Lưu trữ dữ liệu một cách có tổ chức và an toàn.
  - Ý nghĩa: Lưu trữ thông tin nhân viên và phương thức thanh toán.

## c. Biểu đồ package mô tả kiến trúc
![Diagram](https://www.planttext.com/api/plantuml/png/Z9513e8m44NtdA9XpnKCHbYmCo4UO587qzWMqXcCn7Wo5nx9ArX44GIZi-YYR_f-fxrThZ4nEAwD3YgGUzYX2DVGk59haJV4Q49n2eIl7cUsS43iQicrmnTkIseW4kcHqLdGERg3aZZWvw1RnxuDeLW1pPWyQS74yEx8hCygu8-K11Z4KaeacWPbfj9eq3AeqlvKfPOLAvpn9AK1zLNGqIXQFETwRFOJ-FtHDIPqT6hOwTd7cmS-CKQxzTzw1m00__y30000)

# 2. Cơ chế phân tích
## a. Legacy Interface:
- Lý do: Legacy interface là một cách thức hoặc giao thức cho phép các hệ thống mới (như hệ thống payroll) tương tác với các hệ thống cũ (legacy systems) mà không làm thay đổi hoặc phá vỡ hoạt động của các hệ thống đó
## b. Persistence:
- Lý do: Persistence đảm bảo rằng tất cả thông tin về nhân viên, thời gian làm việc, lương và các giao dịch liên quan được lưu trữ và có thể truy xuất lại.
## c. Security:
- Lý do: Security đảm bảo những việc sau trong hệ thống bao gồm bảo vệ thông tin cá nhân và tài chính của nhân viên, cũng như thông tin về lương và thời gian làm việc.

# 3. Phân tích ca sử dụng Payment
## a. Xác định các lớp phân tích cho ca sử dụng Payment
- Boundary: PaymentMethodForm, ProjectManagementDatabase
- Control: PaymentController
- Entity: Employee
## b. Sequence Diagram
![CHESSE!](images/Untitled%20Diagram.drawio.png)
## c. Class Diagram
![Diagram](https://www.planttext.com/api/plantuml/png/T5BBJiCm4BpxArOv0H9HkKTL4G-9GoKalc3ZR1ktVaJs6XGGNyQ1J-8Ni1DQ16akwrtRC-CP-UlZSnKOFKUZHTWhsw570r9Z2DVCNjMHwK4w-wHU2HP232VmYBqXoslYrZNtpXkegjf5sw3lbqju4m2XTI_WEbREXhFpumQtv279H4vrav2ORumNOcqKPxOqll-Jkd6MlTCweQjAZiEFqfRuZv1iIUvFQloIUhSZoMkqkALCVukCDGOwuGEVQOxcpdJQzPHHYKFn0MFHK5gmQJo5a3if4ok3ZQOcdrb99tteHdF3ipTAwwdGDEdYge3BeKwY4TEmYaLPZe2ncNKkvZCvA9RbHN7qBCIAR9E-pJS0003__mC0)

# 4. Phân tích ca sử dụng Maintain Timecard
## a. Xác định các lớp phân tích cho ca sử dụng Payment
- Boundary: TimecardForm, ProjectManagementDatabase
- Control: TimecardController
- Entity: Employee, Timecard
## b. Sequence Diagram
![Diagram](https://www.planttext.com/api/plantuml/png/b9H1ReCm44NtFeMNH6eka4KLYQPg5gsggXUOu4b21JOQnf4uMnSzKgzGOq8CJPmGTZRp_iVVC_n-_onh1c9R5W8oDYHNPLMO1b5iZDKAg96VUOaPa7esL8hCQ2PJd3RJRbqW2TISSoWF0kzalZ3ZLz2mmzALFG731ceKxkdzvFnnvBIGfaATpCHmSrWKd1ToXvnQ8YVTlqtmgBjMGI8WGo6FzukrtfgBh9n7l0dPafPPvo-vF_ubqxCpghok2cZEQG45ovLcH-sDfLfktTraUw0TIctBZSjRkYUU7hRiIukwTUh1DyybNk_XADRjpRpObAHjfO3nbF9DhLZaz-f4utSDkSsf1CwDZZf7S-y-GuNSKH-p_q2c70_OXvuPXVNacDg6z5pQOicrJABJ4L69rj_iqDX1fdNeaFOfNHdT6WxXRgUDy0ZvFmwtHxZ5amdJEcgNkm9e7SQuMBeSt9_p3m00__y30000)
## c. Class Diagram
![Diagram](https://www.planttext.com/api/plantuml/png/Z5DBJiCm4Dtd5AEk08bIjYYgG7ma5aX8S869FMrCOpiQEw22E1aBZiGLc2PrA6cBM2InP_pclNdZV7rydeU871jRPM5XN8sC5bI58Lp4oAPe8jqgxnxCAy4aozeCF1fB2bdVUBQGvuLld4PUJgVmbW6SW3QXhd09SNtkuB0D-vhSUaak4aFf6mumymogH9uJkCOMn65zoA9nKPvXdO3Fj1bx7-gwz2wohogXo7FLRNfnSugW6cQHC2pSfZebocjAEffQOwH_gxXd_qGgtg73ELcXkSA81GRQPTKEogrs12TLJ4oephONpmlIigt5wPhOUDthskWdAGJZPdvlGptdjQqhloGQSZgq91zAQRCYAz0jshgo3buPh22GU2kmzIWbWLepXR0IMdf7FmcI-LQT_fLBO2cMqeD8-NM_HgSZE6xVs-FDTanyD1cFEqYts3kEly4RV72MBaoAzD0MS9G0oRmiEoUdvP_w1W00__y30000)
