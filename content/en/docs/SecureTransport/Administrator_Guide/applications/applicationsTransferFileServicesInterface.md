{
    "title": "File Transfer via File Services Interface application",
    "linkTitle": "File Transfer via File Services Interface application",
    "weight": "240"
}The File Transfer via File Services Interface application processes metadata files sent from another system for a protocol implemented using the file services interface.

You must enable the `FileServicesInterface` rules package in the Transaction Manager before you can use a File Transfer via File Services Interface application. For more information, see [Manage rules packages](../transaction_manager/t_st_rulesPackages.htm#EnableRulesPackage#Enable).

Use the following procedure to create a File Transfer via File Services Interface application.

1.  Select **Application** and click **Add New**.  
    The *New Application* page is displayed.

2.  Select **File Transfer via File Services Interface** from the mandatory **Application Type** list.

3.  Enter a unique **Application Name**. You cannot enter spaces-only values in this field. For more information, see [Spaces in required fields](../../accounts/useraccounts/t_st_create_user_account#Spaces).  

    > **Note:**
    >
    > The application name cannot include any forward slash (/) characters.

4.  (Optional) Use the **Assign** and **Remove** buttons to assign business units for the application. The **Business Unit List** contains the names of business units you have created. For details, see [Business units](../../c_st_advancedaccountadministration/c_st_businessunits#Advanced_Accounts_2036285406_1127756).

5.  (Optional) Enter an application **Description**.

6.  (Optional) Set **Additional attributes**: you can use the group of fields to add (or remove) custom attributes as *attribute:value* pairs. To add a new attribute: click **Add Attribute**, input entries for the attribute and value pair and click the Save (![](/Images/SecureTransport/SaveIcon.png)) icon to store your input. To remove an attribute: select the corresponding checkbox and click **Delete**. You can also edit either entry (for attribute or value) of an existing attribute. See [Additional attributes](../../c_st_setup/t_st_mailtemplates/c_st_mail_template_commands_variables#Addition).

7.  Click **Create Application**.

  
For more information about configuring transfers using a file services interface protocol, see [File services interface transfers](../../c_st_fileservicesinterfacetransfers#FileServicesInterfaceTransfers_2548184958_1041296).

  
See parent topic: [Applications](../) and follow shortcuts to other applications you need to create or configure.

**Related topics:**

-   [Manage applications]()
-   [Archive Maintenance application](../applicationsarchivemaintenance)
-   [Audit Log Maintenance application](../applicationsauditlogmaintenance)
-   [Axway Sentinel Link Data Maintenance application](../applicationssentinellinkdatamaintenance)
-   [Axway Transfer CFT application](../applicationstransfercft)
-   [Basic Application](../applicationsbasic)
-   [Human to System application](../applicationsh2s)
-   [Log Entry Maintenance application](../applicationslogentrymaintenance)
-   [Login Threshold Maintenance application](../applicationsloginthresholdmaintenance)
-   [Package Retention Maintenance application](../applicationspackageretentionmaintenance)
-   [Shared Folder application](../applicationssharedfolder)
-   [Site Mailbox application](../applicationssitemailbox)
-   [Standard Router application](../applicationsstandardrouter)
-   [Transfer Log Maintenance application](../applicationstransferlogmaintenance)
-   [Unlicensed Accounts Maintenance application](../applicationsunlicensedacctsmaintenance)
