{
    "title": "Configure a Point-to-Site connection to your VNet",
    "linkTitle": "Configure a Point-to-Site connection to your VNet",
    "weight": "120"
}A Point-to-Site (P2S) configuration allows you to create a secure connection from a client computer to your virtual network. So, you need a P2S SSTP tunnel for a client to connect to your VM.

On the Azure portal, open your newly created VM and follow the process as defined in the [detailed documentation](https://docs.microsoft.com/en-us/azure/vpn-gateway/vpn-gateway-howto-point-to-site-resource-manager-portal) as provided by Microsoft.

First-timers must go through all steps as defined in the Microsoft documentation:

1.  Create a virtual network.
2.  Specify address space and subnets.
3.  Add a gateway subnet.
4.  Specify a DNS server (optional).
5.  Create a virtual network gateway.
6.  Generate certificates:
    -   Obtain the *.cer* file for the root certificate: generate a network-side certificate and paste the public part in the Gateway >P2S configuration.
    -   Generate a client certificate.
7.  Add the client address pool.
8.  Upload the root certificate *.cer*
9.  Install the VPN client configuration package.
    -   Download the client configuration package: for example, VPN client (e.g. x64).
    -   Install the client configuration package.
10. Install the client certificate - generate a client certificate for secure connection to VPN.
11. Connect to Azure - verify that you can connect to your VM using its private IP address.
12. Verify your connection.
