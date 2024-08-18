---
title : "Gán role"
date : "`r Sys.Date()`"
weight : 7
chapter : false
pre : " <b> 2.7 </b> "
---

#### Gán role

Chúng ta sẽ thực hiện gán role cho EC2 instance.

1. Truy cập vào **EC2**
    
    - Chọn **EC2** mà bạn sử dụng để triển khai ứng dụng
    - Chọn **Actions**
    - Chọn **Security**

![Attach IAM role](https://000023.awsstudygroup.com/images/2.2-attachrole/0001.png?featherlight=false&width=90pc)

2. Tiếp theo chúng ta sẽ chọn **Modify IAM role**

![Attach IAM role](https://000023.awsstudygroup.com/images/2.2-attachrole/0002.png?featherlight=false&width=90pc)

3. Trong bước **Modify IAM role**

- Chọn **CodeDeploy-EC2-Instance-Profile**

![Attach IAM role](https://000023.awsstudygroup.com/images/2.2-attachrole/0003.png?featherlight=false&width=90pc)

4. Chọn **Update IAM role**

![Attach IAM role](https://000023.awsstudygroup.com/images/2.2-attachrole/0004.png?featherlight=false&width=90pc)