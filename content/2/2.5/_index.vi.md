---
title : "Provision an IAM user"
date :  "`r Sys.Date()`" 
weight : 5
chapter : false
pre : " <b> 2.5. </b> "
---

#### Provision an IAM user

1. Nếu bạn chưa có IAM user thì bạn sẽ tạo 1 IAM user.

![IAM user](/images/2/2.5/1.png)
![IAM user](/images/2/2.5/2.png)
![IAM user](/images/2/2.5/3.png)
![IAM user](/images/2/2.5/4.png)
![IAM user](/images/2/2.5/5.png)

2. Sau đó tải **Access key** về để sử dụng **CLI**

![IAM user](/images/2/2.5/6.png)
![IAM user](/images/2/2.5/7.png)
![IAM user](/images/2/2.5/8.png)
![IAM user](/images/2/2.5/9.png)

3. Sau đó chúng ta sẽ tạo **policy**.

![IAM user](/images/2/2.5/14.png)
![IAM user](/images/2/2.5/10.png)
![IAM user](/images/2/2.5/11.png)

4. Chúng ta sẽ cấu hình policy như sau:

```
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "CodeDeployAccessPolicy",
      "Effect": "Allow",
      "Action": [
        "autoscaling:*",
        "codedeploy:*",
        "ec2:*",
        "lambda:*",
        "ecs:*",
        "elasticloadbalancing:*",
        "iam:AddRoleToInstanceProfile",
        "iam:AttachRolePolicy",
        "iam:CreateInstanceProfile",
        "iam:CreateRole",
        "iam:DeleteInstanceProfile",
        "iam:DeleteRole",
        "iam:DeleteRolePolicy",
        "iam:GetInstanceProfile",
        "iam:GetRole",
        "iam:GetRolePolicy",
        "iam:ListInstanceProfilesForRole",
        "iam:ListRolePolicies",
        "iam:ListRoles",
        "iam:PutRolePolicy",
        "iam:RemoveRoleFromInstanceProfile",
        "s3:*",
        "ssm:*"
      ],
      "Resource": "*"
    },
    {
      "Sid": "CodeDeployRolePolicy",
      "Effect": "Allow",
      "Action": [
        "iam:PassRole"
      ],
      "Resource": "arn:aws:iam::account-ID:role/CodeDeployServiceRole"
    }
  ]
}
```

- Chọn **Review policy**

![IAM user](/images/2/2.5/12.png)

5. Kiểm tra lại và sau đó nhập tên policy, chọn **Create policy**

![IAM user](/images/2/2.5/13.png)