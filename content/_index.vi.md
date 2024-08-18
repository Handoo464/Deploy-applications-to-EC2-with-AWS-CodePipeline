---
title : "Triển khai ứng dụng lên EC2 với AWS CodePipeline"
date :  "`r Sys.Date()`" 
weight : 1
chapter : false
---
# Triển khai ứng dụng lên EC2 với AWS CodePipeline

Nhiều tổ chức, công ty đã và đang chuyển sang thực hành DevOps, là sự kết hợp của các triết lý, thực tiễn và công cụ văn hóa nhằm tăng khả năng cung cấp ứng dụng và dịch vụ của tổ chức bạn ở tốc độ cao; ví dụ, phát triển và cải tiến sản phẩm với tốc độ nhanh hơn so với các tổ chức sử dụng quy trình quản lý cơ sở hạ tầng và phát triển phần mềm truyền thống.

![S3 bucket](https://000023.awsstudygroup.com/images/1.1-s3/0008.png?featherlight=false&width=90pc)

Một phần không thể thiếu của DevOps là áp dụng văn hóa tích hợp liên tục và phân phối / triển khai liên tục (CI / CD), trong đó cam kết hoặc thay đổi đối với mã đi qua các cổng giai đoạn tự động khác nhau, tất cả các cách từ xây dựng và thử nghiệm đến triển khai ứng dụng, từ phát triển đến môi trường sản xuất.

Bài lab này sử dụng bộ AWS của các dịch vụ CI / CD để biên dịch, xây dựng và cài đặt ứng dụng Nodejs được kiểm soát theo instance trên một tập hợp các Linux Amazon Elastic Compute Cloud (Amazon EC2) instance thông qua một đường dẫn hoàn toàn tự động và an toàn. Mục tiêu là thúc đẩy cam kết hoặc thay đổi mã để vượt qua các cổng giai đoạn tự động khác nhau từ môi trường phát triển đến sản xuất, trên các tài khoản AWS.

![S3 bucket](https://000023.awsstudygroup.com/images/architecture-1.png?featherlight=false&width=60pc)

#### AWS CodeCommit

- Dịch vụ kiểm soát nguồn được quản lý đầy đủ lưu trữ các kho lưu trữ dựa trên Git an toàn. CodeCommit giúp các nhóm dễ dàng cộng tác trên mã trong một hệ sinh thái an toàn và có khả năng mở rộng cao. Giải pháp này sử dụng CodeCommit để tạo kho lưu trữ ứng dụng và mã triển khai.

#### AWS CodeBuild

- Một dịch vụ tích hợp liên tục được quản lý đầy đủ giúp biên dịch mã nguồn, chạy thử nghiệm và sản xuất các gói phần mềm sẵn sàng triển khai trên một máy chủ xây dựng được tạo động. Giải pháp này sử dụng CodeBuild để xây dựng và kiểm tra mã mà chúng tôi triển khai sau này.

#### AWS CodeDeploy

- Dịch vụ triển khai được quản lý hoàn toàn tự động hóa việc triển khai phần mềm cho nhiều dịch vụ tính toán khác nhau như Amazon EC2, AWS Fargate, AWS Lambda và các máy chủ tại chỗ của bạn. Giải pháp này sử dụng CodeDeploy để triển khai mã hoặc ứng dụng trên một tập hợp các phiên bản EC2 đang chạy các tác nhân CodeDeploy.

#### AWS CodePipeline

- Dịch vụ phân phối liên tục được quản lý hoàn toàn giúp bạn tự động hóa các đường dẫn phát hành của mình để cập nhật cơ sở hạ tầng và ứng dụng nhanh chóng và đáng tin cậy. Giải pháp này sử dụng CodePipeline để tạo một đường dẫn end-to-end tìm nạp mã ứng dụng từ CodeCommit, xây dựng và thử nghiệm bằng CodeBuild và cuối cùng triển khai bằng CodeDeploy.

#### AWS CloudWatch Events

- Quy tắc AWS CloudWatch Events được tạo để kích hoạt CodePipeline trên Git cam kết đối với kho lưu trữ CodeCommit.

#### Dịch vụ lưu trữ đơn giản của Amazon (Amazon S3)

- Dịch vụ lưu trữ đối tượng cung cấp khả năng mở rộng, tính khả dụng của dữ liệu, bảo mật và hiệu suất hàng đầu trong ngành. Giải pháp này sử dụng một thùng S3 để lưu trữ các tạo tác xây dựng và triển khai được tạo trong quá trình chạy đường ống.

#### Dịch vụ quản lý khóa AWS (AWS KMS)

- AWS KMS giúp bạn dễ dàng tạo và quản lý các khóa mật mã cũng như kiểm soát việc sử dụng chúng trên nhiều loại dịch vụ AWS và trong các ứng dụng của bạn. Giải pháp này sử dụng AWS KMS để đảm bảo rằng các tạo tác xây dựng và triển khai được lưu trữ trên nhóm S3 được mã hóa ở trạng thái nghỉ.

#### Nội dung chính

1. [Giới thiệu](https://000023.awsstudygroup.com/vi/1-introduce/)
2. [Các bước chuẩn bị](https://000023.awsstudygroup.com/vi/2-prerequiste/)
3. [CodeDeploy Agent](https://000023.awsstudygroup.com/vi/3-codedeployagent/)
4. [AWS CodeCommit](https://000023.awsstudygroup.com/vi/4-codecommit/)
5. [AWS CodeBuild](https://000023.awsstudygroup.com/vi/5-codebuild/)
6. [AWS CodeDeploy](https://000023.awsstudygroup.com/vi/6-codedeloy/)
7. [AWS CodePipeline](https://000023.awsstudygroup.com/vi/7-codepipeline/)
8. [Khắc phục lỗi](https://000023.awsstudygroup.com/vi/8-troubleshoot/)
9. [Dọn dẹp tài nguyên](https://000023.awsstudygroup.com/vi/9-cleanup/)