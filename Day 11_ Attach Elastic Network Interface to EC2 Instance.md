# Day 11: Attach Elastic Network Interface to EC2 Instance

- An instance named **`nautilus-ec2`** and an elastic network interface named **`nautilus-eni`** already exists in **`us-east-1`** region.

- Attach the **`nautilus-eni`** network interface to the **`nautilus-ec2`** instance.

- Make sure status is attached before submitting the task.

----------------------------------------------------------------------------------------------------------

Method 1: From AWS CLI
----------------------
```sh
aws ec2 describe-instances --region us-east-1 --filters "Name=tag:Name,Values=nautilus-ec2" --output table     #  get instance-id

aws ec2 describe-network-interfaces --region us-east-1 --filter "Name=tag:Name,Values=nautilus-eni" --output table      # get network-interface-id

aws ec2 attach-network-interface --instance-id i-04dbd70f2f2e661cc --network-interface-id eni-0007544d05d30165e --device-index 1 --output table       # Attach network interface to  instance 

aws ec2 describe-instances --region us-east-1 --filters "Name=tag:Name,Values=nautilus-ec2" --output table           #  verify attached or not
```

Method 2: From via AWS Management Console
-----------------------------------------

To attach a network interface using the Network Interfaces page:

- Open the **Amazon EC2** console at https://console.aws.amazon.com/ec2/

- In the navigation pane, choose **Network Interfaces**.

  <img width="192" height="185" alt="image" src="https://github.com/user-attachments/assets/16f59970-c640-4872-a758-cb2b684b9e21" />

- Select the checkbox for the network interface.

  <img width="1108" height="171" alt="image" src="https://github.com/user-attachments/assets/0f417776-fc21-4d06-9903-edbcd039e945" />

- Choose **Actions, Attach**.

- Choose an instance. If the instance supports multiple network cards, you can choose a network card.

  <img width="600" height="314" alt="image" src="https://github.com/user-attachments/assets/f4d60509-628a-40f3-a4da-bc1e733c7368" />

- Choose **Attach**.

### AWS Docs to be followed: [Attach a network interface](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/network-interface-attachments.html)
