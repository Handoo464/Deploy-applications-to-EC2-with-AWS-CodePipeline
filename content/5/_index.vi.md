---
title : "AWS CodeBuild"
date :  "`r Sys.Date()`" 
weight : 5 
chapter : false
pre : " <b> 5. </b> "
---

Chúng tôi sẽ sử dụng repository **[AWS First Cloud Journey](https://github.com/Handoo464/PIPELINE)** này cho demo. Bạn có thể tải lên github của bạn để sử dụng cho các bước thực hiện tiếp theo khi cần sử dụng kết nối với GitHub.

#### AWS CodeBuild

1. Truy cập vào **AWS CodeBuild**
    
    - Chọn **Create project**

![CodeBuild](/images/5/3.png)

2. Trong giao diện **Create build project**

- **Project name**, nhập **AWS-FCJ-APP**

![CodeBuild](/images/5/4.png)

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

![CodeBuild](/images/5/5.png)

5. Tạo Service role hoặc chọn **Service role** bạn đã tạo.

![CodeBuild](/images/5/6.png)

6. Tiếp theo, chúng ta sẽ cấu hình dường đường dẫn **Buildspec**

![CodeBuild](/images/5/7.png)

7. Đối với **Artifact**
    
    - Chúng ta chọn lưu trữ tại **S3**
    - Chọn **bucket** đã tạo.

![CodeBuild](/images/5/8.png)

8. Đối với **Logs**
    
    - Chúng ta sử dụng **CloudWatch logs**
    - Group name: **aws-cicd-ec2-group**
    - Stream name: **aws-cicd-ec2-stream**

![CodeBuild](/images/5/9.png)

9. Chúng ta đã tạo thành công **AWS CodeBuild project**. Để kiểm tra cấu hình đã đúng, thử **Start build**

![CodeBuild](/images/5/10.png)

10. Đợi khoảng 5 phút sau, chọn **Phase details** để xem quá trình build project.

![CodeBuild](/images/5/2.png)