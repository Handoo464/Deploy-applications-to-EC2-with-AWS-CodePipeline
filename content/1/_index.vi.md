---
title : "Giới thiệu"
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
pre : " <b> 1. </b> "
---
#### Tổng quan

Nhiều tổ chức, công ty đã và đang chuyển sang thực hành DevOps, là sự kết hợp của các triết lý, thực tiễn và công cụ văn hóa nhằm tăng khả năng cung cấp ứng dụng và dịch vụ của tổ chức bạn ở tốc độ cao; ví dụ, phát triển và cải tiến sản phẩm với tốc độ nhanh hơn so với các tổ chức sử dụng quy trình quản lý cơ sở hạ tầng và phát triển phần mềm truyền thống.

![S3 bucket](https://000023.awsstudygroup.com/images/1.1-s3/0008.png?featherlight=false&width=90pc)

Một phần không thể thiếu của DevOps là áp dụng văn hóa tích hợp liên tục và phân phối / triển khai liên tục (CI / CD), trong đó cam kết hoặc thay đổi đối với mã đi qua các cổng giai đoạn tự động khác nhau, tất cả các cách từ xây dựng và thử nghiệm đến triển khai ứng dụng, từ phát triển đến môi trường sản xuất.

Bài lab này sử dụng bộ AWS của các dịch vụ CI / CD để biên dịch, xây dựng và cài đặt ứng dụng Nodejs được kiểm soát theo instance trên một tập hợp các Linux Amazon Elastic Compute Cloud (Amazon EC2) instance thông qua một đường dẫn hoàn toàn tự động và an toàn. Mục tiêu là thúc đẩy cam kết hoặc thay đổi mã để vượt qua các cổng giai đoạn tự động khác nhau từ môi trường phát triển đến sản xuất, trên các tài khoản AWS.

![S3 bucket](https://000023.awsstudygroup.com/images/architecture-1.png?featherlight=false&width=60pc)