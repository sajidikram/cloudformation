# cloudformation
IaaS - Examples
I have created network-template.yaml file to provision the following resources
  1. Create an Amazon VPC with a CIDR block equal to 192.168.0.0/16, a name tag of My First VPC, and default tenancy.
  2. Create a subnet with a CIDR block equal to 192.168.1.0/24 and a name tag of My First Public Subnet. Create the subnet in the Amazon  VPC from step 1, and specify an Availability Zone for the subnet (for example, ap-southeast-2a).
  3. Create a subnet with a CIDR block equal to 192.168.2.0/24 and a name tag of My First Private Subnet. Create the subnet in the Amazon VPC from Step 1, and specify a different Availability Zone for the subnet than previously specified (for example, ap-southeast-2b).
  4. Create an IGW with a name tag of My First IGW and attach it to your Amazon VPC created in step 1.
  5. Create a NAT gateway, place it in the public subnet of your custom Amazon VPC, and assign it an EIP.
  6. Create two route tables in your VPC, named "My First Public Route Table" & "My First Private Route Table"
  7. Associate "My First Public Route Table" & "My First Private Route Table" to "My First Public Subnet" & "My First Private Subnet" respectively.
  7. Add a route to the "My Public route table" for your VPC that directs Internet traffic (0.0.0.0/0) to the IGW.
  8. Add a route to the "My First Private Route Table" that directs Internet traffic (0.0.0.0/0) to the NAT gateway. 
  9. Launch a t2.micro Amazon Linux AMI as an Amazon EC2 instance into the public subnet of your custom Amazon VPC, give it a name tag of My First Public Instance, and select the newly-created key pair for secure access to the instance.
  10. Launch a t2.micro Amazon Linux AMI as an Amazon EC2 instance into the private subnet of your custom Amazon VPC, give it a name tag of My First Private Instance, and select the newly-created key pair for secure access to the instance.

Testing & Verification Steps:
1. Securely access the Amazon EC2 instance in the public subnet via SSH with the newly-created key pair.
2. Copy newly created pem/private key to "My First public instance" to login on "My first private instance"
3. Execute an update to the operating system instance libraries by executing the following command on both instances:
  # sudo yum update -y
4. You should see output showing the instances downloading software from the Internet and installing it.
