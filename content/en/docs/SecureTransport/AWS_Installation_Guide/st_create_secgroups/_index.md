{
    "title": "Create Security Groups and Network Access Lists",
    "linkTitle": "Create Security Groups and Network Access Lists",
    "weight": "70"
}Amazon VPC provides the following tools to help you increase the security of your VPC:

-   [Security Groups](st_securitygroups) – these act as a firewall for associated Amazon EC2 instances, controlling both inbound and outbound traffic at the instance level.
-   [Network Access Lists](st_network_access) – also called ACLs, these act as a firewall for associated subnets, controlling both inbound and outbound traffic at the subnet level.

Flow logs - Capture information about the IP traffic going to and from network interfaces in your VPC. AWS provides two features that you can use to increase security in your VPC: security groups and network ACLs. Security groups control inbound and outbound traffic for your instances, and network ACLs control inbound and outbound traffic for your subnets. Learn more about [VPC Security](https://docs.aws.amazon.com/AmazonVPC/latest/UserGuide/VPC_Security.html) in the AWS documentation.

For more details on security options, check the [AWS Security Best Practices guide](https://d1.awsstatic.com/whitepapers/Security/AWS_Security_Best_Practices.pdf).

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">The suggested configurations with Security Groups and Network Access Lists as stated in the current guide do not include outbound rules. For more information on best practices for the outbound rules to apply for your setup, please refer to the SecureTransport Administrator's guide.         </td>
      </tr>
</table>
