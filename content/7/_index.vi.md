---
title : "AWS CodePipeline"
date :  "`r Sys.Date()`" 
weight : 7
chapter : false
pre : " <b> 7. </b> "
---
#### AWS CodePipeline

Sau khi sử dụng **AWS CodeCommit** để đẩy code lên từ máy local, chúng ta thực hiện build qua **AWS CodeBuild** và sử dụng **AWS CodeDeploy** để triển khai ứng dụng lên **EC2** thì bây giờ chúng ta sẽ sử dụng **AWS CodePipeline** để tạo quá trình **CI/CD** triển khai ứng dụng.

1. Truy cập vào **AWS CodePipeline**
    
    - Chọn **Create pipeline**

![CodePipeline](/images/7/1.png)

2. Thực hiện cấu hình **AWS CodePipeline**
    
    - Nhập **Pipeline name**
    - Tạo một **service role** cho **AWS CodePipeline**
    - Chọn **Next**

![CodePipeline](/images/7/8.png)

3. Đối với phần **Advanced settings**
    
    - **Custom location**
    - Chọn **bucket**
    - Chọn **Next**

![CodePipeline](/images/7/9.png)

4. Đối với **AWS source stage**
    
    - Chọn **AWS CodeCommit** đối với **Source provider**
    - Chọn **Repository**
    - Đối với **Branch name**, chọn **master**
    - Chọn **Next**

![CodePipeline](/images/7/10.png)

5. Đối với phần build
    
    - Chọn **Build provider** là **AWS CodeBuild**
    - Chọn **Region**
    - Chọn **Project name** mà bạn đã tạo và build.
    - Chọn **Next**

![CodePipeline](/images/7/2.png)

6. Đối với **Deploy stage**
    
    - **Deploy provider**, chọn **AWS CodeDeploy**
    - Chọn **Region**
    - Chọn **Application name**bạn đã tạo.
    - Chọn **Deployment group**
    - Chọn **Next**

![CodePipeline](/images/7/11.png)

7. Chọn **Create pipeline**

![CodePipeline](/images/7/12.png)

8. Sau khi tạo thành công pipeline, bạn sẽ mất khoảng 10 phút để hoàn thành pipeline.

![CodePipeline](/images/7/3.png)

9. Bạn sẽ thử chỉnh sửa code để kiểm tra pipeline.
    
    - Bạn truy cập vào code ứng dụng
    - Vào phần **layout**, chọn **file main**
    - Chỉnh sửa dòng thứ 17 thành **Deploy Application to EC2 with AWS CodePipeline**

![CodePipeline](/images/7/4.png)

10. Sau đó thực hiện đẩy code lên **AWS CodeCommit**

![CodePipeline](/images/7/5.png)

11. Sau 1 phút tiếp theo, chúng ta sẽ hoàn thành pipeline vừa thay đổi code.

![CodePipeline](/images/7/6.png)

12. Thực hiện kiểm tra ứng dụng đã thay đổi
    
    - Chúng ta truy cập vào **EC2** triển khai
    - Sao chép **DNS**

![CodePipeline](/images/7/7.png)

