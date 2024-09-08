---
title : "Dọn dẹp tài nguyên"
date :  "`r Sys.Date()`" 
weight : 9
chapter : false
pre : " <b> 9. </b> "
---

### Dọn dẹp tài nguyên

#### Terminate EC2 instance

- Truy cập vào **EC2 Management Console**
- Ở thanh điều hướng bên trái, chọn **Instances**
- Chọn **tất cả các EC2 Instance** liên quan đến lab.
- Nhấn **Actions**.
- Nhấn **Manage Instance State**.
- Chọn **Terminate**.
- Nhấn **Change State**.

#### Delete DB Instance

- Truy cập vào **RDS Management Console**
- Ở thanh điều hướng bên trái, chọn **Databases**
- Chọn tất cả **DB Instance** liên quan đến lab.
- Nhấn **Actions**.
- Nhấn **Delete**.
- Bỏ chọn **Create final snapshot?** và chọn **I acknowledge that upon instance deletion, automated backups, including system snapshots and point-in-time recovery, will no longer be available**.
- Nhập **delete me** vào ô trống.
- Nhấn **Delete**.

#### Delete Security Group

- Truy cập vào **EC2 Management Console**
- Ở thanh điều hướng bên trái, chọn **Security Groups**.
- Chọn tất cả **Security Groups** liên quan đến lab.
- Nhấn **Actions**.
- Nhấn **Delete security groups**.
- Nhấn **Delete**.

#### Xóa AWS CodeCommit Repository

[Xóa AWS CodeCommit Repository](https://docs.aws.amazon.com/codecommit/latest/userguide/how-to-delete-repository.html)

#### Xóa AWS CodeBuild Project

[Xóa AWS CodeBuild Project](https://docs.aws.amazon.com/codebuild/latest/userguide/delete-project.html)

#### Xóa AWS CodePipeline

[Xóa Pipeline](https://docs.aws.amazon.com/codepipeline/latest/userguide/pipelines-delete.html)