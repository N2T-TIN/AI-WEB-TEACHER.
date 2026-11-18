# Nền tảng Web, Internet và HTTP

> **ID:** CS-WEB-001  
> **Nhóm:** Computer Science  
> **Cấp độ:** Beginner → Intermediate  
> **Ngôn ngữ:** vi  
> **Phạm vi:** Kiến thức nền tảng Web; HTTP semantics theo RFC 9110, HTML theo WHATWG Living Standard  
> **Ngày tạo:** 2026-11-18  
> **Rà soát gần nhất:** 2026-11-18  
> **Trạng thái:** Reviewed (lý thuyết); ví dụ minh họa chưa chạy  
> **Tiên quyết:** Biết sử dụng trình duyệt và quản lý tệp cơ bản  
> **Nguồn chính:** MDN Learn Web Development; WHATWG; RFC 9110

## 1. Mục tiêu học tập

Sau bài học, học viên có thể:
- Phân biệt Internet, Web, website, webpage, browser và server.
- Mô tả luồng cơ bản khi trình duyệt tải một trang.
- Giải thích vai trò khái quát của DNS, TCP, TLS và HTTP.
- Phân biệt request, response, method, status code, header và body.
- Dùng DevTools Network để quan sát request/response.

## 2. Kiến thức nền tảng

Cần biết mở trình duyệt, nhập địa chỉ website và tạo thư mục/tệp. Không cần biết lập trình trước.

## 3. Giải thích lý thuyết

### Internet và World Wide Web

- **Internet** là hạ tầng mạng kết nối các mạng và thiết bị trên toàn cầu.
- **World Wide Web (Web)** là một hệ thống tài nguyên có thể liên kết và truy cập qua Internet.
- Email, trò chơi trực tuyến và nhiều dịch vụ khác cũng dùng Internet nhưng không đồng nghĩa với Web.

### Client và server

- **Client** là chương trình yêu cầu dịch vụ, thường là trình duyệt.
- **Server** là hệ thống nhận yêu cầu và cung cấp tài nguyên hoặc dữ liệu.
- Một máy có thể vừa làm client vừa làm server tùy vai trò trong từng kết nối.

### Khi nhập địa chỉ website

1. Trình duyệt phân tích URL.
2. Hệ thống tìm địa chỉ IP tương ứng với tên miền qua DNS (có thể dùng cache).
3. Trình duyệt thiết lập kết nối mạng đến máy chủ; HTTP/1.1 và HTTP/2 thường chạy trên TCP, còn HTTP/3 chạy trên QUIC.
4. Với HTTPS, TLS bảo vệ kết nối và giúp xác thực máy chủ bằng chứng chỉ.
5. Trình duyệt gửi HTTP request.
6. Server trả HTTP response, có thể gồm HTML, CSS, JavaScript, ảnh hoặc dữ liệu.
7. Trình duyệt phân tích tài nguyên, tải các tài nguyên phụ và dựng trang.

Đây là mô hình học tập đơn giản; thực tế có thể có CDN, proxy, cache, service worker, nhiều server và các bước tối ưu khác.

### HTTP request và response

Một request thường có:
- Method: hành động mong muốn, ví dụ GET hoặc POST.
- Target: tài nguyên đích.
- Headers: metadata về request.
- Body: dữ liệu gửi lên, thường có ở POST/PUT/PATCH nhưng không phải mọi request đều có.

Một response thường có:
- Status code: kết quả xử lý.
- Headers: metadata về response.
- Body: nội dung trả về, nếu có.

### Nhóm status code thường gặp

| Nhóm | Ý nghĩa | Ví dụ |
|---|---|---|
| 1xx | Thông tin | 100 Continue |
| 2xx | Thành công | 200 OK, 201 Created, 204 No Content |
| 3xx | Chuyển hướng | 301, 302, 304 |
| 4xx | Lỗi liên quan request/client | 400, 401, 403, 404, 429 |
| 5xx | Lỗi phía server | 500, 502, 503, 504 |

Không suy luận rằng mọi lỗi 4xx đều do người dùng; cần đọc ngữ cảnh và response body.

## 4. Thuật ngữ chuyên môn

| Thuật ngữ | Giải thích |
|---|---|
| URL | Địa chỉ định vị tài nguyên |
| DNS | Hệ thống phân giải tên miền thành thông tin định tuyến, thường là địa chỉ IP |
| IP address | Địa chỉ mạng của thiết bị/giao diện |
| TLS | Giao thức bảo vệ kết nối, cung cấp mã hóa và xác thực |
| HTTP | Giao thức trao đổi thông điệp Web |
| Header | Trường metadata trong request/response |
| Status code | Mã trạng thái HTTP |
| Cache | Cơ chế lưu bản sao để giảm tải và tăng tốc |
| CDN | Mạng phân phối nội dung từ các điểm gần người truy cập |

## 5. Cú pháp / cấu trúc

Ví dụ HTTP request dạng khái niệm:

\`\`\`http
GET /learn HTTP/1.1
Host: example.com
Accept: text/html
\`\`\`

Ví dụ response:

\`\`\`http
HTTP/1.1 200 OK
Content-Type: text/html; charset=utf-8

<!doctype html>
<html lang="vi">
  <title>Xin chào</title>
</html>
\`\`\`

Đây là minh họa định dạng thông điệp, không phải lệnh chạy trong terminal.

## 6. Ví dụ code / thao tác

Mở DevTools trong trình duyệt:
1. Mở một trang web bất kỳ.
2. Nhấn F12 hoặc mở Developer Tools từ menu trình duyệt.
3. Chọn tab Network.
4. Tải lại trang.
5. Chọn một request và quan sát Headers, Response, Status Code và Timing.

### Phân tích

- Request URL: tài nguyên được yêu cầu.
- Request Method: phương thức HTTP.
- Status Code: kết quả server trả về.
- Response Headers: metadata của phản hồi.
- Response/Preview: nội dung phản hồi nếu trình duyệt hiển thị được.

**Trạng thái kiểm thử:** Hướng dẫn thao tác; chưa được thực thi trong trình duyệt của kho này.

## 7. Ứng dụng thực tế

Khi trang web không tải được:
- Kiểm tra URL và kết nối.
- Quan sát DNS/network errors.
- Kiểm tra status code.
- Xem response body và console.
- Xác định lỗi nằm ở client, mạng, CDN hay server trước khi sửa.

## 8. Lỗi thường gặp

| Nhầm lẫn | Cách hiểu đúng |
|---|---|
| Internet và Web là một | Web là một dịch vụ/hệ thống chạy trên Internet |
| 404 luôn có nghĩa server ngừng hoạt động | Server đã phản hồi nhưng không tìm thấy tài nguyên theo yêu cầu |
| HTTPS làm website tự động an toàn tuyệt đối | HTTPS bảo vệ đường truyền; ứng dụng vẫn có thể có lỗi bảo mật |
| 200 có nghĩa nội dung chắc chắn đúng | 200 chỉ cho biết request được xử lý thành công theo ngữ nghĩa HTTP |
| DNS là nơi lưu website | DNS chủ yếu phân giải tên; nội dung website nằm ở hạ tầng phục vụ nội dung |

## 9. Phương pháp sửa lỗi

1. Ghi lại URL và thời điểm xảy ra lỗi.
2. Xác định lỗi hiển thị trong trình duyệt hay status code.
3. Kiểm tra Network và Console.
4. So sánh request thành công với request lỗi.
5. Thay đổi từng yếu tố một và kiểm tra lại.
6. Không chia sẻ cookie, token hoặc thông tin cá nhân khi gửi ảnh/chụp DevTools.

## 10. Bài tập cơ bản

1. Nêu hai điểm khác nhau giữa Internet và Web.
2. Ghép các mã: 200, 301, 404, 500 với nhóm trạng thái tương ứng.
3. Client trong trường hợp mở website bằng trình duyệt là gì?

## 11. Bài tập trung cấp

Một trang chủ tải được nhưng ảnh đại diện trả về 404. Hãy nêu quy trình tìm nguyên nhân.

## 12. Bài tập nâng cao

Một API trả 429 khi người dùng gửi nhiều request trong thời gian ngắn. Hãy giải thích ý nghĩa và đề xuất cách xử lý phía client phù hợp, không cố tình né giới hạn.

## 13. Đáp án và giải thích

1. Internet là hạ tầng kết nối mạng; Web là hệ thống tài nguyên/liên kết truy cập qua Internet.
2. 200 thuộc 2xx; 301 thuộc 3xx; 404 thuộc 4xx; 500 thuộc 5xx.
3. Trình duyệt là client.
4. Với ảnh 404: kiểm tra URL ảnh, đường dẫn tương đối/tuyệt đối, tên tệp và chữ hoa/chữ thường, trạng thái deploy, quyền truy cập và response.
5. 429 nghĩa là Too Many Requests. Client nên tôn trọng Retry-After nếu server cung cấp, giảm tần suất request và dùng backoff phù hợp.

## 14. Dự án thực hành

**Dự án:** Nhật ký phân tích tải trang.
- Chọn một website công khai.
- Ghi lại 5 request trong Network.
- Phân loại method, status, content type và thời gian tải.
- Vẽ sơ đồ client → DNS → kết nối bảo mật → server → response.
- Không thu thập hoặc công bố dữ liệu riêng tư.

## 15. Tiêu chí đánh giá

| Tiêu chí | Điểm |
|---|---:|
| Giải thích đúng mô hình Internet/Web | 20 |
| Mô tả luồng tải trang | 25 |
| Đọc đúng request/response | 25 |
| Phân tích lỗi có trình tự | 20 |
| Trình bày rõ ràng, không lộ dữ liệu nhạy cảm | 10 |
| **Tổng** | **100** |

## 16. Tài liệu tham khảo

- MDN, Overview of HTTP: https://developer.mozilla.org/en-US/docs/Web/HTTP/Overview
- MDN, How the Web works: https://developer.mozilla.org/en-US/docs/Learn_web_development/Getting_started/Web_standards/How_the_web_works
- RFC 9110, HTTP Semantics: https://www.rfc-editor.org/rfc/rfc9110
- WHATWG HTML Standard: https://html.spec.whatwg.org/

## 17. Lịch sử thay đổi

| Ngày | Phiên bản | Thay đổi |
|---|---|---|
| 2026-11-18 | 1.0.0 | Nhập bài nền tảng Web và HTTP |

## 18. Ghi chú sư phạm

Dạy theo luồng trực quan trước, sau đó mới giới thiệu thuật ngữ. Yêu cầu học viên dự đoán status code trước khi xem kết quả, tự quan sát Network và giải thích bằng lời của mình. Ôn lại khái niệm sau 1 ngày, 1 tuần và 1 tháng.
