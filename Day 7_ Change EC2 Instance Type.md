# Day 7: Change EC2 Instance Type

During the migration process, the Nautilus DevOps team created several EC2 instances in different regions. They are currently in the process of identifying the correct resources and utilization and are making continuous changes to ensure optimal resource utilization. Recently, they discovered that one of the EC2 instances was underutilized, prompting them to decide to change the instance type. Please make sure the Status check is completed (if its still in Initializing state) before making any changes to the instance.

1) Change the instance type from `t2.micro` to `t2.nano` for `devops-ec2` instance.
2) Make sure the ec2 instance `devops-ec2` is in running state after the change.

------------------------------------------------------------------------------------------------

Method 1: From AWS CLI
----------------------
```sh
aws ec2 describe-instances --region us-east-1 --output table    # to get instance_id

aws ec2 stop-instances --instance-ids i-092de82f86f7f1890     # to stop instance

aws ec2 describe-instances --instance-ids i-092de82f86f7f1890      # to verify if instance is stopped or not

aws ec2 modify-instance-attribute --instance-id i-092de82f86f7f1890 --instance-type "{\"Value\": \"t2.nano\"}"    # to change the instance_type

aws ec2 describe-instances --instance-ids i-092de82f86f7f1890     # to verify if instance_type is changed pr not

aws ec2 start-instances --instance-ids i-092de82f86f7f1890      # to restart the instance

aws ec2 describe-instances --instance-ids i-092de82f86f7f1890 --output table    # to verify if instance is running or not
```

Method 2: From via AWS Management Console
-----------------------------------------

Steps:

1. Open the Amazon EC2 Dashboard. Under `Resource` section, you can already see an instance is running.
   <img width="719" height="245" alt="image" src="https://github.com/user-attachments/assets/978f647a-ad8f-4cec-9cc0-4f790c0a90e0" />

2. Select the instance and from `Instance state` dropdown, click on `Instance Stop`
   <img width="1132" height="180" alt="image" src="https://github.com/user-attachments/assets/f91be5d3-7c6e-4fc0-a654-2ff93f79fca4" />

3. Confirm the insatnce is `stopped` from instance status column
   <img width="1132" height="144" alt="image" src="https://github.com/user-attachments/assets/c0dc40cc-7a9d-40fc-834b-362abfea8f20" />

4. Click **Actions** → **Instance settings** → **Change instance type**
   <img width="1124" height="480" alt="image" src="https://github.com/user-attachments/assets/863be03c-276b-4268-a3b5-74c1fe785f61" />

5. Choose your new instance type (`t2.micro` → `t2.nano`) and **Change instance type**
   <img width="1348" height="394" alt="image" src="https://github.com/user-attachments/assets/9465c9be-5ac6-4c5a-a7d3-055bcb7d86ca" />

6. Start instance from **Instance state** dropdown and verify instance is running and instance type is `t2.nano`
   <img width="1132" height="145" alt="image" src="https://github.com/user-attachments/assets/f45f6343-acea-408f-9c91-c043f67a7110" />

   
