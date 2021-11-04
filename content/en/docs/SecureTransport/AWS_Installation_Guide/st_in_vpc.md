{
    "title": "SecureTransport in Amazon Virtual Private Cloud",
    "linkTitle": "SecureTransport in Amazon Virtual Private Cloud",
    "weight": "50"
}Currently, deployment of SecureTransport on AWS VPC has been verified for Red Hat Enterprise Linux in the following setup:

-   Enterprise Cluster of two servers with streaming to two edges
-   Oracle Database Engine, PostgreSQL and Microsoft SQL Server Engine
-   GlusterFS file system with two servers
-   A Load Balancer (optional)
-   A NAT Gateway (optional)
-   An Administration Host (optional)
-   Four private and two public subnets
-   A VPN Connection (optional)
-   Instances are assigned to five Security Groups
-   All this located in two availability zones

> **Note:**
>
> For a multiple Availability Zone deployment, SecureTransport is supported in Enterprise Cluster mode only. SecureTransport over AWS is not supported in Standard Cluster mode when cluster nodes are deployed across multiple Availability zones. For a Standard Cluster setup in AWS, all nodes must be located in the same Availability Zone.

AWS cloud computing resources are housed in highly available data center facilities. To provide additional scalability and reliability, these data center facilities are distributed in different physical locations, categorized by *regions* and *Availability Zones*.

Regions are large and widely dispersed into separate geographic locations. Availability Zones are distinct locations within a region that are engineered to be isolated from failures in other Availability Zones and provide inexpensive, low latency network connectivity to other Availability Zones in the same region.

Each region is completely independent. Each Availability Zone is isolated, but the Availability Zones in a region are connected through low-latency links. The following diagram illustrates the relationship between regions and Availability Zones.

![](/Images/SecureTransport/aws_regions.png)

The goal is to provide a highly-available, fault-tolerant and secure setup of SecureTransport in the Amazon Web Services Cloud.

<img src="/Images/SecureTransport/scheme3.PNG" class="maxWidth" />

The diagram illustrates a SecureTransport setup of an Enterprise Cluster in streaming mode with two Edge servers, each deployed in a different Availability Zone. Amazon RDS service is used to set up the Oracle / MS SQL / PostgreSQL database depending on your setup. Amazon Relational Database Service (Amazon RDS) is a managed service that makes it easy to set up, operate, and scale a relational database in the cloud.

The setup is dispersed into two Availability Zones from one region in AWS. Each Availability zone contains public and private subnets within your Virtual Private Cloud. The public subnets host the SecureTransport Edge servers and the private subnets host the SecureTransport servers and the external file system. The database instances are located in separate private subnets in the two Availability Zones. The Edge servers are in a constant synchronization connection. The SecureTransport servers are in an Enterprise Cluster setup and in a constant synchronization connection as well. The SecureTransport servers are connected in streaming with the Edge server as each server establishes streaming connections with both Edge servers. Internet-facing load balancer distributes requests to the Edge servers in the two Availability Zones.

In case of a system failure in one of the Availability Zones, the other zone remains fully functional with up to date system configuration. The SecureTransport Edge and server in the functional zone continue to process requests.

The public subnets in AWS Cloud are the equivalent of the DMZ (demilitarized zone) in a classic on-premise deployment. Amazon Web Services cloud provides security tools like Security Groups and Network Access Control Lists (ACLs) to protect the public and private subnets in your VPC. These tools act as the firewalls in the classic on-premise deployments and control both inbound and outbound traffic at an instance and subnet level. There is a Network ACL between each tier of the SecureTransport setup – public subnets, private subnets and private database subnets. The Network ACL is a stateless firewall that works at the subnet level. Each group (Administration host, Edge servers, Servers, File System, Database) and the Load Balancer have a corresponding security group. The security group is a stateful firewall that works at the unit level (EC2 instance, LoadBalancer, RDS).

There is a host placed in one of the public subnets called "Administration host" also known as "Bastion host" in the networking terminology. Bastion hosts are instances that typically reside within your public subnet and are usually accessed using SSH or RDP. Once remote connectivity is established with the bastion host, it then acts as a ‘jump’ server, allowing you to use SSH or RDP to login to other publicly inaccessible instances. When properly configured through the use of security groups and Network ACLs, the bastion host essentially acts as a bridge to your private instances via the Internet. The Administration host is used to perform maintenance and administration tasks on the servers in the SecureTransport setup. You should always consider the resiliency and high availability of your services in cloud deployments and the best practice is to have an Administration host in each availability zone in case one of the zones goes down. For minimal security risks, you should stop your Administration host instances for the duration of no maintenance work and start them when you need access to your servers in AWS again.

You can connect directly to your VPC using VPN in case you don't want to have an Administration host in your setup (see VPN section in this guide).

The installation of SecureTransport on Red Hat instances in Amazon Web Services (AWS) cloud follows the same flow as with the installation on a regular Red Hat machine, including the required installation prerequisites. This process has already been described in the SecureTransport Installation Guide.

You will pass through Amazon Web Services (AWS) cloud specific setup stages and configuration until you can proceed with your SecureTransport installation.

To set up SecureTransport in Amazon Web Services VPC, you must pass through the following steps:

1.  Create a VPC.
2.  Create Security Groups and Network Access Lists.
3.  Create public and private subnets in two availability zones.
4.  Internet Gateway and public subnets routing setup.
5.  NAT Gateway and private subnets routing setup.
6.  Amazon RDS service: Oracle, PostgreSQL or MS SQL database setup.
7.  Amazon EC2 Red Hat instances launch.
    1.  Launch an instance for an Administration Host.
    2.  Launch instances in the public subnets for SecureTransport Edge installations.
    3.  Launch instances in the private subnets for SecureTransport Server installation.
    4.  Launch instances in the private subnets for external GlusterFS file system.
8.  Establish VPN connection to your Amazon VPC.
9.  Configure the SecureTransport Enterprise Cluster setup.
10. Set up Classic Load Balancer.

  
