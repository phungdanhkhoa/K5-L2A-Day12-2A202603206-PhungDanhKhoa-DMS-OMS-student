# Tự đánh giá — Phùng Danh Khoa · G07

## 1. Tự rà soát 4 cảnh

Danh sách dưới đây dựa trên XML xuất từ task 29. Cần mở từng ảnh trong CVAT local để xác nhận loại lỗi và ghi lại cách sửa thực tế.

Loại lỗi: `seat_flip`, `wrong_class`, `guess`, `box`, `missing`, `extra`, `lr_flip` (trái/phải mặt), `flag` (thiếu cờ điểm), `ok`.

| Ảnh | Đối tượng | Loại lỗi | Ghi chú | Đã sửa? |
|---|---|---|---|---|
| [S01_ir](http://localhost:8080/tasks/29/jobs/28?frame=6) | `child_seat.occupied` tại `rear_middle` | Chờ xác nhận | XML ghi `yes`. GUIDE §3 nêu bộ SVIRO của lab không có trẻ em ngồi. Kiểm lại phần lòng ghế và hỏi coach nếu có hình giống trẻ em. | Chờ đối chiếu |
| [S02_ir](http://localhost:8080/tasks/29/jobs/28?frame=8) | `person.seatbelt` tại `rear_left` | Chờ xác nhận | XML ghi `not_worn` ở khung IR-sim và `unknown` ở khung RGB. Kiểm riêng vùng vai và ngực trên khung IR-sim. Chỉ chọn `not_worn` khi thấy rõ không có dây. | Chờ đối chiếu |
| [D01](http://localhost:8080/tasks/29/jobs/28?frame=0) | `face.eye_left` và `face13` | Chờ xác nhận | Mắt trái ghi `unknown`, trong khi cả bốn điểm mắt trái đều không có cờ. Kiểm lý do không phân biệt được mắt và khả năng xác định từng điểm. | Chờ đối chiếu |
| [D04](http://localhost:8080/tasks/29/jobs/28?frame=3) | `face.eye_left`, `face.eye_right` và `face13` | Chờ xác nhận | Hai mắt ghi `closed`, trong khi tất cả điểm của hai mắt có cờ. Kiểm hai mí của từng mắt trước khi quyết định giá trị và giữ cờ phù hợp với mức che khuất của từng điểm. | Chờ đối chiếu |

## 2. Lỗi mình lặp lại nhiều nhất hôm nay

Vấn đề lặp trong kết quả kiểm là trạng thái mắt và cờ điểm cần đối chiếu. D04 và D06 cùng có ít nhất một mắt ghi `closed` trong khi cả bốn điểm của mắt đó có cờ.

Lý do thực tế cần bổ sung sau khi xem lại D04 và D06 trên CVAT local.

Cách tránh đề xuất là kiểm riêng từng mắt trước khi export. Chỉ giữ `closed` khi thấy rõ hai mí khép. Đối chiếu lại cờ trên bốn điểm của mắt đó và chạy lại checker sau khi sửa.

## 3. Ghi chú về disagreement_log

Đã có diff với bản cùng mã G07. Sau khi hai người xem ảnh và chốt verdict, ghi một dòng bất đồng mà nhận xét của bạn giúp sửa nhãn, kèm điều học được.
