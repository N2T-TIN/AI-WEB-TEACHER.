# Lộ trình đào tạo phát triển Web

Phiên bản roadmap: 1.0.0  
Ngày lập: 2026-11-18  
Trạng thái: Khung chương trình — cần triển khai bài học và đánh giá theo từng chủ đề.

## Nguyên tắc xếp cấp độ

- **Beginner:** Hiểu khái niệm, viết chương trình nhỏ, làm theo hướng dẫn.
- **Intermediate:** Tự thiết kế tính năng, kết nối nhiều thành phần, xử lý lỗi phổ biến.
- **Advanced:** Thiết kế hệ thống vừa/lớn, tối ưu, kiểm thử và bảo mật có hệ thống.
- **Expert:** Đánh giá trade-off, kiến trúc quy mô lớn, vận hành và dẫn dắt tiêu chuẩn kỹ thuật.

Không đồng nhất cấp độ với số năm kinh nghiệm. Học viên chuyển cấp khi đạt tiêu chí đầu ra.

## Level 1 — Beginner

### Mục tiêu
Hiểu nền tảng Web và tự xây dựng website tĩnh có cấu trúc, giao diện responsive và tương tác cơ bản.

### Giáo trình
1. Máy tính, tệp/thư mục, terminal và trình soạn thảo.
2. Internet, client/server, DNS ở mức khái niệm, HTTP/HTTPS.
3. Logic, biến, kiểu dữ liệu, điều kiện, vòng lặp, hàm.
4. HTML document, semantic HTML, links, images, lists, forms, tables.
5. CSS syntax, selectors, cascade, specificity, box model.
6. Typography, colors, spacing, Flexbox, Grid và responsive.
7. JavaScript cơ bản, arrays, objects, DOM và events.
8. Git, GitHub, DevTools và debugging căn bản.
9. Accessibility và SEO nền tảng.

### Bài tập và dự án
- Bài tập: tạo trang hồ sơ, biểu mẫu liên hệ, bố cục thẻ sản phẩm, menu responsive.
- Dự án: website giới thiệu cá nhân gồm nhiều section, điều hướng, biểu mẫu có kiểm tra đầu vào phía trình duyệt.

### Đánh giá
- HTML có cấu trúc và semantic phù hợp.
- CSS hiển thị tốt ở nhiều kích thước màn hình.
- JavaScript xử lý được tương tác yêu cầu.
- Biết commit, đọc lỗi console và giải thích code của mình.
- Không có lỗi accessibility cơ bản nghiêm trọng.

## Level 2 — Intermediate

### Mục tiêu
Xây dựng ứng dụng front-end có cấu trúc và back-end API cơ bản, lưu trữ dữ liệu và kiểm thử.

### Giáo trình
1. JavaScript ES modules, scope, closures, promises, async/await, Fetch.
2. TypeScript: types, interfaces, generics và narrowing.
3. React: components, props, state, effects, forms và composition.
4. Routing, state management và tổ chức ứng dụng.
5. Node.js runtime, npm và Express.
6. REST API, validation, middleware và error handling.
7. SQL, thiết kế bảng, quan hệ, joins, indexes cơ bản và PostgreSQL.
8. Authentication và authorization; session/token ở mức kiến trúc và thực hành an toàn.
9. Testing: unit, integration và component testing.
10. Deployment, biến môi trường, logging và Git workflow.

### Bài tập và dự án
- Bài tập: CRUD API, truy vấn SQL, form React, kiểm thử component.
- Dự án: ứng dụng quản lý công việc có đăng nhập, API, cơ sở dữ liệu và giao diện responsive.

### Đánh giá
- Ranh giới client/server rõ ràng.
- API có validation và xử lý lỗi nhất quán.
- Có kiểm thử tự động cho luồng quan trọng.
- Secrets không nằm trong source control.
- Có hướng dẫn cài đặt và triển khai.

## Level 3 — Advanced

### Mục tiêu
Thiết kế ứng dụng nhiều thành phần, tối ưu hiệu năng, bảo mật, khả năng quan sát và độ tin cậy.

### Giáo trình
1. Next.js và rendering strategies; routing, data fetching và caching.
2. Kiến trúc front-end, design systems và accessibility nâng cao.
3. Node.js concurrency, streams và performance profiling.
4. Database transactions, isolation, indexing và query plans.
5. MongoDB và lựa chọn mô hình dữ liệu phù hợp.
6. API versioning, pagination, rate limiting và idempotency.
7. Security engineering: threat modeling, OWASP Top 10, secure headers, dependency hygiene.
8. CI/CD, Docker, môi trường staging và rollback.
9. Caching, CDN, queues và background jobs.
10. Observability: logs, metrics, traces và alerting.
11. WebSockets và ứng dụng real-time.
12. Load testing, performance budgets và resilience.

### Dự án
- Nền tảng nội dung hoặc cửa hàng thử nghiệm có phân quyền, tìm kiếm, cache, realtime notifications, CI/CD và monitoring.

### Đánh giá
- Có tài liệu kiến trúc và threat model.
- Có số đo trước/sau khi tối ưu.
- Có chiến lược xử lý lỗi, backup và rollback.
- Kiểm thử tích hợp các luồng trọng yếu.
- Có quy trình xử lý dependency và lỗ hổng.

## Level 4 — Expert

### Mục tiêu
Đưa ra quyết định kiến trúc có căn cứ, thiết kế hệ thống có khả năng mở rộng và dẫn dắt chất lượng kỹ thuật.

### Giáo trình
1. System design: requirements, capacity estimation và trade-offs.
2. Distributed systems: consistency, availability, partitioning và failure modes.
3. Scalable architecture, service boundaries và domain modeling.
4. Advanced database design, replication và data lifecycle.
5. Performance engineering, profiling và capacity planning.
6. Distributed caching, messaging và event-driven architecture.
7. Cloud architecture, deployment strategies và infrastructure as code.
8. Advanced security architecture, privacy và incident response.
9. Reliability engineering, SLO/SLI và disaster recovery.
10. Architecture Decision Records, technical governance và mentoring.

### Dự án
- Thiết kế và triển khai hệ thống có yêu cầu tải, độ sẵn sàng, bảo mật và khả năng phục hồi được mô tả rõ; cung cấp ADR, sơ đồ, benchmark, runbook và postmortem mô phỏng.

### Đánh giá
- Giải thích được trade-offs và giới hạn của lựa chọn.
- Có mô hình tải và dữ liệu kiểm thử.
- Có SLO, quan sát hệ thống và kế hoạch phục hồi.
- Có đánh giá rủi ro và kiểm soát bảo mật.
- Tài liệu kỹ thuật đủ để nhóm khác vận hành.

## Ma trận nhóm kiến thức

| Nhóm | Beginner | Intermediate | Advanced | Expert |
|---|---|---|---|---|
| Computer Science | Logic, nền tảng Web | DS&A, networking thực hành | concurrency, complexity | distributed systems |
| HTML/CSS | Cấu trúc, layout | responsive nâng cao | accessibility/performance | design systems, standards |
| JavaScript | Core language, DOM | async, modules, TypeScript | runtime, profiling | platform architecture |
| Front-end | HTML/CSS/JS | React, routing | Next.js, state, testing | large-scale frontend |
| Back-end | HTTP, API khái niệm | Node, Express, SQL | auth, caching, queues | distributed backend |
| Professional | Git, DevTools | testing, deploy | CI/CD, Docker, OWASP | SRE, governance |
| Advanced | Nhận biết khái niệm | mô hình hóa cơ bản | realtime, cloud | system design quy mô lớn |

## Điều kiện hoàn thành một cấp độ

Mỗi cấp độ cần có:
- Bài giảng theo mẫu chuẩn.
- Bài tập cơ bản, trung cấp, nâng cao kèm lời giải giải thích.
- Ít nhất một dự án có rubric.
- Bài kiểm tra kiến thức và bài thực hành.
- Tiêu chí đạt/chưa đạt minh bạch.
- Ghi nhận các chủ đề chưa học và khuyến nghị ôn tập.
