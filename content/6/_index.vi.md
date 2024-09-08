---
title : "AWS CodeDeploy"
date :  "`r Sys.Date()`" 
weight : 6 
chapter : false
pre : " <b> 6. </b> "
---
#### AWS CodeDeploy

1. Truy cập vào **AWS CodeDeploy**
    
    - Chọn **Create application**

![CodeBuild](/images/6/6.png)

2. Trong giao diện **Create application**
    
    - Đối với **Application name**, nhập **AWS-FCJ-APP**
    - Đối với **Compute platform**, chúng ta sẽ chọn **EC2/On-Premises**

![CodeBuild](/images/6/7.png)

3. Chúng ta sẽ tạo **Deployment groups** để thực hiện deployment ứng dụng.

![CodeBuild](/images/6/8.png)

4. Thực hiện cấu hình **Deployment group**
    
    - Nhập **Deployment group name**
    - Nhập **Service role**

![CodeBuild](/images/6/9.png)

5. Đối với **Deployment type**
    
    - Chúng ta sẽ chọn **In-place**
    - Đối với môi trường triển khai là **Amazon EC2 instances**
    - Chọn theo tag group, chọn các key và value phù hợp với **EC2** mà bạn muốn dùng triển khai ứng dụng.

![CodeBuild](/images/6/10.png)

6. Đối với cài đặt **Install AWS CodeDeploy Agent**
    
    - Chúng ta sẽ chọn **Nerver**
    - Đối với **Deployment settings**, chọn **CodeDeployDefault.OneAtATime**
    - Chọn **Create deployment group**

![CodeBuild](/images/6/11.png)

7. Hoàn thành tạo **Deployment group**

![CodeBuild](/images/6/12.png)

8. Chúng ta sẽ quay lại **Applications**
    
    - Chọn ứng dụng đã chuẩn bị.
    - Chọn **Deploy application**

![CodeBuild](/images/6/13.png)

9. Chúng ta sẽ cung cấp các thông tin **Create deployment**
    
    - Sử dụng **Deployment group**
    - Chọn **Revision type**
    - Và đối với **Revision location** chọn dẫn của **S3 bucket**
    - Dạng file sẽ là **.zip**

![CodeBuild](/images/6/14.png)

10. Kiểm tra lại và chọn **Create deployment**

![CodeBuild](/images/6/15.png)

11. Sau thời gian khoảng 5 phút.

- Chúng ta sẽ hoàn thành deployment.

![CodeBuild](/images/6/1.png)

12. Chúng ta sẽ xem lịch sử triển khai.

![CodeBuild](/images/6/2.png)

13. Truy cập vào ứng dụng qua **DNS** của **EC2** thông qua port 5000.

![CodeBuild](/images/6/3.png)
![CodeBuild](/images/6/4.png)

{{%notice tip%}}
Hãy nhớ truy cập đường dẫn với http chứ không phải https
{{%/notice%}}
![CodeBuild](/images/6/5.png)