# Day 20: Create IAM Role for EC2 with Policy Attachment

Create an IAM role as below:

- IAM role name must be `iamrole_jim`.
- Entity type must be `AWS Service` and use case must be `EC2`.
- Attach a policy named `iampolicy_jim`.

----------------------------------------------------------------------------------------------------------

Method 1: From AWS CLI
----------------------
```sh
vi trust-policy.json                       #  Create trust policy for EC2
```

Paste the below content:
```sh
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Principal": {
        "Service": "ec2.amazonaws.com"
      },
      "Action": "sts:AssumeRole"
    }
  ]
}
```

```sh
aws iam create-role --role-name iamrole_jim --assume-role-policy-document file://trust-policy.json         #  Create IAM role iamrole_jim

aws iam attach-role-policy  --role-name iamrole_jim --policy-arn arn:aws:iam::$(aws sts get-caller-identity --query Account --output text):policy/iampolicy_jim    #  Attach policy iampolicy_jim to role

aws iam list-attached-role-policies  --role-name iamrole_jim   # Verify attachment
```

Method 2: From via AWS Management Console
-----------------------------------------

To create IAM role for custom policy:

1. Go to IAM Dashboard and choose `Roles` from navigation pane.

   <img width="263" height="472" alt="image" src="https://github.com/user-attachments/assets/e89eecb4-7b2f-4081-a147-b463f8806425" />

2. Click `Create role` and select `AWS service` under `Trusted Entity Type`

   <img width="1325" height="435" alt="image" src="https://github.com/user-attachments/assets/7d4e67ff-cd1c-493e-9adc-2076c482a23c" />

3. Under `Use case`, select `EC2` and click `Next` to proced on step 2.

   <img width="1015" height="364" alt="image" src="https://github.com/user-attachments/assets/423e44d8-bad9-4c2b-b783-6e4d14887f05" />

4. On step 2, in the `Permission policy` tab, search for the custom policy and select it.

   <img width="1366" height="448" alt="image" src="https://github.com/user-attachments/assets/6228ec61-060e-432f-90be-c9b1554f6f76" />

5. On step 3, enter preferred role name and click on `Create role`.

   <img width="1349" height="406" alt="image" src="https://github.com/user-attachments/assets/165a56e6-3ffc-4e6a-b272-96256bc34b42" />


