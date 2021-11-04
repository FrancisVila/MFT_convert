{
    "title": "Subnets",
    "linkTitle": "Subnets",
    "weight": "90"
}After creating a VNet, you can add one or more subnets. Both Public and Private Subnets have outbound access to the Internet by default. If you want inbound Internet traffic to you rVM, you give it a Public IP, no matter of the Subnet. When you create a subnet, you specify the CIDR block for the subnet, which is a subset of the VNet CIDR block.

Learn more about [Subnets](https://docs.microsoft.com/en-us/azure/virtual-network/virtual-network-manage-subnet).

In the following example, the VNet has a single subnet.

<img src="/Images/SecureTransport/subnets-example.png" class="maxWidth" />

## Create subnets

Create three subnets (two private and one public) as follows:

1.  Navigate to the Azure Portal, go to "All resources" and select your VNet.
2.  Under the "Settings" section, choose **Subnets**.
3.  Click **+Subnet**.
4.  Fill the following settings.
    -   **Name:** specify unique name for each subnet

    -   **IPv4 CIDR block:** for each subnet specify a different block

    -   **Network Security Group:** None

    -   **Route table:** None  
        For example:

        -   1.0.0/24 - Public
        -   1.1.0/24 - Private1
        -   1.2.0/24 - Private2

        **Note:** This is an example CIDR block size. You can configure the CIDR block according to your needs.
5.  Click **OK** to add your subnet.
6.  Repeat the steps for the additional subnets you wish to create.

![](/Images/SecureTransport/create-subnet.PNG)

 
