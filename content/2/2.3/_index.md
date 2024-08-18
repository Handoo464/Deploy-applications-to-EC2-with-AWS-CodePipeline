---
title : "Create Git Connection"
date : "`r Sys.Date()`"
weight : 3
chapter : false
pre : " <b> 2.3. </b> "
---

## Tạo kết nối với GitHub (bảng điều khiển)

Bạn có thể sử dụng bảng điều khiển để tạo kết nối với GitHub.

###### Ghi

Hiện tại, nếu bạn sử dụng bảng điều khiển để tạo kết nối, điều này sẽ chỉ tạo tài nguyên có trong tài nguyên ARN. Để tạo tài nguyên có tiền tố dịch vụ trong ARN, hãy sử dụng CLI, SDK hoặc CFN. Tài nguyên có cả hai tiền tố dịch vụ sẽ vẫn hiển thị trong bảng điều khiển. Việc tạo tài nguyên bảng điều khiển sẽ có sẵn bắt đầu từ ngày 1 tháng 7 năm 2024.`codestar-connections``codeconnections`

1. Đăng nhập vào Bảng điều khiển quản lý AWS và mở bảng điều khiển Công cụ dành cho nhà phát triển tại [https://console.aws.amazon.com/codesuite/settings/connections](https://console.aws.amazon.com/codesuite/settings/connections).
    
2. Chọn **Thiết đặt > Kết nối**, sau đó chọn **Tạo kết nối**.
    
3. Để tạo kết nối với kho lưu trữ GitHub hoặc GitHub Enterprise Cloud, bên dưới **Chọn nhà cung cấp**, chọn **GitHub**. Trong **Tên kết nối**, nhập Tên cho kết nối mà bạn muốn tạo. Chọn **Kết nối với GitHub** và chuyển sang Bước 2.
    
    ![Ảnh chụp màn hình bảng điều khiển hiển thị tùy chọn kết nối được chọn cho GitHub.](https://docs.aws.amazon.com/images/dtconsole/latest/userguide/images/github-conn.png)
    

###### Để tạo kết nối với GitHub

1. Trong **cài đặt kết nối GitHub**, tên kết nối của bạn xuất hiện trong **Tên kết nối**. Chọn **Kết nối với GitHub**. Trang yêu cầu truy cập sẽ xuất hiện.
    
    ![Ảnh chụp màn hình bảng điều khiển hiển thị trang truy cập tài khoản GitHub.](https://docs.aws.amazon.com/images/dtconsole/latest/userguide/images/github-conn-access.png)
    
2. Chọn **Authorize AWS Connector for GitHub**. Các trang kết nối hiển thị và hiển thị trường **Ứng dụng GitHub**.
    
    ![Ảnh chụp màn hình bảng điều khiển hiển thị trang kết nối GitHub ban đầu với trường Ứng dụng GitHub.](https://docs.aws.amazon.com/images/dtconsole/latest/userguide/images/github-conn-access-app.png)
    
3. Trong **Ứng dụng GitHub**, chọn cài đặt ứng dụng hoặc chọn **Cài đặt ứng dụng mới** để tạo ứng dụng.
    
    Bạn cài đặt một ứng dụng cho tất cả các kết nối của bạn với một nhà cung cấp cụ thể. Nếu bạn đã cài đặt ứng dụng AWS Connector for GitHub, hãy chọn nó và bỏ qua bước này.
    
    ###### Ghi
    
    Nếu bạn muốn tạo một [Mã truy cập người dùng](https://docs.github.com/en/apps/creating-github-apps/authenticating-with-a-github-app/generating-a-user-access-token-for-a-github-app), đảm bảo rằng bạn đã cài đặt AWS Trình kết nối cho ứng dụng GitHub và sau đó để trống trường Cài đặt ứng dụng. CodeConnections sẽ sử dụng mã truy cập người dùng cho kết nối.
    
4. Trên trang Cài đặt **AWS Connector cho GitHub**, chọn tài khoản mà bạn muốn cài đặt ứng dụng.
    
    ![Ảnh chụp màn hình bảng điều khiển hiển thị trang cài đặt AWS Connector for GitHub.](https://docs.aws.amazon.com/images/dtconsole/latest/userguide/images/github-conn-access-app-install1.png)
    
    ###### Ghi
    
    Bạn chỉ cài đặt ứng dụng một lần cho mỗi tài khoản GitHub. Nếu trước đây bạn đã cài đặt ứng dụng, bạn có thể chọn **Cấu hình** tiến hành đến trang sửa đổi để cài đặt ứng dụng của bạn hoặc bạn có thể sử dụng mặt sau để quay lại bảng điều khiển.
    
5. Trên trang **Cài đặt AWS Connector cho GitHub**, hãy để lại nút mặc định và chọn **Cài đặt**.
    
    ![Ảnh chụp màn hình Bảng điều khiển hiển thị trang cài đặt AWS Connector cho GitHub thứ hai.](https://docs.aws.amazon.com/images/dtconsole/latest/userguide/images/github-conn-access-app-install2.png)
    
    Sau bước này, một trang quyền cập nhật có thể hiển thị trong GitHub.
    
6. Nếu một trang hiển thị hiển thị rằng có các quyền cập nhật cho AWS Trình kết nối cho ứng dụng GitHub, chọn **Chấp nhận mới quyền**.
    
    ![Ảnh chụp màn hình bảng điều khiển hiển thị trang quyền cập nhật AWS Connector for GitHub.](https://docs.aws.amazon.com/images/dtconsole/latest/userguide/images/accept-new-permissions.png)
    
7. Bạn được đưa trở lại trang **Connect to GitHub**. Các ID kết nối cho cài đặt mới của bạn xuất hiện trong **GitHub Ứng dụng**. Chọn **Kết nối**.
    

### Xem bạn đã tạo Kết nối

- Kết nối đã tạo sẽ hiển thị trong danh sách kết nối.
    
    ![Ảnh chụp màn hình bảng điều khiển hiển thị danh sách kết nối với kết nối được tạo thành công.](https://docs.aws.amazon.com/images/dtconsole/latest/userguide/images/connections-create-ghe-complete.png)