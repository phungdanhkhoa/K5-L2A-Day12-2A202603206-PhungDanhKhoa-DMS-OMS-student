# TEAM — Ngày 12

Mã bộ ảnh: **G07** · Hình thức: cá nhân

| Họ tên | MSSV | Đã gán đủ 22 ảnh? | Review chéo với (peer diff) | Số dòng disagreement đã xử lý |
|---|---|---|---|---|
| Phùng Danh Khoa | 2A202603206 | Export đủ 22 khung. Đã chỉnh landmark trên bản nhãn import. Phần nhãn import chờ coach xác nhận. | Chưa có review chéo | Chưa thực hiện |

Khoa tiếp tục làm cá nhân và tự rà soát trên CVAT. E3 vẫn chờ review cùng mã G07 hoặc phương án được coach duyệt.

## Tình trạng bằng chứng khi nộp

- E1. Bản CVAT hiện có 22 khung. Khoa import bản nhãn cũ rồi chỉnh landmark. Hồ sơ này chưa có export xác nhận là phần gán nhãn cá nhân đầy đủ.
- E2. Ba log đính kèm được chạy từ cùng bản export cuối của CVAT task 29. Log A/B là kết quả kiểm lại phạm vi checkpoint. Kiểm lần cuối trên 22 khung ghi 0 lỗi và 4 cảnh báo về trạng thái mắt và cờ điểm mặt, còn chờ đối chiếu ảnh.
- E3. Chưa có review chéo. Phần tự rà soát nằm trong `self_review.md`.
- E4. Bốn dòng trong `ir_log.csv` là ca cần xem trong CVAT dựa trên XML. Phần hiện tượng quan sát thực tế còn chờ điền.
- E5. Danh sách lớp và hai câu hỏi gắn với khung G07 có trong `class_list_v0.md`.
- Exit ticket. Chưa có câu trả lời cá nhân trong hồ sơ này.
