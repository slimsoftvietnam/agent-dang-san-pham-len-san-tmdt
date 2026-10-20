# Cấu trúc Excel và kiểm tra trước khi tạo nháp

Mẫu có ba tab: `Hướng dẫn` (không nhập), `Sản phẩm` và `Biến thể`. Hàng 1 của hai tab dữ liệu là tên trường cố định. Hàng 2 trở đi là dữ liệu; bỏ qua hàng hoàn toàn trống. Mỗi sản phẩm cần ít nhất một biến thể, kể cả sản phẩm chỉ có một SKU. Một `ma_san_pham` có thể có nhiều `sku`; `sku` phải duy nhất trong toàn file. Không dùng thứ tự dòng làm khóa.

## Sản phẩm

| Trường | Yêu cầu | Kiểm tra |
| --- | --- | --- |
| `ma_san_pham` | Bắt buộc | Mã nội bộ dạng văn bản, duy nhất, không khoảng trắng đầu/cuối. |
| `ten_san_pham` | Bắt buộc | Không trống; đối chiếu độ dài và từ cấm của sàn/danh mục. Giữ bản gốc khi đề xuất bản SEO. |
| `mo_ta` | Bắt buộc trong mẫu | Không trống; đối chiếu định dạng và nội dung được phép. Giữ bản gốc khi đề xuất bản SEO. |
| `danh_muc_san` | Bắt buộc | Mã danh mục đúng của sàn đích; kiểm tra qua danh mục hiện hành, không đoán từ tên. |
| `thuong_hieu` | Bắt buộc khi sàn/danh mục có dấu sao | Không tự bịa nhãn hiệu. Chỉ chọn “không thương hiệu” nếu đó là lựa chọn hợp lệ và phù hợp dữ liệu người bán. |
| `anh_chinh` | Bắt buộc | URL HTTPS hoặc đường dẫn ảnh nội bộ được phép truy cập; kiểm tra ảnh và quyền dùng. |
| `anh_phu` | Tùy chọn | Nhiều URL/đường dẫn phân tách bằng dấu `|`; kiểm tra từng ảnh và giới hạn số ảnh. |
| `can_nang_g` | Bắt buộc khi sàn yêu cầu | Số dương, đơn vị gram. |
| `dai_cm`, `rong_cm`, `cao_cm` | Bắt buộc khi sàn yêu cầu | Số dương, đơn vị cm. |
| `hang_nguy_hiem` | Tùy sàn/danh mục | Chỉ nhận phân loại do người dùng xác nhận; không suy từ ảnh minh họa. |
| `loai_bao_hanh` | Tùy sàn/danh mục | Loại bảo hành hoặc không bảo hành theo xác nhận của người bán; không tự tạo cam kết. |
| `thoi_gian_bao_hanh` | Khi có bảo hành | Giá trị và đơn vị đúng tùy chọn hiện hành của sàn; nhất quán với loại bảo hành. |
| `chinh_sach_bao_hanh` | Khi có bảo hành hoặc sàn yêu cầu | Văn bản chính sách do người bán cung cấp; không tự bịa điều khoản. |
| `chinh_sach_doi_tra` | Tùy sàn/danh mục | Văn bản do người bán cung cấp, đối chiếu chính sách hiện hành của sàn. |
| `thuoc_tinh_json` | Tùy sàn/danh mục | JSON object cho thuộc tính theo mã sàn; kiểm tra schema danh mục. |
| `ghi_chu_noi_bo` | Tùy chọn | Chỉ để người kiểm tra đọc; không gửi lên sàn. |

## Biến thể

| Trường | Yêu cầu | Kiểm tra |
| --- | --- | --- |
| `ma_san_pham` | Bắt buộc | Phải khớp chính xác một sản phẩm trong tab `Sản phẩm`. |
| `sku` | Bắt buộc | Văn bản duy nhất; giữ số 0 đầu nếu có. |
| `ten_bien_the` | Tùy chọn | Ví dụ kích cỡ/màu; đối chiếu nhóm biến thể của sàn. |
| `gia_vnd` | Bắt buộc | Số lớn hơn 0, VND; đối chiếu mức giá của sàn. |
| `so_luong` | Bắt buộc | Số nguyên không âm. |
| `gia_khuyen_mai_vnd` | Tùy chọn | Số lớn hơn 0 và không vượt `gia_vnd`; chỉ gửi nếu sàn hỗ trợ lưu nháp an toàn. |
| `gtin` | Tùy sàn/danh mục | Mã dạng văn bản; kiểm tra chuẩn và số 0 đầu. |
| `anh_bien_the` | Tùy chọn | URL HTTPS hoặc đường dẫn ảnh nội bộ. |
| `thuoc_tinh_bien_the_json` | Tùy sàn/danh mục | JSON object như `{"Màu":"Đen","Cỡ":"M"}`; kiểm tra khóa/giá trị theo sàn. |

## Cách diễn giải và ánh xạ

- Ô trống tùy chọn là “không cung cấp”, không phải số 0 hoặc chuỗi rỗng để ghi đè dữ liệu đã có.
- Giá, tồn kho, kích thước và cân nặng phải là ô số thật; SKU, GTIN và mã sản phẩm phải là văn bản. Khối lượng/kích thước là **kiện hàng sau đóng gói**, không phải số đo sản phẩm trần. Không đổi đơn vị ngầm.
- Khi sàn có mục Vận chuyển và Bảo hành, kiểm tra từng trường, kể cả trường đang bị thu gọn trong giao diện. Để trống nghĩa là chưa cung cấp; không tự chọn “không bảo hành”, thời hạn, điều khoản đổi trả hoặc giá trị cân nặng/kích thước cho hàng thật. Nếu người dùng yêu cầu dữ liệu DEMO, ghi rõ mọi giá trị giả định ở bản sao và bản xem trước; không gọi hàng DEMO là sẵn sàng bán.
- Trường có dấu sao và yêu cầu có điều kiện của biểu mẫu/API hiện hành được ưu tiên hơn nhãn “tùy chọn” trong mẫu chung. Lập checklist theo từng danh mục/biến thể; thiếu bất kỳ trường bắt buộc nào thì giữ sản phẩm ở bước kiểm tra, không cập nhật bản nháp rồi báo là đã hoàn tất.
- JSON chỉ dùng cho thuộc tính chưa có cột riêng. Không cho phép khóa kiểm soát trạng thái như `status`, `publish`, `active`, `is_live`, `submit_for_review` trong JSON. Khi sàn dùng tên khóa khác có cùng tác dụng, cũng loại bỏ và báo lỗi.
- Kiểm tra các yêu cầu thay đổi theo sàn/danh mục ngay trước khi chạy. Tạo bảng ánh xạ trường Excel → trường sàn và báo các trường bắt buộc không có trong mẫu; có thể bổ sung cột rõ ràng sau khi thống nhất với người dùng. Không đưa dữ liệu thiếu vào payload giả định.
- Bản ghi ví dụ trong tab `Hướng dẫn` không được nhập lên sàn. Chỉ đọc dữ liệu ở hai tab dữ liệu.
- Báo cáo kết quả cần lưu `ma_san_pham`, danh sách `sku`, dòng nguồn, trạng thái trước/sau, ID/URL quản trị, lỗi và thời điểm. Không ghi credential.
