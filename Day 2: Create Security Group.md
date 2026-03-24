# Day 2: Create Security Group

For this task, create a security group under default VPC with the following requirements:

Name of the security group is `devops-sg`.

The description must be **Security group for Nautilus App Servers**

Add the inbound rule of type `HTTP`, with port range of `80`. Enter the source CIDR range of `0.0.0.0/0`.

Add another inbound rule of type `SSH`, with port range of `22`. Enter the source CIDR range of `0.0.0.0/0`.
--------------------------------------------------------------------------------------------------------------------------------------------------

Method 1: From AWS CLI
----------------------

-aws ec2 describe-vpcs --region us-east-1 # to get vpc-id 

-aws ec2 create security-group --group-name devops-sg --description "Security group for Nautilus App Servers" # to create sg

-aws ec2 describe-security-groups --region us-east-1 --group-name devops-sg    # to get sg-id

-aws ec2 authorize-security-group-ingress --group-id sg-0123456789abcdef0 --protocol tcp --port 80 --cidr 0.0.0.0/0   # to add inbound rule for port 80

-aws ec2 authorize-security-group-ingress --group-id sg-0123456789abcdef0 --protocol tcp --port 22 --cidr 0.0.0.0/0   # to add inbound rule for port 22

Method 2: From via AWS Management Console
-----------------------------------------

### Step 1: Go to EC2 Dashboard

<img width="1366" height="615" alt="image" src="https://github.com/user-attachments/assets/6f9f9e9c-f2c8-48bf-86cc-a0c7bfa20937" />

### Step 2: Click on Security Groups

<img width="1366" height="615" alt="image" src="https://github.com/user-attachments/assets/afeb47c3-39f1-4aa4-8e6a-8ba1535fbece" />

### Step 3: Click on "Create a security group"

Name of the security group is `devops-sg`.

The description must be **Security group for Nautilus App Servers**

<img width="1366" height="353" alt="image" src="https://github.com/user-attachments/assets/cc1e0272-343b-477e-ad1d-c5a4b2b1f976" />

### Step 4: Add inbound rules

Add the inbound rule of type `HTTP`, with port range of `80`. Enter the source CIDR range of `0.0.0.0/0`.

Add another inbound rule of type `SSH`, with port range of `22`. Enter the source CIDR range of `0.0.0.0/0`.

<img width="1366" height="298" alt="image" src="https://github.com/user-attachments/assets/7486aa22-ee7a-476b-abaf-ec145390c96a" />

### Step 5: Review

<img width="1108" height="245" alt="image" src="https://github.com/user-attachments/assets/2fd7d75c-91eb-4bd5-9418-b7480bda0fa1" />

