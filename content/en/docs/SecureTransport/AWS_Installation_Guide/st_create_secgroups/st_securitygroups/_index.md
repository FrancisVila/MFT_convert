{
    "title": "Security Groups",
    "linkTitle": "Security Groups",
    "weight": "90"
}## Security Groups

An EC2 instance is a virtual machine in Amazon’s Elastic Compute Cloud (EC2) for running applications on the Amazon Web Services (AWS) infrastructure.

When you launch an EC2 instance in a VPC, you can associate it with one or more security groups that you've created. Each instance in your VPC could belong to a different set of security groups. If you don't specify a security group when you launch an instance, the instance automatically belongs to the default security group for the VPC. For more information about security groups, see [Security Groups for Your VPC](https://docs.aws.amazon.com/AmazonVPC/latest/UserGuide/VPC_SecurityGroups.html) in the AWS documentation..

We recommend you create the security groups you need for your SecureTransport infrastructure in AWS as a first stage before proceeding with rest of the setup. You need to group (assign) the instances and components into the following security groups:

-   SecureTransport Edge security group
-   SecureTransport Server security group
-   External Database security group
-   External File System security group
-   Load Balancer security group
-   Administration Host security group

Later, during the launch process of the instances and the creation of different components recommended for your SecureTransport setup, you will just select the security group you need from the list. You can always create the Security Groups on a later stage but we suggest you adhere to the flow as described.

To create a security group in Amazon VPC:

1.  Navigate to the AWS console->Services.
2.  Under the Networking & Content Delivery section, choose VPC.
3.  Navigate to Virtual Private Cloud->Security->Security Groups and click **Create Security Group**.
4.  On the newly opened dialog box, enter the required information and click **Yes, Create**.  
    <img src="/Images/SecureTransport/create-sg.PNG" class="maxWidth" />
5.  Select your security group from the "All security groups" table.
6.  Edit the "Inbound Rules"/"Outbound Rules" section of the security group.
7.  Use the **Add another rule** button to enable or disable access to your instances on specific ports or sources.  
    <img src="/Images/SecureTransport/sg-inb-rule.PNG" class="maxWidth" />

You must add the necessary inbound/outbound rules to the security groups and the instances assigned to each group will have the required for the group level of connectivity and security. Please refer to the firewall specific information already provided in SecureTransport Administrator's Guide.

> **Note:**
>
> The rules defined in the following Security Groups cover the most basic security scenario. If you would like more restrictive rules, you can add more Inbound and Outbound rules.

> **Note:**
>
> The described rules use default ports or ports specific for the test setup. Please change/add rules according to your specific setup. Check the FTP does not work through the firewall section in the SecureTransport Administrator's Guide if you want to configure FTP.
