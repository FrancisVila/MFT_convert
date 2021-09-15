{
    "title": "Administration Host Security Group",
    "linkTitle": "Administration Host Security Group",
    "weight": "140"
}<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">Adding and Administration Host is an optional step. You can skip this subtopic if you are not using an Administration Host in your deployment.         </td>
      </tr>
</table>

Allow the following inbound traffic:

<table cellspacing="0">
   <col/>
   <col/>
   <col/>
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Type</th>
         <th>Protocol</th>
         <th>Port / Port Range</th>
         <th>Source</th>
         <th>Description</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>RDP         </td>
         <td>TCP         </td>
         <td>3389         </td>
         <td>Your IP address         </td>
         <td>Remote connection to the Administration Host         </td>
      </tr>
   </tbody>
</table>

The inbound rule is applicable for Windows instance in our case. Enter the source address from which you plan to connect to the Administration Host.

### Access your servers using Administration host

When designing the Administration host for your Azure infrastructure, you should use it only for maintenance and administration. You need to keep it locked down as much as possible and avoid opening unnecessary security holes. You could look into hardening your chosen operating system for even tighter security. In order to minimize security risks, you should start your Administration host instances only when you need access to your servers in Azure.

Network Security groups are essential for maintaining tight security and play a big part in making this solution work. First, you need to create a network security group or update an existing one that will be used to allow connectivity from the Administration host for your existing private instances (see the SecureTransport Server Network Security Group in the *Network Security groups* section of the guide). This NSG should only accept SSH or RDP inbound requests from your Administration hosts. Apply this group to all your private instances that require connectivity.

Next, create a network security group to be applied to your Administration host. Inbound and outbound traffic must be restricted at the protocol level as much as possible. The inbound rule base should accept SSH or RDP connections only from the specific IP addresses (usually those of your administrators' work computers). See the *Administration Host Network Security Group* in the *Network Security groups* section of the guide. Your outbound connection should again be restricted to SSH or RDP access to the private instances of your Azure infrastructure. An easy way to do this is to populate the 'Destination' field with the IP of your private instances.

For more info, see ***[Launch an instance for the Administration Host](../../../launch-adminhost-instance)*.**
