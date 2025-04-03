### Khả năng mở rộng của Microsoft Copilot thông qua các tác vụ trong Declarative Agents và Custom Agents

Microsoft Copilot cung cấp khả năng mở rộng thông qua việc sử dụng các tác vụ (Actions) trong cả Declarative Agents và Custom Agents. Bài viết cung cấp một bản demo thực tế về việc sử dụng trình kết nối Adobe Acrobat để truy xuất danh sách thỏa thuận. Người dùng có thể thêm hành động vào tác nhân, kiểm tra các kết nối và xác thực quyền truy cập dữ liệu.

# Phân biệt Declarative Agents và Custom Agents

| **Declarative Agents**                                                                                                                                     | **Custom Agents**                                                                                         |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------- |
| Được xây dựng để hoạt động trong Microsoft 365; - Không thực sự tự mình làm bất cứ điều gì. - Được xây dựng trong thư viện trong Microsoft Copilot Studio. | Có thể được sử dụng trong Microsoft 365, trên trang web, trong ứng dụng Dynamics, và nhiều nền tảng khác. |
| Được tạo trong Copilot Studio và sử dụng dữ liệu nội bộ của doanh nghiệp.                                                                                  | Yêu cầu cấu hình mô hình AI, ví dụ như GPT-3.5 hoặc GPT-4.0, để hoạt động theo nhu cầu cụ thể.            |
| Cho phép thêm nguồn kiến thức, lời nhắc và hành động để truy xuất thông tin doanh nghiệp.                                                                  | Được thiết kế để hoạt động như các hệ thống độc lập.                                                      |

### Khả năng mở rộng của Copilot

Khi sử dụng Copilot trong Teams hoặc Bing, nó truy xuất thông tin từ internet và dữ liệu có sẵn.

Để mở rộng Copilot với dữ liệu doanh nghiệp, người dùng cần tích hợp các nguồn dữ liệu nội bộ thông qua API, luồng tự động hoặc trình kết nối.

### Các hành động có thể sử dụng để mở rộng Copilot

Trình kết nối: Dùng nền tảng Microsoft Power để liên kết với các dữ liệu ngoài như SQL, Adobe, Freshdesk, v.v.

Hành động hội thoại: Hỗ trợ các câu hỏi và trả lời như các chatbot truyền thống.

Luồng tự động: Giúp thực hiện các quy trình dựa trên dữ liệu nội bộ.

REST API: Nếu không có trình kết nối phù hợp, có thể sử dụng API để truy xuất dữ liệu.

### Ví dụ minh họa

Trong bài hướng dẫn này, chúng ta sẽ cùng tìm hiểu cách chọn và thiết lập một Custom Agent, cũng như cách mở rộng nó bằng cách tích hợp các hành động từ Adobe.
Nếu bạn đang trong trình quản lý Agent, bạn sẽ chọn một Custom Agent. Đợi quá trình tải hoàn tất—lúc này, bạn sẽ thấy toàn bộ nội dung có sẵn bên trong Agent của mình.

(screenshot-01JQXZZJHQFMFV7WX9GRG9J1PT.png)

Đây là giao diện của Agent. Hiện tại, chúng ta chưa có nguồn kiến thức (Knowledge) nào. Tuy nhiên, chúng ta thấy rằng một số hành động liên quan đến Adobe đã được thêm vào trước đó. Điều này cho phép chúng ta mở rộng khả năng của Copilot để truy cập dữ liệu Adobe — từ việc tạo mẫu thư viện, tải lên tài liệu, đến các tác vụ khác.

**Thêm hành động mới**
Bây giờ, tôi muốn thêm một hành động để lấy danh sách tất cả các thỏa thuận (agreements) trên Adobe Acrobat.

Nhấn Thêm hành động.
![alt text](screenshot-01JQXZZJHQFMFV7WX9GRG9J1PT-1.png)

Chọn từ danh sách các hành động khả dụng thông qua trình kết nối Microsoft. Tìm kiếm Adobe Acrobat.

![alt text](screenshot-01JQYATJAVFNYBZ1Q2G2XVN2K4-1.png)

Chọn hành động lấy danh sách tất cả các thỏa thuận.

Xác thực kết nối với Adobe, đảm bảo rằng Agent có quyền truy xuất dữ liệu.

Sau khi thiết lập xong, hệ thống sẽ hiển thị hành động mới.
![alt text](screenshot-01JQY0B7ZB3SKQHZ5GX0R981TX-1.png)

Chúng ta có thể kiểm tra khả năng hoạt động của nó thông qua bảng kiểm tra.
![alt text](screenshot-01JQY0BFHFBD3XH1K38N3BH5J3.png)

**Tích hợp REST API để mở rộng khả năng truy xuất dữ liệu**
Nếu bạn muốn lấy dữ liệu từ một hệ thống mà không có trình kết nối sẵn, REST API là giải pháp phù hợp.

- Cách thêm REST API vào Copilot
  Truy cập Copilot Studio và vào khu vực Actions.
  ![alt text](screenshot-01JQY0D3VJ8128KVTN9EQ171C5.png)

Nhấn Thêm hành động (Add Action).

Tìm kiếm REST API → Chọn Thêm API mới (New REST API).
![alt text](screenshot-01JQY0DRR5W0MMPQ47YZ3XH3DE.png)

Tải lên tệp Swagger hoặc mô tả API từ máy tính.
![alt text](03.04.2025_21.22.03_REC.gif)
Hệ thống sẽ xử lý và xác nhận rằng tệp API đúng định dạng.
![alt text](screenshot-01JQY0MTXPKDQVXZMKYXQM65TY-1.png)
Cấu hình API: Đặt tên và mô tả API, điều chỉnh xác thực (OAuth 2.0 hoặc API Key).
![alt text](screenshot-01JQY0R8HM2559S4NH3BH03GMH.png)
Chọn các hành động bạn muốn thực hiện, chẳng hạn như:

Truy xuất danh sách dữ liệu

Tạo mới thông tin

Cập nhật hoặc xóa dữ liệu (nếu cần)
![alt text](screenshot-01JQY0Q9K18MP5WEH60VKMP8H3.png)

Ở đây tôi chọn Không xác thực (None) → Phù hợp cho các API công khai (chỉ dùng trong bản demo). Sau đó nhấn Next.

Sau khi xác thực API, bạn sẽ thấy danh sách các hành động có thể sử dụng:

GET Tickets → Lấy danh sách tất cả vé từ hệ thống.

CREATE Ticket → Tạo một vé mới dựa trên đầu vào của người dùng.

UPDATE / DELETE → Nếu không chọn, người dùng sẽ không thể chỉnh sửa hoặc xóa vé.
![alt text](screenshot-01JQY0TRVY011FHTPHER8RNE0Q.png)

Kiểm tra và tinh chỉnh kết nối
Kiểm tra đầu vào (input) và đầu ra (output) của hành động.

Đầu vào: Các tham số cần thiết để lấy dữ liệu từ API.

Đầu ra: Dữ liệu mà API sẽ phản hồi sau khi xử lý yêu cầu.

Ví dụ, với REST API để lấy danh sách vé hỗ trợ (Get Tickets), đầu vào có thể bao gồm ID vé, trạng thái, và đầu ra có thể là danh sách vé với thông tin chi tiết.
Tắt AI General Knowledge nếu muốn Copilot chỉ sử dụng dữ liệu nội bộ.
![alt text](screenshot-01JQY0XNSDJKCPKXYJ8QAF8VB9.png)
![alt text](screenshot-01JQY0XYHEV07475GF41QF0KJT.png)

Tích hợp Adaptive Cards
Mặc dù phần này không được đào sâu trong phiên này, nhưng Adaptive Cards giúp hiển thị thông tin một cách trực quan hơn trong giao diện Copilot. Điều này giúp người dùng dễ dàng tương tác với dữ liệu mà họ truy xuất.
![alt text](screenshot-01JQY0YEF0S0BMBPKQNQF0GKBA.png)

Kiểm tra và tinh chỉnh
Để đảm bảo các hành động hoạt động tốt, hãy:

Làm mới hệ thống để hiển thị các hành động mới.

Kiểm tra đầu vào & đầu ra bằng thử nghiệm mô phỏng.

Tắt AI General Knowledge nếu bạn chỉ muốn Copilot sử dụng dữ liệu nội bộ.

![alt text](screenshot-01JQY15GZYFVS0XEFCDEDHNZEJ.png)

Publish Action
![alt text](screenshot-01JQY15Q4HF4CWF2S3QA00B2AW.png)

**Kết luận**

Việc tích hợp các hành động như trình kết nối, REST API, và các công cụ khác vào Microsoft Copilot giúp mở rộng khả năng truy xuất dữ liệu và tự động hóa quy trình. Điều này không chỉ tăng cường hiệu suất làm việc mà còn mang lại sự linh hoạt trong việc tùy chỉnh Copilot theo nhu cầu cụ thể của doanh nghiệp.
