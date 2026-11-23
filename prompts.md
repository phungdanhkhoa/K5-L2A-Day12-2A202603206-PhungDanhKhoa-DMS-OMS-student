# Khai báo dùng AI — Phùng Danh Khoa

| # | Công cụ | Bạn hỏi gì (tóm tắt) | Bạn dùng kết quả thế nào | Bạn có kiểm lại không? Bằng gì? |
|---|---|---|---|---|
| 1 | OpenAI Codex | Chuẩn bị CVAT local và quy trình chạy checkpoint, kiểm tra cuối, đối chiếu hai bản export | Chuẩn bị lệnh Python và thư mục nháp cho G07 | Đối chiếu GUIDE, RULES, CHECKPOINTS và SUBMISSION. Chạy thử checker trên dữ liệu giả lập. |
| 2 | OpenAI Codex | Gợi ý cách trình bày bản nháp danh sách lớp DMS và OMS | Tham khảo cách diễn đạt mục đích từng lớp và chuẩn bị chỗ điền ví dụ từ khung mình đã xem | Đối chiếu thuộc tính với Guideline Cabin v1.0. Người làm sẽ kiểm lại câu hỏi theo ảnh G07. |
| 3 | OpenAI Codex | Cập nhật JSON nhãn do coach gửi ngày 21/11/2026 | Đồng bộ thuộc tính child_seat.occupied trong schema, checker và tài liệu | So sánh JSON và chạy checker với mẫu tổng hợp. |
| 4 | OpenAI Codex | Kiểm QC kỹ thuật cho các tệp G07 hiện có và chuẩn bị ghi chú kỹ thuật để tự rà soát | Xác định các cảnh báo face13, mâu thuẫn giữa log và XML, và các tệp cần thay bằng bản xuất có nguồn xác thực | Chạy cabin_check trên XML, kiểm nội dung ZIP và đối chiếu với các XML làm việc trong scratch. Phần nhận xét trên ảnh và review chéo chờ người thực hiện xác nhận. |
| 5 | OpenAI Codex | Hỗ trợ xuất ZIP chỉ chứa nhãn từ task Day12-G07 trên CVAT local và chạy checker | Lưu bản xuất hiện tại, ghi lại bốn cảnh báo giữa thuộc tính mắt và cờ landmark để kiểm trực quan | Xác minh đúng task 29, đủ 22 khung, ZIP chỉ có XML và đối chiếu toạ độ/cờ điểm với bản v2. |
| 6 | OpenAI Codex | Soạn câu hỏi leo thang và bốn dòng nháp IR từ bản xuất G07 | Chọn khung và trường cần đối chiếu. Các dòng IR đang chờ ghi quan sát trực tiếp. | Đối chiếu mã khung và giá trị nhãn từ cả hai bản XML G07. Hiện tượng trên ảnh còn chờ Khoa kiểm trong CVAT local. |
| 7 | OpenAI Codex | Kiểm bản ZIP nhận để review và so nhãn trên 22 khung cốt lõi | Tạo CSV nháp, thêm mục guideline và hướng kiểm 8 dòng ưu tiên | Kiểm ZIP chỉ có XML, đối chiếu danh sách và kích thước khung, chạy cabin_check và diff. Khoa xác nhận bản nhận là G07. Kết luận trên ảnh đang chờ xác nhận. |
| 8 | OpenAI Codex | Viết E3 theo các khác biệt trong hai bản G07 | Điền 8 dòng với verdict ambiguous, mục guideline và hành động khi đối chiếu CVAT | Chạy lại diff gốc và đối chiếu các giá trị trong CSV. Cần hai người kiểm trên CVAT trước khi xác nhận kết luận trực quan. |
| 9 | OpenAI Codex | Hoàn thiện tệp E1 và rà E3 trước khi đóng gói | Đưa bản CVAT task 29 vào hồ sơ dưới tên `export_final.zip`, khai báo nguồn nhãn import và giữ các verdict E3 ở mức nháp | Chạy checker trên bản CVAT, so lại 140 dòng diff gốc và kiểm các tệp trong ZIP. |
| 10 | OpenAI Codex | Ghi nhận trạng thái sau khi Khoa báo review xong | Cập nhật xác nhận chung vào `TEAM.md` và `self_review.md` | Đối chiếu với lời xác nhận của Khoa. CSV hiện lưu 8 verdict nháp. |

Ảnh cabin chỉ dùng trong CVAT local. Khoa xác nhận bản CVAT được khởi tạo từ bản nhãn cũ và đã chỉnh landmark. Nguồn bản nhãn nhập và cách sử dụng trong bài nộp cần ghi rõ theo phần coach xác nhận hoặc phần gán lại thực tế.
