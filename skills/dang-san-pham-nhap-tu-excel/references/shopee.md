# Mô-đun Shopee

Trạng thái: mô-đun tách riêng, **chưa chuẩn hóa theo cửa hàng/danh mục cụ thể**. Không dùng trường, giới hạn hoặc nút của Lazada. Bắt đầu từ [Shopee Open Platform](https://open.shopee.com/) và Seller Centre của đúng quốc gia/cửa hàng; kiểm tra tài liệu hiện hành trước mỗi lô. Không giả định API tạo sản phẩm có trạng thái nháp.

1. Xác minh cửa hàng, quyền kết nối và SKU đã tồn tại. Từ danh mục hiện hành, lập bảng thuộc tính bắt buộc ở cấp sản phẩm/biến thể, hình ảnh, nhãn hiệu, giá/kho, vận chuyển, cân nặng/kích thước, bảo hành/chính sách khi biểu mẫu yêu cầu. Mở mọi nhóm thu gọn và kiểm tra các dấu sao phát sinh sau khi chọn danh mục hoặc biến thể.
2. Xác minh cách API tạo/cập nhật **bản nháp** và cách đọc lại trạng thái bằng tài liệu chính thức + quyền của tài khoản. Chỉ dùng API khi đã chứng minh không đưa sản phẩm lên bán/gửi duyệt. Nếu không, dùng trình duyệt trong công cụ agent với nút lưu nháp đã quan sát. Nếu không có cách lưu nháp an toàn, dừng.
3. Tối ưu tên/mô tả theo quy tắc chung, đối chiếu độ dài và chính sách Shopee hiện hành. Cho người dùng duyệt toàn bộ giá trị bắt buộc, sau đó chỉ lưu nháp. Mở lại để xác minh tất cả trường bắt buộc và trạng thái không hiển thị/bán. Không tuyên bố mô-đun đã sẵn sàng cho cửa hàng mới chỉ vì tệp này tồn tại.
