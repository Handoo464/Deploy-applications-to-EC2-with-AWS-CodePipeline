---
title : "AWS CodeDeploy"
date :  "`r Sys.Date()`" 
weight : 6 
chapter : false
pre : " <b> 6. </b> "
---

#### AWS CodeDeploy

1. Access to **AWS CodeDeploy**
    
    - Select **Create application**

![CodeBuild](/images/6/6.png)

2. In the **Create application** interface
    
    - For **Application name**, enter **AWS-FCJ-APP**
    - For **Compute platform**, we will choose **EC2/On-Premises**

![CodeBuild](/images/6/7.png)

3. We will create **Deployment groups** to implement the application deployment.

![CodeBuild](/images/6/8.png)

4. Configure **Deployment group**
    
    - Enter **Deployment group name**
    - Enter **Service role**

![CodeBuild](/images/6/9.png)

5. For **Deployment type**
    
    - We will choose **In-place**
    - For deployment environment is **Amazon EC2 instances**
    - Select by tag group, select the keys and values ​​suitable for **EC2** that you want to use to deploy the application.

![CodeBuild](/images/6/10.png)

6. For installation **Install AWS CodeDeploy Agent**
    
    - We will choose **Nerver**
    - For **Deployment settings**, select **CodeDeployDefault.OneAtATime**
    - Select **Create deployment group**

![CodeBuild](/images/6/11.png)

7. Finish creating **Deployment group**

![CodeBuild](/images/6/12.png)

8. We will return to **Applications**
    
    - Select the prepared application.
    - Select **Deploy application**

![CodeBuild](/images/6/13.png)

9. We will provide **Create deployment** information
    
    - Use **Deployment group**
    - Select **Revision type**
    - And for **Revision location** choose the lead of **S3 bucket**
    - File format will be **.zip**

![CodeBuild](/images/6/14.png)

10. Double check and select **Create deployment**

![CodeBuild](/images/6/15.png)

11. After a period of about 5 minutes.

- We will complete the deployment.

![CodeBuild](/images/6/1.png)

12. We’ll take a look at the deployment history.

![CodeBuild](/images/6/2.png)

13. Access the application via **DNS** of **EC2** via https://ec2-18-141-13-141.ap-southeast-1.compute.amazonaws.com/.

![CodeBuild](/images/6/3.png)
![CodeBuild](/images/6/4.png)

{{%notice tip%}}
Remember to access the link with http instead of https
{{%/notice%}}
![CodeBuild](/images/6/5.png)