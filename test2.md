# Git

Git là một hệ thống kiểm soát phiên bản phân tán mã nguồn mở phổ biến hiện nay. Nó có thể giúp cho chúng ta lưu lại các phiên bản của những lần thay đổi vào mã nguồn và có thể dễ dàng khôi phục lại dễ dàng và người khác có quyền truy cập mã nguồn họ có thể xem các thay đổi ở từng phiên bản. Cơ chế lưu trữ của Git là nó sẽ tạo một snapshot trên mỗi tập tin và thư mục sau khi commit, từ đó chúng ta có thể tái sử dụng lại một ảnh chụp nào đó.

## Một số định nghĩa cơ bản tong Git:

- Thư mục làm việc là thư mục có nội dung cần Git quản lý
- Mỗi `commit` là một snapshot tất cả nội dung thư mục làm việc, được theo dõi bằng 40 kí tự SHA1 hash
- Index là nơi chụp ảnh nhanh tất cả thay đổi của thư mục làm việc
- Branch trong Git là con trỏ đến commit cụ thể

## Cài đặt git

Git có hầu hết trong mọi loại biến thể Linux, nhưng không phải ở dạng built-in, do đó sẽ cnầ cài đặt thông qua command

```
sudo apt-get install git
```
Sau đó cũng có thể kiểm tra phiên bản của Git `git --version`\

## Sử dụng Git

1. __Index__

Index nằm giữa thư mục làm việc và commit, khi thực  hiện lệnh có nghĩa lả đang chụp ảnh nhanh thu mục làm việc vào index, cho tới khi lệnh `commit` được thực hiện thì nội dung trong __index__ mới sao chép để tạo commit mới

Lúc này có thể dùng `commit status` để theo dõi các thay đổi

Có thể sử dụng `git diff` tượng tự nhưng __diff__ hiển thị thay đổi giữa thư mục làm việc và index trong khi đó, `git -diff --cahed` hiển thị thay đổi giữa index và commit mới nhất

2. __Branch__

Công dụng của __branch__ là đưa con trỏ đến các vị trí commit, sau lần commit đầu tiên thì sẽ là _brach master_, trừ khi đổi branch thì các lần commit sau đó đều được đưa vào _branch master_ cừa có

Để tạo branch mới dùng lệnh `git branch [new-branch]`

Tuy nhiên khi làm việc, con trỏ vẫn sẽ đưa về _branch master_, do đó để chuyển sang branch mới thì cần gõ:
```
git checkout [new-branch]
```
3. __Merge__

Trong cùng 1 project thì sẽ có nhiều phần task khác nhau, khi tập hợp lại cần đồng bộ các task theo 1 chuẩn thống nhất

Thực hiện phép __Merge__ qua các bước sau:
```
git checkout master
git merge [sub-branch]
```
Chuyển con trỏ đưa về branch master trước khi thực hiện

Tiến hành merge tất cả thay đổi/commit từ branch được chỉ định về branch master

__Lưu ý:__ mọi thay đổi về  nội dung hay folder đều phải được commit

Có đôi lúc quá trình merge sẽ gặp vấn đề, nó sẽ dừng lại trong khi user cần tìm ra và xử lí lỗi, để có thể xem được các file không được merge tại bất kì vị trí nào khi xảy ra lỗi conflict, dùng lệnh `git status`

Bất kỳ nội dung nào bị lỗi ghép và chưa được xử lý đều được xem là chưa ghép. Các file bị lỗi sẽ được xếp vào 1 thư mục riêng và có thể mở và chỉnh sửa thủ công

4. __Quản lý merge__

Hoàn toàn có thể dùng `git branch` nhưng những câu lệnh thông thường như liệt kê mọi branch hiện có
```
$ git branch
    iss53
  * master  [* thể hiện vị trí branch đang đứng hiện tại]
    testing
```
Xem lại lần commit cuối/mới nhất ở mỗi branch:
```
git branch -v
```
Với 2 option `--merge` và `--no-merge` giúp user xem được những branch nào đã hoặc chưa gộpvào branch hiện tại mà user đang đứng

Xóa 1 branch bất kỳ:
```
git branch -d/-D [branch-name]
```
Khi dùng option [`-d`] cho phép xóa 1 branch với điều kiện branch đó đã có gộp hoàn toàn, nếu không quá trình sẽ thất bại

Đối với option [`-D`] là cướng bức xóa trực tiếp 1 branch cũng như toàn bộ hoạt động/nội dung trong đó mà không cần biết nó đã được gộp hay chưa

5. __fetch và push - pull__

[`fetch`] là option cho phép user tải file cũng như các hoạt động liên quan từ 1 branch được chỉ định, nhưng không gán hay tích hợp gì khác vào repo local, giúp user có thể kiểm tra các thay đổi trước khi tiến hành gộp

Trong khi đó, [`pull`] là dạng tự động của __fetch__, tự lấy file từ remote repo và sau đó merge thẳng vào branch hiện tại user đang đứng

Còn [`push`] thì ngược lại với __fetch__, cho phép user đời file và thư mục công việc sang 1 repo khác

