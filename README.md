# package nguyenchicong-npm
https://docs.npmjs.com/changing-package-visibility

https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax

coppy https://duthanhduoc.com/blog/tao-va-publish-package-len-npm
new folder nguyenchicong-npm/
## update
npm version patch

npm publish
## package.json
npm init -y
## index.js
new file index.js
## test-folder
new folder test-folder/
# test
### main.js
new file test-folder/main.js
## cd folder nguyenchicong-npm
npm link
### cd test-folder
npm link nguyenchicong-npm
## cd test-folder
node main.js
# Publish package npm
## npm login
npm login

Press ENTER to open in the browser...
## publish package npm
npm publish

# git hay sai
git add. >> git commit -m 'init'

# git

Không dài dòng, chỉ cần nhớ những câu lệnh này là làm việc với Git được rồi. Tất nhiên sẽ có những câu lệnh tương tự nhưng không cần thiết phải nhớ những câu lệnh đó. Vì nhớ thêm chỉ làm bạn đâu đầu thôi.

Để có thể dễ dàng hiểu rõ các câu lệnh dưới cũng như là thuận tiện cho việc học thì mình khuyên anh em nên đọc 2 bài mình đã viết trước đó.

Tôi học git lại từ đầu phần 1

Tôi học git lại từ đầu phần 2

🥇Cài đặt Git

Windows và Mac thì cài thông qua link này: https://git-scm.com/

Còn anh em Linux thì đã đã được cài sẵn rồi!

🥇Cấu hình git

Tên và email của bạn sẽ đại diện cho bạn khi bạn commit cũng như là push code. Đây là bắt buộc nếu như bạn mới cài đặt Git lần đầu.

bash

git config --global user.name "Du Thanh Duoc"

git config --global user.email "duthanhduoc@gmail.com"

Để xem các config thì

bash

git config --global --list

Muốn config chỉ riêng một repository thôi thì dùng --local

🥇Khởi tạo repository ở local và push lên remote

Khởi tạo một Git repository

bash

git init

Tạo file, rồi code các kiểu trong Git repository. Bây giờ chúng ta sẽ tiến hành commit

bash

git add .

git commit -m 'init'

Mặc định thì mới khởi tạo Git Repository ở local, nhánh mặc định sẽ là master, nếu anh em muốn đổi tên sang nhánh khác, ví dụ main thì dùng câu lệnh

bash

git branch -M main

Nhánh đầu tiên push lên Git chính là nhánh mặc định của Git Repository đó trên remote

Bây giờ chúng ta sẽ tạo một mối liên kết giữa local và remote để có thể push code lên

bash

git remote add origin git@github.com:duthanhduoc/123.git

Các bạn thay thế git@github.com:duthanhduoc/123.git thành URL SSH Git Repository của các bạn nhé

Bước cuối cùng là push lên thôi. Dưới đây là mình push lên với tư cách là nhánh main.

bash

git push -u origin main

Mình thêm -u để những lần sau thì chỉ cần git push thôi là nó cũng hiểu là mình push ở nhánh hiện tại trên local, khỏi cần phải origin main cho mệt.

🥇Clone Repository ở remote về

Quá dễ, chúng ta sẽ clone bằng giao thức SSH, ai đang dùng HTTPS thì cũng nên đổi sang SSH đi cho tiện và bảo mật

bash

git clone git@github.com:duthanhduoc/123.git

🥇Kiểm tra đang ở branch nào

Câu lệnh dưới sẽ show branch hiện tại, các file mà bạn modify trong các trạng thái của git

bash

git status

Show hết tất cả branch có ở máy bạn.

bash

git branch -a

À mà nếu anh em thấy thiếu hay dư branch nào thì cứ git fetch -p rồi chạy lại git branch -a là được.

🥇Tạo một branch mới từ branch hiện tại

Cứ câu lệnh dưới đây mà phang

bash

git checkout -b TenBranchMoi

🥇Chuyển sang branch khác

Cứ checkout mà phang

bash

git checkout TenBranch

Nếu branch đó không có trên local thì dùng git fetch để nó update các branch trên local là được

🥇Kiểm tra lịch sử commit

Phổ biến nhất là

bash

git log --oneline

À mà nếu muốn thoát ra khỏi cái Editor trên terminal thì nhấn q, muốn xem trang tiếp theo thì w, trang trước đó thì space

Nhưng mình thường dùng Git UI trên VS Code cho trực quan 🤣

🥇Kéo code từ remote về để cập nhập code dưới local

Ví dụ bạn đang code ở branch feature/Login, anh Leader bảo bạn kéo code nhánh feature/Register về nhánh feature/Login của bạn đi, vì ảnh mới cập nhật trên đó.

Công việc của bạn chỉ là

bash

git pull origin feature/Register

Điều này cũng áp dụng cho nhánh của bạn được, ví dụ có ai đó cập nhật code nhánh feature/Login trên remote, bây giờ bảo bạn kéo code mới về rồi code tiếp chứ code trên local bạn cũ rồi.

bash

git pull

Không cần phải thêm origin feature/Login vì mặc định nó tự hiểu

Code xong thì cứ git push lên thôi.

Đơn giản mà đúng không!

git pull là sự kết hợp của git fetch và git merge, tức là mà đang dùng merge để gộp branch.

Còn cách dùng rebase nữa, nhưng nó khá nguy hiểm nếu không biết dùng đúng cách, vậy nên nhiều team còn cấm anh em dùng git rebase.

Anh em nào muốn tìm hiểu về git rebase thì cứ đọc bài này của mình: Tôi học git lại từ đầu

🥇Cập nhật code ở local giống hệt trên remote

Hay còn gọi là pull force, nghĩa là nhánh ở local anh em quá cũ rồi, giờ anh em muốn xóa code ở local và đem code ở remote về làm?

Anh em thực hiện pull code về ư? Không phải là lựa chọn hay, vì nếu như local của anh em có một số file thay đổi hoặc edit dở, nó bắt anh em phải commit rồi mới được phép pull cơ. Chưa kể pull về còn có khả năng bị conflict 😳.

Khổ vãi, tôi chỉ muốn code trên remote thôi mà 🥲

Cách nhanh nhất là

Cập nhật tất cả các origin/branch ở local

bash

git fetch --all

Backup branch hiện tại cho an toàn (ví dụ master). Cái này là optional thôi, anh em tự tin thì khỏi cần backup.

bash

git branch backup-master

Nhảy để commit mới nhất của origin/master.

bash

git reset --hard origin/master

🥇Cập nhật commit trước đó

Ví dụ vừa commit, bổng nhiên nhận ra là chúng ta commit thiếu một số file hoặc cần update thêm. Chúng ta có thể thêm vào commit trước đó một cách dễ dàng bằng

bash

git commit --amend --no-edit

--no-edit là cho nó git khỏi hỏi bạn có edit message commit không, nếu không có thì nó sẽ hiển thị cái editor cho bạn edit message.

À mà cập nhật commit thì sẽ làm thay đổi hash commit, nếu anh em đã push lên remote rồi thì muốn push lại thì phải git push -f mới được nhé.

🥇Lưu lại trạng thái branch hiện tại với git stash
Khi anh em đang làm dỡ branch feature/Login, sếp bảo là "feature/Register đang có bug, em kéo code về mà sửa rồi push lên lại cho anh!"

Bây giờ thì anh em cần lưu toàn bộ thay đổi trên nhánh featuer/Login

bash

git stash

Tiếp theo cứ git checkout feature/Register để sang làm việc bên branch đó. Sau khi làm việc xong chúng ta chuyển qua lại branch feature/Login.

bash

git checkout feature/Login
Apply cái stash lưu trước đó

bash

git stash apply stash@{0}

Khóa học ReactJs giúp bạn chinh phục mức lương 25 - 30 triệu/tháng
Phew! Cuối cùng bạn cũng đã đọc xong. Bài viết này có hơi dài một tí vì mình muốn nó đầy đủ nhất có thể 😅

Chúng ta đều hiểu rằng Javascript và React không hề dễ, chúng có quá nhiều concept cần phải học. Mình cũng cảm thấy nó khó! Nay lại có thể Typescript nữa 🥲, thật sự khó nuốt.

Nhưng đừng lo: Bạn có thể nắm vững các kiến thức trên chỉ trong một khóa học ReactJs Super - Shopee Clone Typescript

Mình đã bắt đầu code React vào năm 2019, và nó đã trở thành thư viện ưa thích của mình để xây dựng UI và web app. Mình cũng đã làm việc với nhiều framework khác như Angular, Vue nhưng thực sự chỉ có React là đem lại cho mình cảm xúc và sự hiệu quả. 💓

Nếu bạn đang gặp khó khăn với React, mình ở đây để giúp bạn!

Mình đã dành hơn 6 tháng để phát triển khóa học ReactJs Super - Shopee Clone Typescript. Trong khóa này bạn sẽ được học mọi thứ về thư viện ReactJs, các kiến thức từ cơ bản cho đến nâng cao nhất, mục đích của mình là giúp bạn chinh phục mức lương 25 - 30 triêu/tháng

Nếu bạn cảm thấy bài viết này của mình hữu ích, mình nghĩ bạn sẽ thích hợp với phong cách dạy của mình. Không như bài viết này, khóa học là sự kết hợp giữa các bài viết, video, quizz, bài tập nhỏ và dự án lớn có thể xin việc được ngay. Học xong mình đảm bảo bạn sẽ lên tay ngay. 💪🏻
# hoc them
1. Khởi tạo Repository trên máy tính với git init
git init

2. Config name và email cho git với git config
git config --local --list

git config --global --list

3. Hiển thị trạng thái với git status
git status

4. Các khu vực làm việc với Git

## Chúng ta sẽ có các khu vực theo thứ tự dưới đây
- Khu vực làm việc: Chính là nơi chúng ta đang code, vẫn ở local
- Khu vực staging: Sau khi dùng git add thì file sẽ được đưa lên  khu vực này, vẫn ở trên local
- Khu vực committed: Sau khi dùng git commit thì file từ staging sẽ được đưa lên đây, cũng vẫn ở trên local
- Khu vực remote (gọi origin cũng được): Sau khi dùng git push sẽ file ở commited lên đây, bây giờ file của bạn đã đưa lên trên server
5. Thêm file vào khu vực Staging với git add
- Thêm 1 file
git add index.html
- Thêm nhiều file
git add index.html app.js
- Thêm tất cả các file.
git add .
6. Khôi phục những file ở khu vực Staging về khu vực code với git reset
- Khôi phục 1 file từ staging về khu vực code
git reset index.html
- Khôi phục nhiều file
git reset index.html app.js
- Khôi phục tất cả các file.
git reset .
7. Commit code với git commit
git commit -m "Tôi thay đổi dòng này vì nó xảy ra tình trạng vòng lặp vô tận"
- Trong trường hợp bạn muốn đính kèm thêm description để mô tả thêm cho title thì bạn có thể dùng 2 cách
- Cách 1:
git commit -m "Title" -m "Description"
- Cách 2
git commit -m "Title
> Description"
8. Tạo và clone remote repo với HTTPS và SSH
- 8.1. Clone với Https
- Mở remote repo trên github lên, click vào "Code" chọn "HTTPS" và copy đường link
- Mở terminal lên paste đường link đó kèm với câu lệnh git clone, ví dụ:
git clone https://github.com/dreact04072022/git-can-ban.git
- Trong trường hợp repo đó ở chế độ public thì không sao, nếu repo đó ở chế độ private hoặc ở public nhưng bạn muốn có quyền push code lên remote repo đó thì bạn phải nhập username và mật khẩu vào khi clone. Ví dụ:
git clone https://username:password@github.com/dreact04072022/git-can-ban.git
- 8.2. Clone với SSH
- Tạo SSH key và add vào github (xem phần tiếp theo)
- Copy đường link SSH trên Github repo rồi chạy câu lệnh git clone là được
git clone git@github.com:dreact04072022/git-can-ban.git
- 8.3. Tạo SSH key
- Đầu tiên mở terminal Gish Bash lên
- Paste text bên dưới, thay thế email là địa chỉ email Github của bạn
ssh-keygen -t ed25519 -C "your_email@example.com"
- Nó sẽ yêu cầu bạn nhập tên file để lưu, nếu bạn enter thì nó sẽ lấy tên file mặc định như trong dấu (). Lưu ý là khi nhập tên file phải nhập đầy đủ đường dẫn lưu file tương tự như trong dấu () nhé.
Enter file in which to save the key (/c/Users/dutha/.ssh/id_ed25519):
- Tiếp theo nó sẽ yêu cầu bạn nhập passphrase (tương tự password thôi). Cá nhân mình thì không nhập, cứ Enter thôi vì khi nhập sau này mỗi khi làm việc với Git phải nhập passphrase khá mệt
Enter passphrase (empty for no passphrase):
Enter same passphrase again:
- Sau khi tạo thành công thì nó sẽ sinh ra cho bạn 2 file là private key và public key theo đường dẫn mà bạn nhập tên file. File chứa public key sẽ có đuôi .pub phía sau.
Your identification has been saved in /c/Users/dutha/.ssh/id_ed25519
Your public key has been saved in /c/Users/dutha/.ssh/id_ed25519.pub
Để đọc nội dung public SSH key thì bạn chỉ có khá nhiều cách, bạn dùng cách nào dưới đây cũng được. Ví dụ file public key của mình bên trên là id_ed25519.pub

Copy đường dẫn này c:/Users/dutha/.ssh/id_ed25519.pub bỏ lên Chrome thì nó sẽ ra nội dung của public key
Dùng git bash gõ cat /c/Users/dutha/.ssh/id_ed25519.pub
Lưu ý: Nếu mọi người đổi tên file khác tên mặc định thì có thể Git nó sẽ không tự động tham chiếu đến cái file đó mỗi khi nó cần xác thực ssh key. Một số tên ssh key mặc định như: id_ed25519, id_rsa

Lúc này mọi người cần tạo thêm 1 file tên là config (không có đuôi mở rộng) nằm trong thư mục .ssh có dạng như sau.

- Ví dụ như dưới đây, sửa id_duthanhduoc10 thành tên file private ssh key của bạn là được
#Default GitHub
Host github.com
HostName github.com
User git
IdentityFile ~/.ssh/id_duthanhduoc10
- 8.4. Tiến hành thêm SSH key vào Github
Github, Gitlab hay Bitbucket đều có chỗ thêm SSH public key vào.

Thêm vào là để mỗi lần clone repo từ Github ở máy tính cá nhân của chúng ta thì chúng ta không cần nhập username hay password, vì Github nó tự xác thực qua ssh.

Copy SSH public key

Nếu SSH public key có một tên khác thì nhớ sửa lại cho đúng nhé. Khi copy đừng thêm bất cứ dòng mới hay khoảng trắng nào

- Mình dùng git bash để copy
clip < ~/.ssh/id_ed25519.pub
-Click vào góc phải trên cùng của avatar trang github của các bạn, sau đó chọn Settings
Trong khu vực sidebar "Access", click chọn SSH và GPG keys.

Click New SSH key hoặc Add SSH key
Nhập mô tả bất ký cho trường "Title", ví dụ "Laptop cá nhân"

Chọn loại key tại "Key Type", ở đây cứ để mặc định là "Authentication Key"

Paste key của bạn vào trường "Key"
Click vào Add SSH key

Nếu có hỏi gì thì xác nhận tài khoản Github là xong.

- 8.5. Kiểm ta SSH key đã kết nối github thành công hay chưa
Mở Git bash

- Nhập dòng này vào và enter ssh -T git@github.com Có thể bạn sẽ thấy cảnh báo này, cứ gõ "yes" và enter thôi.
> The authenticity of host 'github.com (IP ADDRESS)' can't be established.
> RSA key fingerprint is SHA256:nThbg6kXUpJWGl7E1IGOCspRomTxdCARLviKw6E5SY8.
> Are you sure you want to continue connecting (yes/no)?

- 9. Dùng nhiều tài khoản Github trên cùng một máy tính
Tạo 1 file tên là config trong thư mục ~/.ssh/

- Viết nội dung file này tương tự như nội dung bên dưới
#Default GitHub
Host github.com
HostName github.com
User git
IdentityFile ~/.ssh/id_rsa

#React-Awesome duthanhduoc06
Host github-duthanhduoc06.com
HostName github.com
User git
IdentityFile ~/.ssh/id_rsa_duthanhduoc06
10. Đẩy code lên git server với git push
Muốn đẩy code của bạn lên server thì local repo phải được liên kết với remote repo. Có 2 cách để bạn liên kết:

Bạn chưa có local repo, bạn tiến hành clone một remote repo về máy tính thì lúc này bạn sẽ có được local repo
Bạn có local repo nhưng chưa có remote repo, lúc này bạn cần tiến hành tạo một remote repo mới hoàn toàn và tiến hành liên kết nó với local repo của bạn.
-Nếu bạn đang ở nhánh master, câu lệnh dưới đây sẽ đẩy code của bạn lên nhánh master ở remote repo (hay còn gọi là origin master)
git push origin master
11. Hiển thị log commit với git log
git log
-Nếu muốn nhìn thấy thông tin rút gọn thì
git log --oneline
12. Kéo code từ remote repo về với git pull
- Câu lệnh dưới đây sẽ pull code từ nhánh master về nhánh hiện tại của bạn ở local
git pull orgin master
13. Bỏ qua file với .gitignore
# Comment
node_modules/
.logs
- ignore các file cấu hình trên máy tính cá nhân mà không muốn xuất hiện ở các máy thành viên khác
- Cách viết .gitignore
Comment thì dùng #
Ignore file: example.exe
Ignore cả thư mục: folder/, tất nhiên là bạn dùng folder cũng được nhưng nên thêm / để phân biệt với file
Phủ định thì thêm !: !folder/file.exe
Ignore tất cả các file có đuôi là .exe: *.exe
Ignore tất cả các file có tên bắt đầu là log: log*
Ignore tất cả các file có đuôi là .exe ở theo đường dẫn folder/file.exe (các file ở đường dẫn folder/sub/file.exe sẽ không bị ignore): folder/**.exe
Ignore tất cả các file có đuôi là .exe ở thư mục folder dù cho có nằm ở sub-folder đi chăng nữa: folder/**/**.exe
Ignore mọi thứ bên trong thư mục folder: folder/**
- Xử lý Git cache
- Trong một số trường hợp bạn code một thời gian rồi, push pull các kiểu rồi, sau đó bạn mới thêm các file vào .gitignore, lúc này những file đó có thể không bị ignore vì nó đã bị git cache từ trước và git nó vẫn quản lý những file này. Cách giải quyết là hãy xóa những file đó ra khỏi cache
git rm -r --cached /đường-dẫn-file-hoặc-folder
14. Tạo file README.md
Tham khảo cách viết tại: https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax
15. Giải quyết conflict code
Code bị conflict khi code trên local branch khác xung đột với remote branch, vấn đề này xảy ra khi có ai đó đã cập nhật 1 đoạn code trên remote branch và bạn cũng cập nhật đoạn đó trên local branch.

Lúc này git sẽ không cho phép bạn push code lên, bạn phải pull code trên remote branch về và lựa chọn xem nên chọn những đoạn code nào.

Thứ tự thường dùng:

- Pull code mới nhất trên remote branch về bằng git pull
- Giải quyết conflict bằng tay, thảo luận với những người liên quan đoạn code xung đột nên chọn cái nào.
- Add file xung đột vào khu vực staging git add TenFile. Hoặc có thể git add . cũng được
- Commit cho những file xung đột đó và push code lên

16. Tạo branch mới
1 Câu lệnh này sẽ tạo một nhánh mới dựa trên nhánh hiện tại

git branch TenNhanhMoi

2 câu lệnh dưới sẽ tạo một nhánh mới dựa trên nhánh hiện tại và chuyển sang nhánh mới luôn.

git checkout -b TenNhanhMoi

git switch -c TenNhanhMoi

17. List tất cả branch
git branch

hoặc git branch --list đều như nhau

Nếu muốn thấy các remote branch

git branch -r

Nếu muốn thấy tất cả local và remote branch

git branch -a
- Đổi tên branch
git branch -m TenMoi

Cách trên chỉ áp dụng khi nhánh hiện tại của bạn là nhánh sai và bạn muốn đổi tên nhánh hiện tại. Trong trường hợp bạn muốn đổi tên nhánh nào đó không nhất thiết là nhánh hiện tại thì bạn phải ghi rõ tên nhánh cũ và nhánh mới như dưới đây

git branch -m TenNhanhCu TenNhanhMoi

- Chuyển branch

git switch TenNhanh

git checkout TenNhanh

- Push một branch
Nếu local branch của bạn không tồn tại trên remote, chạy câu lệnh sau

git push -u origin localBranch

Hoặc câu lệnh này, nó sẽ giúp các bạn không cần gõ chính xác tên local branch

git push -u origin HEAD

- Xóa branch
Xóa branch ở local

git branch -D localBranchName

Xóa branch ở remote

git push origin --delete remoteBranchName

Hoặc bạn có thể dùng cú pháp rút gọn

git push origin :remoteBranchName

Nếu bạn gặp lỗi dưới đây thì có thể ai đó đã xóa branch

error: unable to delete 'branchName': remote ref does not exist
error: failed to push some refs to 'git@repository_name'

Khi ai đó đã xóa một branch trên remote nhưng khi bạn gõ git branch -r vẫn show ra origin branch đó thì bạn cần thực hiện đồng bộ hóa bằng câu lệnh dưới đây.

git fetch -p

-p nghĩa là "prune". Sau khi fetch, những branch không còn trên remote cũng sẽ xóa khỏi local repo của bạn.

- Push code mà không cần origin

Nếu bạn để ý thì khi ở nhánh master, bạn push code lên orgin thì bạn chỉ cần git push là xong, không cần git push origin master. Nhưng nếu bạn ở nhánh khác ví dụ nhánh feature thì khi bạn push code lên origin feature thì phải git push orgin feature khá dài dòng và phải nhớ tên nhánh mệt mỏi.

Cách cải thiện khá đơn giản, bạn chỉ cần thêm option -u câu lệnh push là được, chỉ cần làm 1 lần, lần sau không cần làm với nhánh đó nữa.

git push -u origin feature


-u là short-hand của --set-upstream. Nó cho git biết rằng hãy tự kết nối nhánh local feature với origin feature

Làm 1 lần thôi, lần sau chỉ cần ở nhánh feature và nhấn git push là code tự lên.
- git merge
Gộp các commit lại của 2 nhánh với nhau dựa trên thời gian các commit, sau khi gộp thì sẽ tạo ra một commit gộp sau cùng.

git merge branchTarget

Chúng ta có 3 nhánh:

main
- Alpha: checkout từ nhánh main và thêm 2 commit D,E
- Beta: checkout từ nhánh main và thêm 2 commit là F,G
Thứ tự các commit theo chiều ngang được sắp xếp theo thời gian

   (main)
A--B-C---D--E (Alpha)
      \
       -F-----G (Beta)

Nếu ở nhánh Beta chúng ta muốn có những commit của nhánh Alpha (hay còn gọi là có code) thì ta sẽ tiến hành merge Alpha vào Beta nên ta thực hiện lệnh

git checkout Beta

git merge Alpha

Sơ đồ commit sẽ như thế này, các commit của Alpha sẽ xuất hiện trong Beta và được sắp xếp theo thứ tự thời gian. Ta sẽ thấy sự xuất hiện của một commit merge nữa phía sau cùng, commit merge này chứa tất cả những sự thay đổi của nhánh Beta sau khi merge nhánh Alpha vào.

   (main)
A--B-C---D--E (Alpha)
      \       \
       -F----G-M (Beta)

Bây giờ nhánh Beta đã có đầy đủ code của nhánh Alpha.

Nếu trong quá trình merge có bị conflict thì thao tác theo thứ tự

Tìm file conflict trong tab source và fix nó.
Sau khi fix hết các file bị conflict rồi thì dùng git add . hoặc add từng file
Tiến hành thêm commit cho những file vừa fix conflict bằng câu lệnh git commit --no-edit, nếu muốn edit commit thì git merge --continue, còn nếu muốn tự viết commit thì cứ git commit -m 'thông điệp' như thường
push hết lên với câu lệnh git push
Nếu merge xong rồi mới nhận ra mình không cần merge nữa thì có thể dùng git reset --hard <commit-của bạn-trước-khi-merge>. Cách này áp dụng cho cả đã push code hay chưa push đều được.

- git rebase
Lấy tất cả các commit của branchTarget làm lại base (gọi là re-base) cho mình, các commit của mình mà khác so với branchTarget sẽ bị thay đổi hash và thêm vào sau cùng.

git rebase branchTarget

   (main)
A-B-C-----D (feature)
     \
      --E----F (feature/Login)

git checkout feature/Login

git rebase feature

   (main)(feature)
A-B-C-----D--E'----F' (feature/Login)

