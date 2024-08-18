---
title : "CodeDeploy Agent"
date :  "`r Sys.Date()`" 
weight : 3 
chapter : false
pre : " <b> 3. </b> "
---

#### CodeDeploy Agent (Session Manager)

Chúng ta sẽ cài đặt **CodeDeploy Agent**

1. Truy cập vào **EC2**
    
    - Chọn **EC2** mà bạn muốn triển khai ứng dụng.
    - Chọn **Connect**

![CodeDeploy Agent](https://000023.awsstudygroup.com/images/3.2-codedeployagent/0001.png?featherlight=false&width=90pc)

2. Sau đó, chúng ta sẽ chuyển đến giao diện connect.

![CodeDeploy Agent](https://000023.awsstudygroup.com/images/3.2-codedeployagent/0002.png?featherlight=false&width=90pc)

3. Thực hiện các lệnh sau đê cài đặt **CodeDeploy Agent**

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

![CodeDeploy Agent](https://000023.awsstudygroup.com/images/3.2-codedeployagent/0003.png?featherlight=false&width=90pc)

4. Hoàn thành cài **CodeDeploy Agent**

![CodeDeploy Agent](https://000023.awsstudygroup.com/images/3.2-codedeployagent/0004.png?featherlight=false&width=90pc)

#### CodeDeploy Agent (Add User Data Cho EC2)

1. Từ khi bắt đầu tạo EC2 Instance bạn có thể thực hiện add user data để tạo CodeDeploy Agent. Nhấn thả Advanced details
![CodeDeploy Agent](/images/3/2.png)

1. Nếu muốn bạn có thể thêm IAM Role ngay ở bước này
![CodeDeploy Agent](/images/3/3.png)
1. Thực hiện thêm User data
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