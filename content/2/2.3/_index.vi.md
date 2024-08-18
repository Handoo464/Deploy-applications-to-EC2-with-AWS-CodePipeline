---
title : "Tạo Git Conection"
date :  "`r Sys.Date()`" 
weight : 3
chapter : false
pre : " <b> 2.3. </b> "
---

## Create a connection to GitHub (console)

You can use the console to create a connection to GitHub.

###### Note

Currently, if you use the console to create a connection, this will only create resources with `codestar-connections` in the resource ARN. To create a resource that will have the `codeconnections` service prefix in the ARN, use the CLI, SDK, or CFN. Resources with both service prefixes will still display in the console. Console resource creation will be available beginning July 1, 2024.

1. Sign in to the AWS Management Console, and open the Developer Tools console at [https://console.aws.amazon.com/codesuite/settings/connections](https://console.aws.amazon.com/codesuite/settings/connections).
    
2. Choose **Settings > Connections**, and then choose **Create connection**.
    
3. To create a connection to a GitHub or GitHub Enterprise Cloud repository, under **Select a provider**, choose **GitHub**. In **Connection name**, enter the name for the connection that you want to create. Choose **Connect to GitHub**, and proceed to Step 2.
    
    ![Console screenshot showing connection option selected for GitHub.](https://docs.aws.amazon.com/images/dtconsole/latest/userguide/images/github-conn.png)
    

###### To create a connection to GitHub

1. Under **GitHub connection settings**, your connection name appears in **Connection name**. Choose **Connect to GitHub**. The access request page appears.
    
    ![Console screenshot showing the GitHub account access page.](https://docs.aws.amazon.com/images/dtconsole/latest/userguide/images/github-conn-access.png)
    
2. Choose **Authorize AWS Connector for GitHub**. The connection page displays and shows the **GitHub Apps** field.
    
    ![Console screenshot showing the initial GitHub connection page with the GitHub Apps field.](https://docs.aws.amazon.com/images/dtconsole/latest/userguide/images/github-conn-access-app.png)
    
3. Under **GitHub Apps**, choose an app installation or choose **Install a new app** to create one.
    
    You install one app for all of your connections to a particular provider. If you have already installed the AWS Connector for GitHub app, choose it and skip this step.
    
    ###### Note
    
    If you want to create a [user access token](https://docs.github.com/en/apps/creating-github-apps/authenticating-with-a-github-app/generating-a-user-access-token-for-a-github-app), make sure that you've already installed the AWS Connector for GitHub app and then leave the App installation field empty. CodeConnections will use the user access token for the connection.
    
4. On the Install **AWS Connector for GitHub** page, choose the account where you want to install the app.
    
    ![Console screenshot showing the AWS Connector for GitHub installation page.](https://docs.aws.amazon.com/images/dtconsole/latest/userguide/images/github-conn-access-app-install1.png)
    
    ###### Note
    
    You only install the app once for each GitHub account. If you previously installed the app, you can choose **Configure** to proceed to a modification page for your app installation, or you can use the back button to return to the console.
    
5. On the **Install AWS Connector for GitHub** page, leave the defaults, and choose **Install**.
    
    ![Console screenshot showing the second AWS Connector for GitHub installation page.](https://docs.aws.amazon.com/images/dtconsole/latest/userguide/images/github-conn-access-app-install2.png)
    
    After this step, an updated permissions page might display in GitHub.
    
6. If a page displays showing that there are updated permissions for the AWS Connector for GitHub app, choose **Accept new permissions**.
    
    ![Console screenshot showing the AWS Connector for GitHub updated permissions page.](https://docs.aws.amazon.com/images/dtconsole/latest/userguide/images/accept-new-permissions.png)
    
7. You are returned to the **Connect to GitHub** page. The connection ID for your new installation appears in **GitHub Apps**. Choose **Connect**.
    

### View your created connection

- The created connection displays in the connections list.
    
    ![Console screenshot showing connections listing with successfully created connection.](https://docs.aws.amazon.com/images/dtconsole/latest/userguide/images/connections-create-ghe-complete.png)