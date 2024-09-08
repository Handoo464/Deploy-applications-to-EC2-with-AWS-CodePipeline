---
title : "Deploy applications to EC2 with AWS CodePipeline"
date :  "`r Sys.Date()`" 
weight : 1
chapter : false
---

Many organizations and companies have turned to DevOps practices, a combination of philosophies, practices, and cultural tools to increase your organization’s ability to deliver applications and services at high speed. ; for example, develop and improve products at a faster rate than organizations using traditional software development and infrastructure management processes.

![S3 bucket](https://000023.awsstudygroup.com/images/1.1-s3/0008.png?featherlight=false&width=90pc)

An integral part of DevOps is adopting a culture of continuous integration and continuous delivery/deployment (CI/CD), where commits or changes to code pass through various automated phase gates. , all the way from building and testing to application deployment, from development to production environments.

This lab uses the AWS suite of CI/CD services to compile, build, and install an instance-controlled Nodejs application on a set of Linux Amazon Elastic Compute Cloud (Amazon EC2) instances over a single pipeline. Fully automatic and safe guide. The goal is to drive commits or code changes to pass through various automated stage gates from development to production environments, across AWS accounts.

![S3 bucket](https://000023.awsstudygroup.com/images/architecture-1.png?featherlight=false&width=60pc)

- **AWS CodeCommit** – A fully-managed source control service that hosts secure Git-based repositories. CodeCommit makes it easy for teams to collaborate on code in a secure and highly scalable ecosystem. This solution uses CodeCommit to create a repository to store the application and deployment codes. AWS CodeBuild – A fully managed continuous integration service that compiles source code, runs tests, and produces software packages that are ready to deploy, on a dynamically created build server. This solution uses CodeBuild to build and test the code, which we deploy later.
- **AWS CodeDeploy** – A fully managed deployment service that automates software deployments to a variety of compute services such as Amazon EC2, AWS Fargate, AWS Lambda, and your on-premises servers. This solution uses CodeDeploy to deploy the code or application onto a set of EC2 instances running CodeDeploy agents.
- **AWS CodePipeline** – A fully managed continuous delivery service that helps you automate your release pipelines for fast and reliable application and infrastructure updates. This solution uses CodePipeline to create an end-to-end pipeline that fetches the application code from CodeCommit, builds and tests using CodeBuild, and finally deploys using CodeDeploy.
- **AWS CloudWatch Events** – An AWS CloudWatch Events rule is created to trigger the CodePipeline on a Git commit to the CodeCommit repository.
- **Amazon Simple Storage Service (Amazon S3)** – An object storage service that offers industry-leading scalability, data availability, security, and performance. This solution uses an S3 bucket to store the build and deployment artifacts created during the pipeline run.
- **AWS Key Management Service (AWS KMS**) – AWS KMS makes it easy for you to create and manage cryptographic keys and control their use across a wide range of AWS services and in your applications. This solution uses AWS KMS to make sure that the build and deployment artifacts stored on the S3 bucket are encrypted at rest.

#### Main content

1. [Introduction](https://000023.awsstudygroup.com/1-introduce/)
2. [Preparation steps](https://000023.awsstudygroup.com/2-prerequiste/)
3. [CodeDeploy Agent](https://000023.awsstudygroup.com/3-codedeployagent/)
4. [AWS CodeCommit](https://000023.awsstudygroup.com/4-codecommit/)
5. [AWS CodeBuild](https://000023.awsstudygroup.com/5-codebuild/)
6. [AWS CodeDeploy](https://000023.awsstudygroup.com/6-codedeloy/)
7. [AWS CodePipeline](https://000023.awsstudygroup.com/7-codepipeline/)
8. [Troubleshooting](https://000023.awsstudygroup.com/8-troubleshoot/)
9. [Resource Cleanup](https://000023.awsstudygroup.com/9-cleanup/)