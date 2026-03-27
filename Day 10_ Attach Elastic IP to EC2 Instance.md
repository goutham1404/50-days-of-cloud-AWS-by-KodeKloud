# Day 10: Attach Elastic IP to EC2 Instance

1. There is an instance named `devops-ec2` and an elastic-ip named `devops-ec2-eip` in `us-east-1` region. 
2. Attach the `devops-ec2-eip` elastic-ip to the devops-ec2 instance.

----------------------------------------------------------------------------------------------------------

Method 1: From AWS CLI
----------------------
```sh
aws ec2 describe-instances  --region us-east-1 --filters "Name=tag:Name,Values=devops-ec2"  --query "Reservations[].Instances[].InstanceId" --output text     # Get the Instance ID of datacenter-ec2

aws ec2 describe-addresses  --region us-east-1  --filters "Name=tag:Name,Values=devops-ec2-eip"  --query "Addresses[].AllocationId"  --output text       # Get the Allocation ID of the Elastic IP datacenter-ec2-eip

aws ec2 associate-address  --region us-east-1  --instance-id i-0abc12345def6789 --allocation-id eipalloc-0123abcd4567efgh        #Attach (Associate) Elastic IP to the EC2 Instance

aws ec2 describe-addresses  --region us-east-1  --filters "Name=tag:Name,Values=devops-ec2-eip" --output table        #  Verify the Attachment
```

Method 2: From via AWS Management Console
-----------------------------------------

AWS Documentation to be folllowed: [Associate an Elastic IP address](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/working-with-eips.html#using-instance-addressing-eips-associating)

To associate an Elastic IP address with an instance

1. Open the Amazon EC2 console at https://console.aws.amazon.com/ec2/

3. In the navigation pane, choose **Elastic IPs**.
  
6. Select the Elastic IP address to associate and choose **Actions, Associate Elastic IP address**.

7. For **Resource type**, choose **Instance**.

8. For instance, choose the instance with which to associate the Elastic IP address. You can also enter text to search for a specific instance.

9. (Optional) For **Private IP** address, specify a private IP address with which to associate the Elastic IP address.

10. Choose **Associate**.
