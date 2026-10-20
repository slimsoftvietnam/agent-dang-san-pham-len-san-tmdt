# Mô-đun Lazada (Seller Center Việt Nam)

Phạm vi: sản phẩm của đúng cửa hàng Lazada được người dùng chỉ định. Ghi nhận biểu mẫu Seller Center ngày 19/10/2026; các dấu sao và giới hạn phải kiểm tra lại theo danh mục khi chạy. Không dùng mô-đun này cho Shopee/TikTok Shop.

## Khảo sát và ánh xạ

1. Xác nhận cửa hàng, tra SKU/ID để quyết định tạo mới hay cập nhật đúng bản nháp. Chọn danh mục lá; qua API, `GetCategoryTree` và `GetCategoryAttributes` cho biết danh mục lá, `is_mandatory`, thuộc tính SPU/SKU và tùy chọn hợp lệ. [Tài liệu danh mục Lazada](https://open.lazada.com/apps/doc/doc?docId=120946&nodeId=30715).
2. Mở toàn bộ phần của biểu mẫu (kể cả “Hiển thị thêm”): Thông tin cơ bản, Đặc tính sản phẩm, Giá bán/Kho/biến thể, Mô tả, Vận chuyển/Bảo hành. Ghi danh sách dấu sao và trường bắt buộc có điều kiện sau khi đã chọn danh mục/biến thể. Chỉ đánh dấu đủ khi kiểm tra từng trường và thông báo lỗi sau khi lưu/mở lại.
3. Quan sát ngày 19/10/2026 với danh mục túi tote nữ: ảnh chính, tên, danh mục, thương hiệu, chất liệu, giá, khối lượng kiện hàng, dài × rộng × cao kiện hàng có dấu sao. Danh mục khác có thể thêm/bớt thuộc tính; không dùng danh sách này thay cho bước 2. Không tự lấy thương hiệu/chất liệu từ AI gợi ý. Nếu không có thương hiệu, chỉ chọn lựa chọn “không thương hiệu” khi UI cho phép và dữ liệu người bán phù hợp; nếu không, hỏi người dùng.
4. Excel dùng `can_nang_g`; biểu mẫu đang hiển thị kg, nên chuyển chính xác g ÷ 1000 và kiểm tra lại giá trị/đơn vị. Dài/rộng/cao là cm của **kiện hàng sau đóng gói**. Giới hạn UI quan sát: 0,001–300 kg và 0,01–320 cm; kiểm tra lại tại thời điểm nhập. Bảo hành không có dấu sao trên biểu mẫu đã quan sát nhưng vẫn điền theo dữ liệu đã duyệt; “Không bảo hành” là một tùy chọn UI, không được tự chọn cho hàng thật.

## Đường ghi nháp

- [Product API Overview](https://open.lazada.com/apps/doc/doc?docId=120945&nodeId=29614) và [CreateProduct](https://open.lazada.com/apps/doc/doc?docId=120949&nodeId=30720) xác nhận API tạo/cập nhật sản phẩm và truy vấn thuộc tính. **Chưa xác minh CreateProduct có chế độ lưu nháp an toàn cho cửa hàng này**, nên không gọi API đó để thử bằng hàng thật hoặc DEMO. Nếu sau này xác minh được chế độ nháp bằng tài liệu và tài khoản được cấp quyền, cập nhật mô-đun rồi mới dùng API.
- Hiện dùng giao diện Seller Center: nhập đầy đủ trường đã duyệt, kiểm tra mọi dấu sao, chỉ bấm **Lưu bản nháp**, tuyệt đối không bấm **Gửi đi**. Trước khi lưu, xác nhận “Mở bán” của từng SKU vẫn tắt và cửa hàng đích đúng.
- Mở lại URL nháp, kiểm tra tên/mô tả/ảnh/danh mục/brand/thuộc tính/giá/SKU/kho/khối lượng/kích thước, các cảnh báo bắt buộc và trạng thái “Khách hàng sẽ không nhìn thấy Bản Nháp”. Lazada có thể hiện lại nhãn `PreFilled` cùng thuộc tính do AI gợi ý dù đã xóa trước khi lưu; đừng coi gợi ý đó là dữ kiện từ Excel hoặc tuyên bố đã xác minh nội dung thuộc tính. Sửa khi có thể, ghi rõ phần còn mơ hồ trong HTML và tiếp tục sản phẩm độc lập khác nếu chỉ lỗi riêng bản nháp này. Nếu còn lỗi bắt buộc thì **không** báo là đã điền đủ để người bán đăng.

## Kinh nghiệm thực tế (chạy ngày 20/10/2026, cửa hàng thử nghiệm)

- **Điểm nội dung** nằm ở thẻ “Điểm nội dung” góc trên bên phải form (kèm checklist các mục). Hai nháp tạo mới chỉ có 1 ảnh, không video, mô tả ngắn chỉ đạt **75** (không đạt yêu cầu > 90). Để vượt 90, lên kế hoạch ngay từ chặng 1: ≥ 3–5 ảnh sản phẩm (ảnh chính nền trắng vuông 1:1, tối thiểu 330×330, khuyến nghị 1000×1000), thuộc tính đủ 100%, mô tả đầy đủ, khối lượng/kích thước, video nếu có, tên đủ dài; đọc checklist dưới điểm để biết mục nào còn thiếu và đọc lại điểm sau khi lưu và mở lại nháp.
- **Mẹo tăng điểm nhanh nhất (đã kiểm chứng 20/10/2026): chèn ít nhất 1 ảnh vào ô “Mô tả sản phẩm”.** Nháp có 7 ảnh sản phẩm vẫn chỉ 88; thêm 1 ảnh trong mô tả lên **100**, giữ nguyên sau khi lưu và mở lại. Cách làm: cuộn tới ô mô tả, bấm biểu tượng ảnh (`.lzd-pdp-editor .weicon-toolbar-picture`, bấm bằng `dispatchEvent` mousedown/mouseup/click lên `.icon-button` cha), trong hộp “Thư viện đa phương tiện” tích checkbox ảnh của đúng sản phẩm (ảnh đã tải lên trước đó, đặt tên theo SKU để dễ chọn), bấm “Gửi”, rồi “Lưu bản nháp” và đọc lại điểm. Thêm ảnh sản phẩm thường không làm điểm tăng.
- **Tạo nháp mới:** bước đầu chỉ có ảnh + tên + danh mục; điền tên ≥ 10 ký tự, chọn danh mục lá (có thể gõ từ khóa và chọn radio gợi ý) rồi bấm “Tiếp theo” mới ra form đầy đủ. Lazada tự thêm tên tiếng Anh (AI) vào ô đa ngôn ngữ.
- **Thương hiệu:** gõ “No Brand” rồi chọn mục “No Brand” trong danh sách; sau khi chọn form vẽ lại và có thể xóa giá đã nhập, nên nhập giá sau thương hiệu.
- **Công tắc “Mở bán”** của SKU trong hàng giá/kho mặc định BẬT ở nháp mới; tắt trước khi lưu. Công tắc “Tiêu chuẩn” ở mục Vận chuyển là tùy chọn giao hàng, để nguyên.
- **Mô tả:** ô soạn tuỳ biến, không phải contenteditable; bấm vào ô để focus rồi gõ. Gõ nhầm lúc giá chưa vào ô đã làm “45000” lọt vào mô tả: sau khi gõ, đọc lại nội dung ô mô tả.
- **Bảo hành:** bấm “Cài đặt bảo hành hơn” mới hiện Loại bảo hành, Thời gian bảo hành, Chính sách bảo hành, Return Policy. “Không bảo hành” là một lựa chọn trong danh sách (hàng thật chỉ chọn khi người bán xác nhận).
- **Thuộc tính AI:** sau mỗi lần lưu Lazada có thể điền lại “Loại khóa”, “Tính năng bảo quản”… vô nghĩa với sản phẩm (Khóa kéo, Nhiều ngăn, Chống nước). Xóa khi lưu, mở lại kiểm tra; nếu bị điền lại, ghi vào báo cáo.
- **Danh mục** “Dụng cụ lưu trữ và sắp xếp › hộp bút” là gợi ý từ khóa “ống cắm bút”; “Khay đựng đồ để bàn” là lựa chọn gần khác. Luôn cho người dùng xác nhận.
- **Tải ảnh bằng trình duyệt trong app (không có hộp chọn file):** (1) trên trang Lazada ghi đè `HTMLInputElement.prototype.click` để bắt `input[type=file]` vào `window.__fi`; (2) bấm “+” ảnh (nếu hiện menu thì chọn “Đăng tải”); (3) `fetch` ảnh (images.pexels.com cho CORS; thêm `?w=1200&h=1200&fit=crop` để cắt vuông) thành `File`, gán `__fi.files` bằng `DataTransfer` rồi bắn sự kiện `change`. Thư viện Đa phương tiện chỉ chứa ảnh đã tải lên trước đó, không có ô nhập URL; thêm ảnh vào cùng ô để đủ nhiều ảnh cho điểm nội dung.
- **Toạ độ chuột:** công cụ nhận toạ độ trong khung ảnh chụp (800×514 khi viewport 1400×900), không phải pixel CSS; bấm bằng tham chiếu (`ref`) từ `find`/`read_page` cho chắc.
- Mở nháp bằng `https://sellercenter.lazada.vn/apps/product/publish?draftId=<ID>`; ID lấy từ liên kết “Chỉnh sửa” trong tab Bản nháp (`?tab=draft`). Sau khi lưu, trang tự chuyển sang URL có `draftId`.

## Nội dung SEO

Ưu tiên cụm sản phẩm tự nhiên ở đầu tên; đưa đặc điểm đã xác nhận vào phần còn lại. Mô tả có câu đầu nêu đúng loại sản phẩm, sau đó chất liệu, kích cỡ/công dụng, thông tin đóng gói/bảo quản khi có nguồn. Tránh lặp từ khóa, nhãn hiệu giả, chất liệu/nguồn gốc do AI đoán. Với hàng mẫu, đánh dấu DEMO và nguồn ảnh trong SKU/bản xem trước/báo cáo; tên và mô tả hiển thị có thể viết tự nhiên theo yêu cầu người dùng. So sánh tên–mô tả gốc với bản SEO trong xem trước.
