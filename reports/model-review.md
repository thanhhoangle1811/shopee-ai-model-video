# HON-2 — Kiểm tra dữ liệu model Shopee

Ngày kiểm tra: 13/11/2026. Phạm vi: workspace hiện tại và toàn bộ ảnh trong `data/model`; chưa tạo video.

## Bộ ảnh gốc đã chọn

Theo chỉ định của người dùng: dùng `data/model/model 2/` làm bộ ảnh gốc. Ảnh chuẩn khuôn mặt là `01_chan_dung_chinh_dien.png`; ảnh chuẩn toàn thân là `06_toan_than_chinh_dien.png`. Sáu ảnh còn lại bổ sung tham chiếu các góc. Bộ `original` được giữ để lưu trữ, không dùng pha trộn vào diện mạo mặc định của project.

## Workspace và quyền truy cập

- Thư mục làm việc xác nhận bằng `pwd`: `/workspace/shopee-ai-model-video`.
- Có quyền đọc, duyệt và ghi tại thư mục gốc; đã ghi được báo cáo vào `reports/`. Đọc thành công cả 15 tệp ảnh.
- Trước khi tạo báo cáo, dữ liệu project nhìn thấy gồm `data/model` và các thư mục ẩn `.agents/`, `.aws/`, `.codex/`, `.git/`. Không đọc nội dung cấu hình nhạy cảm trong các thư mục ẩn.
- Không thấy README, mã nguồn, kịch bản, ảnh sản phẩm riêng, âm thanh hoặc video trong phần dữ liệu hiện có. Nhận xét này chỉ áp dụng cho workspace đang được cung cấp.

## Cấu trúc và danh sách đầy đủ ảnh

```text
/workspace/shopee-ai-model-video/
├── .agents/
├── .aws/
├── .codex/
├── .git/
├── data/
│   └── model/
│       ├── model 2/
│       │   ├── 01_chan_dung_chinh_dien.png
│       │   ├── 02_chan_dung_3_4_trai.png
│       │   ├── 03_chan_dung_3_4_phai.png
│       │   ├── 04_chan_dung_nghieng_trai.png
│       │   ├── 05_chan_dung_nghieng_phai.png
│       │   ├── 06_toan_than_chinh_dien.png
│       │   ├── 07_toan_than_nghieng.png
│       │   └── 08_toan_than_phia_sau.png
│       └── original/
│           ├── original_model_v1_character_sheet_v1.png
│           ├── original_model_v1_reference.png
│           └── face/
│               ├── original_model_v1_face_back.png
│               ├── original_model_v1_face_front.png
│               ├── original_model_v1_face_left_3q.png
│               ├── original_model_v1_face_right_3q.png
│               └── original_model_v1_face_sheet_v1.png
└── reports/                         # tạo trong lần kiểm tra này
    ├── model-image-inventory.json
    └── model-review.md
```

## Nội dung đã quan sát trực tiếp

### Bộ `original` — 7 ảnh

Nhân vật nữ, tóc nâu sẫm dài, hơi gợn, nụ cười nhẹ; áo dài trắng, quần trắng và giày trắng, nền studio xám. Áo không có bảng cài ngực như bộ `model 2`.

| Tệp (tương đối từ `data/model/original`) | Kích thước pixel | Nội dung và công dụng |
|---|---:|---|
| `original_model_v1_reference.png` | 1024 × 1536 | Toàn thân chính diện, thấy đủ giày; ảnh khởi đầu phù hợp cho cảnh giới thiệu và chuyển động nhẹ. |
| `original_model_v1_character_sheet_v1.png` | 1536 × 1024 | Bảng 4 góc toàn thân: chính diện, hai góc xoay và phía sau; tham chiếu vóc dáng, trang phục, tóc. |
| `face/original_model_v1_face_front.png` | 1086 × 1448 | Chân dung chính diện, cười nhẹ; chuẩn khuôn mặt cho bộ original. |
| `face/original_model_v1_face_left_3q.png` | 1086 × 1448 | Chân dung ba phần tư hướng trái khung hình. |
| `face/original_model_v1_face_right_3q.png` | 1086 × 1448 | Chân dung ba phần tư hướng phải khung hình. |
| `face/original_model_v1_face_back.png` | 1086 × 1448 | Sau đầu và vai, tóc che mặt; tham chiếu tóc phía sau, không phải ảnh nhận diện khuôn mặt. |
| `face/original_model_v1_face_sheet_v1.png` | 4344 × 1448 | Bảng ghép 4 góc đầu: trước, hai góc ba phần tư, sau; để đối chiếu tổng quan. |

Bảng góc mặt có bố cục tương ứng các ảnh rời; không nên tính bảng ghép như một tư thế mới độc lập. Bộ này chưa có ảnh rời nghiêng mặt 90 độ hay ảnh rời toàn thân phía sau; các góc toàn thân bổ sung nằm trong character sheet.

### Bộ `model 2` — 8 ảnh

Nhân vật nữ, tóc nâu sẫm dài và khá thẳng, biểu cảm trung tính; áo dài trắng ngà có vân và độ bóng rõ, quần/giày trắng. Có khuyên tai sáng và bảng cài ngực chữ nhật viền vàng, nền be ấm.

| Tệp (tương đối từ `data/model/model 2`) | Kích thước pixel | Nội dung và công dụng |
|---|---:|---|
| `01_chan_dung_chinh_dien.png` | 1122 × 1402 | Chân dung thẳng, tham chiếu mặt chính. |
| `02_chan_dung_3_4_trai.png` | 1122 × 1402 | Chân dung ba phần tư hướng trái khung hình. |
| `03_chan_dung_3_4_phai.png` | 1122 × 1402 | Chân dung ba phần tư hướng phải khung hình. |
| `04_chan_dung_nghieng_trai.png` | 1122 × 1402 | Nghiêng mặt gần 90 độ hướng trái khung hình. |
| `05_chan_dung_nghieng_phai.png` | 1122 × 1402 | Nghiêng mặt gần 90 độ hướng phải khung hình. |
| `06_toan_than_chinh_dien.png` | 1024 × 1536 | Đứng thẳng chính diện, thấy đủ tay và giày; phù hợp làm khung hình đầu cho cảnh toàn thân. |
| `07_toan_than_nghieng.png` | 1024 × 1536 | Toàn thân nghiêng hướng trái khung hình; tham chiếu phom áo và tà xẻ. |
| `08_toan_than_phia_sau.png` | 1024 × 1536 | Toàn thân sau lưng; tham chiếu chiều dài tóc, áo và giày. |

Quy ước trái/phải trong báo cáo là hướng trên ảnh người xem thấy, tránh nhầm với bên trái/phải giải phẫu của nhân vật.

## Kiểm tra kỹ thuật và giới hạn

- Đã mở và xem trực tiếp 15/15 ảnh; không có tệp không mở được.
- Tổng dung lượng: 43.201.061 byte (khoảng 41,20 MiB). Tất cả là PNG.
- Đã đọc toàn bộ byte, kiểm tra chữ ký PNG, CRC từng chunk, kết thúc IEND và giải nén dữ liệu IDAT: 15/15 đạt.
- SHA-256 khác nhau cho cả 15 tệp: không có tệp trùng byte. Điều này không loại trừ nội dung tương tự giữa bảng ghép và ảnh rời.
- Danh mục máy đọc được, kích thước, dung lượng và SHA-256 từng tệp nằm trong `model-image-inventory.json`.
- Các ảnh toàn thân là tỷ lệ 2:3, chưa phải 9:16. Khi dựng video dọc nên mở rộng nền hoặc đặt ảnh vào khung, kiểm tra đủ đầu và giày; không kéo giãn người.
- Hai bộ có khác biệt thấy được về khuôn mặt, biểu cảm, tóc, phụ kiện và nền. Chưa có thông tin xác nhận quan hệ phiên bản; không suy luận rằng có thể thay thế hai bộ cho nhau trong cùng cảnh.
- Cận mặt bộ original có vân da khá rõ; cần xem ở kích thước đầu ra để đánh giá có nên giảm nét. Tóc dài, sợi tóc mảnh và bề mặt áo bóng là những vùng cần kiểm tra khi tạo chuyển động.
- Chưa thử tạo video, đồng bộ khẩu hình hay thử tính nhất quán qua nhiều khung hình; việc ảnh mở được không bảo đảm chất lượng video đầu ra.

## Đề xuất bước tiếp theo

1. Người dùng đã chọn `model 2` làm bộ ảnh gốc cho project. Sử dụng các ảnh trong `data/model/model 2/` làm chuẩn ngoại hình cho những bước tạo video tiếp theo; giữ nhất quán khuôn mặt, tóc, trang phục và phụ kiện theo bộ này.
2. Lập bộ tham chiếu tối thiểu từ ảnh đã có: mặt thẳng + hai góc ba phần tư + toàn thân thẳng. Thêm nghiêng/sau khi cảnh cần; dùng bảng ghép để đối chiếu thay vì làm khung hình đầu có nhiều người.
3. Chuẩn bị khung dọc 9:16 từ ảnh toàn thân, giữ tỷ lệ người và khoảng trống an toàn ở đầu/chân; giữ nguyên các tệp gốc.
4. Đề xuất clip thử 5–8 giây: đứng tự nhiên, chớp mắt, chuyển trọng tâm nhẹ hoặc xoay nhỏ. Kiểm tra mặt, tay, tóc, tà áo, khuyên tai và bảng cài ngực trước khi làm chuỗi cảnh dài.
5. Trước video bán hàng cụ thể, xác định sản phẩm, thông điệp, thời lượng, lời thoại và công cụ tạo video. Workspace hiện có đủ ảnh tham chiếu model để bắt đầu chuẩn bị; không cần gửi lại các ảnh đã liệt kê.

Không sửa ảnh gốc và không gửi dữ liệu tới dịch vụ tạo ảnh/video trong lần kiểm tra này.
