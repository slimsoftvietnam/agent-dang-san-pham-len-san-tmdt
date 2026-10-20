---
name: dang-san-pham-nhap-tu-excel
description: Phân tích Excel (thiếu/sai thì hỏi lại người dùng), tối ưu nội dung, điền đủ mọi trường bắt buộc và đưa Điểm nội dung của sàn lên trên 90 trước khi lưu nháp; xuất báo cáo HTML đẹp mắt. Dùng khi nhập sản phẩm từ Excel lên sàn thương mại điện tử, không tự đăng bán.
---

# Đăng sản phẩm nháp từ Excel

Thực hiện theo bốn chặng dưới đây, đúng thứ tự. Mục tiêu là bản nháp đã điền đủ trường bắt buộc để người bán có thể tự xem xét bước đăng, không phải bản nháp thiếu dữ liệu. Chỉ lưu nháp, không gửi duyệt hoặc kích hoạt bán. Điền đủ dấu sao không bảo đảm sàn phê duyệt; dữ liệu DEMO không được coi là hàng thật sẵn sàng bán.

## Năm yêu cầu bắt buộc (đạt cả năm mới được báo “hoàn tất”)

1. **Điểm nội dung > 90.** Đọc “Điểm nội dung” ở góc trên bên phải của biểu mẫu sàn (trên Lazada: thẻ “Điểm nội dung” cạnh danh sách các mục) *sau khi mở lại bản nháp đã lưu*. Điểm phải **lớn hơn 90** (không phải 90). Mở checklist ngay dưới điểm, làm từng mục thiếu có nguồn dữ liệu thật (ảnh, video, thuộc tính, mô tả, kích thước…) rồi lưu và đọc lại điểm. Điểm ≤ 90 thì sản phẩm chưa hoàn tất: nêu rõ mục nào còn thiếu và hỏi người dùng dữ kiện còn thiếu; không tự bịa thuộc tính hay thông số để chạy điểm.
2. **Điền đầy đủ mọi trường bắt buộc** (dấu sao và bắt buộc theo điều kiện) ở mọi mục, kể cả mục thu gọn; không còn lỗi đỏ sau khi lưu và mở lại.
3. **Báo cáo HTML đẹp mắt**, theo mục “Yêu cầu báo cáo HTML” bên dưới.
4. **Phân tích Excel trước khi ghi lên sàn**; thấy thiếu hoặc sai thông tin thì **dừng và hỏi lại người dùng**, không tự suy diễn (xem chặng 1).
5. **Học từ kinh nghiệm**: áp dụng mục “Kinh nghiệm và lưu ý” ở cuối file này và mô-đun sàn; có điều mới thì bổ sung vào đó.

## 1. Hỏi file Excel, đọc và phân tích

- Nếu chưa có file, trước tiên hỏi người dùng tải lên hoặc chỉ đường dẫn file Excel chứa thông tin sản phẩm. Có thể đưa [file mẫu](assets/mau-san-pham-nhap.xlsx) để họ điền. Chờ file rồi mới chuyển sang câu hỏi về sàn. Nếu người dùng đã cung cấp file, đọc ngay; không hỏi lại.
- Đọc nguyên trạng file. Dùng [cấu trúc mẫu và quy tắc kiểm tra](references/excel-schema.md) khi phù hợp; với Excel khác mẫu, nhận diện cột thực tế, lập ánh xạ và chỉ hỏi những trường không thể suy ra an toàn. Kiểm tra kiểu dữ liệu, mã sản phẩm/SKU trùng, quan hệ sản phẩm–biến thể, giá, tồn kho, ảnh, dữ liệu thiếu và các lỗi theo tab/dòng/cột. Không tự bịa dữ liệu hoặc sửa âm thầm file nguồn. Nếu một biến thể lỗi, giữ toàn bộ sản phẩm đó lại để sửa.
- Nếu người dùng yêu cầu tự tạo dữ liệu DEMO, tạo trong bản sao có nhãn DEMO và đưa vào bản xem trước; không biến số đo, chất liệu, thương hiệu hoặc chính sách giả định thành thông tin hàng thật. Với hàng thật, hỏi dữ kiện còn thiếu.
- **Phân tích đầy đủ trước khi đăng, lập bảng “thiếu/sai” theo từng sản phẩm.** Kiểm tra: trường bắt buộc trống (tên, mô tả, danh mục, thương hiệu, ảnh chính, giá, tồn kho, khối lượng và kích thước kiện, bảo hành/đổi trả nếu sàn yêu cầu); sai kiểu hoặc đơn vị (giá/số lượng không phải số, âm hoặc 0; khối lượng không phải gam; kích thước ngoài giới hạn sàn); SKU/mã trùng; biến thể không khớp sản phẩm; đường dẫn ảnh không tồn tại hoặc không tải được; tên/mô tả quá ngắn, quá dài hoặc chứa từ cấm; giá khuyến mại cao hơn giá gốc; thông tin mâu thuẫn (tên nói “gỗ” mà thuộc tính nói “nhựa”); ảnh tham chiếu thư mục không có trong máy (ví dụ `images/...png` không tồn tại).
- **Thiếu hoặc sai thì hỏi lại người dùng trước khi ghi**, bằng một câu hỏi gộp: liệt kê sản phẩm/dòng/cột, giá trị hiện có, vấn đề, và các lựa chọn (người dùng bổ sung/sửa file; dùng dữ liệu DEMO có gắn nhãn; bỏ qua sản phẩm đó). Chỉ khi người dùng chọn DEMO mới được tạo giá trị giả định. Không hỏi lại điều đã rõ; không đăng sản phẩm còn lỗi chặn.
- Tóm tắt đã đọc được bao nhiêu sản phẩm và SKU, các lỗi cần sửa, rồi mới sang chặng 2. Nếu file không đọc được, hỏi người dùng gửi lại file; không hỏi sàn khi chưa phân tích được dữ liệu.

## 2. Hỏi sàn, xác định API hoặc trình duyệt

- Sau khi phân tích Excel, hỏi người dùng muốn đăng lên sàn nào và cửa hàng/tài khoản nào. Nếu họ đã nói rõ cả hai, dùng thông tin đó và chỉ hỏi phần còn thiếu.
- Chỉ đọc mô-đun của sàn đã chọn: [Lazada](references/lazada.md), [Shopee](references/shopee.md), hoặc [TikTok Shop](references/tiktok-shop.md). Không dùng quy tắc, đơn vị, tùy chọn hoặc nút của sàn này cho sàn khác. Với sàn chưa có mô-đun, khảo sát và tạo mô-đun riêng trước khi ghi.
- Xem tài liệu chính thức hiện hành và khả năng của kết nối được cấp quyền. Xác định API đăng sản phẩm, endpoint tạo/cập nhật, quyền cần có, giới hạn, ánh xạ trường, và đặc biệt cách lưu **nháp**. Cho người dùng biết API/tài liệu và cách sẽ dùng. Nếu có thể kết nối và lấy quyền qua cơ chế chính thức, thực hiện trong phạm vi tài khoản được người dùng cấp; không xuất token hay bí mật ra chat, Excel hoặc báo cáo.
- Nếu có API đăng nhưng chưa lấy được quyền truy cập, đọc tài liệu chính thức và hướng dẫn cụ thể người dùng tạo ứng dụng/lấy quyền/kết nối API cho sàn đó; chờ họ hoàn tất rồi tiếp tục. Không giả định thông tin xác thực hoặc lách quy trình cấp quyền. Nếu sàn không có API đăng sản phẩm phù hợp, hoặc API không có cách lưu nháp an toàn, chuẩn bị dùng trình duyệt bên trong công cụ agent với phiên đăng nhập của người dùng. Nếu trình duyệt cũng không lưu nháp được, dừng và báo rõ.
- Sau khi biết sàn, kiểm tra thêm yêu cầu theo danh mục, đối chiếu sản phẩm đã có bằng mã/SKU để tránh trùng, và hoàn tất danh sách lỗi/thiếu dữ liệu trước bước duyệt.
- Kiểm tra riêng mục **Vận chuyển và Bảo hành** của biểu mẫu sàn: khối lượng và kích thước của *kiện hàng sau đóng gói*, phân loại hàng nguy hiểm (nếu có), loại/thời hạn/chính sách bảo hành và chính sách đổi trả (nếu sàn yêu cầu). Không suy ra khối lượng, kích thước hoặc cam kết bảo hành từ ảnh hay tên sản phẩm. Trường còn thiếu phải hiện rõ trong bản xem trước và báo cáo; yêu cầu người dùng cung cấp trước khi ghi giá trị đó lên sàn.
- Kiểm kê **toàn bộ trường có dấu sao và trường bắt buộc theo điều kiện** ở mọi mục, kể cả mục đang thu gọn hoặc phát sinh khi đổi danh mục/biến thể. Đối chiếu dữ liệu nguồn, tùy chọn hợp lệ và đơn vị; thiếu một trường bắt buộc thì sản phẩm chưa đạt điều kiện ghi lên sàn. Không coi “Lưu nháp được” là “đủ để đăng”.

## 3. Cho người dùng kiểm tra trước khi ghi lên sàn

- Tối ưu tên và mô tả trước khi nhập: loại sản phẩm/từ khóa chính ở đầu, đặc tính phân biệt có bằng chứng (chất liệu, kích cỡ, màu, công dụng), văn phong tự nhiên dễ quét, đúng giới hạn sàn. Không nhồi từ khóa hoặc bịa thương hiệu, xuất xứ, chứng nhận, hiệu quả, khuyến mại. Với sản phẩm minh họa, giữ dấu DEMO/không sẵn sàng bán ở SKU, bản xem trước và báo cáo; nếu người dùng muốn câu chữ tự nhiên, không ép các nhãn này vào tên/mô tả hiển thị trên sàn.
- Trình bày bản xem trước có tên file, sàn/cửa hàng, phương thức, sản phẩm/SKU/ID đích, tên–mô tả gốc và bản SEO cạnh nhau, toàn bộ trường bắt buộc và dữ liệu DEMO, lỗi còn chặn, trạng thái dự kiến là **nháp**. Chỉ gọi sản phẩm “đã điền đủ trường bắt buộc” khi mọi dấu sao có giá trị hợp lệ; không đồng nghĩa “đã được sàn duyệt”.
- Cho người dùng cơ hội kiểm tra bản xem trước trước lần ghi đầu tiên. Khi người dùng đã yêu cầu tiếp tục với lô/cửa hàng đó hoặc giao quyền tự hoàn thiện, chủ động xử lý những chỉnh sửa thường lệ trong cùng phạm vi (SEO, ảnh minh họa, thuộc tính giao diện tự điền sai) mà không xin duyệt lại từng lần. Chỉ hỏi khi thiếu dữ kiện hàng thật không thể suy ra, thay đổi sàn/cửa hàng, hoặc mở rộng phạm vi sang sản phẩm khác.
- Chỉ ghi những sản phẩm hợp lệ và nằm trong phạm vi người dùng đã duyệt. Nếu không có sản phẩm hợp lệ, dừng ở báo cáo lỗi.

## 4. Tạo nháp và xuất báo cáo HTML

- Với API, dùng thao tác lưu nháp đã xác minh. Nếu không có API phù hợp, quan sát giao diện trình duyệt, điền **tất cả trường bắt buộc** của từng sản phẩm rồi chỉ chọn **Lưu nháp** hoặc tương đương. Không nhấn Đăng bán, Xuất bản, Gửi duyệt, Kích hoạt hay thao tác tương đương.
- Khi dùng trình duyệt, nhập và quan sát ở nhịp đủ để phát hiện lỗi giao diện; không giả lập người thật để né cơ chế chống tự động. Cảnh báo thông tin hoặc lỗi trường có thể tự sửa trong phạm vi nháp thì xử lý và kiểm tra lại. Nếu gặp cảnh báo chặn thao tác, mã xác minh, CAPTCHA, OTP/2FA, bị đăng xuất hoặc hết phiên, dừng và báo người dùng; không tự vượt qua. Quy tắc này không áp dụng cho API.
- Trước khi tạo, tra cứu mã/SKU và ID từ lần chạy trước để tránh trùng. Chỉ cập nhật bản nháp thuộc đúng cửa hàng và nằm trong phạm vi đã duyệt. Nếu kết quả ghi mơ hồ, tra cứu lại trước khi thử lại; không đổi sang trình duyệt ngay vì có thể tạo trùng.
- Sau mỗi lần ghi, mở lại bản nháp và kiểm tra từng trường bắt buộc đã lưu, không còn lỗi bắt buộc, SKU chưa mở bán và trạng thái vẫn là nháp không hiển thị. Nếu sàn tự điền/sửa sai thuộc tính, sửa trực tiếp trên đúng bản nháp rồi lưu và kiểm tra lại. Chỉ dừng khi lỗi không thể sửa an toàn, lặp lại sau khi thử hợp lý, hoặc trạng thái nháp không xác minh được; không coi HTTP 200 hay thông báo lưu thành công là đủ.
- Xử lý tuần tự từng sản phẩm: hoàn thiện một bản nháp, lưu, mở lại và ghi kết quả trước khi bắt đầu sản phẩm kế tiếp. Nếu một sản phẩm không xác minh được vì vấn đề riêng của nó, đánh dấu chưa hoàn tất và tiếp tục sản phẩm độc lập khác khi không có nguy cơ sai cửa hàng, tạo trùng hoặc mở bán; không tuyên bố cả lô hoàn tất.
- **Điểm nội dung phải > 90** (mặc định cho mọi lần chạy, không cần người dùng nhắc). Sau khi lưu, mở lại bản nháp, đọc điểm ở góc trên bên phải và checklist kèm theo; sửa các mục thiếu có nguồn dữ liệu xác thực rồi lưu và đọc lại, lặp đến khi > 90 hoặc hết dữ kiện thật. Nếu cần thêm ảnh phụ, video, thuộc tính, mô tả dài hơn, kích thước… mà không có nguồn thật thì hỏi người dùng (hoặc xin phép dùng DEMO có gắn nhãn). Ghi điểm trước/sau vào báo cáo. Sản phẩm điểm ≤ 90 phải được đánh dấu “chưa đạt” kèm mục còn thiếu; không bịa thuộc tính hay hứa trước điểm số.
- **Mọi trường bắt buộc phải có giá trị hợp lệ** trước khi coi là hoàn tất: kiểm tra lại trên bản nháp đã mở lại, không chỉ trên form trước khi lưu. Thuộc tính do AI của sàn tự gợi ý (PreFilled/Suggest) không tính là dữ kiện Excel: chỉ giữ khi khớp nguồn, ngược lại xóa hoặc sửa và ghi chú trong báo cáo.
- Ưu tiên ảnh sản phẩm do người dùng cung cấp; khi chỉ cần ảnh mẫu, có thể tự tìm ảnh stock phù hợp, không mặc định tạo ảnh AI. Ảnh tìm trên internet chỉ dùng khi giấy phép cho phép mục đích dự kiến và không gây hiểu nhầm ảnh là hàng thật của người bán. Lưu nguồn ảnh trong báo cáo; có thể thay/thêm ảnh minh họa trong lô nháp đã được người dùng cho tiếp tục mà không hỏi lại từng ảnh.
- Tạo một file HTML đẹp mắt (xem “Yêu cầu báo cáo HTML” bên dưới), dễ mở, chứa thời điểm chạy, file nguồn, sàn/cửa hàng, phương thức, tổng số theo trạng thái và bảng theo `ma_san_pham`/SKU: dòng nguồn, tên–mô tả gốc/SEO, trường bắt buộc đã điền/chưa điền, dữ liệu DEMO, kết quả (tạo nháp, cập nhật nháp, bỏ qua, lỗi, chưa xác minh), trạng thái trước/sau, ID, liên kết quản trị và việc người duyệt cần làm. Escape dữ liệu Excel trước khi chèn vào HTML; không chèn token, cookie hoặc mật khẩu. Nếu quy trình dừng trước bước ghi, vẫn xuất HTML ghi rõ phần đã kiểm tra và lý do chưa đăng.
- Gửi liên kết file HTML cho người dùng. Người duyệt xem bản nháp trên sàn và tự quyết định khi nào mở bán; skill không thực hiện xuất bản.

## Yêu cầu báo cáo HTML

Một file HTML tự chứa (CSS nội tuyến, không cần mạng), mở trực tiếp được, đẹp và dễ quét. Bắt đầu từ [mẫu báo cáo](assets/bao-cao-mau.html) rồi thay dữ liệu. Bắt buộc:
- **Đầu trang:** tiêu đề, sàn/cửa hàng, file nguồn, thời điểm, phương thức; các thẻ số liệu (tổng sản phẩm, đã tạo/cập nhật nháp, lỗi, chưa đạt điểm) và dải cảnh báo DEMO/“không sẵn sàng bán” nổi bật.
- **Thẻ từng sản phẩm** (không dùng bảng thô): ảnh đại diện, tên, SKU, mã sản phẩm, ID nháp kèm liên kết quản trị, huy hiệu trạng thái (Nháp ✓ / Lỗi / Chưa xác minh), **vòng hoặc thanh Điểm nội dung (xanh khi > 90, cam/đỏ khi thấp hơn)** kèm điểm trước/sau, danh sách trường bắt buộc đã điền (✓/✗), giá, kho, kích thước kiện, và nguồn ảnh/giấy phép.
- **Mục “Việc người duyệt cần làm”** (thay dữ liệu DEMO, kiểm tra thuộc tính AI tự gợi ý, tự bật Mở bán và Gửi đi) và mục “Điểm còn mơ hồ”.
- Thiết kế: bảng màu thống nhất, chữ dễ đọc, khoảng cách rộng, bo góc, bố cục thẻ co giãn tốt trên màn hình hẹp và khi in; có chế độ tối nếu tiện. Escape dữ liệu Excel; không chèn token, cookie, mật khẩu. Sau khi tạo, mở thử trong trình duyệt để kiểm tra hiển thị.

## Kinh nghiệm và lưu ý (học từ các lần chạy)

Chi tiết theo sàn nằm ở mô-đun (Lazada: mục “Kinh nghiệm thực tế”). Điểm chung:
- Trước khi tạo, tra danh sách Bản nháp theo SKU/tên: lần chạy trước có thể đã có nháp; cập nhật đúng nháp đó thay vì tạo trùng.
- Biểu mẫu sàn thường vẽ lại khi đổi thương hiệu/danh mục và có thể xóa giá trị vừa nhập; chọn danh mục và thương hiệu trước, nhập giá sau, rồi đọc lại toàn bộ giá trị trước khi lưu.
- Gõ nhầm do bấm lệch toạ độ rất dễ xảy ra (giá lọt vào ô mô tả…). Bấm bằng tham chiếu phần tử (`find`/`read_page`) thay cho toạ độ, đọc lại giá trị từng ô sau khi điền, và kiểm tra ô mô tả/tên không bị lẫn chữ lạ.
- Công tắc “Mở bán” của SKU có thể **bật sẵn** ở nháp mới: luôn kiểm tra và tắt trước khi lưu; xác nhận lại sau khi mở nháp.
- Thuộc tính AI tự điền (PreFilled/Updated) có thể sai ngành hàng (ví dụ “Loại khóa” cho ống cắm bút) và được điền lại sau mỗi lần lưu. Xóa nếu không bắt buộc, ghi vào báo cáo nếu không xóa bền được; nếu là trường bắt buộc, chọn giá trị đúng theo dữ liệu thật.
- Trình duyệt trong công cụ agent không có hộp chọn file: dùng kỹ thuật gán `File` vào ô tải lên (mô-đun sàn mô tả). Ảnh phải đúng loại sản phẩm, vuông, nền sáng nếu sàn khuyến nghị; ảnh stock chỉ dùng khi giấy phép cho phép và phải ghi nguồn.
- Ảnh/trang bị chặn bằng kiểm tra bot (Unsplash…) thì chuyển nguồn khác, không vượt kiểm tra.
- **Lazada: chèn ít nhất 1 ảnh vào phần Mô tả sản phẩm là cách nhanh nhất để điểm nội dung > 90** (88 → 100 trong lần chạy thực tế); làm bước này trước khi tìm thêm video hay ảnh nền trắng, rồi lưu, mở lại và đọc điểm. Chi tiết thao tác ở mô-đun Lazada.
- **Tồn kho:** nếu Excel để tồn kho 0 hoặc trống thì hỏi người dùng ở chặng 1 (nhập số thật, hay cho phép tự đặt số DEMO). Tồn kho DEMO (ví dụ 60–150) chỉ điền khi người dùng đồng ý, ghi rõ “DEMO” trong báo cáo; điền tồn kho **không** làm sản phẩm mở bán, nhưng vẫn phải giữ công tắc “Mở bán” tắt. Sau khi lưu, mở lại và đọc lại tồn kho của từng SKU. Điền ô tồn kho bằng cách đặt giá trị cho ô thứ hai trong hàng giá/kho (sau khi trang đã tải xong, không vừa đổi thương hiệu/danh mục) rồi bấm “Lưu bản nháp”.
- Điểm nội dung thấp thường do thiếu ảnh phụ, video, thuộc tính tùy chọn, mô tả ngắn, kích thước/khối lượng: lên kế hoạch xin dữ kiện từ chặng 1 thay vì để đến cuối mới phát hiện.

## Giới hạn thực thi

- Luôn ghi trạng thái nháp bằng cơ chế được xác minh cho sàn cụ thể. Nếu API chỉ tạo sản phẩm trực tiếp để bán, dùng trình duyệt nếu có lưu nháp; nếu cả hai đều không có, dừng.
- Không chấp nhận ô trạng thái trong Excel làm quyền xuất bản. Mẫu cố ý không có cột `publish` hoặc `active`.
- Tách rõ “đã điền đủ trường bắt buộc”, “đã được sàn duyệt” và “hàng thật sẵn sàng bán”; không hứa người bán bấm đăng là chắc chắn thành công. Dữ liệu DEMO dù điền đủ vẫn luôn gắn nhãn **không sẵn sàng bán**.
- Giữ báo cáo lỗi và kết quả tách khỏi dữ liệu nguồn; không sửa âm thầm file Excel của người dùng.
- Dừng lô khi gặp sai cửa hàng, quyền truy cập bất thường, xác minh trạng thái thất bại, yêu cầu captcha/2FA chưa được người dùng hoàn tất, hoặc dấu hiệu tạo trùng. Báo rõ các dòng đã ghi trước lúc dừng để lần chạy sau có thể đối chiếu.
