{
    "title": "Launch an instance for the Administration Host",
    "linkTitle": "Launch an instance for the Administration Host",
    "weight": "80"
}<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">Adding and Administration Host is an optional step. You can skip this chapter if you are not using an Administration Host in your deployment.         </td>
      </tr>
</table>

The Administration Host is an instance of a virtual machine you launch in the public subnet in your VNet. You can use this machine to perform the following activities:

-   SecureTransport installations on launched instances
-   Configurations on your launched instances
-   Maintenance and administration tasks on your instances

Follow the steps for launching RHEL Instance with the following specifics:

1.  Choose an Azure image and select the operating system that will be most suitable for your administering needs.
2.  Choose an Instance Size that will be most suitable for your administering needs.
3.  Configure Instance **Settings -> Virtual network**.
4.  Choose your Virtual Network.
5.  Configure Instance **Settings -> Subnet**.
6.  Choose the public subnet in your VNet.
7.  Configure Instance **Settings -> Public IP address** (depending on the connectivity you would like to have to this host).
8.  Configure Instance **Settings -> Network security group**.
9.  Assign the instance with the previously created Administration Host Network Security Group as described in *Network Security Groups*.
