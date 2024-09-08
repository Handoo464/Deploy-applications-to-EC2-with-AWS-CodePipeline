---
title : "Create instance profile"
date : "`r Sys.Date()`"
weight : 7
chapter : false
pre : " <b> 2.7. </b> "
---

#### Create instance profile

1. We will create IAM instance profile for Amazon EC2 instance
    
    - Access to **IAM**
    - Select **Policies**
    - Select **Create policy**

![IAM user](/images/2/2.7/1.png)

2. In the step of creating **policy**, enter the content policy

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
      "Resources": [
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

- Select **Next:Tags**

![IAM user](/images/2/2.7/2.png)

3. Select **Next:Review**

4. Enter **policy** and select **Create policy**

![IAM user](/images/2/2.7/3.png)
5. Complete policy creation.

![IAM user](/images/2/2.7/4.png)
6. Next we will create a role
    
    - Access to **IAM**
    - Select **Roles**
    - Select **Create role**

![IAM user](/images/2/2.7/4.png)

7. Select **AWS service** as **EC2**. Select **Next**

![IAM user](/images/2/2.7/5.png)

8. Find and select the newly created policy. Select **Next**

![IAM user](/images/2/2.7/6.png)

9. Enter the name **role**

10. Select **Create role**

![IAM user](/images/2/2.7/7.png)

11. Complete role creation.

![IAM user](/images/2/2.7/8.png)