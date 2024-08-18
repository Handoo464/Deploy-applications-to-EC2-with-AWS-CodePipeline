---
title : "Dọn dẹp tài nguyên"
date :  "`r Sys.Date()`" 
weight : 9
chapter : false
pre : " <b> 9. </b> "
---
#### Dọn dẹp tài nguyên

#### Terminate EC2 instance

- Access **EC2 Management Console**
- On the left navigation bar, select **Intances**
- Select **all EC2 Instance** related to the lab.
- Click **Actions**.
- Click **Manage Instance State**.
- Select **Terminate**.
- Click **Change State**

#### Delete DB Instance

- Access **RDS Management Console**
- On the left navigation bar, select **Databases**
- Select all **DB Instance** related to the lab.
- Click **Actions**.
- Click **Delete**
- Uncheck **Create final snapshot? and select I acknowledge that upon instance deletion, automated backups, including system snapshots and point-in-time recovery, will no longer be available**
- Type **delete me** in the empty box.
- Click **Delete**.

#### Delete Security Group

- Access **EC2 Management Console**
- On the left navigation bar, select **Security Groups**
- Select all **Security Groups** related to the lab.
- Click **Actions**.
- Click **Delete security groups**
- Click **Delete**

#### Xóa AWS CodeCommit Repository

[Xóa AWS CodeCommit Repository](https://docs.aws.amazon.com/codecommit/latest/userguide/how-to-delete-repository.html)

#### Xóa AWS CodeBuild Project

[Xóa AWS CodeBuild Project](https://docs.aws.amazon.com/codebuild/latest/userguide/delete-project.html)

#### Xóa AWS CodePipeline

[Xóa Pipeline](https://docs.aws.amazon.com/codepipeline/latest/userguide/pipelines-delete.html)