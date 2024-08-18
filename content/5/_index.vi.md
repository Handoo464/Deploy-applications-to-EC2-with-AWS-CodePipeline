---
title : "AWS CodeBuild"
date :  "`r Sys.Date()`" 
weight : 5 
chapter : false
pre : " <b> 5. </b> "
---

#### AWS CodeBuild

1. Truy cập vào **AWS CodeBuild**
    
    - Chọn **Create project**

![CodeBuild](https://000023.awsstudygroup.com/images/5-codebuild/0001.png?featherlight=false&width=90pc)

2. Trong giao diện **Create build project**

- **Project name**, nhập **AWS-FCJ-APP**

![CodeBuild](https://000023.awsstudygroup.com/images/5-codebuild/0002.png?featherlight=false&width=90pc)

3. Cấu hình _Source_*
{{%notice info%}}
Demo code này mang tính chất đơn giản cho bạn hiểu rõ những thứ cần thiết cho quá trình build, deploy.
{{%/notice%}}
    
    - Chọn **Source provider** là **Github**
    - Chọn **Repository** là **PIPELINE**
    - Chọn **Branch**
    - Chọn **main**

![CodeBuild](/images/5/1.png)

4. Đối với **Environment**
    
    - Chọn **Managed image**
    - Chọn **Operating system** là **Amazon Linux 2**
    - Chọn **Run time** là **Standard**
    - Chọn **Image**
    - Chọn kiểu môi trường là **Linux**
    - Tick chọn vào **Enable** Privileged.

![CodeBuild](https://000023.awsstudygroup.com/images/5-codebuild/0004.png?featherlight=false&width=90pc)

5. Tạo Service role hoặc chọn **Service role** bạn đã tạo.

![CodeBuild](https://000023.awsstudygroup.com/images/5-codebuild/0005.png?featherlight=false&width=90pc)

6. Tiếp theo, chúng ta sẽ cấu hình dường đường dẫn **Buildspec**

![CodeBuild](https://000023.awsstudygroup.com/images/5-codebuild/0006.png?featherlight=false&width=90pc)

7. Đối với **Artifact**
    
    - Chúng ta chọn lưu trữ tại **S3**
    - Chọn **bucket** đã tạo.

![CodeBuild](https://000023.awsstudygroup.com/images/5-codebuild/0007.png?featherlight=false&width=90pc)

8. Đối với **Logs**
    
    - Chúng ta sử dụng **CloudWatch logs**
    - Group name: **aws-cicd-ec2-group**
    - Stream name: **aws-cicd-ec2-stream**

![CodeBuild](https://000023.awsstudygroup.com/images/5-codebuild/0008.png?featherlight=false&width=90pc)

9. Chúng ta đã tạo thành công **AWS CodeBuild project**. Để kiểm tra cấu hình đã đúng, thử **Start build**

![CodeBuild](https://000023.awsstudygroup.com/images/5-codebuild/0009.png?featherlight=false&width=90pc)

10. Đợi khoảng 5 phút sau, chọn **Phase details** để xem quá trình build project.

![CodeBuild](/images/5/2.png)