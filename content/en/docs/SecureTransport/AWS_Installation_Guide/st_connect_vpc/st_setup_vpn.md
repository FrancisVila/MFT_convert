{
    "title": "Set up VPN connection",
    "linkTitle": "Set up VPN connection",
    "weight": "120"
}## Set up VPN connection

A VPN configuration allows you to create a secure connection from a client computer to your AWS virtual private network. Amazon VPC provides different VPN connection options to your VPC depending on your needs. Learn more about [supported VPN connectivity options](http://docs.aws.amazon.com/AmazonVPC/latest/UserGuide/vpn-connections.html) in the AWS documentation.

One of the connectivity options, described in this guide, is to configure an AWS hardware VPN. In this case you create the following items from the AWS console:

-   **Customer gateway**

The VPN endpoint on your network. Here you specify your customer gateway device public IP address and [autonomous system](https://en.wikipedia.org/wiki/Autonomous_system_%28Internet%29) number (ASN) if you intend to use the [Border Gateway Protocol (BGP)](https://en.wikipedia.org/wiki/Border_Gateway_Protocol) or dynamic routing.

-   **Virtual private gateway**

The VPN endpoint on your AWS VPC.

-   **VPN connection**

The connection between your network and your AWS VPC. You can automate configuration of the customer gateway device for your network with a configuration file that is generated when you create your Customer Gateway and Virtual Private Gateway.

1.  Create a customer gateway:  
    1.  Open the Amazon VPC console.
    2.  In the navigation pane, under VPN Connections, choose Customer Gateways.
    3.  Choose Create Customer Gateway.  
        -   Enter a meaningful name for the customer gateway.
        -   Choose an option for Static or Dynamic routing.
        -   Enter the public IP address of your customer gateway device.
        -   Enter your BGP ASN if you selected the option for dynamic routing.
    4.  Click **Yes, Create**.

<!-- -->

1.  Create a virtual private gateway:  

    1.  In the VPC console, under VPN Connections, choose Virtual Private Gateways.
    2.  Choose Create Virtual Private Gateway.
    3.  Enter a meaningful name for the virtual private gateway.
    4.  Click **Yes, Create**.
    5.  Select the new virtual private gateway and open the context menu (using right-button click with the mouse). Click **Attach to VPC**.  
        On the newly opened screen, select your VPC and then click **Yes, attach**.  

    <img src="/Images/SecureTransport/vpn-attach-vpc.PNG" class="maxWidth" />  

    Initially, the virtual private gateway is in "attaching" state for some time and then after success the state is updated to "attached".

      
    <img src="/Images/SecureTransport/vpn-attached.PNG" class="maxWidth" />  

<!-- -->

1.  Create a VPN connection:  
    1.  In the VPC console, under VPN Connections, choose VPN Connections.
    2.  Select Create VPN Connection.  
        -   Enter a meaningful name for the VPN connection.
        -   For Virtual Private Gateway, select the virtual private gateway you just created.
        -   For Customer Gateway, select the entry you just created.
        -   For Routing Options, choose Dynamic or Static. If you choose static routing, specify the Static IP Prefixes of the appropriate private network(s) on your LAN.
        -   Click **Yes, Create**.

    <img src="/Images/SecureTransport/vpn-connection.PNG" class="maxWidth" />
2.  Get the VPN connection configuration and configure your customer gateway:  
    1.  In the VPC console, under VPN Connections, select VPN Connection.
    2.  Select the VPN connection you created, and then choose Download Configuration.
    3.  In the Download Configuration dialog box, select the vendor for the customer gateway, the platform, and the software version, and then click **Yes, Download**.
    4.  Save the text file that contains the VPN configuration and give it to your network administrator, along with the [Amazon VPC Network Administrator Guide](http://docs.aws.amazon.com/AmazonVPC/latest/NetworkAdminGuide/). The VPN would not work until the network administrator configures the customer gateway.
3.  Test your VPN connection as described in the [AWS Documentation](http://docs.aws.amazon.com/AmazonVPC/latest/UserGuide/HowToTestEndToEnd_Linux.html).
