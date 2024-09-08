---
title : "AWS CodeBuild"
date :  "`r Sys.Date()`" 
weight : 5 
chapter : false
pre : " <b> 5. </b> "
---

We will use the **[AWS First Cloud Journey](https://github.com/Handoo464/PIPELINE)** repository for this demo. You can upload it to your own GitHub repository for use in the following steps when connecting with GitHub is required.

### AWS CodeBuild Setup

1. **Access AWS CodeBuild**

    - Click on **Create project**

![CodeBuild](/images/5/3.png)

2. In the **Create build project** interface

- For **Project name**, enter **AWS-FCJ-APP**

![CodeBuild](/images/5/4.png)

3. Configure the **Source**

{{%notice info%}}
This demo code is simplified to help you understand the essentials of the build and deploy process.
{{%/notice%}}
    
    - Select **Source provider** as **GitHub**
    - Choose **Repository** as **PIPELINE**
    - Choose **Branch**
    - Select **main**

![CodeBuild](/images/5/1.png)

4. For the **Environment**

    - Select **Managed image**
    - Choose **Operating system** as **Amazon Linux 2**
    - Select **Run time** as **Standard**
    - Choose **Image**
    - Set the environment type to **Linux**
    - Check **Enable** Privileged mode.

![CodeBuild](/images/5/5.png)

5. Create a Service role or select an existing **Service role** that you have already created.

![CodeBuild](/images/5/6.png)

6. Next, we will configure the **Buildspec** path.

![CodeBuild](/images/5/7.png)

7. For the **Artifact**

    - We will store it in **S3**
    - Select the **bucket** that you have created.

![CodeBuild](/images/5/8.png)

8. For the **Logs**

    - We will use **CloudWatch logs**
    - Group name: **aws-cicd-ec2-group**
    - Stream name: **aws-cicd-ec2-stream**

![CodeBuild](/images/5/9.png)

9. We have successfully created the **AWS CodeBuild project**. To verify that the configuration is correct, try **Start build**.

![CodeBuild](/images/5/10.png)

10. Wait for about 5 minutes, then select **Phase details** to view the project build process.

![CodeBuild](/images/5/2.png)