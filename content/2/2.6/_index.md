---
title : "Provision an IAM user"
date :  "`r Sys.Date()`" 
weight : 6
chapter : false
pre : " <b> 2.6. </b> "
---

#### Provision an IAM user

1. If you do not have an IAM user, you will create an IAM user.

![IAM user](/images/2/2.5/1.png)
![IAM user](/images/2/2.5/2.png)
![IAM user](/images/2/2.5/3.png)
![IAM user](/images/2/2.5/4.png)
![IAM user](/images/2/2.5/5.png)

2. Then download **Access key** to use **CLI**
![IAM user](/images/2/2.5/6.png)
![IAM user](/images/2/2.5/7.png)
![IAM user](/images/2/2.5/8.png)
![IAM user](/images/2/2.5/9.png)



3. Then we will create **policy**.

![IAM user](/images/2/2.5/14.png)
![IAM user](/images/2/2.5/10.png)
![IAM user](/images/2/2.5/11.png)

4. We will configure the policy as follows:

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

- Select **Review policy**

![IAM user](/images/2/2.5/12.png)

5. Check again and then enter the policy name, select **Create policy**

![IAM user](/images/2/2.5/13.png)