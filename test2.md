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
Xem lại lần commit mới nhất ở mỗi branch:
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

Còn [`push`] thì ngược lại với __fetch__, cho phép user đẩy file và các nội dụng đã xác nhận lên 1 branch được chỉ định, để tránh bị ghi đè thì Git sẽ không push khi nó ko fast-forward-merge thành công trên repo đích

```
git [remote] [branch]
```
với option [--force]: buộc đẩy ngay cả khi chưa đủ điều kiển push, hạn chế sử dụng khi chưa đảm bảo nội dung được xác nhận

Option [--all]: đẩy toàn bộ file và nội dung đến remote branch được chỉ định

Option [--tags]: các tag thường không được push tự động mà cần dùng option này để đẩy toàn bộ tag đến remote repo được chỉ định

User có thể đổi tên branch cho phù hợp ý muốn của mình
```
git branch --move [old-name] [new-name]
```
Tuy nhiên đây chỉ là thay đổi cục bộ và không ai khác ngoài chính user đó nhìn thấy, để có thể thay đổi trên remote repo và nhiều người thấy hơn
```
git push --set-upstream origin new-name
```
Nếu ở main branch hoạt như master brench, user có thể xóa master branch

6. __Remote Repository__

Mục đích của việc sử dụng remote repository là cho phép bất cứ ai ở những địa điểm khác nhau cũng có thể đóng góp các thay đổi mới cho repository.

- Khởi tạo 1 repository trong folder trống có sẵn:
```
$ cd /home/user/[folder-name]
$ git init
```
Tại đây sẽ tạo thư mục nhánh với đuôi dạng ".git" và chứ toàn bộ file, nội dung cần thiết cho 1 repository cơ bản (khung git repo). 

- Khởi tạo trong folder đang sử dụng từ trước cần có các bước lệnh để dò tìm theo thư mục đó cũng như xác thực:
```
$ git add *.c
$ git add LICENSE
$ git commit -m 'Initial project version
```
- Sao chép repository có sẵn từ trước:
```
$ git clone URL
```
Ví dụ: sao chép repo từ link tên "report"
`$ git clone https://github.com/dinh-nam/report `

Lúc này sẽ có thư mục tên là "report" cùng với đầy đủ file cũng như nội dung sao chép đã sẵn sàng làm việc bên trong

Nếu user muốn clone vào 1 nơi có tên khác với tên mặc định thì cần nêu tên được chỉ định làm đối số:

`$ git clone https://github.com/dinh-nam/report testing-file`

Sau đó file sẽ được đưa thẳng đến thư mục "testing-file" 

7. __Aliases__

Có thể gọi là 1 cách viết tắt lệnh, hỗ trợ người dùng về mặt syntax rất nhiều
```
$ git config --global aliases.ci 'commit -a'
hoặc là
$ git config --global aliases.unstage 'reset HEAD --'
```
Trong đó, user được phép gán lệnh cần thực thi vào ký tự hoặc cụm từ được chỉ định, qua đó khi gọi lệnh không cần phải nhập toàn bộ chính xác mà có thể dùng ngay các cụm từ đó như sau:
```
$ git ci
$ git unstage fileA
```
8. __Tag__

Git gắn thẻ vào các mốc cụ thể  quan trọng trong lịch sử của repo, thông thường sẽ là các điểm công bố phiên bản (v1.0,v2.0)

Phân biệt loại tag, liêt kê tag, tạo-xóa tag

Để liệt kê các tag hiện có:
```
git tag -l
```
Kết quả trả về sẽ xếp theo thứ tự alphabet (bảng chữ cái), không có tính quan trọng

Ngoài ra user có thể tìm kiếm tag theo mẫu chỉ định. Ví dụ source repo có khoảng 500 tags và user cần tìm tag thuộc series 1.8:
```
git tag -l "v1.8"
v1.8.0-rc0
v1.8.0-rc1
v1.8
v1.8.1
v1.8.2
v1.8.5
```
Đối với tìm theo mẫu cụ thể thì option [-l/list] là bắt buộc

- Tạo tag

Git hỗ trợ 2 loại tag: lightweight và annotated

_Annotated tag:_

Là tag có chứ đầy đủ object của Git database, chúng đã được kiểm tra tổng hợp, chứa thời gian, tên, email người gán tag, có cả lời nhắn tag, được ký thực và xác thực bởi GNU-PG

Cách tạo đơn giản
```
git tag -a [name-tag] -m "text mess here"
```

_Lighweight tag:_

Là tag trỏ về  1 commit cụ thể và không thay đởi gì trong branch, không hiện quá nhiều thông tin chi tiết
```
git tag v1.8.6-lw
```
Không cần thêm bất cứ option nào, khi dùng `git show` sẽ chỉ hiển thị thông tin phần commit

_Tag Later:_

Dành cho các trường hợp bỏ sót hoặc quên tag commit, Git vẫn cho phép user tag lại phần commit sau đó
```
git log --pretty=oneline
```
Lệnh này cho user nhìn toàn bộ các hoạt động đã diễn ra trong lịch sử commit 

Kết quả sẽ trả về 1 chuỗi kí tự checksum cũng như tên commit đã hoàn thành trước đó. Sau khi chọn được phần commit cần tìm, bắt đầu gán tag vào trùng khớp với dãy checksum (hoặc 1 vài kí tự đầu) để tiền hành thay đổi tag.
```
git tag -a [name-tag] [checksum]
```
_Sharing tag:_

Mặc định lệnh `push` sẽ không chuyển tag lên remote server, do đó cần đẩy các tag lên server sau khi khởi tạo xong
```
git push origin <tagname>
```
Trong trường hợp cần đẩy nhiều tag cùng lúc lên server:
```
$ git push origin --tags
```
Hệ thống sẽ đẩy toàn bộ các tag lên và khi có user khác clone repo cũng sẽ được kèm theo các tag (bao gồm lightweight lẫn annotated)

Nếu chỉ push annotated tag lên mà không kèm lightweight:
```
git push <remote> --follow-tags
```
- Xóa tag

Để xóa tag ở local repo: 
```
git tag -d <tagname>
```
Nhưng để xóa tag ở remote server có 2 cách xóa như sau:
```
git push <remote> :refs/tags/<tagname>
```
Lúc này git sẽ đọc giá trị null, đẩy lên trên remote servertrước khi dấu colon được đưa lên, qua đó hủy bỏ tag hiệu quả

Còn cách khác khá trực quan và dễ nhớ hơn (thường dùng nhiều hơn)
```
$ git push origin --delete <tagname>
```
- CheckOut tag

Để kiểm tra các tag hiện tại đang trỏ về các phiên bản file khác nhau, dùng lệnh `git checkout`, lúc này repository sẽ đặt vào trạng thái __"detached HEAD"__, có thể mất tính an toàn cho nội dung bên trong

Ở trạng thái, mọi sửa đổi vẫn nằm trong tag cũ nhưng sẽ cần commit mới và branch mới, không thuộc về bên nào khác và không thể truy cập trừ commit hash. Do đó nếu muốn thay đổi, chỉnh sửa bất kì điều gì, ngay cả sửa lỗi, đều phải tạo 1 nhánh mới

Sau khi hoàn thành và commit, nhánh mới này sẽ có khác biệt một chút so với bản gốc và nó sẽ theo các thay đổi mới này