# CSS: Nền tảng, Box Model và Responsive Layout

> **ID:** CSS-CORE-001  
> **Nhóm:** CSS  
> **Cấp độ:** Beginner → Intermediate  
> **Ngôn ngữ:** vi  
> **Công nghệ:** CSS hiện đại theo tài liệu MDN/W3C; tránh phụ thuộc vào một phiên bản trình duyệt cụ thể  
> **Ngày tạo:** 2026-11-18  
> **Rà soát gần nhất:** 2026-11-18  
> **Trạng thái:** Reviewed (lý thuyết); ví dụ chưa chạy kiểm thử đa trình duyệt  
> **Tiên quyết:** HTML cơ bản  
> **Nguồn chính:** MDN CSS; W3C CSS

## 1. Mục tiêu học tập

- Giải thích vai trò của CSS và cách áp dụng CSS vào HTML.
- Viết selector, declaration, property và value.
- Hiểu cascade, specificity và inheritance ở mức cơ bản.
- Tính toán kích thước theo box model.
- Dùng Flexbox và Grid cho bố cục.
- Tạo giao diện responsive bằng đơn vị linh hoạt và media queries.
- Biết kiểm tra CSS bằng DevTools.

## 2. Kiến thức nền tảng

HTML mô tả cấu trúc và ý nghĩa nội dung; CSS mô tả cách trình bày. Một rule CSS gồm selector và declaration block.

## 3. Giải thích lý thuyết

### Cú pháp CSS

\`selector { property: value; }\`

Ví dụ:
\`p { color: navy; }\`

### Cascade, specificity và inheritance

Khi nhiều rule cùng tác động lên một element, trình duyệt giải quyết theo cơ chế cascade. Nguồn khai báo, layer, độ ưu tiên, specificity và thứ tự xuất hiện có thể ảnh hưởng kết quả. Một số thuộc tính được kế thừa từ cha, ví dụ color và font-family; nhiều thuộc tính layout không tự kế thừa.

Không nên giải quyết mọi xung đột bằng cách tăng specificity hoặc thêm \`!important\`. Hãy tổ chức CSS rõ ràng.

### Box Model

Mỗi hộp thông thường gồm:
- Content: vùng nội dung.
- Padding: khoảng đệm bên trong.
- Border: đường viền.
- Margin: khoảng cách bên ngoài.

Với \`box-sizing: content-box\`, width/height mặc định áp dụng cho content. Với \`border-box\`, width/height bao gồm content + padding + border.

### Flexbox và Grid

- **Flexbox** phù hợp bố cục một chiều: hàng hoặc cột.
- **Grid** phù hợp bố cục hai chiều: hàng và cột.
- Hai công cụ có thể kết hợp trong cùng giao diện.

### Responsive design

Thiết kế responsive thích ứng với nhiều kích thước màn hình:
- Dùng chiều rộng linh hoạt như %, fr, minmax, max-width.
- Ảnh thường nên có max-width: 100%.
- Dùng media query khi bố cục cần thay đổi theo điều kiện viewport.
- Tránh cố định mọi kích thước bằng pixel.

## 4. Thuật ngữ chuyên môn

| Thuật ngữ | Giải thích |
|---|---|
| Selector | Bộ chọn element |
| Declaration | Cặp property/value |
| Cascade | Cơ chế phân xử rule áp dụng |
| Specificity | Độ ưu tiên của selector trong cascade |
| Inheritance | Cơ chế một số giá trị truyền từ cha xuống con |
| Box model | Mô hình hộp CSS |
| Flex container | Phần tử cha có display:flex |
| Grid container | Phần tử cha có display:grid |
| Breakpoint | Ngưỡng tại đó layout thay đổi |
| Viewport | Vùng hiển thị trang trong trình duyệt |

## 5. Cú pháp

\`\`\`css
.card {
  box-sizing: border-box;
  width: min(100%, 32rem);
  padding: 1rem;
  border: 1px solid #d0d7de;
  border-radius: 0.75rem;
}
\`\`\`

## 6. Ví dụ code

HTML:

\`\`\`html
<div class="layout">
  <header class="header">Trang học tập</header>
  <main class="cards">
    <article class="card">
      <h2>HTML</h2>
      <p>Học cấu trúc nội dung.</p>
    </article>
    <article class="card">
      <h2>CSS</h2>
      <p>Học cách trình bày giao diện.</p>
    </article>
  </main>
</div>
\`\`\`

CSS:

\`\`\`css
*,
*::before,
*::after {
  box-sizing: border-box;
}

body {
  margin: 0;
  font-family: system-ui, sans-serif;
  line-height: 1.5;
}

.layout {
  width: min(100% - 2rem, 70rem);
  margin-inline: auto;
}

.header {
  padding: 1.5rem 0;
  font-size: 1.5rem;
  font-weight: 700;
}

.cards {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(min(100%, 16rem), 1fr));
  gap: 1rem;
}

.card {
  padding: 1rem;
  border: 1px solid #d0d7de;
  border-radius: 0.75rem;
}

@media (max-width: 35rem) {
  .header {
    font-size: 1.25rem;
  }
}
\`\`\`

### Giải thích từng phần

| Đoạn | Ý nghĩa |
|---|---|
| universal selector và pseudo-elements | Áp dụng box-sizing thống nhất |
| body | Đặt margin, font và line-height cơ bản |
| min() | Giữ layout trong giới hạn chiều rộng |
| margin-inline:auto | Căn giữa theo trục ngang trong layout thông thường |
| display:grid | Bật CSS Grid |
| repeat/auto-fit/minmax | Tạo cột linh hoạt theo không gian |
| gap | Khoảng cách giữa các card |
| media query | Điều chỉnh font khi viewport hẹp |

**Trạng thái kiểm thử:** Chưa chạy trong browser automation; cần kiểm tra ở các viewport và trình duyệt mục tiêu trước khi dùng production.

## 7. Ứng dụng thực tế

CSS được dùng để xây dựng navigation, card, dashboard, form, trang sản phẩm và layout responsive. Grid hữu ích cho lưới card; Flexbox hữu ích cho thanh điều hướng và căn chỉnh nhóm phần tử.

## 8. Lỗi thường gặp

| Lỗi | Nguyên nhân | Cách sửa |
|---|---|---|
| Element rộng hơn dự kiến | content-box cộng thêm padding/border | Dùng border-box và kiểm tra box model |
| Rule không có tác dụng | Selector sai hoặc rule khác thắng cascade | Xem Computed Styles |
| Dùng margin âm để sửa mọi layout | Đang xử lý triệu chứng | Chọn Flexbox/Grid và kiểm tra cấu trúc |
| Giao diện tràn ngang | Kích thước cứng hoặc nội dung dài | Dùng kích thước linh hoạt và xử lý overflow |
| Dùng quá nhiều breakpoint | Layout chưa linh hoạt | Ưu tiên intrinsic sizing trước |
| Dùng div thay cho nội dung semantic | CSS bị trộn với cấu trúc HTML | Chọn semantic HTML trước, CSS sau |

## 9. Phương pháp sửa lỗi

1. Mở DevTools → Elements.
2. Chọn element bị lỗi.
3. Xem Styles và Computed.
4. Kiểm tra box model, kích thước cha/con và overflow.
5. Tắt/bật từng declaration để tìm nguyên nhân.
6. Kiểm tra viewport nhỏ, vừa và lớn.
7. Không chỉ sửa trên một kích thước màn hình.

## 10. Bài tập cơ bản

1. Tạo một class đổi màu chữ và nền.
2. Tạo card có padding, border và margin.
3. Áp dụng border-box toàn trang.

## 11. Bài tập trung cấp

Tạo lưới 6 card, tự thay đổi số cột theo chiều rộng vùng hiển thị bằng Grid.

## 12. Bài tập nâng cao

Tạo layout dashboard gồm sidebar và main content. Ở màn hình hẹp, sidebar chuyển thành vùng điều hướng nằm trên nội dung. Bảo đảm không xuất hiện cuộn ngang ngoài ý muốn.

## 13. Đáp án và giải thích

Một lời giải Grid cơ bản:

\`\`\`css
.grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(15rem, 1fr));
  gap: 1rem;
}
\`\`\`

Grid tự bố trí số cột theo không gian khả dụng. Nếu phần tử nhỏ hơn 15rem, cần cân nhắc minmax với min(100%, ...) để tránh tràn ở viewport rất hẹp.

## 14. Dự án thực hành

**Dự án:** Trang danh mục khóa học.
- Header và menu điều hướng.
- Lưới ít nhất 6 card.
- Card có tiêu đề, mô tả và liên kết.
- Layout thích ứng với màn hình hẹp.
- Dùng CSS variables cho màu và khoảng cách.
- Kiểm tra focus keyboard và độ tương phản.

## 15. Tiêu chí đánh giá

| Tiêu chí | Điểm |
|---|---:|
| Selector và cascade hợp lý | 15 |
| Box model chính xác | 20 |
| Flexbox/Grid phù hợp | 25 |
| Responsive và không tràn | 20 |
| Dễ đọc, tái sử dụng | 10 |
| Accessibility và focus | 10 |
| **Tổng** | **100** |

## 16. Tài liệu tham khảo

- MDN CSS first steps: https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/Styling_basics
- MDN CSS box model: https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_box_model
- MDN Flexbox: https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_flexible_box_layout
- MDN Grid: https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_grid_layout
- MDN Responsive design: https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/CSS_layout/Responsive_Design
- W3C CSS: https://www.w3.org/Style/CSS/

## 17. Lịch sử thay đổi

| Ngày | Phiên bản | Thay đổi |
|---|---|---|
| 2026-11-18 | 1.0.0 | Nhập bài CSS nền tảng |

## 18. Ghi chú sư phạm

Dạy box model bằng hình vẽ và DevTools. Cho học viên dự đoán chiều rộng thực tế trước khi chạy. Khi học Grid/Flexbox, yêu cầu giải thích vì sao chọn công cụ đó thay vì học thuộc thuộc tính.
