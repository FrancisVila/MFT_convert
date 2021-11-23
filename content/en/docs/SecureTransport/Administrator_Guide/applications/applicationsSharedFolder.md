{
    "title": "Shared Folder application",
    "linkTitle": "Shared Folder application",
    "weight": "290"
}The Shared Folder application provides shared data storage between accounts.

You must enable the `SharedFolder` rules package in the Transaction Manager before you can use a Shared Folder application. For more information, see [Manage rules packages](../transaction_manager/t_st_rulesPackages.htm#EnableRulesPackage#Enable).

All users of a shared folder must be either repository encryption users or not repository encryption users.

1.  Select **Application** and click **Add New**.  
    The *New Application* page is displayed.

2.  Select **Shared Folder** from the mandatory **Application Type** list.

3.  Enter a unique **Application Name**. You cannot enter spaces-only values in this field. For more information, see [Spaces in required fields](../../accounts/useraccounts/t_st_create_user_account#Spaces).  

    > **Note:**
    >
    > The application name cannot include any forward slash (/) characters.

4.  (Optional) Use the **Assign** and **Remove** buttons to assign business units for the application. The **Business Unit List** contains the names of business units you have created. For details, see [Business units](../../c_st_advancedaccountadministration/c_st_businessunits#Advanced_Accounts_2036285406_1127756).

5.  (Optional) Enter an application **Description**.

6.  In the **Folder** field, type the full path of the folder that you want to share for the accounts that subscribe to the new application.  
    You cannot use the following characters in the folder path or name: `* < > ? " / \ | :`  

    > **Note:**
    >
    > Under Windows, you use Windows-style paths when you specify a shared folder. Denote drives as C:\\ and D:\\.

7.  (Optional) Set **Additional attributes**: you can use the group of fields to add (or remove) custom attributes as *attribute:value* pairs. To add a new attribute: click **Add Attribute**, input entries for the attribute and value pair and click the Save (![](/Images/SecureTransport/SaveIcon.png)) icon to store your input. To remove an attribute: select the corresponding checkbox and click **Delete**. You can also edit either entry (for attribute or value) of an existing attribute. See [Additional attributes](../../c_st_setup/t_st_mailtemplates/c_st_mail_template_commands_variables#Addition).

8.  Click **Create Application**.

  
See parent topic: [Applications](../) and follow shortcuts to other applications you need to create or configure.

**Related topics:**

-   [Manage applications]()
-   [Archive Maintenance application](../applicationsarchivemaintenance)
-   [Audit Log Maintenance application](../applicationsauditlogmaintenance)
-   [Axway Sentinel Link Data Maintenance application](../applicationssentinellinkdatamaintenance)
-   [Axway Transfer CFT application](../applicationstransfercft)
-   [Basic Application](../applicationsbasic)
-   [File Transfer via File Services Interface application](../applicationstransferfileservicesinterface)
-   [Human to System application](../applicationsh2s)
-   [Log Entry Maintenance application](../applicationslogentrymaintenance)
-   [Login Threshold Maintenance application](../applicationsloginthresholdmaintenance)
-   [Package Retention Maintenance application](../applicationspackageretentionmaintenance)
-   [Site Mailbox application](../applicationssitemailbox)
-   [Standard Router application](../applicationsstandardrouter)
-   [Transfer Log Maintenance application](../applicationstransferlogmaintenance)
-   [Unlicensed Accounts Maintenance application](../applicationsunlicensedacctsmaintenance)
