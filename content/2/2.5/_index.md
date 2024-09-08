---
title : "Create Service Role"
date :  "`r Sys.Date()`" 
weight : 5.
chapter : false
pre : " <b> 2.5. </b> "
---

#### Create Service Role for CodeDeploy

To do the labs, we need to create **Service role** for **CodeDeploy**

1. Access to **IAM**
    
    - Select **Create role**

![Service Role](/images/2/2.4/1.png)

2. Configure the role creation steps
    
    - Select **AWS service**
    - Select **CodeDeploy**
    - Select **Next**

![Service Role](/images/2/2.4/2.png)

3. Select **Next**

![Service Role](/images/2/2.4/3.png)

4. Enter a name and create a role
    
    - **Role name**, enter **CodeDeployServiceRoleEC2**
    - Keep the description intact.

![Service Role](/images/2/2.4/4.png)

5. Select **Create role**

![Service Role](/images/2/2.4/5.png)

6. Create a successful role.

![Service Role](/images/2/2.4/6.png)

7. After creating the role, we will edit **Trust relationships**

![Service Role](/images/2/2.4/7.png)

8. Replace with the following content:

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

- Select **Update policy**

![Service Role](/images/2/2.4/8.png)