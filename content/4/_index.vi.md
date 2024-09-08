---
title : "AWS CodeCommit"
date :  "`r Sys.Date()`" 
weight : 4 
chapter : false
pre : " <b> 4. </b> "
---

### Di chuyển các repository từ AWS CodeCommit sang nhà cung cấp khác

Vào ngày 25 tháng 7 năm 2024, AWS đã thông báo rằng sản phẩm quản lý mã nguồn (SCM) của họ, **CodeCommit**, không còn khả dụng cho khách hàng mới.

Khách hàng có thể di chuyển các repository Git của [AWS CodeCommit](https://docs.aws.amazon.com/codecommit/latest/userguide/getting-started-cc.html) sang các nhà cung cấp Git khác bằng nhiều phương pháp như sao chép repository, mirroring, hoặc di chuyển các nhánh cụ thể. Bài viết này mô tả một ví dụ cơ bản về việc mirroring repository sang một nhà cung cấp khác và cung cấp liên kết đến các hướng dẫn chi tiết hơn về việc mirroring sang các nhà cung cấp cụ thể. Các bước thực hiện có thể khác nhau tùy thuộc vào loại hoặc độ phức tạp của repository và các quyết định liên quan đến cách thức di chuyển. Bài viết này chỉ mô tả cách di chuyển dữ liệu Git repository, không bao gồm việc xuất các dữ liệu khác từ CodeCommit như pull requests.

### Điều kiện tiên quyết

1. Trước khi có thể di chuyển repository CodeCommit của bạn sang nhà cung cấp khác, hãy đảm bảo rằng bạn có thông tin đăng nhập và quyền truy cập cần thiết cho cả AWS Management Console và tài khoản nhà cung cấp khác. Để di chuyển sang GitHub và GitLab, hãy sử dụng thông tin đăng nhập tĩnh của CodeCommit như được mô tả trong [HTTPS người dùng sử dụng thông tin Git](https://docs.aws.amazon.com/codecommit/latest/userguide/setting-up-gc.html). Nếu bạn chọn sử dụng quy trình di chuyển chung được mô tả dưới đây, bất kỳ loại thông tin đăng nhập nào của CodeCommit đều có thể được sử dụng. Để biết thêm thông tin về việc thiết lập quyền truy cập AWS CodeCommit, xem [Thiết lập cho AWS CodeCommit](https://docs.aws.amazon.com/codecommit/latest/userguide/setting-up.html).
   
2. Trong bảng điều khiển AWS CodeCommit, chọn URL clone cho repository bạn sẽ di chuyển. URL clone chính xác (HTTPS, SSH hoặc HTTPS (CRC)) phụ thuộc vào loại thông tin đăng nhập và giao thức mạng mà bạn đã chọn.

![](/images/4/1.png)

### Di chuyển repository AWS CodeCommit của bạn sang GitLab

Sử dụng URL clone CodeCommit kết hợp với thông tin đăng nhập Git repository qua HTTPS, làm theo hướng dẫn trong tài liệu của GitLab để [nhập mã nguồn](https://docs.gitlab.com/ee/user/project/import/) từ một [repository bằng URL](https://docs.gitlab.com/ee/user/project/import/repo_by_url.html).

### Di chuyển repository AWS CodeCommit của bạn sang GitHub

Sử dụng URL clone CodeCommit kết hợp với thông tin đăng nhập Git repository qua HTTPS, làm theo hướng dẫn trong tài liệu của GitHub để [nhập mã nguồn](https://docs.github.com/en/migrations/importing-source-code/using-github-importer/about-github-importer).

### Di chuyển repository AWS CodeCommit của bạn sang Bitbucket Cloud

Sử dụng URL clone CodeCommit kết hợp với thông tin đăng nhập Git repository qua HTTPS, làm theo hướng dẫn trong [bài viết blog của Bitbucket](https://bitbucket.org/blog/migrating-aws-codecommit-to-bitbucket-cloud).

### Di chuyển chung sang nhà cung cấp repository khác

**1.     Clone repository AWS CodeCommit**  
Clone repository từ AWS CodeCommit về máy của bạn bằng Git. Nếu bạn sử dụng HTTPS, bạn có thể thực hiện bằng lệnh sau:

`git clone --mirror https://your-aws-repository-url your-aws-repository`

Thay thế _your-aws-repository-url_ bằng URL của repository AWS CodeCommit của bạn.  
Thay thế _your-aws-repository_ bằng tên cho repository này. Ví dụ:

`git clone https://git-codecommit.us-east-2.amazonaws.com/v1/repos/MyDemoRepo my-demo-repo`

**2.     Thiết lập remote repository mới**

Chuyển đến thư mục của repository AWS CodeCommit đã clone. Sau đó, thêm URL repository từ nhà cung cấp mới làm remote:

`git remote add <provider name> <provider-repository-url>`

Thay _<provider name>_ bằng tên nhà cung cấp bạn đã chọn (ví dụ: gitlab).  
Thay _<provider-repository-url>_ bằng URL của repository trên nhà cung cấp mới.

**3.     Đẩy repository local của bạn lên remote repository mới**

Lệnh này sẽ đẩy tất cả các nhánh và tags lên repository của nhà cung cấp mới. Tên nhà cung cấp phải khớp với tên nhà cung cấp từ bước 2.

`git push <provider name> --mirror`

**Lưu ý:**

- Remote repository nên trống.
- Remote repository có thể có nhánh bảo vệ không cho phép push mạnh. Trong trường hợp này, hãy vào repository nhà cung cấp mới và tắt bảo vệ nhánh để cho phép push mạnh.

**4.     Kiểm tra việc di chuyển**

Khi quá trình đẩy hoàn tất, hãy kiểm tra xem tất cả các file, nhánh, và tag đã được di chuyển thành công sang repository mới hay chưa. Bạn có thể làm điều này bằng cách duyệt repository trực tuyến hoặc clone nó về một vị trí khác và kiểm tra cục bộ.

**5.     Cập nhật URL Remote**

Nếu bạn có kế hoạch tiếp tục làm việc với repository đã di chuyển trên máy local, bạn có thể cập nhật URL remote để trỏ đến repository của nhà cung cấp mới thay vì AWS CodeCommit. Bạn có thể làm điều này bằng lệnh sau:

`git remote set-url origin <provider-repository-url>`

Thay _<provider-repository-url>_ bằng URL của repository trên nhà cung cấp mới.

**6.     Cập nhật CI/CD Pipelines và sửa nhánh bảo vệ**

Nếu bạn có các CI/CD pipeline tương tác với repository của mình, như GitLab, GitHub hoặc AWS CodePipeline, hãy cập nhật cấu hình của chúng để phản ánh URL repository mới. Nếu bạn đã xóa quyền bảo vệ nhánh trong bước 3, có thể bạn muốn thêm lại chúng cho nhánh chính.

**7.     Thông báo cho nhóm của bạn**

Nếu bạn đang di chuyển một repository mà người khác đang làm việc, hãy thông báo cho nhóm của bạn về việc di chuyển và cung cấp cho họ URL repository mới.

**8.     Xóa repository AWS CodeCommit đã di chuyển**

Hành động này không thể hoàn tác. Quay lại bảng điều khiển AWS CodeCommit và xóa repository đã di chuyển bằng nút "Delete Repository".

![](/images/4/2.png)