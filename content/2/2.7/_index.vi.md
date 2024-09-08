---
title : "Tạo instance profile"
date :  "`r Sys.Date()`" 
weight : 7
chapter : false
pre : " <b> 2.7. </b> "
---

#### Tạo instance profile

1. Chúng ta sẽ tạo IAM instance profile cho Amazon EC2 instance
    
    - Truy cập vào **IAM**
    - Chọn **Policies**
    - Chọn **Create policy**

![IAM user](/images/2/2.6/1.png)

2. Trong bước tạo **policy**, nhập nội dung policy

```
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": [
        "s3:Get*",
        "s3:List*"
      ],
      "Resource": [
        "arn:aws:s3:::replace-with-your-s3-bucket-name/*",
        "arn:aws:s3:::aws-codedeploy-us-east-2/*",
        "arn:aws:s3:::aws-codedeploy-us-east-1/*",
        "arn:aws:s3:::aws-codedeploy-us-west-1/*",
        "arn:aws:s3:::aws-codedeploy-us-west-2/*",
        "arn:aws:s3:::aws-codedeploy-ca-central-1/*",
        "arn:aws:s3:::aws-codedeploy-eu-west-1/*",
        "arn:aws:s3:::aws-codedeploy-eu-west-2/*",
        "arn:aws:s3:::aws-codedeploy-eu-west-3/*",
        "arn:aws:s3:::aws-codedeploy-eu-central-1/*",
        "arn:aws:s3:::aws-codedeploy-ap-east-1/*",
        "arn:aws:s3:::aws-codedeploy-ap-northeast-1/*",
        "arn:aws:s3:::aws-codedeploy-ap-northeast-2/*",
        "arn:aws:s3:::aws-codedeploy-ap-southeast-1/*",        
        "arn:aws:s3:::aws-codedeploy-ap-southeast-2/*",
        "arn:aws:s3:::aws-codedeploy-ap-south-1/*",
        "arn:aws:s3:::aws-codedeploy-sa-east-1/*"
      ]
    }
  ]
}
```

- Chọn **Next:Tags**

![IAM user](/images/2/2.7/2.png)

3. Chọn **Next:Review**

4. Nhập tên **policy** và chọn **Create policy**

![IAM user](/images/2/2.7/3.png)


5. Hoàn thành tạo policy.

![IAM user](/images/2/2.7/4.png)

6. Tiếp đến chúng ta sẽ tạo một role
    
    - Truy cập vào **IAM**
    - Chọn **Roles**
    - Chọn **Create role**

![IAM user](/images/2/2.7/5.png)

7. Chọn **AWS service** là **EC2**. Chọn **Next**

![IAM user](/images/2/2.7/5.png)

8. Tìm và chọn policy vừa tạo. Chọn **Next**

![IAM user](/images/2/2.7/6.png)
9. Nhập tên **role**

10. Chọn **Create role**

![IAM user](/images/2/2.7/7.png)

11. Hoàn thành tạo role.

![IAM user](/images/2/2.7/8.png)