{
    "title": "Network Security Groups",
    "linkTitle": "Network security groups",
    "weight": "60"
}Azure provides two features that you can use to increase security in your VNet: *network security groups* and *endpoint ACLs*. Security groups control inbound and outbound traffic for your instances or subnets, and endpoint ACLs control inbound and outbound traffic for your VM endpoint. For more information, see the [Azure Security Documentation](https://docs.microsoft.com/en-us/azure/security/):

-   [Network Security groups](https://docs.microsoft.com/en-us/azure/virtual-network/virtual-networks-nsg) - these act as a firewall for associated VMs or Subnets, controlling both inbound and outbound traffic.
-   [Endpoint access control lists (ACLs)](https://docs.microsoft.com/en-us/azure/virtual-network/virtual-networks-acl) - provides the ability to selectively permit or deny traffic for a virtual machine endpoint. This packet filtering capability provides an additional layer of security. You can specify network ACLs for endpoints only. You cannot specify an ACL for a virtual network or a specific subnet contained in a virtual network. It is recommended to use network security groups (NSGs) instead of ACLs, whenever possible.

For more details on security options check the [Azure Security Best Practices guide.](https://docs.microsoft.com/en-us/azure/security/azure-security-network-security-best-practices)

> **Note:**
>
> The firewall of the instance is with higher priority than the instance’s Network Security Group. So, if you would like to use NSG, the instance’s firewall must be configured in the same way as the NSG’s rules.

> **Note:**
>
> The suggested configurations with Network Security Groups as stated in the current guide do not include outbound rules. For more information on best practices for the outbound rules to apply for your setup, please refer to the SecureTransport Installation guide.
