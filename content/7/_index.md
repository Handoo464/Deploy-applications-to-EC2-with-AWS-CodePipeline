---
title : "AWS CodePipeline"
date :  "`r Sys.Date()`" 
weight : 7
chapter : false
pre : " <b> 7. </b> "
---

#### AWS CodePipeline

After using **AWS CodeCommit** to push the code from the local machine, we build through **AWS CodeBuild** and use **AWS CodeDeploy** to deploy the application to **EC2** then we will now use **AWS CodePipeline** to create the **CI/CD** process to deploy the application.

1. Access to **AWS CodePipeline**
    
    - Select **Create pipeline**

![CodePipeline](/images/7/1.png)

2. Configure **AWS CodePipeline**
    
    - Enter **Pipeline name**
    - Create a **service role** for **AWS CodePipeline**
    - Select **Next**

![CodePipeline](/images/7/8.png)

3. For the **Advanced settings** section
    
    - **Custom location**
    - Select **bucket**
    - Select **Next**

![CodePipeline](/images/7/9.png)

4. For **AWS source stage**
    
    - Select **AWS CodeCommit** for **Source provider**
    - Select **Repository**
    - For **Branch name**, select **master**
    - Select **Next**

![CodePipeline](/images/7/10.png)

5. For the build
    
    - Select **Build provider** as **AWS CodeBuild**
    - Select **Region**
    - Select **Project name** that you created and build.
    - Select **Next**

![CodePipeline](/images/7/2.png)

6. For **Deploy stage**
    
    - **Deploy provider**, select **AWS CodeDeploy**
    - Select **Region**
    - Select **Application name** you created.
    - Select **Deployment group**
    - Select **Next**

![CodePipeline](/images/7/11.png)

7. Select **Create pipeline**

![CodePipeline](/images/7/12.png)

8. After successfully creating the pipeline, it will take you about 10 minutes to complete the pipeline.

![CodePipeline](/images/7/3.png)

9. You will try editing the code to test the pipeline.
    
    - You access the application code
    - Go to **index.html**, edit line 31 with "!!!"

![CodePipeline](/images/7/4.png)


10. Then commit chages

![CodePipeline](/images/7/5.png)

11. After the next 1 minutes, we will finish the pipeline we just changed the code.

![CodePipeline](/images/7/6.png)

12. Perform a changed application check
    
    - We access **EC2** deployment
    - Copy **DNS**

![CodePipeline](/images/7/7.png)