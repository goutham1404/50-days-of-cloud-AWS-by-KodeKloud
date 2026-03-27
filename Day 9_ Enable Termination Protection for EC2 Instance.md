# Day 9: Enable Termination Protection for EC2 Instance

An instance named `nautilus-ec2` already exists in `us-east-1` region. Enable termination protection for the same.

----------------------------------------------------------------------------------------------------------

Method 1: From AWS CLI
----------------------
```sh
aws ec2 describe-instances --output table            # to get instance-id

aws ec2 stop-instances --instance-ids i-0634226fa194cc986               # to stop the instance

aws ec2 modify-instance-attribute --instance-id i-0634226fa194cc986 --region us-east-1 --disable-api-termination     # to enable termination protection

aws ec2 start-instances --instance-id i-0634226fa194cc986 --region us-east-1           #  to start the instances

# To Disable Termination Protection
aws ec2 modify-instance-attribute --instance-id i-0634226fa194cc986 --region us-east-1 --no-disable-api-termination
```
Method 2: From via AWS Management Console
-----------------------------------------

Step 1: Go to EC2 Dashboard and Click on `Instances running` in resource section.

<img width="719" height="239" alt="image" src="https://github.com/user-attachments/assets/e40a9874-9629-4dd7-a864-e8f6c4cd3d73" />

Step 2: Select instance and Click on `Action` and from  `Instance Settings`, click on `Change termination protection`.

<img width="1366" height="615" alt="image" src="https://github.com/user-attachments/assets/74f40eda-faf8-4375-81a7-e7079c4ad88a" />

Step 3: Then click on `Enable` under Termination Protection and `Save`

<img width="600" height="249" alt="image" src="https://github.com/user-attachments/assets/477b6b97-6800-4e3d-bc76-b86ab7d2952d" />
