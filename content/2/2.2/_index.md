---
title : "Create S3 bucket"
date : "`r Sys.Date()`"
weight : 2
chapter : false
pre : " <b> 2.2 </b> "
---

#### Create S3 bucket

1. Prepare an S3 bucket to store build artifact
    
    - Go to **S3** page
    - Select **Bucket**
    - Select **Create bucket**

![S3 bucket](/images/2/1.png)
![S3 bucket](/images/2/2.png)

2. In the **Create bucket** interface
    
    - Enter **Bucket name**
    - Select **Region**

![S3 bucket](https://000023.awsstudygroup.com/images/1.1-s3/0002.png?featherlight=false&width=90pc)

3. Uncheck **Block Public Access**

![S3 bucket](https://000023.awsstudygroup.com/images/1.1-s3/0003.png?featherlight=false&width=90pc)

4. Check again and select **Create bucket**

![S3 bucket](https://000023.awsstudygroup.com/images/1.1-s3/0004.png?featherlight=false&width=90pc)

5. After creating the bucket successfully.
    
    - Select the bucket and select **Permissions**
    - Scroll down and select **Edit** Bucket policy.

![S3 bucket](/images/2/5.png)

6. Fill in the policy content.

```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "ListObjectsInBucket",
            "Effect": "Allow",
            "Principal": "*",
            "Action": "s3:ListBucket",
            "Resource": "arn:aws:s3:::aws-cicd-ec2"
        },
        {
            "Sid": "AllObjectActions",
            "Effect": "Allow",
            "Principal": "*",
            "Action": "s3:*Object*",
            "Resource": "arn:aws:s3:::aws-cicd-ec2/*"
        }
    ]
}
```

![S3 bucket](https://000023.awsstudygroup.com/images/1.1-s3/0006.png?featherlight=false&width=90pc)

7. Then we will see that the S3 bucket is public.

![S3 bucket](/images/2/7.png)