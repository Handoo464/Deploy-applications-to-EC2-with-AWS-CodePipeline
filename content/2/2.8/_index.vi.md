---
title : "Gán role"
date : "`r Sys.Date()`"
weight : 8
chapter : false
pre : " <b> 2.8. </b> "
---

#### Gán role

Chúng ta sẽ thực hiện gán role cho EC2 instance.

1. Truy cập vào **EC2**
    
    - Chọn **EC2** mà bạn sử dụng để triển khai ứng dụng
    - Chọn **Actions**
    - Chọn **Security**

![Attach IAM role](/images/2/2.8/0001.png)


2. Tiếp theo chúng ta sẽ chọn **Modify IAM role**

![Attach IAM role](/images/2/2.8/0002.png)

3. Trong bước **Modify IAM role**

- Chọn **CodeDeploy-EC2-Instance-Profile**

![Attach IAM role](/images/2/2.8/0003.png)

4. Chọn **Update IAM role**

![Attach IAM role](/images/2/2.8/0004.png)