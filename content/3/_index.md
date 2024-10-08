---
title : "CodeDeploy Agent"
date : "`r Sys.Date()`"
weight : 3
chapter : false
pre : " <b> 3. </b> "
---

#### CodeDeploy Agent (Session Manager)

We will install **CodeDeploy Agent**

You have 2 ways to configure the CodeDeploy Agent for your EC2:

- Session Manager
- Add User Data

1. Access to **EC2**
    
    - Select **EC2** to which you want to deploy the application.
    - Select **Connect**

![CodeDeploy Agent](/images/3/5.png)

2. Then we will move to the connecting interface.

![CodeDeploy Agent](/images/3/6.png)

3. Execute the following commands to install **CodeDeploy Agent**

```
REGION=$(curl 169.254.169.254/latest/meta-data/placement/availability-zone/ | sed 's/[a-z]$//') &&

sudo yum update -y &&

sudo yum install -y python-pip &&

sudo yum install -y ruby &&

sudo yum install -y wget &&

cd /home/ec2-user

wget https://aws-codedeploy-$REGION.s3.amazonaws.com/latest/install &&

chmod +x ./install &&

sudo ./install auto &&

sudo yum remove -y wget &&

sudo service codedeploy-agent start
```

![CodeDeploy Agent](/images/3/7.png)

4. Complete installation of **CodeDeploy Agent**

![CodeDeploy Agent](/images/3/8.png)

#### CodeDeploy Agent (Add User Data For EC2)

1. When creating an EC2 Instance, you can add user data to install the CodeDeploy Agent. Click on "Advanced details."
![CodeDeploy Agent](/images/3/2.png)
1. If you want, you can also add an IAM Role at this step.
![CodeDeploy Agent](/images/3/3.png)
1. Proceed to add User data.
```
#!/bin/bash
yum -y update
yum install -y ruby
yum install -y aws-cli
cd /home/ec2-user
https://aws-codedeploy-us-east-1.s3.us-east-1.amazonaws.com/latest/install
wget chmod +x ./scripts/*
./install auto
```
![CodeDeploy Agent](/images/3/4.png)
