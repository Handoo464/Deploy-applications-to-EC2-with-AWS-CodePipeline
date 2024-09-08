---
title : "Tạo S3 bucket"
date :  "`r Sys.Date()`" 
weight : 2 
chapter : false
pre : " <b> 2.2 </b> "
---

#### Tạo S3 bucket

1. Chuẩn bị một S3 bucket để lưu trữ build artifact
    
    - Truy cập vào trang **S3**
    - Chọn **Bucket**
    - Chọn **Create bucket**

![S3 bucket](/images/2/1.png)
![S3 bucket](/images/2/2.png)

2. Trong giao diện **Create bucket**
    
    - Nhập **Bucket name**
    - Chọn **Region**

![S3 bucket](/images/2/1.png)

3. Bỏ chọn **Block Public Access**

![S3 bucket](/images/2/2.png)

4. Kiểm tra lại và chọn **Create bucket**

![S3 bucket](/images/2/2.2/3.png)

5. Sau khi tạo bucket thành công.
    
    - Chọn bucket và chọn **Permissions**
    - Kéo xuống và chọn **Edit** Bucket policy.

![S3 bucket](/images/2/5.png)

6. Thực hiện điền nội dung policy.

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

![S3 bucket](/images/2/2.2/4.png)

7. Sau đó chúng ta sẽ thấy S3 bucket được public.

![S3 bucket](/images/2/7.png)