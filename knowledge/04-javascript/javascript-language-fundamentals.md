# JavaScript: Nền tảng ngôn ngữ

> **ID:** JS-CORE-001  
> **Nhóm:** JavaScript  
> **Cấp độ:** Beginner  
> **Ngôn ngữ:** vi  
> **Công nghệ:** ECMAScript; ví dụ dùng cú pháp JavaScript hiện đại  
> **Ngày tạo:** 2026-11-18  
> **Rà soát gần nhất:** 2026-11-18  
> **Trạng thái:** Reviewed (lý thuyết); code chưa được thực thi trong runtime  
> **Tiên quyết:** HTML cơ bản và tư duy logic  
> **Nguồn chính:** MDN JavaScript Guide; ECMAScript specification

## 1. Mục tiêu học tập

- Giải thích vai trò của JavaScript trong website.
- Khai báo biến bằng const và let.
- Nhận biết các kiểu dữ liệu phổ biến.
- Dùng toán tử, điều kiện và vòng lặp.
- Viết hàm, truyền tham số và trả kết quả.
- Làm việc với array và object.
- Nhận biết lỗi cú pháp, lỗi runtime và lỗi logic.

## 2. Kiến thức nền tảng

JavaScript là ngôn ngữ lập trình được dùng rộng rãi trên Web. Trong trình duyệt, JavaScript có thể thao tác DOM, xử lý sự kiện, gọi mạng và cập nhật giao diện. JavaScript cũng chạy ngoài trình duyệt, ví dụ với Node.js.

## 3. Giải thích lý thuyết

### Biến

- Dùng \`const\` khi không cần gán lại binding.
- Dùng \`let\` khi cần gán lại.
- Tránh \`var\` trong code mới nếu không có lý do tương thích cụ thể.

\`const\` không làm object/array trở thành bất biến; nó ngăn gán lại biến đó, còn nội dung object vẫn có thể thay đổi.

### Kiểu dữ liệu

Primitive thường gặp: string, number, boolean, undefined, null, bigint, symbol. Object là nhóm dữ liệu tham chiếu, bao gồm array và function.

JavaScript có kiểu động: biến có thể nhận giá trị thuộc kiểu khác ở thời điểm khác nhau. Nên viết code rõ ràng và kiểm tra dữ liệu đầu vào.

### Điều kiện và vòng lặp

- \`if/else\` chọn nhánh theo điều kiện.
- \`switch\` phù hợp khi so sánh một biểu thức với nhiều trường hợp.
- \`for\`, \`while\` lặp theo điều kiện.
- \`for...of\` duyệt giá trị iterable như array.

### Hàm

Hàm đóng gói thao tác có thể tái sử dụng. Hàm có thể nhận tham số và trả về giá trị bằng \`return\`. Arrow function là một cách viết hàm, có khác biệt về \`this\` so với function thông thường.

### Array và object

- Array lưu danh sách có thứ tự.
- Object lưu dữ liệu theo cặp key/value.
- Dùng \`map\` để biến đổi danh sách thành danh sách mới.
- Dùng \`filter\` để lọc phần tử.
- Dùng \`find\` để tìm phần tử đầu tiên thỏa điều kiện.

## 4. Thuật ngữ chuyên môn

| Thuật ngữ | Giải thích |
|---|---|
| Variable | Tên tham chiếu đến giá trị |
| Scope | Phạm vi có thể truy cập biến |
| Primitive | Giá trị nguyên thủy |
| Object | Cấu trúc dữ liệu dạng thuộc tính |
| Function | Khối lệnh có thể gọi |
| Parameter | Biến nhận dữ liệu trong định nghĩa hàm |
| Argument | Giá trị truyền khi gọi hàm |
| Return | Giá trị hàm trả về |
| Array | Danh sách có thứ tự |
| Iteration | Một lần lặp |

## 5. Cú pháp

\`\`\`js
const name = "An";
let score = 8;

if (score >= 5) {
  console.log(name + " đã đạt.");
}
\`\`\`

## 6. Ví dụ code

\`\`\`js
const scores = [7, 9, 6, 10];

function calculateAverage(numbers) {
  if (numbers.length === 0) {
    return 0;
  }

  const total = numbers.reduce((sum, value) => sum + value, 0);
  return total / numbers.length;
}

const average = calculateAverage(scores);

if (average >= 8) {
  console.log("Kết quả tốt:", average);
} else {
  console.log("Tiếp tục luyện tập:", average);
}
\`\`\`

### Giải thích từng phần

| Đoạn | Ý nghĩa |
|---|---|
| const scores | Tạo array điểm |
| function | Khai báo hàm tính trung bình |
| numbers.length | Kiểm tra số phần tử |
| reduce | Cộng dồn các giá trị |
| return | Trả kết quả trung bình |
| calculateAverage(scores) | Gọi hàm với array |
| if/else | Chọn thông báo theo kết quả |

**Trạng thái kiểm thử:** Chưa chạy bằng Node.js hoặc trình duyệt trong phiên nhập liệu này. Cần chạy ví dụ và xác minh output trước khi nâng trạng thái sang Code-checked.

## 7. Ứng dụng thực tế

JavaScript có thể:
- Kiểm tra dữ liệu form ở phía trình duyệt.
- Hiển thị danh sách sản phẩm từ dữ liệu.
- Xử lý menu, tab, modal và tương tác.
- Gọi API để lấy dữ liệu.
- Tạo ứng dụng phía server với Node.js.

Kiểm tra phía client cải thiện trải nghiệm nhưng không thay thế kiểm tra bảo mật ở server.

## 8. Lỗi thường gặp

| Lỗi | Nguyên nhân | Cách sửa |
|---|---|---|
| Dùng biến trước khi khởi tạo | Sai thứ tự hoặc scope | Khởi tạo trước khi dùng |
| So sánh lỏng không chủ ý | Dùng == | Ưu tiên === khi không cần coercion |
| Quên return | Hàm trả undefined | Thêm return hoặc dùng biểu thức phù hợp |
| Sửa nhầm array gốc | Method mutate dữ liệu | Chọn method không mutate hoặc tạo bản sao |
| Nhầm = với === | Gán khác so sánh | Kiểm tra toán tử |
| Lỗi undefined | Truy cập thuộc tính không tồn tại | Kiểm tra dữ liệu và đường đi truy cập |

## 9. Phương pháp sửa lỗi

1. Đọc thông báo lỗi và vị trí dòng.
2. Kiểm tra tên biến, dấu ngoặc và dấu nháy.
3. Dùng console.log có mục đích để quan sát giá trị.
4. Kiểm tra kiểu dữ liệu bằng typeof khi phù hợp.
5. Chia bài toán thành hàm nhỏ.
6. Thử trường hợp rỗng, một phần tử, giá trị biên và dữ liệu sai.
7. Xóa log tạm và viết lại kiểm thử sau khi sửa.

## 10. Bài tập cơ bản

1. Khai báo biến tên và tuổi, in ra console.
2. Viết điều kiện kiểm tra một số chẵn/lẻ.
3. Viết vòng lặp in các số từ 1 đến 10.

## 11. Bài tập trung cấp

Viết hàm nhận array số và trả về số lớn nhất. Xử lý riêng array rỗng.

## 12. Bài tập nâng cao

Nhận array object học viên có name và score. Trả về danh sách học viên đạt score từ 8 trở lên, chỉ giữ name và score, không thay đổi array đầu vào.

## 13. Đáp án và giải thích

\`\`\`js
function getTopStudents(students) {
  return students
    .filter((student) => student.score >= 8)
    .map((student) => ({
      name: student.name,
      score: student.score,
    }));
}
\`\`\`

- \`filter\` tạo danh sách mới chỉ gồm học viên đạt điều kiện.
- \`map\` tạo object mới chứa hai trường được yêu cầu.
- Code không sửa array đầu vào hay object gốc.
- Bài thực tế cần xác thực rằng students là array và score có kiểu dữ liệu hợp lệ.

## 14. Dự án thực hành

**Dự án:** Bộ tính điểm học tập.
- Nhập danh sách điểm.
- Kiểm tra dữ liệu đầu vào.
- Tính trung bình, cao nhất và thấp nhất.
- Xếp loại theo quy tắc được công bố.
- Hiển thị kết quả rõ ràng.
- Tách logic tính toán thành các hàm có thể kiểm thử.

## 15. Tiêu chí đánh giá

| Tiêu chí | Điểm |
|---|---:|
| Biến và kiểu dữ liệu đúng | 15 |
| Điều kiện và vòng lặp | 15 |
| Hàm và chia nhỏ logic | 20 |
| Xử lý array/object | 20 |
| Trường hợp biên và lỗi | 20 |
| Tên biến và trình bày | 10 |
| **Tổng** | **100** |

## 16. Tài liệu tham khảo

- MDN JavaScript Guide: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide
- MDN JavaScript First Steps: https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/Scripting
- ECMAScript specification: https://tc39.es/ecma262/

## 17. Lịch sử thay đổi

| Ngày | Phiên bản | Thay đổi |
|---|---|---|
| 2026-11-18 | 1.0.0 | Nhập bài JavaScript nền tảng |

## 18. Ghi chú sư phạm

Yêu cầu học viên dự đoán output trước khi chạy. Dạy biến và điều kiện bằng ví dụ nhỏ, sau đó tăng dần độ phức tạp. Dùng lỗi logic có chủ đích để học viên tìm nguyên nhân, không chỉ sửa theo đáp án.
