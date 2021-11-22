{
    "title": "Network Access Lists",
    "linkTitle": "Network Access Lists",
    "weight": "100"
}You can secure your VPC instances using only security groups and in general they are sufficient to secure your subnets, but we recommend you to add network ACLs as a second layer of defense. Learn more about [Network ACLs](http://docs.aws.amazon.com/AmazonVPC/latest/UserGuide/VPC_ACLs.html) in the AWS documentation.

-   Create one Network ACL for your public subnets hosting the SecureTransport Edge servers and add inbound/outbound rules limiting the access to the required minimum for the relevant subnets.
-   Create one Network ACL for your private subnets hosting the SecureTransport servers and add inbound/outbound rules limiting the access to the required minimum for the relevant subnets.
-   Create one Network ACL for the private subnets hosting the database instances and add inbound/outbound rules limiting the access to the required minimum for the relevant subnets. Later after you create the subnets, associate them with their corresponding Network ACL.

To create Network Access Lists in Amazon VPC:

1.  Navigate to the AWS console -> Services.
2.  Under the Networking & Content Delivery section, choose **VPC**.
3.  Navigate to Virtual Private Cloud -> Security -> Network ACLs.
4.  Select Create Network ACL, enter a meaningful name, choose your VPC and confirm by clicking **Yes, Create**.  
    <img src="/Images/SecureTransport/net-accss-list_480x237.png" class="img_1" />  

<!-- -->

1.  Enter Inbound/Outbound rules relevant for the subnets that will be associated with this Network ACL and then click **Save**.  
      
    <img src="/Images/SecureTransport/net-accss-list1_480x226.png" class="img_1" />

<!-- -->

1.  Associate the corresponding subnets with this Network ACL and save.  
    <img src="/Images/SecureTransport/net-accss-list2_480x284.png" class="img_1" />  

## Access your servers using Administration host

When designing the Administration host for your AWS infrastructure, you should use it only for maintenance and administration tasks and avoid opening unnecessary security holes. You need to keep it locked down as much as possible. You could look into hardening your chosen operating system for even tighter security. You should stop your Administration host instances for the duration with no maintenance work and start them when you need access to your servers in AWS in order to minimize the security risks.

Here are the basic steps for creating a bastion host for your AWS infrastructure (see section ):

-   Launch an EC2 instance.
-   Apply your OS hardening as required.
-   Set up the appropriate security groups (SG).
-   Implement either SSH-Agent Forwarding (Linux connectivity) or Remote Desktop Gateway (Windows connectivity).
-   Deploy an AWS bastion host in each of the Availability Zones you’re using.

Learn more about the [Linux Bastion Host Architecture](http://docs.aws.amazon.com/quickstart/latest/linux-bastion/architecture.html) in the AWS documentation.

Also, see [How to record ssh sessions established through a bastion host](https://aws.amazon.com/blogs/security/how-to-record-ssh-sessions-established-through-a-bastion-host/) topic for closer monitoring over this host.

Security groups are essential for maintaining tight security and play a big part in making this solution work. First, you need to create a security group or update an existing security group that will be used to allow connectivity from the Administration host for your existing private instances (see the {{< SecureTransport/componentshortname  >}} *Server Security Group* in the *Security* section of the guide). This SG should only accept SSH or RDP inbound requests from your Administration hosts across your Availability Zones. Apply this group to all your private instances that require connectivity.

Next, create a security group to be applied to your Administration host. Inbound and outbound traffic must be restricted at the protocol level as much as possible. The inbound rule base should accept SSH or RDP connections only from specific IP addresses (usually those of your administrators’ work computers). See the *Administration Host Security Group* in the *Security Groups* section of this guide. Your outbound connection should again be restricted to SSH or RDP access to the private instances of your AWS infrastructure. An easy way to do this is to populate the ‘Destination’ field with the ID of the security group you are using for your private instances.

SSH and RDP connections require private and public key access to authenticate. This does not pose a problem when you are trying to connect to your Administration host from a local machine, as you can easily store the private key locally. However, once you have connected to your Administration host, logging in to your private instances from this host would require having their private keys on the Administration host (storing private keys on remote instances is not a good security practice).

As a result, you should implement either Remote Desktop Gateway (for connecting to Windows instances) or SSH-agent forwarding (for Linux instances). Both of these solutions eliminate the need for storing private keys on the Administration host. AWS provides detailed documentation on how to implement [Windows Remote Desktop Gateway](https://aws.amazon.com/blogs/security/controlling-network-access-to-ec2-instances-using-a-bastion-server/) and [SSH-agent forwarding](https://aws.amazon.com/blogs/security/securely-connect-to-linux-instances-running-in-a-private-amazon-vpc/). 

## Replacing the Administration Host with Amazon EC2 Systems Manager

There is an alternative solution to having an Administration host with access to your private servers in the VPC and it is called Amazon EC2 Systems Manager.

Systems Manager allows you to remotely execute commands on managed hosts without using an Administration host. A host-based agent polls Systems Manager to determine if there is a command awaiting execution.

Learn more about [Replacing a Bastion Host with Amazon EC2 Systems Manager](https://aws.amazon.com/blogs/mt/replacing-a-bastion-host-with-amazon-ec2-systems-manager/) in the AWS documentation.

There is no cost to use Systems Manager but you are responsible for the costs of the resources that use Systems Manager, such as the EC2 instances, SNS messages, and S3 storage.
