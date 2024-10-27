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
## a. Legacy Interface:
- Lý do: Legacy interface là một cách thức hoặc giao thức cho phép các hệ thống mới (như hệ thống payroll) tương tác với các hệ thống cũ (legacy systems) mà không làm thay đổi hoặc phá vỡ hoạt động của các hệ thống đó
## b. Persistence:
- Lý do: Persistence đảm bảo rằng tất cả thông tin về nhân viên, thời gian làm việc, lương và các giao dịch liên quan được lưu trữ và có thể truy xuất lại.
## c. Security:
- Lý do: Security đảm bảo những việc sau trong hệ thống bao gồm bảo vệ thông tin cá nhân và tài chính của nhân viên, cũng như thông tin về lương và thời gian làm việc.
