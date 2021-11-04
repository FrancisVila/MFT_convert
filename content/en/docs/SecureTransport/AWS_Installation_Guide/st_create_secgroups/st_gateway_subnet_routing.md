{
    "title": "Internet Gateway and public subnets routing",
    "linkTitle": "Internet Gateway and public subnets routing",
    "weight": "120"
}An Internet gateway is a horizontally scaled, redundant, and highly available VPC component that allows communication between instances in your VPC and the Internet. It therefore imposes no availability risks or bandwidth constraints on your network traffic.

An Internet gateway serves two purposes: to provide a target in your VPC route tables for Internet-routable traffic, and to perform network address translation (NAT) for instances that have been assigned public IPv4 addresses.

In order for the resources in a VPC to send and receive traffic from the Internet, the following conditions must be met:

-   An [Internet gateway must be attached](http://docs.aws.amazon.com/AmazonVPC/latest/UserGuide/VPC_Internet_Gateway.html#Add_IGW_Attach_Gateway) to the VPC.
-   The [route tables associated with your public subnet](http://docs.aws.amazon.com/AmazonVPC/latest/UserGuide/VPC_Route_Tables.html) (including [custom route tables](http://docs.aws.amazon.com/AmazonVPC/latest/UserGuide/VPC_Internet_Gateway.html#Add_IGW_Routing)) must have a route to the Internet gateway.
-   The [security groups](http://docs.aws.amazon.com/AmazonVPC/latest/UserGuide/VPC_Internet_Gateway.html#Add_IG_Security_Groups) associated with your VPC must allow traffic to flow to and from the Internet.
-   Any instances in the VPC must either have a [public IP address or an attached Elastic IP address](http://docs.aws.amazon.com/AmazonVPC/latest/UserGuide/VPC_Internet_Gateway.html#Add_IG_EIPs).

You can find instructions for each of these steps at [Creating a VPC with an Internet Gateway](http://docs.aws.amazon.com/AmazonVPC/latest/UserGuide/VPC_Internet_Gateway.html#d0e22943).

## Attach an Internet gateway

Follow these steps to attach an Internet gateway to your VPC to enable communication of the public subnets with the Internet:

1.  Navigate to the AWS console -> Services.
2.  Under the Networking & Content Delivery section, choose VPC.
3.  Navigate to Virtual Private Cloud -> Internet Gateways.
4.  Click **Create Internet Gateway**.
5.  Type a name in the Name tag text box and click **Yes, Create**.  
    <img src="/Images/SecureTransport/create-inet-gw.PNG" class="maxWidth" />  
    The internet gateway just created is in a "detached" state. Your next step is to attach it to your VPC.  
      
6.  Click **Attach to VPC**.
7.  Select your VPC from the Name tag drop-down list and click **Yes, Attach**.  
    <img src="/Images/SecureTransport/ig-attach-to-vpc.PNG" class="maxWidth" />  
    On success, the state of the internet gateway changes to "attached".  
    <img src="/Images/SecureTransport/ig-attached.PNG" class="maxWidth" />

## Routing of public subnets

Now you need to configure the routing for your public subnets. Enable traffic from your public subnets to Internet by using the internet gateway attached to the VPC.

Configure the public subnets Route Table:

1.  Navigate to VPC Dashboard -> Subnets.
2.  Select your first public subnet from the list and navigate to its Summary section.
3.  Click on the name of the Route Table of the subnet.
4.  You are then redirected to the Route Table in the Virtual Private Cloud -> Route Tables section.
5.  Add two routes for the Route Table - one for the traffic to the Internet to be routed using the Internet Gateway.
6.  Add new rules: for destination type 0.0.0.0/0 (all packets for the internet) and for target choose the Internet Gateway you have created as in the previous subtopic.  
    <img src="/Images/SecureTransport/pub-add-rout.PNG" class="maxWidth" />  
7.  Save the rules.
8.  Navigate to "Subnet Associations" tab and associate your public subnets to the route table and save the changes.  
    <img src="/Images/SecureTransport/route-assign-sn.PNG" class="maxWidth" />

Now traffic from instances in the public subnets destined to the Internet will be redirected to the Internet Gateway.
