# TEAM — Ngày 12

Mã bộ ảnh: **G07** · Hình thức: cá nhân

| Họ tên | MSSV | Đã gán đủ 22 ảnh? | Review chéo với (peer diff) | Số dòng disagreement đã xử lý |
|---|---|---|---|---|
| Phùng Danh Khoa | 2A202603206 | `export_final.zip` đủ 22 khung. Đã chỉnh landmark trên bản nhãn import. Phần nhãn import chờ coach xác nhận. | Đã chạy diff kỹ thuật với bản G07 đã xác nhận | 8 dòng đã điền verdict nháp, mục guideline và hướng xử lý. Chờ đối chiếu ảnh. |

Khoa tiếp tục làm cá nhân và tự rà soát trên CVAT. Bản nhận để đối chiếu có 26 khung. Diff dùng 22 khung cốt lõi D01–D06 và S01–S08. Bốn khung S09–S10 thuộc phần mở rộng.

## Tình trạng bằng chứng khi nộp

- E1. `export_final.zip` là bản CVAT for images 1.1 từ task 29, gồm 22 khung với `frame_meta` và chỉ chứa `annotations.xml`. Checker ghi 0 lỗi và 4 cảnh báo. Khoa import bản nhãn cũ rồi chỉnh landmark. Các box và tag trùng bản nhập khi đối chiếu XML. Phần tự gán đủ 22 khung theo `RULES.md` cần được coach xác nhận.
- E2. Ba log đính kèm được chạy từ cùng bản export cuối của CVAT task 29. Log A/B là kết quả kiểm lại phạm vi checkpoint. Kiểm lần cuối trên 22 khung ghi 0 lỗi và 4 cảnh báo về trạng thái mắt và cờ điểm mặt, còn chờ đối chiếu ảnh.
- E3. Diff giữa `export_final.zip` và bản nhận đã được Khoa xác nhận là G07, dùng 22 khung có tên và kích thước khớp ở ngưỡng IoU 0,5. Kết quả có 140 dòng trên 18 khung. Trong `disagreement_log.csv`, 8 dòng ưu tiên trên 7 khung đã điền verdict nháp `ambiguous`, mục guideline và hướng xử lý dựa trên XML. Hai người cần xem trực tiếp trong CVAT để chốt ít nhất 5 dòng. Nếu vẫn không phân xử được, giữ `ambiguous` và hỏi coach bằng mã khung. Phần tự rà soát nằm trong `self_review.md`.
- E4. Bốn dòng trong `ir_log.csv` là ca cần xem trong CVAT, có đối chiếu giá trị từ hai bản XML G07. Phần hiện tượng quan sát thực tế còn chờ điền.
- E5. Danh sách lớp và hai câu hỏi gắn với khung G07 có trong `class_list_v0.md`.
- Exit ticket. Chưa có câu trả lời cá nhân trong hồ sơ này.
