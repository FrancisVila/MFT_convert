{
    "title": "Connect to your VPC",
    "linkTitle": "Connect to your VPC",
    "weight": "100"
}There are a few ways to connect to a VPC, and the right one for you depends on your use case and preferences. You can use the following protocols or services to connect to a VPC:

-   VPN
-   AWS Direct Connect
-   VPC peering
-   VPC endpoints
-   EC2 ClassicLink

## VPN

A virtual private network (VPN) connection is established to an AWS-managed virtual private gateway (VPG). For more information, see [Set up VPN connection](st_setup_vpn).

A virtual private gateway is the VPN device on the AWS side of the VPN connection. After you have created your VPN, you can download the IPsec VPN configuration from the Amazon VPC console to configure the firewall or device in your local network that will connect to the VPN.

AWS offers a managed VPN service, but you can also use a third-party software VPN solution. The latter is suitable if you need to have full access and management of the AWS side of your connection.

Learn more about [VPN Connections](http://docs.aws.amazon.com/AmazonVPC/latest/UserGuide/vpn-connections.html) in the AWS documentation.

## AWS Direct Connect

Direct Connect creates a direct, private connection from your on-premises data center to AWS, letting you establish a 1-gigabit or 10-gigabit dedicated network connection using Ethernet fiber-optic cable. Learn more about [AWS Direct Connect](http://docs.aws.amazon.com/directconnect/latest/UserGuide/Welcome.html) in the AWS documentation.

Direct Connect is priced per port-hour, with additional data transfer rates that vary by region. Learn more about the [AWS Direct Connect pricing](https://aws.amazon.com/directconnect/pricing/).

## VPC peering

VPC peering allows you to connect two VPCs using each VPC's private IP address. This makes it appear as if the 2 VPCs are on the same network.

This option is recommended for connecting VPCs within a region or across AWS accounts. Because these connections do not rely on physical hardware, they are not subject to issues with single-point of failure or network bandwidth bottlenecks. Learn more about [VPC Peering](http://docs.aws.amazon.com/AmazonVPC/latest/UserGuide/vpc-peering.html) in the AWS documentation.

## VPC endpoints

VPC endpoints enable you to create a private connection between your VPC and another AWS service, without the need for Internet access. A VPC endpoint enables instances in your VPC to use private IP addresses to communicate with resources in other services. Learn more about [VPC Endpoints](http://docs.aws.amazon.com/AmazonVPC/latest/UserGuide/vpc-endpoints.html) in the AWS documentation.

## EC2 ClassicLink

ClassicLink allows you to link an EC2-Classic instance to a VPC in your account within same region, without using public IP addresses or Elastic IP addresses to enable communication between instances. You can associate VPC security groups with the EC2-Classic instance and enable a connection between the EC2-Classic instance and instances in your VPC by using a private IP address.

This option is available to users with accounts that support the EC2-Classic platform and can be used with any EC2-Classic instance. Learn more about [ClassicLink](http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/vpc-classiclink.html) in the AWS documentation.
