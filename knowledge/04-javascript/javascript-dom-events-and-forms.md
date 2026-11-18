# JavaScript: DOM, Events và xử lý Form

> **ID:** JS-DOM-001  
> **Nhóm:** JavaScript / Web APIs  
> **Cấp độ:** Beginner → Intermediate  
> **Ngôn ngữ:** vi  
> **Công nghệ:** DOM Standard và Web APIs trong trình duyệt hiện đại  
> **Ngày tạo:** 2026-11-18  
> **Rà soát gần nhất:** 2026-11-18  
> **Trạng thái:** Reviewed (lý thuyết); ví dụ chưa chạy browser test  
> **Tiên quyết:** HTML và JavaScript cơ bản  
> **Nguồn chính:** MDN DOM; DOM Standard

## 1. Mục tiêu học tập

- Giải thích DOM là gì.
- Chọn element bằng querySelector/querySelectorAll.
- Đọc và cập nhật nội dung/thuộc tính an toàn.
- Gắn event listener và hiểu event object.
- Xử lý form submit và validation cơ bản.
- Tránh lỗi phổ biến khi thao tác DOM.

## 2. Kiến thức nền tảng

DOM (Document Object Model) là giao diện biểu diễn tài liệu thành một cây node/đối tượng. JavaScript có thể truy vấn và thay đổi cây này. DOM là Web API của môi trường trình duyệt, không phải cú pháp cốt lõi của ngôn ngữ JavaScript.

## 3. Giải thích lý thuyết

### Chọn phần tử

- \`document.querySelector(selector)\`: trả về phần tử đầu tiên khớp hoặc null.
- \`document.querySelectorAll(selector)\`: trả về NodeList các phần tử khớp.
- Luôn kiểm tra phần tử có tồn tại trước khi truy cập thuộc tính.

### Thay đổi nội dung

- \`textContent\` đặt/đọc văn bản.
- \`classList.add/remove/toggle\` quản lý class.
- \`setAttribute\` đặt attribute.
- Khi hiển thị dữ liệu người dùng, ưu tiên textContent thay vì đưa chuỗi không tin cậy vào innerHTML.

### Events

Event là đối tượng biểu diễn sự kiện như click, input, change, submit và keydown. Dùng \`addEventListener\` để đăng ký handler. Event handler nhận event object chứa thông tin sự kiện.

### Form

Sự kiện submit phát ra khi form được gửi. Gọi \`event.preventDefault()\` khi muốn ngăn hành vi gửi mặc định để tự xử lý ở client. Việc kiểm tra ở client không thay thế validation phía server.

## 4. Thuật ngữ chuyên môn

| Thuật ngữ | Giải thích |
|---|---|
| DOM | Mô hình đối tượng tài liệu |
| Node | Một nút trong cây DOM |
| Selector | Biểu thức chọn phần tử |
| Event | Sự kiện xảy ra trong giao diện |
| Handler/listener | Hàm xử lý sự kiện |
| Event target | Đối tượng nơi sự kiện bắt đầu/được phát |
| preventDefault | Ngăn hành vi mặc định của sự kiện |
| Event bubbling | Sự kiện lan truyền từ phần tử con lên tổ tiên |
| Validation | Kiểm tra dữ liệu theo quy tắc |

## 5. Cú pháp

\`\`\`js
const button = document.querySelector("#save");

if (button) {
  button.addEventListener("click", () => {
    console.log("Đã nhấn nút");
  });
}
\`\`\`

## 6. Ví dụ code

HTML:

\`\`\`html
<form id="message-form">
  <label for="message">Nội dung</label>
  <input id="message" name="message" required maxlength="120" />
  <button type="submit">Gửi</button>
</form>
<p id="result" aria-live="polite"></p>
\`\`\`

JavaScript:

\`\`\`js
const form = document.querySelector("#message-form");
const messageInput = document.querySelector("#message");
const result = document.querySelector("#result");

if (form && messageInput && result) {
  form.addEventListener("submit", (event) => {
    event.preventDefault();

    const message = messageInput.value.trim();

    if (message.length === 0) {
      result.textContent = "Vui lòng nhập nội dung.";
      messageInput.focus();
      return;
    }

    result.textContent = \`Bạn đã nhập: \${message}\`;
    form.reset();
  });
}
\`\`\`

### Giải thích từng phần

| Đoạn | Ý nghĩa |
|---|---|
| querySelector | Tìm các phần tử theo id |
| if (form...) | Đảm bảo các phần tử tồn tại |
| addEventListener | Lắng nghe sự kiện submit |
| preventDefault | Ngăn form tải lại trang theo hành vi mặc định |
| trim | Bỏ khoảng trắng đầu/cuối |
| textContent | Hiển thị nội dung dưới dạng văn bản |
| focus | Đưa focus về ô nhập |
| reset | Đặt form về trạng thái ban đầu |

**Trạng thái kiểm thử:** Chưa chạy trong browser; cần kiểm tra submit, dữ liệu rỗng, bàn phím và screen reader.

## 7. Ứng dụng thực tế

DOM/events được dùng cho form đăng ký, bộ lọc, menu, tab, thông báo và các tương tác nhỏ không cần framework. Với ứng dụng lớn, framework có thể quản lý UI state nhưng vẫn dựa trên nền tảng DOM và event của trình duyệt.

## 8. Lỗi thường gặp

| Lỗi | Nguyên nhân | Cách sửa |
|---|---|---|
| Cannot read properties of null | Selector không tìm thấy phần tử | Kiểm tra id/class và thời điểm script chạy |
| Handler chạy nhiều lần | Gắn listener lặp lại | Kiểm soát nơi đăng ký listener |
| Form tải lại bất ngờ | Chưa xử lý submit mặc định | Dùng preventDefault khi phù hợp |
| Dữ liệu hiển thị sai | Không trim hoặc validate | Chuẩn hóa và kiểm tra đầu vào |
| Dùng innerHTML với input | Có nguy cơ HTML injection | Dùng textContent hoặc API DOM an toàn |
| Không thao tác được bằng bàn phím | Chỉ xử lý click tùy biến | Dùng control semantic và kiểm tra keyboard |

## 9. Phương pháp sửa lỗi

1. Kiểm tra selector có trả về null không.
2. Xác nhận script chạy sau khi DOM sẵn sàng hoặc dùng defer.
3. Đặt breakpoint trong handler.
4. Quan sát event.target và giá trị input.
5. Kiểm tra cả chuột và bàn phím.
6. Kiểm tra dữ liệu rỗng, khoảng trắng, độ dài tối đa và ký tự đặc biệt.

## 10. Bài tập cơ bản

Tạo nút bấm; mỗi lần nhấn, số đếm tăng một đơn vị và hiển thị trên trang.

## 11. Bài tập trung cấp

Tạo form thêm công việc. Khi submit, thêm nội dung vào danh sách bằng createElement và textContent.

## 12. Bài tập nâng cao

Tạo danh sách công việc có chức năng hoàn thành và xóa. Dùng event delegation để xử lý sự kiện trên danh sách. Không chèn nội dung người dùng bằng innerHTML.

## 13. Đáp án và giải thích

Ví dụ thêm item an toàn:

\`\`\`js
const list = document.querySelector("#tasks");
const form = document.querySelector("#task-form");
const input = document.querySelector("#task-name");

if (list && form && input) {
  form.addEventListener("submit", (event) => {
    event.preventDefault();
    const value = input.value.trim();

    if (!value) return;

    const item = document.createElement("li");
    item.textContent = value;
    list.append(item);
    form.reset();
  });
}
\`\`\`

createElement tạo node mới; textContent đưa nội dung vào dạng text; append thêm node vào danh sách. Trong ứng dụng thực tế, cần bổ sung xử lý lỗi, trạng thái rỗng và lưu dữ liệu nếu yêu cầu.

## 14. Dự án thực hành

**Dự án:** Danh sách công việc mini.
- Thêm công việc.
- Đánh dấu hoàn thành.
- Xóa công việc.
- Hiển thị thông báo trạng thái bằng aria-live.
- Dùng semantic form/button/list.
- Không chèn dữ liệu người dùng qua innerHTML.

## 15. Tiêu chí đánh giá

| Tiêu chí | Điểm |
|---|---:|
| Chọn DOM đúng | 15 |
| Xử lý event đúng | 20 |
| Validation form | 20 |
| Hiển thị dữ liệu an toàn | 20 |
| Keyboard/accessibility | 15 |
| Code rõ ràng | 10 |
| **Tổng** | **100** |

## 16. Tài liệu tham khảo

- MDN DOM introduction: https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model/Introduction
- MDN addEventListener: https://developer.mozilla.org/en-US/docs/Web/API/EventTarget/addEventListener
- MDN Event: https://developer.mozilla.org/en-US/docs/Web/API/Event
- DOM Standard: https://dom.spec.whatwg.org/
- MDN Client-side form validation: https://developer.mozilla.org/en-US/docs/Learn_web_development/Extensions/Forms/Form_validation

## 17. Lịch sử thay đổi

| Ngày | Phiên bản | Thay đổi |
|---|---|---|
| 2026-11-18 | 1.0.0 | Nhập bài DOM và events |

## 18. Ghi chú sư phạm

Bắt đầu bằng yêu cầu học viên vẽ cây DOM đơn giản. Sau đó cho dự đoán event flow và tự gắn listener. Khi dạy bảo mật, so sánh textContent với innerHTML bằng ví dụ vô hại và nhấn mạnh nguyên tắc không diễn giải dữ liệu người dùng thành markup ngoài ý muốn.
