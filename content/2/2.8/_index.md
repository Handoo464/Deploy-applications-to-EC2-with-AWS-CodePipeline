---
title : "Attach role"
date : "`r Sys.Date()`"
weight : 8
chapter : false
pre : " <b> 2.8. </b> "
---

#### Attach roles

We will perform role assignment to EC2 instance.

1. Access to **EC2**
    
    - Select **EC2** which you use to deploy the application
    - Select **Actions**
    - Select **Security**

![Attach IAM role](/images/2/2.8/0001.png)

2. Next we will choose **Modify IAM role**

![Attach IAM role](/images/2/2.8/0002.png)

3. In **Modify IAM role** step

- Select **CodeDeploy-EC2-Instance-Profile**

![Attach IAM role](/images/2/2.8/0003.png)

4. Select **Update IAM role**

![Attach IAM role](/images/2/2.8/0004.png)