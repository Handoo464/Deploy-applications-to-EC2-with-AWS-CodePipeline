---
title : "Clean up resources"
date :  "`r Sys.Date()`" 
weight : 9
chapter : false
pre : " <b> 9. </b> "
---

#### Clean up resources

#### Terminate EC2 instance

- Access **EC2 Management Console**
- On the left navigation bar, select **Intances**
- Select **all EC2 Instance** related to the lab.
- Click **Actions**.
- Click **Manage Instance State**.
- Select **Terminate**.
- Click **Change State**

#### Delete Security Group

- Access **EC2 Management Console**
- On the left navigation bar, select **Security Groups**
- Select all **Security Groups** related to the lab.
- Click **Actions**.
- Click **Delete security groups**
- Click **Delete**

#### Remove AWS CodeBuild Project

[Delete AWS CodeBuild Project](https://docs.aws.amazon.com/codebuild/latest/userguide/delete-project.html)

#### Remove AWS CodePipeline

[Delete Pipeline](https://docs.aws.amazon.com/codepipeline/latest/userguide/pipelines-delete.html)
