{
    "title": "Subnets",
    "linkTitle": "Subnets",
    "weight": "110"
}After creating a VPC, you can add one or more subnets in each Availability Zone. Public Subnets have access to the Internet, while private do not. When you create a subnet, you specify the CIDR block for the subnet, which is a subset of the VPC CIDR block. Each subnet must reside entirely within one Availability Zone and cannot span zones. Availability Zones are distinct locations that are engineered to be isolated from failures in other Availability Zones. By launching instances in separate Availability Zones, you can protect your applications from the failure of a single location.

Learn more about [VPCs and Subnets](https://docs.aws.amazon.com/AmazonVPC/latest/UserGuide/VPC_Subnets.html) in the AWS documentation.

In the following example, the VPC on the left has a single CIDR block (10.0.0.0/16) and two subnets.

![](/Images/SecureTransport/vpc-multiple-cidrs.png)

## Create subnets

Create six subnets (four private and two public) as follows:

Two private and one public subnets per availability zone.

1.  Navigate to the AWS console Services.
2.  Under Networking & Content Delivery section choose.
3.  Navigate toSubnets and Create Subnet.
4.  Fill the settings and click **Yes, Create**.  
    -   Name tag: specify unique name for each subnet
    -   VPC: select you VPC for all subnets
    -   Availability Zone: create each subnet in a different zone  
        For example: the first public and the first and third private subnets are in eu-west-1 b.  
        The second public and the second private subnets are in eu-west-1 c.
    -   IPv4 CIDR block: for each subnet specify a different block  
        For example:
        -   172.31.0.0/24 - Public1
        -   172.31.3.0/24 - Public2
        -   172.31.1.0/24 - Private1
        -   172.31.2.0/24 - Private2
        -   172.31.4.0/24 - Private3
        -   172.31.5.0/24 - Private4
5.  Repeat the steps for the rest subnets.  
    <img src="/Images/SecureTransport/create-subnet.PNG" class="maxWidth" />  
