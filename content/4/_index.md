---
title : "AWS CodeCommit"
date :  "`r Sys.Date()`" 
weight : 4 
chapter : false
pre : " <b> 4. </b> "
---

On July 25, 2024, AWS announced that their source code management (SCM) product - CodeCommit, is no longer available to new customers.

Customers can migrate their [AWS CodeCommit](https://docs.aws.amazon.com/codecommit/latest/userguide/getting-started-cc.html) Git repositories to other Git providers using several methods, such as cloning the repository, mirroring, or migrating specific branches. This blog describes a basic use case to mirror a repository to a generic provider, and links to instructions for mirroring to more specific providers. Your exact steps could vary depending on the type or complexity of your repository, and the decisions made on what and how you want to migrate. This post only describes how to migrate Git repository data, and does not describe exporting other data from CodeCommit such as pull requests.

### Pre-requisites

1. Before you can migrate your CodeCommit repository to another provider, make sure that you have the necessary credentials and permissions to both the AWS Management Console and the other provider’s account. For migrating to GitHub and Gitlab, use CodeCommit static credentials as described in [HTTPS users using Git credentials](https://docs.aws.amazon.com/codecommit/latest/userguide/setting-up-gc.html). If you choose to use the generic migration option process described below, any type of CodeCommit credentials can be used. To learn more about setting up AWS CodeCommit access control see [Setting up for AWS CodeCommit](https://docs.aws.amazon.com/codecommit/latest/userguide/setting-up.html).
2. In the AWS CodeCommit console, select the clone URL for the repository you will migrate. The correct clone URL (HTTPS, SSH, or HTTPS (CRC)) depends on which credential type and network protocol you have chosen to use.

![](/images/4/1.png)


### Migrating your AWS CodeCommit repository to a GitLab repository

Using the CodeCommit clone URL in combination with the HTTPS Git repository credentials, follow the guidance in GitLab’s documentation for [importing source code](https://docs.gitlab.com/ee/user/project/import/) from a [repository by URL](https://docs.gitlab.com/ee/user/project/import/repo_by_url.html).

### Migrating your AWS CodeCommit repository to a GitHub repository

Using the CodeCommit clone URL in combination with the HTTPS Git repository credentials, follow the guidance in GitHub’s documentation for [importing source code](https://docs.github.com/en/migrations/importing-source-code/using-github-importer/about-github-importer).

### Migrating your AWS CodeCommit repository to a Bitbucket Cloud repository

Using the CodeCommit clone URL in combination with the HTTPS Git repository credentials, follow the instructions provided in [Bitbucket’s blog post](https://bitbucket.org/blog/migrating-aws-codecommit-to-bitbucket-cloud).

### Generic migration to a different repository provider

**1.     Clone the AWS CodeCommit Repository**  
Clone the repository from AWS CodeCommit to your local machine using Git. If you’re using HTTPS, you can do this by running the following command:

`git clone --mirror https://your-aws-repository-url your-aws-repository`

Replace _your-aws-repository-url_ with the URL of your AWS CodeCommit repository.  
Replace _your-aws-repository_ with a name for this repository. Example:

`git clone https://git-codecommit.us-east-2.amazonaws.com/v1/repos/MyDemoRepo my-demo-repo`

**2.     Set up new remote repository**

Navigate to the directory of your cloned AWS CodeCommit repository. Then, add the repository URL from the new repository provider as a remote:

`git remote add <provider name> <provider-repository-url>`

Replace _<provider name>_ with the provider name of your choice. (Example: gitlab)  
Replace _<provider-repository-url>_ with the URL of your new repository provider’s repository.

**3.     Push your local repository to the new remote repository**

This will push all branches and tags to your new repository provider’s repository. The provider name must match the provider name from step 2.

`git push <provider name> --mirror`

**Notes:**

- The remote repository should be empty
- The remote repository may have protected branches not allowing force push. In this case, navigate to your new repository provider and disable branch protections to allow force push.

**4.     Verify the Migration**

Once the push is complete, verify that all files, branches, and tags have been successfully migrated to the new repository provider. You can do this by browsing your repository online or by cloning it to another location and checking it locally.

**5.     Update Remote URLs**

If you plan to continue working with the migrated repository locally, you may want to update the remote URL to point to the new provider’s repository instead of AWS CodeCommit. You can do this using the following command:

`git remote set-url origin <provider-repository-url>`

Replace _<provider-repository-url>_ with the URL of your new repository provider’s repository.

**6.     Update CI/CD Pipelines and fix protected branches**

If you have CI/CD pipelines set up that interact with your repository, such as GitLab, GitHub or AWS CodePipeline, update their configuration to reflect the new repository URL. If you removed protected branch permissions in Step 3 you may want to add these back to your main branch.

**7.     Inform Your Team**

If you’re migrating a repository that others are working on, be sure to inform your team about the migration and provide them with the new repository URL.

**8.     Delete the, now migrated, AWS CodeCommit repository**

This action cannot be undone. Navigate back to the AWS CodeCommit console and delete the repository that you have migrated using the “Delete Repository” button.

![](/images/4/2.png)

