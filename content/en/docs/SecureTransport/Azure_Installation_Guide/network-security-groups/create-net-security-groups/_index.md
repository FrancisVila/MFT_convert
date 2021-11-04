{
    "title": "Create Network Security groups",
    "linkTitle": "Create Network Security groups",
    "weight": "80"
}When you launch a virtual machine in a VNet, you can associate it with one network security group that you have created. If you do not specify a network security group when you launch an instance, all traffic to this instance is allowed.

It is recommended that you create the network security groups you need for your <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> infrastructure in Azure as a first stage before proceeding with rest of the setup. You need to group (assign) the instances and components into the following security groups:

-   SecureTransport Edge network security group
-   SecureTransport Server network security group
-   External Database network security group
-   External File System network security group
-   Administration Host security group

It is recommended to have all components prepared prior the launch process of the instances. In this way, during your <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> setup, you will just select the network security group you need from the list. You can always create the Network Security Groups on a later stage but we suggest you adhere to the flow as described.

To create a network security group in Azure VNet:

1.  Navigate to the Azure Portal and go to **Create a resource**.
2.  Under the "Azure Marketplace" section, choose **Networking**.
3.  Under the "Featured" section, choose **Network Security Group**.
4.  On the newly opened dialog box, enter the required information and click **Create**.  
    ![](/Images/SecureTransport/edgeSG.PNG)  
5.  Now that your NSG is created, you can select it on the "All resources" list.
6.  Edit the **"Inbound security rules"** section of the network security group.
7.  Use **"Add"** to enable/disable access to/from your instances on specific ports/source.  
    <img src="/Images/SecureTransport/create-SG.PNG" class="mediumWidth" />  

You must add the necessary inbound/outbound rules to the network security groups and the instances assigned to each group will have the required for the group level of connectivity and security. Please refer to the firewall specific information already provided in <span class="mc-variable axway_variables.Component_Short_Name variable" style="font-style: italic;">SecureTransport</span> *Administrator guide*.

You must give unique **Name** and **Priority** to each rule. Please, keep in mind that rules are applied according to their priority. The lower the number, the higher the priority.

> **Note:**
>
> There are three default rules in each Network security group with the lowest priority that cannot be modified and deleted. If you do not want them to take action, you can create a rule with higher priority that denies all traffic.

> **Note:**
>
> The rules defined in the following Network Security Groups cover the most basic security scenario. If you would like more restrictive rules, you can add more Inbound and Outbound rules.

> **Note:**
>
> The rules below use default ports or ports specific for the test setup. Please change/add rules according to your specific setup. Check the FTP does not work through the firewall section in the SecureTransport Administrator Guide if you want to configure FTP.
