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

Về cơ bản SSL và TSL ko quá khác nhau trừ cách gọi tên, các cơ chế hoạt động gần như không đổi

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
- SSL Handshake Protocol. (được dùng phổ biến)
- SSL Change Cipher Spec Protocol.
- SSL Alert Protocol.
- SSL Record Protocol.

### Các thuật toán mã hóa dùng trong SSL
Một số thuật toán SSL sử dụng:

- DES (Data Encryption Standard) là một thuật toán mã hoá có chiều dài khoá là 56 bit.
- 3-DES (Triple-DES): là thuật toán mã hoá có độ dài khoá gấp 3 lần DES
- DSA (Digital Signature Algorithm): là một phần trong chuẩn về xác thực số đang được được chính phủ Mỹ sử dụng.
- EA (Key Exchange Algorithm) là một thuật toán trao đổi khoá đang được chính phủ Mỹ sử dụng.
- MD5 (Message Digest algorithm) được phát thiển bởi Rivest.
- RSA: là thuật toán mã hoá công khai dùng cho cả quá trình xác thực và mã hoá dữ liệu được Rivest, Shamir, and Adleman phát triển.
- RSA key exchange: là thuật toán trao đổi khoá dùng trong SSL dựa trên thuật toán RSA.
- RC2 and RC4: là các thuật toán mã hoá được phát triển bởi Rivest dùng cho RSA Data Security.
- SHA-1 (Secure Hash Algorithm): là một thuật toán băm đang được chính phủ Mỹ sử dụng.

## Tổng quan về Domain
Domain là tên miền của 1 trang web hay còn gọi là địa chỉ trang web, định danh trang web đó chính xác theo tìm kiếm của người dùng

Domain có 2 cấp là 2 cấp chính là 1 cấp phụ 
### Cấu trúc của domain
Tối thiểu 1 tên miền có 2 phần là tên miền cấp cao và toplevel domain

Ngoài ra có thêm subdomain mà dễ thấy nhất là "www"-world wide web

### Cách hoạt động của domain
Khi 1 user muốn truy cập vào 1 địa chỉ cụ thế, tên miền chính là đường đi ngắn nhất để đến website đó

Nếu DNS server gần nhất chưa được quảng bá tên miền trên vào bảng ghi nhớ, nó sẽ tìm hỏi ở các DNS server khác gần nó nhất và tiến trình lặp lại đến khi có 1 DNS server nào đó biết hoặc có được thông tin về domain này, sau đó từ client user sẽ tìm đường đi ngắn nhất kết nối đến website đó, trong khi đó các server chưa có thông tin trước đó sẽ lưu lại vào database của mình 

** Trong trường hợp không có tên domain thì chỉ có thể truy cập website thông qua IP của máy chủ đó **

### Phân loại domain
1. Top level domain

Là tên miền cấp cao nhất đứng sau dấu chấm đầu tiên và gần như bao gồm mọi domain hiện có, được dùng phổ biến nhất như ".com" ".org" ".gov" ".edu" ".info" ".net" ...

2. ccTLD: country-code top-level-domain

Là tên miền cấp cao dành riêng cho từng quốc qia cụ thể như Mỹ(.us) hay Pháp(.fr), chúng còn được các doanh nghiệp lớn hay tập đoàn đa quốc gia sử dụng cho từng site cụ thể ở các thị trường nhất định

3. gTLD: generic top-level-domain

Nhóm tên miền này được xem là domain cấp cao của chung không thuộc riêng của hội nhóm hay tổ chức, chính phủ quốc gia nào mà là hướng đến 1 lĩnh vực, mục đích cụ thế. Ví dụ như giáo dục(.edu)

4. sTLD

Sponsored top-level domain là tiên miền cấp cao nhất được tài trợ, các tên miền cấp này bị giới hạn như (.mil), (.gov). Ngoài ra, còn có một số tên miền khác cũng đại diện cho sTLD, chẳng hạn như (.edu) – dành cho tổ chức giáo dục, (.asia) – dành cho các công ty tại thị trường Châu Á hay (.post) – dành cho bưu chính viễn thông,...

5. uTLD

Ngược lại với sTLD thì uTLD không được tài trợ sử dụng chủ yêu cho mục đích chia sẻ thông tin chung như các đầu báo tin tức online (.info)

6. iTLD

Viết đầy đủ là Infrastructure top-level domain, là tên miền (.arpa). Đây là tên miền đại diện cho ARPA và chỉ dành riêng cho ICANN dùng để giải quyết các vấn đề về cơ sở hạ tầng internet.

