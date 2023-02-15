# Khái niệm chuyên môn
## Tổng quan SSL
SSL được viết tắt từ __Sercure Sockets Layer__, là một tiêu chuẩn bảo bật công nghệ, tạo ra liên kết giữa máy chủ web và trình duyệt. Nó giúp đảm bảo các dữ liệu trao đổi giửa 2 phía luôn được an toàn.

Ngoài ra khi sử dụng thì mọi dữ kiệu trao đổi giữa người nhận và website hau người gửi đều được bảo vệ bở cơ chế mạnh mẽ nhất hiện tại, được hàng triệu khách hàng tin tưởng và sử dụng hơn.

SSL sẽ giúp bảo mật các giao dịch giữa khách hàng và doanh nghiệp, các dịch vụ truy nhập hệ thống trang web và các ứng dụng như Outlook Web Access, Exchange, và Office Communication Server,... và còn bảo mật cả các ứng dụng ảo hóa hoặc các ứng dụng điện toán đám mây (cloud)

### Phân loại SSL
1. DV-SSL: domain validation

Dành cho khách hàng cá nhân, cấu hình cơ bản và giá rẻ

Chỉ yêu cầu quyền sở hữu domain và thời gian đăng ký, thời gian xác minh ngắn

Ngoài ra, các website của khách hàng sẽ được kích hoạt trạng thái __"khóa an toàn"__, đảm bảo an toàn cho các giao dịch thương mại điện tử, thông tin đăng nhập tài khoản web, email trực tuyến, lưu lượng mạng và dịch vụ trực tuyến

2. OV-SSL: organization validation

Dành cho khách hàng thuộc tệp tổ chức, văn phòng, công ty, doanh nghiệp, tập đoàn,... có độ tin cậy cao

OV-SSL sẽ chứng thực, xác minh website cũng như doanh nghiệp sở hữu website đó

Các website của khách hàng sẽ được kích hoạt trạng thái __"khóa an toàn"__, đảm bảo an toàn cho các giao dịch thương mại điện tử, thông tin đăng nhập tài khoản web, email trực tuyến, lưu lượng mạng và dịch vụ trực tuyến

3. EV-SSL: extent validation

EV-SSL tuân thủ nghiêm ngặt các quy định của tổ chức CA-Browser Forum trong quá trình xác minh doanh nghiệp. Khi người dùng truy cập vào các website được trang bị EV-SSL, thanh địa chỉ của browser sẽ chuyển sang màu xanh lá cây, đồng thời hiển thị tên doanh nghiệp sở hữu website đó. Điều này giúp gia tăng độ tin cậy của website đó đối với người dùng.

4. Wildcard SSL Certificate

Chuyên dành cho các website có nhu cầu sử dụng SSL cho nhiều subdomain khác nhau. Wildcard SSL khác với các loại SSL bình thường là có thể chạy cho không giới hạn tên miền phụ với một chứng chỉ SSL duy nhất

5. SANS:

Được thiết kế cho các ứng dụng Communication của Microsoft như Microsoft Exchange Server, Microsoft Office Communications, Lync và cũng là giải pháp tiết kiệm cho các môi trường khác như Share Hosting & QA Testing. Lựa chọn thêm SANs cho phép bảo mật tới 40 tên miền và máy chủ chỉ với một chứng thư số. Ngoài ra, SANs còn mang lại sự linh hoạt cho người sử dụng, dễ dàng hơn trong việc cài đặt, sử dụng và quản lý chứng thư số SSL. 

Ngoài ra còn có MDC-SSL (chứng chỉ đa miền) và UCC-SSL (truyền thông hợp nhất) 

### Sự thay thế

Công nghệ này đang lỗi thời và được thay thế hoàn toàn bởi TLS.

TLS là chữ viết tắt của __Transport Layer Security__, nó cũng giúp bảo mật thông tin truyền giống như SSL. Nhưng vì SSL không còn được phát triển nữa, nên TLS mới là thuật ngữ đúng nên dùng.

Về cơ bản SSL và TSL ko quá khác nhau trừ cách gọi tên, các chơ chế hoạt động gần như không đổi

### Vai trò của SSL với 1 trang web

- Mã hóa thông tin: các dữ liệu, thông tin trong quá trình truyền giữa browser và server được bảo vệ an toàn, tránh các tình huống huống xâm phạm, phá hoại, đánh cắp từ kẻ tấn công
- Nâng cao tính xác thực trang web: hạn chế thông tin sai sót và truyền đi lung tung trong quá trình truyền giữa server tới browser được chỉ định, các thông tin đó sẽ chỉ có các bên được xác định mới có thể đọc được
- Gia tăng độ tin cậy cho khách hàng: khách hàng sẽ không muốn truy cập, trao đổi thông tin với trang web bị gán cảnh báo không an toàn, nếu được trang bị SSL, khách hàng sẽ yên tâm hơn khi lựa chọn truy cập trang web, chọn lọc thông tin và tải xuống
- Nâng cao, tối ưu vị trí tìm kiếm trên bảng xếp hạng: Với vị trí càng cao trên bảng tìm kiếm sẽ là lợi thế với các trang web có SSL. Ở góc độ doanh nghiệp thì điều này giúp tiếp cận các tệp khách hàng hiệu quả cũng như chuyển đổi khách hàng tiềm năng thành khách hàng thực tế. 
- Điều kiện tiêu chuẩn cho các trang web có tính năng thanh toán trực tiếp (PCI compliance). Các trang web thu thập thông tin khách hàng, số tài khoản ngân hàng, thẻ tín dụng,.... đều cần có chứng chỉ SSL hợp lệ để  có thể tiếp nhận thông tin khách hàng  

### Các chú ý khi đăng ký SSL
- Giá thành: với đối tượng khách hàng cá nhân hay doanh nghiệp vừa và nhỏ thì 1 chứng chỉ SSL giá thành thấp nhưng hiệu suất bảo mật vẫn phải tối ưu là điều cần thiết để cân bằng chi phí
- Gia hạn chứng chỉ: tất cả chứng chỉ SSL đều có thời hạn, thông thường SSL sẽ hết hiệu lực sau 1 năm kể từ ngày kích hoạt, do đó cần lưu ý về thời hạn SSL, để  tránh việc trang web có nhiều lỗ hổng cho cả người dùng lẫn doanh nghiệp dễ bị kẻ xấu lợi dụng.
- Sử dụng HTTPS: https bảo mật hơn giap thức cũ là http ở việc có thêm  SSL, 2 công nghệ này luôn đi liền với nhau và trở thành tiêu chuẩn mới cho website hiện nay đều yêu cầu sử dụng giao thức HTTPS thay vì giao thức cũ
- Số lượng tên miền: như đã nêu rằng có SSL dơn miền và SSL đa miền, trừ khi khách hàng có dự dịnh mở rộng tên miền trong tương lại thì việc lựa chọn SSL đợn miền cũng là 1 cách để tối ưu chi phí cho bản thân
- Loại SSL: tùy theo qui mô doanh nghiệp sẽ lựa chọn loại SSL tương ứng. Tăng độ tin cậy trong mắt khách hàng cũng là 1 cách tăng độ uy tín doanh nghiệp, chứng chỉ xác thực càng cao cấp thì độ bảo vệ cũng như đảm bảo quyền lợi, kể cả giá thành cũng cao theo 

### Cơ chế hoạt động của SSL
SSL hoạt động dựa trên mã khóa public khi user sử dụng 1 dịch vụ có SSL hỗ trợ như truy cập 1 website

Mã khóa này có 2 phần là private key và public key để truyền dữ liệu giữa 2 hệ thống:

- client truy cập dịch vụ của server có SSL, ứng dụng dịch vụ yêu cầu lấy public key từ server đổi với key của chính client
- client nhận public key từ server, giải mã và gửi lại key mã hóa vừa tạo về lại server
- server nhận kkey và giải mã, sau đó gửi cả key và nội dung được mã hóa về  client
- client nhận packet, giải mã nội dung vừa nhận, hoàn tất bước "bắt tay SSL/TLS"

### Thành phần chung của SSL
- CSR (Certificate Signing request): Là 1 đoạn text chứa thông tin của chủ sở hữu tên miền được mã hóa. Thông tin này được gửi đến nhà cung cấp dịch vụ SSL

- CRT (Certificate): phần kết quả được trả về website từ SSL provider sau khi nhận CSR

- Private key: được sinh ra cùng lúc CRT, CRT được mã hóa khi đưa về browser và phần key này dùng để giải mã thông tin mã hóa của CRT

- CA (Certificate Authority): tổ chức cung cấp thong tin SSL

### Các giao thức con của SSL

- SSL Handshake Protocol.
- SSL Change Cipher Spec Protocol.
- SSL Alert Protocol.
- SSL Record Protocol.

