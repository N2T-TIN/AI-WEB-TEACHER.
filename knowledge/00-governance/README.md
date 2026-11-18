# Quản trị kho tri thức

## 1. Mục đích

Đảm bảo kho tri thức AI WEB TEACHER có thể mở rộng, truy vết, cập nhật và dùng được trong đào tạo. Tài liệu trong kho là nội dung học tập có cấu trúc, không phải bản sao toàn bộ website bên ngoài.

## 2. Metadata bắt buộc

Mỗi bài học cần có:
- ID chủ đề ổn định.
- Tên chủ đề và nhóm kiến thức.
- Cấp độ: Beginner, Intermediate, Advanced hoặc Expert.
- Mục tiêu học tập có thể đánh giá.
- Ngôn ngữ.
- Công nghệ và phiên bản/phạm vi phiên bản.
- Ngày tạo, ngày rà soát gần nhất.
- Trạng thái chất lượng.
- Nguồn tham khảo chính thức.
- Quan hệ tiên quyết và chủ đề liên quan.

## 3. Trạng thái chất lượng

| Trạng thái | Ý nghĩa |
|---|---|
| Draft | Bản nháp, chưa rà soát đầy đủ |
| Reviewed | Đã rà soát nội dung và nguồn |
| Code-checked | Ví dụ code đã được thực thi trong môi trường ghi rõ |
| Needs-update | Có dấu hiệu lỗi thời hoặc nguồn đã thay đổi |
| Deprecated | Không còn khuyến nghị cho dự án mới; giữ lại để tham khảo lịch sử |

Không nâng trạng thái chỉ dựa trên cảm tính. Ghi rõ bằng chứng và môi trường kiểm tra.

## 4. Quy tắc chống trùng lặp

1. Tìm theo ID, tiêu đề, alias và từ khóa trước khi tạo bài mới.
2. Nếu nội dung đã có, cập nhật bài hiện tại hoặc liên kết bài liên quan.
3. Chỉ tách bài khi có mục tiêu học tập, phạm vi hoặc đối tượng khác biệt rõ ràng.
4. Không xóa bản cũ khi chưa xác định bài thay thế và ghi chú chuyển đổi.

## 5. Quy tắc cập nhật

- Kiểm tra tài liệu chính thức và ghi ngày truy cập.
- Ghi rõ phiên bản hoặc ngày thay đổi nếu nguồn công bố.
- Phân tích ảnh hưởng đến cú pháp, hành vi, bảo mật và bài tập.
- Cập nhật ví dụ và bài kiểm tra liên quan.
- Giữ lịch sử thay đổi trong Git và changelog.
- Nếu chưa xác minh được, ghi **Needs verification** thay vì suy đoán.

## 6. Quy tắc code và bảo mật

- Không lưu token, mật khẩu, private key, cookie hoặc dữ liệu cá nhân.
- Không đưa thông tin nhạy cảm vào ví dụ.
- Ví dụ server phải minh họa xác thực đầu vào, xử lý lỗi và nguyên tắc least privilege khi phù hợp.
- Không dùng mã dễ tổn thương làm ví dụ khuyến nghị; nếu cần minh họa lỗ hổng thì phải cô lập, giải thích rủi ro và kèm cách phòng tránh.
- Ghi rõ môi trường, phiên bản runtime, lệnh chạy và kết quả nếu đã thực thi.

## 7. Chuẩn đặt tên

- Thư mục: số thứ tự + tên nhóm, ví dụ `02-html`.
- Tệp: `topic-name.md`, dùng kebab-case.
- ID: `HTML-SEMANTIC-001`, `JS-PROMISE-001`.
- Ngày: ISO 8601, `YYYY-MM-DD`.

## 8. Phương pháp sư phạm

Kết hợp Learning by Doing, Project-Based Learning, Active Recall, Spaced Repetition, Scaffolding, Adaptive Learning, Problem-Based Learning và Error-Based Learning. Điều chỉnh độ khó theo bằng chứng học tập, không chỉ theo tự đánh giá.

## 9. Quy trình nhập kiến thức

1. Kiểm tra kho hiện có và tìm nội dung trùng.
2. Xác định khoảng trống theo roadmap.
3. Chọn nguồn chính thức phù hợp.
4. Viết theo mẫu chuẩn.
5. Rà soát tính đúng, đủ, phiên bản, bảo mật và khả năng áp dụng.
6. Chạy thử code nếu có môi trường; nếu không, ghi rõ chưa chạy.
7. Cập nhật mục lục và changelog.
8. Báo cáo tệp đã thêm/sửa, nguồn, kiểm tra và phần còn thiếu.

## 10. Nhật ký

### 2026-11-18 — Khởi tạo v1.0.0
- Tạo bộ quy tắc quản trị kho.
- Tạo roadmap bốn cấp độ và mẫu tài liệu.
- Chưa nhập các bài giảng chuyên đề; chưa có ví dụ code nào được xác nhận chạy thử.
