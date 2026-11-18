# HTML: Cấu trúc tài liệu và ngữ nghĩa

> **ID:** HTML-CORE-001  
> **Nhóm:** HTML  
> **Cấp độ:** Beginner  
> **Ngôn ngữ:** vi  
> **Công nghệ:** HTML Living Standard (WHATWG); không gắn với một phiên bản trình duyệt cụ thể  
> **Ngày tạo:** 2026-11-18  
> **Rà soát gần nhất:** 2026-11-18  
> **Trạng thái:** Reviewed (lý thuyết); ví dụ code chưa chạy kiểm thử tự động  
> **Tiên quyết:** Biết tạo và lưu tệp văn bản  
> **Nguồn chính:** MDN; WHATWG HTML Standard

## 1. Mục tiêu học tập

- Giải thích HTML dùng để làm gì và phân biệt HTML với CSS/JavaScript.
- Tạo một tài liệu HTML hoàn chỉnh.
- Phân biệt element, tag, attribute và content.
- Chọn semantic elements phù hợp với cấu trúc nội dung.
- Viết heading, paragraph, link, image, list và form cơ bản.
- Nhận biết lỗi lồng thẻ và lỗi accessibility phổ biến.

## 2. Kiến thức nền tảng

HTML là ngôn ngữ đánh dấu, không phải ngôn ngữ lập trình theo nghĩa thông thường. Trình duyệt phân tích HTML để tạo cấu trúc tài liệu (DOM). CSS điều khiển cách trình bày; JavaScript thêm hành vi.

## 3. Giải thích lý thuyết

### Cấu trúc tài liệu

- \`<!doctype html>\`: khai báo doctype HTML hiện đại, giúp trình duyệt dùng standards mode.
- \`<html lang="vi">\`: phần tử gốc; lang khai báo ngôn ngữ chính.
- \`<head>\`: metadata, title, liên kết CSS và thông tin tài liệu.
- \`<body>\`: nội dung tài liệu hiển thị trong trang.

### Element, tag và attribute

\`<a href="https://example.com">Trang ví dụ</a>\`
- \`<a>\` và \`</a>\` là start/end tag.
- Toàn bộ cụm là element.
- \`href\` là attribute.
- \`https://example.com\` là giá trị attribute.
- \`Trang ví dụ\` là content.

Một số phần tử là void elements, ví dụ \`img\`, \`br\`, \`meta\`, \`input\`; chúng không có end tag. Không tự ý thêm thẻ đóng cho void element.

### Semantic HTML

Semantic HTML dùng phần tử theo ý nghĩa nội dung:
- \`header\`: phần đầu của trang hoặc vùng nội dung.
- \`nav\`: nhóm liên kết điều hướng.
- \`main\`: nội dung chính của trang.
- \`article\`: nội dung độc lập, có thể phân phối/tái sử dụng.
- \`section\`: nhóm nội dung theo chủ đề, thường có heading.
- \`aside\`: nội dung bổ trợ.
- \`footer\`: phần chân trang hoặc vùng nội dung.

Không chọn phần tử chỉ vì kiểu hiển thị mặc định. Dùng \`div\` hoặc \`span\` khi không có phần tử semantic phù hợp.

### Heading và nội dung

Heading \`h1\` đến \`h6\` biểu thị cấp bậc tiêu đề, không phải công cụ chọn kích thước chữ. Không bỏ cấp chỉ để đạt giao diện mong muốn; dùng CSS để điều chỉnh kích thước.

### Link và image

- Dùng \`a\` để điều hướng.
- Dùng \`button\` để thực hiện hành động.
- Ảnh có ý nghĩa cần văn bản thay thế phù hợp qua \`alt\`.
- Ảnh trang trí có thể dùng \`alt=""\` để công nghệ hỗ trợ bỏ qua.
- Không viết alt kiểu “ảnh của ảnh”; hãy truyền đạt thông tin cần thiết trong ngữ cảnh.

### Form và accessibility

Mỗi input cần nhãn có thể nhận biết. Dùng \`label\` gắn với input qua \`for\` và \`id\`, hoặc lồng input trong label. Dùng loại input phù hợp và nút submit thực sự. Kiểm tra form bằng bàn phím.

## 4. Thuật ngữ chuyên môn

| Thuật ngữ | Giải thích |
|---|---|
| Element | Đơn vị cấu trúc HTML |
| Tag | Dấu đánh dấu mở/đóng phần tử |
| Attribute | Thuộc tính bổ sung thông tin cho phần tử |
| DOM | Cấu trúc đối tượng mà trình duyệt tạo từ tài liệu |
| Semantic HTML | HTML thể hiện ý nghĩa nội dung |
| Void element | Phần tử không có nội dung con và không có end tag |
| Accessibility | Khả năng tiếp cận, sử dụng bởi nhiều nhóm người dùng |

## 5. Cú pháp

\`\`\`html
<element attribute="value">Nội dung</element>
\`\`\`

Ví dụ:
\`\`\`html
<a href="/about">Giới thiệu</a>
<img src="logo.png" alt="Logo của câu lạc bộ" />
\`\`\`

## 6. Ví dụ code

Tệp \`index.html\`:

\`\`\`html
<!doctype html>
<html lang="vi">
  <head>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1" />
    <title>Trang giới thiệu câu lạc bộ</title>
  </head>
  <body>
    <header>
      <h1>Câu lạc bộ Lập trình</h1>
      <nav aria-label="Điều hướng chính">
        <a href="#gioi-thieu">Giới thiệu</a>
        <a href="#hoat-dong">Hoạt động</a>
      </nav>
    </header>

    <main>
      <section id="gioi-thieu">
        <h2>Chúng tôi là ai?</h2>
        <p>Nơi học sinh cùng học và thực hành lập trình.</p>
      </section>

      <section id="hoat-dong">
        <h2>Hoạt động</h2>
        <ul>
          <li>Học HTML và CSS</li>
          <li>Làm dự án nhóm</li>
        </ul>
      </section>
    </main>

    <footer>
      <p>© 2026 Câu lạc bộ Lập trình</p>
    </footer>
  </body>
</html>
\`\`\`

### Giải thích từng phần

| Dòng/khối | Ý nghĩa |
|---|---|
| doctype | Bật cách xử lý tài liệu HTML hiện đại |
| html lang | Khai báo ngôn ngữ tiếng Việt |
| meta charset | Dùng UTF-8 để mã hóa văn bản |
| meta viewport | Giúp layout hiển thị theo chiều rộng thiết bị |
| title | Tiêu đề tài liệu trên tab/trình duyệt |
| header/nav | Phần đầu và nhóm liên kết điều hướng |
| main | Nội dung chính của trang |
| section/h2 | Nhóm nội dung theo chủ đề |
| ul/li | Danh sách không thứ tự |
| footer | Thông tin chân trang |

**Trạng thái kiểm thử:** Chưa thực thi bằng trình duyệt hoặc HTML validator trong phiên nhập liệu này.

## 7. Ứng dụng thực tế

Semantic HTML hữu ích cho website tin tức, trang trường học, cửa hàng, biểu mẫu đăng ký và ứng dụng web. Cấu trúc có ý nghĩa giúp người dùng công nghệ hỗ trợ điều hướng tốt hơn và giúp mã nguồn dễ bảo trì.

## 8. Lỗi thường gặp

| Lỗi | Vì sao không tốt | Cách sửa |
|---|---|---|
| Dùng \`div\` cho mọi thứ | Mất ý nghĩa cấu trúc | Chọn semantic element phù hợp |
| Thiếu \`lang\` | Khó xác định ngôn ngữ đọc | Đặt lang ở html |
| Thiếu alt cho ảnh có ý nghĩa | Người dùng screen reader thiếu thông tin | Viết alt theo ngữ cảnh |
| Dùng heading để phóng to chữ | Sai cấu trúc tài liệu | Dùng CSS |
| Dùng link làm nút hành động | Sai ngữ nghĩa tương tác | Dùng button |
| Lồng thẻ sai thứ tự | DOM có thể không như dự kiến | Đóng thẻ theo thứ tự ngược lúc mở |

## 9. Phương pháp sửa lỗi

1. Kiểm tra Console và Elements trong DevTools.
2. Xem cây DOM thực tế, không chỉ nhìn giao diện.
3. Kiểm tra cấu trúc heading và landmark.
4. Dùng bàn phím Tab/Shift+Tab để kiểm tra điều hướng.
5. Dùng HTML validator để tìm lỗi markup.
6. Sửa từng lỗi và kiểm tra lại.

## 10. Bài tập cơ bản

1. Tạo trang có title, h1, hai paragraph và một link.
2. Thêm ảnh có alt phù hợp.
3. Tạo danh sách ba mục bằng ul/li.

## 11. Bài tập trung cấp

Tạo trang giới thiệu trường học với header, nav, main, hai section và footer. Các liên kết nav phải dẫn tới đúng section.

## 12. Bài tập nâng cao

Tạo biểu mẫu đăng ký câu lạc bộ gồm họ tên, email, lựa chọn khối lớp và nút gửi. Bảo đảm label gắn đúng control, trường bắt buộc được khai báo phù hợp và có thể thao tác bằng bàn phím.

## 13. Đáp án và giải thích

Ví dụ đáp án form:

\`\`\`html
<form action="/register" method="post">
  <label for="full-name">Họ và tên</label>
  <input id="full-name" name="fullName" autocomplete="name" required />

  <label for="email">Email</label>
  <input id="email" name="email" type="email" autocomplete="email" required />

  <button type="submit">Đăng ký</button>
</form>
\`\`\`

Giải thích:
- \`for\` khớp với \`id\` để label gắn với input.
- \`name\` là tên trường dữ liệu khi gửi form.
- \`type="email"\` cung cấp kiểm tra định dạng cơ bản ở trình duyệt.
- \`required\` đánh dấu trường bắt buộc.
- \`button type="submit"\` gửi form.
- Kiểm tra phía trình duyệt không thay thế validation và bảo vệ dữ liệu ở server.

## 14. Dự án thực hành

**Dự án:** Website giới thiệu câu lạc bộ.
- Có ít nhất 4 landmark/semantic regions phù hợp.
- Có điều hướng đến các phần.
- Có danh sách hoạt động và ảnh minh họa.
- Có form liên hệ với label.
- Có title, lang, charset, viewport.
- Không dùng bảng để dàn layout.

## 15. Tiêu chí đánh giá

| Tiêu chí | Điểm |
|---|---:|
| Cấu trúc tài liệu hợp lệ | 20 |
| Semantic HTML và heading | 25 |
| Link, ảnh, danh sách | 15 |
| Form và label | 20 |
| Bàn phím và alt text | 15 |
| Tên tệp, thụt lề, dễ đọc | 5 |
| **Tổng** | **100** |

## 16. Tài liệu tham khảo

- MDN, Basic HTML syntax: https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/Structuring_content/Basic_HTML_syntax
- MDN, Structuring content with HTML: https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/Structuring_content
- MDN, Forms and buttons: https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/Structuring_content/HTML_forms
- WHATWG HTML Living Standard: https://html.spec.whatwg.org/
- W3C WAI: https://www.w3.org/WAI/

## 17. Lịch sử thay đổi

| Ngày | Phiên bản | Thay đổi |
|---|---|---|
| 2026-11-18 | 1.0.0 | Nhập bài HTML nền tảng |

## 18. Ghi chú sư phạm

Cho học viên dự đoán cấu trúc DOM trước khi mở DevTools. Dạy từng nhóm element, sau đó yêu cầu tự dựng một trang nhỏ. Dùng lỗi markup và lỗi label làm bài tập sửa lỗi; ôn lại semantic elements bằng active recall.
