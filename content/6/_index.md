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

![CodeBuild](https://000023.awsstudygroup.com/images/6-codedeploy/0001.png?featherlight=false&width=90pc)

2. In the **Create application** interface
    
    - For **Application name**, enter **AWS-FCJ-APP**
    - For **Compute platform**, we will choose **EC2/On-Premises**

![CodeBuild](https://000023.awsstudygroup.com/images/6-codedeploy/0002.png?featherlight=false&width=90pc)

3. We will create **Deployment groups** to implement the application deployment.

![CodeBuild](https://000023.awsstudygroup.com/images/6-codedeploy/0003.png?featherlight=false&width=90pc)

4. Configure **Deployment group**
    
    - Enter **Deployment group name**
    - Enter **Service role**

![CodeBuild](https://000023.awsstudygroup.com/images/6-codedeploy/0004.png?featherlight=false&width=90pc)

5. For **Deployment type**
    
    - We will choose **In-place**
    - For deployment environment is **Amazon EC2 instances**
    - Select by tag group, select the keys and values ​​suitable for **EC2** that you want to use to deploy the application.

![CodeBuild](https://000023.awsstudygroup.com/images/6-codedeploy/0005.png?featherlight=false&width=90pc)

6. For installation **Install AWS CodeDeploy Agent**
    
    - We will choose **Nerver**
    - For **Deployment settings**, select **CodeDeployDefault.OneAtATime**
    - Select **Create deployment group**

![CodeBuild](https://000023.awsstudygroup.com/images/6-codedeploy/0006.png?featherlight=false&width=90pc)

7. Finish creating **Deployment group**

![CodeBuild](https://000023.awsstudygroup.com/images/6-codedeploy/0007.png?featherlight=false&width=90pc)

8. We will return to **Applications**
    
    - Select the prepared application.
    - Select **Deploy application**

![CodeBuild](https://000023.awsstudygroup.com/images/6-codedeploy/0008.png?featherlight=false&width=90pc)

9. We will provide **Create deployment** information
    
    - Use **Deployment group**
    - Select **Revision type**
    - And for **Revision location** choose the lead of **S3 bucket**
    - File format will be **.zip**

![CodeBuild](https://000023.awsstudygroup.com/images/6-codedeploy/0009.png?featherlight=false&width=90pc)

10. Double check and select **Create deployment**

![CodeBuild](https://000023.awsstudygroup.com/images/6-codedeploy/00010.png?featherlight=false&width=90pc)

11. After a period of about 5 minutes.

- We will complete the deployment.

![CodeBuild](/images/6/1.png)

12. We’ll take a look at the deployment history.

![CodeBuild](/images/6/2.png)

13. Access the application via **DNS** of **EC2** via https://ec2-18-141-13-141.ap-southeast-1.compute.amazonaws.com/.

![CodeBuild](/images/6/3.png)
![CodeBuild](/images/6/4.png)
![CodeBuild](/images/6/5.png)