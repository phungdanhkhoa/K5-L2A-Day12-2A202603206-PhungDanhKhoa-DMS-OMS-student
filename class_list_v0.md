# Bản nháp danh sách lớp v0 — Phùng Danh Khoa · G07

## DMS

| Lớp hoặc thuộc tính | Giá trị theo v1.0 | Để làm gì | Khả năng quan sát trong NIR thật |
|---|---|---|---|
| `person.seat` | `driver` | Xác định vùng tài xế để liên kết kết quả của mặt, mắt và tay với đúng người. | Theo hình dáng và vị trí trong cabin. |
| `face` | Hộp mặt | Xác định vùng ảnh cần phân tích để ước lượng trạng thái mắt và hướng nhìn. | Còn dùng được khi thấy các nét chính của mặt. |
| `face.eye_left`, `face.eye_right` | `open`, `closed`, `unknown` | Theo dõi độ khép mắt theo thời gian để hỗ trợ đánh giá mức tỉnh táo. | Gán riêng hai mắt. Phản xạ hoặc che khuất có thể làm một mắt không đọc được. |
| `face.glasses` | `none`, `clear`, `sun`, `unknown` | Chọn cách đánh giá mắt phù hợp khi có tròng kính. | Khả năng phân biệt loại kính tùy độ truyền NIR và phản xạ. |
| `face.gaze_zone` | `road`, `mirror_l`, `mirror_r`, `mirror_c`, `cluster`, `center`, `lap`, `other` | Ước lượng thời gian nhìn về từng vùng cabin để đánh giá mức tập trung. | Phụ thuộc hướng đầu, mắt và góc camera. |
| `face13` | 13 điểm với cờ `occluded` và `outside` | Đo hình học mí mắt, mũi và miệng để hỗ trợ căn chỉnh mặt và theo dõi chuyển động. | Có thể mất từng điểm do kính, góc nghiêng hoặc vật che. |
| `hand.whose`, `hand.side`, `hand.on_wheel` | `driver/passenger`, `left/right`, `yes/no/unknown` | Theo dõi bàn tay nào đang tiếp xúc vô lăng, cùng trạng thái lái hiện tại. | Cần thấy cạnh tay và vùng tiếp xúc. |
| `phone.state` | `held`, `mounted`, `lap` | Phân biệt điện thoại cầm tay với điện thoại trên giá hoặc đặt ở đùi. | Cần nhận được cạnh, góc hoặc màn hình của thiết bị. |

## OMS

| Lớp hoặc thuộc tính | Giá trị theo v1.0 | Để làm gì | Khả năng quan sát trong IR mô phỏng |
|---|---|---|---|
| `person` | Hộp phần người nhìn thấy | Đếm người theo ghế và xác định vị trí cần kiểm tra dây an toàn. | Dựa vào hình dáng và vị trí phần cơ thể nhìn thấy. |
| `person.seat` và `seat` của vật hoặc ghế trẻ em | `rear_left`, `rear_middle`, `rear_right` trong bộ OMS | Gắn trạng thái người và vật với ghế theo hệ tọa độ của xe. | Thường suy được từ bố trí hàng ghế và vị trí vật. |
| `person.seatbelt` | `not_worn`, `unknown` trong SVIRO | Ghi lại khả năng quan sát dây ở ghế có người. Muốn học các kiểu thắt cần thêm dữ liệu có dây. | Vệt tối hoặc vùng bị che làm giảm khả năng quan sát. |
| `face` | Hộp mặt người lớn | Tách vùng mặt khỏi phần thân để hỗ trợ xác nhận vùng người nhìn thấy. | Phụ thuộc kích thước, hướng mặt và độ tương phản. |
| `child_seat.occupied` | `unknown`, `no`, `yes` | Phân biệt ghế trẻ em trống với ghế có người ngồi và đánh dấu trường hợp chưa quan sát được. | Hình dáng ghế có thể rõ hơn phần lòng ghế. |
| `infant_seat.facing` | `rear`, `front` | Phân biệt hướng đặt nôi theo xe để cung cấp thông tin cho hệ thống an toàn ghế. | Dựa vào quai, lưng nôi và hình dáng tổng thể, nếu thấy. |
| `object.type` | `bag`, `box`, `cup`, `other` | Phân biệt đồ vật với người và ghế trẻ em để giảm báo nhầm ghế có hành khách. | Dựa vào hình dáng, kích thước và ngữ cảnh thay cho màu. |

## Hai câu hỏi leo thang cần xác nhận trên G07

1. Nếu vẫn nhìn được một đoạn mí nhưng cả bốn điểm mốc của mắt khó xác định, coach yêu cầu nhìn rõ đến mức nào để ghi `closed`?
   - Khung cần đối chiếu trên CVAT local là `D04.png`. Bản export hiện ghi `eye_left=closed` và `eye_right=closed`, đồng thời đánh dấu cả bốn điểm mốc của mỗi mắt bằng cờ che khuất hoặc ngoài khung.
   - Chỉ giữ `closed` khi thấy rõ hai mí khép. Nếu không phân biệt được trạng thái mắt, dùng `unknown` theo §4.5 và đặt cờ riêng cho từng điểm theo §4.6.
2. Schema cập nhật có `child_seat.occupied=yes`, còn GUIDE §3 nêu bộ SVIRO của lab không có trẻ em ngồi. Nếu thấy hình giống trẻ em nhưng không xác định được đó là người hay vật, coach cần dấu hiệu nào để phân xử?
   - Cặp cần đối chiếu trên CVAT local là `S01_rgb.png` và `S01_ir.png`. Export ghi `child_seat.occupied=yes` tại `rear_middle` ở cả hai khung.
   - Kiểm từng khung theo §4.4 và §4.8. Dùng `unknown` nếu không thấy rõ phần lòng ghế, và hỏi coach khi có hình giống trẻ em theo §3.
