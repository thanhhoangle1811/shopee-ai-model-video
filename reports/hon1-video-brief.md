# HON-1 — Bộ chỉ dẫn sản xuất với model 2

## Đã xác nhận

- Workspace shared: `/workspace/shopee-ai-model-video`; `pwd` đúng đường dẫn này.
- Đã đọc `reports/model-review.md` và tài liệu HON-1; giữ phạm vi thử nghiệm đã được duyệt.
- Model gốc: `data/model/model 2/`. Đã đối chiếu SHA-256 cả 8 ảnh với danh mục hiện có, tất cả khớp.
- Mặt chuẩn: `01_chan_dung_chinh_dien.png`; toàn thân chuẩn: `06_toan_than_chinh_dien.png`. Các góc còn lại chỉ dùng khi cảnh cần. Không trộn bộ `original`.
- Đã mở trực tiếp ảnh toàn thân chính diện. Ảnh 1024×1536 cần đặt vừa khung 9:16 với nền bổ sung, giữ đủ đầu và giày, không kéo giãn người.

## Clip kiểm tra 6 giây

Đây là chỉ dẫn đã chuẩn bị, chưa chạy tạo video.

> Use the full-body front reference as the first frame and the front portrait as the identity reference. A single woman stands naturally in a warm beige studio. Preserve her face, long dark brown hair, body proportions, ivory ao dai, white trousers and shoes, earrings and rectangular gold-edged chest badge exactly as shown. One subtle blink, gentle breathing and a small weight shift. Static camera, continuous shot, soft stable lighting. No walking, large turn, speech, added text, extra people, invented logos or new accessories. Keep hands anatomically consistent, garment texture stable and both shoes visible. Six seconds, vertical 9:16.

Nếu công cụ chỉ nhận một ảnh, dùng ảnh toàn thân chính diện; không đưa bảng ghép nhiều góc làm khung đầu. Nếu công cụ không hỗ trợ ảnh đầu vào thì chưa phù hợp để thử tính nhất quán mẫu này.

## Video sản phẩm 18 giây

Chỉ tạo sau khi có ảnh, biến thể và link sản phẩm đã kiểm tra. Trang phục hiện có trên model chưa được xác nhận tương ứng một sản phẩm Shopee.

| Thời gian | Cảnh | Chữ dựng sau |
|---|---|---|
| 0–3 giây | Toàn thân mặc đúng sản phẩm được chọn | Tên sản phẩm đã xác minh |
| 3–9 giây | Chuyển trọng tâm nhẹ, thấy rõ phom | Chi tiết có bằng chứng từ ảnh/shop |
| 9–14 giây | Góc ba phần tư nhỏ nếu có ảnh sản phẩm tương ứng | Gợi ý hoàn cảnh phối đồ |
| 14–18 giây | Trở lại toàn cảnh, giữ đủ đầu/chân | Xem sản phẩm ở bình luận; kiểm tra size và giá tại shop |

Với video sản phẩm, dùng model 2 để giữ nhận diện; thay trang phục theo ảnh sản phẩm đã xác minh. Không sao chép khuyên tai hoặc bảng cài ngực vào sản phẩm nếu ảnh sản phẩm không có. Không suy đoán thiết kế phía sau từ ảnh phía trước.

## Kiểm tra trước khi đăng

Xem toàn bộ video ở kích thước xuất: khuôn mặt, tay, tóc, vải, màu và thiết kế qua từng cảnh; đối chiếu đúng biến thể. Thêm thông báo AI và liên kết tiếp thị theo khung trong tài liệu affiliate-workflow. Đăng lên đúng Page đã chỉ định và kiểm tra lại video cùng link bình luận.

## Tình trạng và đầu vào còn thiếu

- Chưa có sản phẩm, ảnh sản phẩm hoặc link affiliate. Không tự ghép mã affiliate hay gán bộ áo dài trong ảnh cho một shop chưa kiểm tra.
- Facebook qua Composio chưa có tài khoản hoạt động. Bước tiếp tục kết nối yêu cầu hoàn tất quyền truy cập ở nhà cung cấp; chưa nhận được URL đăng nhập, chưa xác minh được Page hoặc quyền đăng.
- Chưa có dịch vụ tạo video từ ảnh được xác nhận dùng được. Công cụ Gemini được tìm thấy chỉ nhận prompt chữ, không nhận các ảnh mẫu; chưa phù hợp cho yêu cầu này. Chưa chọn hoặc mua dịch vụ khác.
- Môi trường hiện có không tìm thấy ffmpeg, Pillow, imageio hoặc OpenCV. Chưa dựng video, không coi bản chỉ dẫn là video đã tạo.
- Chưa gửi ảnh lên dịch vụ tạo video, chưa đăng Facebook, chưa phát sinh khoản mua công cụ.

Tệp `hon1-model-reference.json` lưu bộ tham chiếu và cấu hình đầu ra. Tệp `hon1-affiliate-tracking.csv` mới có tiêu đề cột; chưa có số liệu, không ghi dữ liệu chưa biết thành 0.
