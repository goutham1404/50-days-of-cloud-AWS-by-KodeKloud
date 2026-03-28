# Day 16: Create IAM User

When establishing infrastructure on the AWS cloud, Identity and Access Management (IAM) is among the first and most critical services to configure. IAM facilitates the creation and management of user accounts, groups, roles, policies, and other access controls. The Nautilus DevOps team is currently in the process of configuring these resources and has outlined the following requirements:

For this task, create an IAM user named `iamuser_james`.

---------------------------------------------------------------------------------------------------------

Method 1: From AWS CLI
----------------------
```sh
aws iam create-user --user-name iamuser_james             # creates iam user

aws iam get-user --user-name iamuser_james                   # gets user info
```

Method 2: From via AWS Management Console
-----------------------------------------

Create an IAM user:

1. Go to `IAM` Dashboard and Click on `Users` on navigation pane.

   <img width="263" height="452" alt="image" src="https://github.com/user-attachments/assets/732d543d-b7b2-49d6-97eb-90582f047c6e" />

2. Click on `Create user`.

   <img width="1069" height="244" alt="image" src="https://github.com/user-attachments/assets/6aa3f1d4-ac17-4636-b07f-d6dc411144d4" />

3. Enter user name and choose `Next` and heads to `Review and create`.

   <img width="1317" height="410" alt="image" src="https://github.com/user-attachments/assets/10c41a0e-cddd-4af8-aada-5da5fd2bbfb0" />

4. Click on `Create` and View user summary.

   <img width="1038" height="480" alt="image" src="https://github.com/user-attachments/assets/d5bade56-bdae-4c79-b288-669bd6801946" />


