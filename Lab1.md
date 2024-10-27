# 1. Phân tích kiến trúc
## a. Đề xuất kiến trúc
Kiến trúc đề xuất cho hệ thống này là kiến trúc Clean Architecture của Unclude Bob. Kiến trúc này bao gồm các lớp chính sau:

- Infrastructure Presentation Layer: .
- Use Case Layer: .
- Infrastructure Data Layer: .
- Entities Layer: .

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
