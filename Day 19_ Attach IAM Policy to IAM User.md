# Day 19: Attach IAM Policy to IAM User

An IAM user named `iamuser_john` and a policy named `iampolicy_john` already exist. Attach the IAM policy `iampolicy_john` to the IAM user `iamuser_john`.

----------------------------------------------------------------------------------------------------------

Method 1: From AWS CLI
----------------------
```sh
aws iam list-policies --query "Policies[?PolicyName=='iampolicy_john'].Arn" --output table       #  Display ARN (--policy-arn) of IAM policy iampolicy_kirsty

aws iam attach-user-policy --user-name iamuser_john --policy-arn arn:aws:iam::316890205783:policy/iampolicy_john --output table      #  aws iam attach-user-policy --user-name iamuser_kirsty --policy-arn arn:aws:iam::316890205783:policy/iampolicy_kirsty --output table

aws iam list-attached-user-policies --user-name iamuser_john        #  Verify policy attachment to the user
```

Method 2: From via AWS Management Console
-----------------------------------------

To attach the policy to a user:

- In the IAM console, in the navigation pane, choose `Policies`.

  <img width="263" height="468" alt="image" src="https://github.com/user-attachments/assets/7205a4cf-349f-45ef-a471-bbf0d300527e" />

- Select the policy and click on `Action` to choose `Attach`.

  <img width="1070" height="303" alt="image" src="https://github.com/user-attachments/assets/6bfdb1b4-af3e-4fd8-80b3-5333c4156068" />

- In the `Attach policy` tab, select the user you want to attach the policy and click on `Attach policy`.

  <img width="1366" height="507" alt="image" src="https://github.com/user-attachments/assets/07a87483-8a72-4d9d-8ccc-127b9ed74116" />
