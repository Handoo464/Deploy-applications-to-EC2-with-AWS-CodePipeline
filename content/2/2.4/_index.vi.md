---
title : "Tạo Service Role"
date :  "`r Sys.Date()`" 
weight : 4
chapter : false
pre : " <b> 2.4 </b> "
---

#### Tạo Service Role cho CodeDeploy

Để thực hiện các bài lab, chúng ta cần tạo **Service role** cho **CodeDeploy**

1. Truy cập vào **IAM**
    
    - Chọn **Create role**

![Service Role](/images/2/2.4/1.png)

2. Thực hiện cấu hình các bước tạo role
    
    - Chọn **AWS service**
    - Chọn **CodeDeploy**
    - Chọn **Next**

![Service Role](/images/2/2.4/2.png)

3. Chọn **Next**

![Service Role](/images/2/2.4/3.png)

4. Thực hiện nhập tên và tạo role
    
    - **Role name**, nhập **CodeDeployServiceRoleEC2**
    - Giữ nguyên phần mô tả.

![Service Role](/images/2/2.4/4.png)

5. Chọn **Create role**

![Service Role](/images/2/2.4/5.png)

6. Tạo role thành công.

![Service Role](/images/2/2.4/6.png)

7. Sau khi tạo role, chúng ta sẽ thực hiện chỉnh sửa **Trust relationships**

![Service Role](/images/2/2.4/7.png)

8. Thay bằng nội dung sau:

```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "",
            "Effect": "Allow",
            "Principal": {
                "Service": [
                    "codedeploy.us-east-2.amazonaws.com",
                    "codedeploy.us-east-1.amazonaws.com",
                    "codedeploy.us-west-1.amazonaws.com",
                    "codedeploy.us-west-2.amazonaws.com",
                    "codedeploy.eu-west-3.amazonaws.com",
                    "codedeploy.ca-central-1.amazonaws.com",
                    "codedeploy.eu-west-1.amazonaws.com",
                    "codedeploy.eu-west-2.amazonaws.com",
                    "codedeploy.eu-central-1.amazonaws.com",
                    "codedeploy.ap-east-1.amazonaws.com",
                    "codedeploy.ap-northeast-1.amazonaws.com",
                    "codedeploy.ap-northeast-2.amazonaws.com",
                    "codedeploy.ap-southeast-1.amazonaws.com",
                    "codedeploy.ap-southeast-2.amazonaws.com",
                    "codedeploy.ap-south-1.amazonaws.com",
                    "codedeploy.sa-east-1.amazonaws.com"
                ]
            },
            "Action": "sts:AssumeRole"
        }
    ]
}
```

- Chọn **Update policy**

![Service Role](/images/2/2.4/8.png)