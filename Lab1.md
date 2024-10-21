# 1. Phân tích kiến trúc
## a. Đề xuất kiến trúc
Kiến trúc đề xuất cho hệ thống này là kiến trúc Layered Architecture (kiến trúc phân lớp). Kiến trúc này bao gồm các lớp chính sau:

- Presentation Layer: Giao diện người dùng.
- Business Logic Layer: Xử lý logic nghiệp vụ.
- Data Access Layer: Truy cập dữ liệu.
- Database Layer: Lưu trữ dữ liệu.

## b. Giải thích lý do lựa chọn và ý nghĩa từng thành phần trong kiến trúc
- Presentation Layer:
  - Lý do lựa chọn: Tách biệt giao diện người dùng khỏi logic nghiệp vụ giúp dễ dàng thay đổi giao diện mà không ảnh hưởng đến các phần khác của hệ thống.
  - Ý nghĩa: Cung cấp giao diện để nhân viên chọn và nhập thông tin phương thức thanh toán.
- Business Logic Layer:
  - Lý do lựa chọn: Tách biệt logic nghiệp vụ giúp dễ dàng bảo trì và mở rộng hệ thống.
  - Ý nghĩa: Xử lý các yêu cầu từ Presentation Layer, thực hiện các quy tắc nghiệp vụ như xác minh thông tin nhân viên, cập nhật phương thức thanh toán.
- Data Access Layer:
  - Lý do lựa chọn: Tách biệt logic truy cập dữ liệu giúp dễ dàng thay đổi cách thức lưu trữ dữ liệu mà không ảnh hưởng đến các phần khác của hệ thống.
  - Ý nghĩa: Quản lý việc truy xuất và cập nhật dữ liệu từ cơ sở dữ liệu.
- Database Layer:
  - Lý do lựa chọn: Lưu trữ dữ liệu một cách có tổ chức và an toàn.
  - Ý nghĩa: Lưu trữ thông tin nhân viên và phương thức thanh toán.

## c. Biểu đồ package mô tả kiến trúc
![Diagram](https://www.planttext.com/api/plantuml/svg/d9GnIyD068Rt_8gFJ3eKmT51IbkeOYaAiRWUQSWTffUGD4AHJWuE8kZWu5XB5o5OSCiX3f7-Z_i5_WNlMjeclOIctlgztyFxtht9B_kk1dtazyEUetd8l4Qs1Ve9P_TWOCwUgGtdQE2xZgF3hGRYh4JDv9D0ao0N6aJeAUnTdkulLVAO3Wg2kM8XQEFaZNP8yavJec6X_2BayPWQFcSFYdwevNYvuYo2Ll85RHjBWWSTpYQgeuOWcbZEZ2IYk3MRpaOYPx6dzKAf22a-wLacyhlbn1XHRBZ9I6NdnZNyS01r7aUUX7n0IsOErRXds9NpnRXKWCn6YGnP_QunaiZ481etzbJlDSvUwpWSS7P7VvuuUo6Dsc4HDxTfbSfnqOCVWHx8odJ5WDhw1YDTlnqX1T8ifItkgKCiAWasPuzaXztLc_ndT_q-sUqDnCgVN2_ga20uisbuq9TTlE7nX2fEbbOLJ3h4DiZQiuh9v550soucls62D8UOylFIDL6mgaMxuX_v1m00__y30000)

# 2. Cơ chế phân tích
## a. Xác thực Người dùng (User Authentication):

- Mô tả: Đảm bảo rằng chỉ những nhân viên đã đăng nhập mới có thể truy cập tính năng chọn phương thức thanh toán.
- Lý do: Bảo mật thông tin cá nhân và ngăn chặn truy cập trái phép vào hệ thống.
## b. Xác minh Thông tin Nhân viên (Employee Information Validation):

- Mô tả: Kiểm tra tính chính xác và tính hợp lệ của thông tin nhân viên trước khi cho phép họ thay đổi phương thức thanh toán.
- Lý do: Đảm bảo rằng các thay đổi không gây ra lỗi hoặc thông tin không chính xác trong hệ thống.
## c. Quản lý Tùy chọn Phương thức Thanh toán (Payment Method Management):

- Mô tả: Cung cấp cho nhân viên các tùy chọn để chọn phương thức thanh toán và thu thập thông tin cần thiết cho từng phương thức.
- Lý do: Tạo điều kiện thuận lợi cho nhân viên trong việc lựa chọn và cập nhật phương thức thanh toán theo nhu cầu của họ.
## d. Cập nhật Thông tin Nhân viên (Employee Information Update):

- Mô tả: Cập nhật thông tin thanh toán vào cơ sở dữ liệu khi nhân viên đã chọn xong phương thức.
- Lý do: Đảm bảo rằng tất cả thông tin mới được lưu trữ và sử dụng cho các giao dịch sau này.
## e. Thông báo và Xử lý Lỗi (Notification and Error Handling):

- Mô tả: Cung cấp thông báo cho nhân viên về tình trạng cập nhật phương thức thanh toán và xử lý các lỗi xảy ra trong quá trình.
- Lý do: Giúp nhân viên nắm rõ tình trạng yêu cầu của họ và giảm thiểu sự nhầm lẫn khi có lỗi xảy ra.

## f. Lưu trữ và Quản lý Dữ liệu (Data Storage and Management):

- Mô tả: Lưu trữ thông tin nhân viên và phương thức thanh toán trong cơ sở dữ liệu an toàn.
- Lý do: Đảm bảo tính toàn vẹn và bảo mật của thông tin cá nhân, đồng thời cho phép truy xuất và cập nhật dễ dàng.
