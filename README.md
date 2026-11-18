# AI WEB TEACHER — Knowledge Base

> Kho tri thức đào tạo phát triển Web từ nền tảng đến chuyên sâu. Nội dung được tổ chức theo chủ đề, cấp độ, phiên bản công nghệ và nguồn tham khảo.

## Trạng thái dự án

- **Phiên bản cấu trúc:** 1.0.0
- **Ngày khởi tạo kho:** 2026-11-18
- **Ngôn ngữ chính:** Tiếng Việt; giữ thuật ngữ kỹ thuật tiếng Anh khi cần.
- **Trạng thái:** Khung quản trị và lộ trình đã được khởi tạo; các bài học chuyên đề sẽ được nhập theo từng đợt và phải qua kiểm tra chất lượng.
- **Nguyên tắc:** Không xóa bản cũ khi chưa có bản thay thế; không ghi nhận kiểm thử nếu chưa chạy; không bịa nguồn hoặc phiên bản.

## Bắt đầu

1. Đọc [quy tắc quản trị kho](knowledge/00-governance/README.md).
2. Xem [lộ trình bốn cấp độ](knowledge/00-governance/curriculum-roadmap.md).
3. Dùng [mẫu tài liệu chuẩn](knowledge/00-governance/knowledge-article-template.md) khi tạo bài học.
4. Tra cứu [danh mục nguồn chính thức](SOURCES.md).

## Phạm vi kiến thức

| Nhóm | Nội dung |
|---|---|
| Computer Science | Logic, thuật toán, cấu trúc dữ liệu, kiến trúc máy tính, hệ điều hành, mạng, HTTP/HTTPS |
| HTML | HTML Living Standard, semantic HTML, forms, tables, media, accessibility, SEO |
| CSS | Selectors, box model, Flexbox, Grid, responsive, animation, variables, modern CSS |
| JavaScript | Ngôn ngữ cốt lõi, DOM, events, async, Fetch, modules, Web APIs |
| Front-end | React, TypeScript, Next.js, routing, state, UI/UX, accessibility, performance, testing |
| Back-end | Node.js, Express, REST, authentication, authorization, middleware, SQL, PostgreSQL, MongoDB |
| Professional | Git, GitHub, clean code, debugging, testing, deployment, CI/CD, Docker, security, OWASP |
| Advanced | System design, patterns, scalable architecture, performance engineering, caching, real-time, WebSockets, cloud |

## Cấu trúc thư mục dự kiến

```text
knowledge/
  00-governance/       # Quy tắc, mẫu bài, lộ trình, nhật ký thay đổi
  01-computer-science/
  02-html/
  03-css/
  04-javascript/
  05-frontend/
  06-backend/
  07-professional/
  08-advanced/
SOURCES.md
```

## Quy trình đóng góp

- Một chủ đề có một tài liệu chuẩn; tránh tạo bản sao chỉ khác tên.
- Tên tệp dùng chữ thường, kebab-case; nội dung Markdown UTF-8.
- Mỗi tài liệu phải ghi cấp độ, ngày rà soát, trạng thái, phiên bản công nghệ và nguồn.
- Phân biệt rõ **đã xác minh**, **cần kiểm tra**, **đã lỗi thời**.
- Thay đổi lớn phải có mục trong changelog và giữ lại lịch sử Git.
- Không đưa secrets, token, mật khẩu, dữ liệu cá nhân hoặc khóa API vào repository.

## Lưu ý kiểm thử

Tài liệu và ví dụ code được xem là **chưa chạy thử** trừ khi có mục kiểm thử ghi rõ môi trường, lệnh chạy và kết quả thực tế. Việc đọc hoặc rà soát cú pháp không tương đương với thực thi.

## Giấy phép và bản quyền

Ưu tiên nội dung tự biên soạn, ví dụ code nguyên bản và liên kết đến tài liệu chính thức. Không sao chép nguyên văn các tài liệu có bản quyền; khi trích dẫn phải tuân thủ giấy phép và ghi nguồn.
