{
    "title": "Axway Transfer CFT application",
    "linkTitle": "Axway Transfer CFT application",
    "weight": "210"
}The Axway Transfer CFT application enables {{< SecureTransport/companyname  >}} Transfer CFT to push files to {{< SecureTransport/componentshortname  >}}.

You must enable the `AxwayTransferCFT` rules package in the Transaction Manager before you can use an {{< SecureTransport/companyname  >}} Transfer CFT application. For more information, see [Manage rules packages](../transaction_manager/t_st_rulesPackages.htm#EnableRulesPackage#Enable).

> **Note:**
>
> This application is not needed for Transfer CFT communication and is used only for legacy configurations.

Use the following procedure to create an {{< SecureTransport/companyname  >}} Transfer CFT application.

1.  Select **Application** and click **Add New**.  
    The *New Application* page is displayed.

2.  Select **{{< SecureTransport/companyname >}} Transfer CFT** from the mandatory **Application Type** list.

3.  Enter a unique **Application Name**. You cannot enter spaces-only values in this field. For more information, see [Spaces in required fields](../../accounts/useraccounts/t_st_create_user_account#Spaces).  

    > **Note:**
    >
    > The application name cannot include any forward slash (/) characters.

4.  (Optional) Use the **Assign** and **Remove** buttons to assign business units for the application. The **Business Unit List** contains the names of business units you have created. For details, see [Business units](../../c_st_advancedaccountadministration/c_st_businessunits#Advanced_Accounts_2036285406_1127756).

5.  (Optional) Enter an application **Description**.

6.  (Optional) Set **Additional attributes**: you can use the group of fields to add (or remove) custom attributes as *attribute:value* pairs. To add a new attribute: click **Add Attribute**, input entries for the attribute and value pair and click the Save (![](/Images/SecureTransport/SaveIcon.png)) icon to store your input. To remove an attribute: select the corresponding checkbox and click **Delete**. You can also edit either entry (for attribute or value) of an existing attribute. See [Additional attributes](../../c_st_setup/t_st_mailtemplates/c_st_mail_template_commands_variables#Addition).

7.  Click **Create Application**.

  
See parent topic: [Applications](../) and follow shortcuts to other applications you need to create or configure.

**Related topics:**

-   [Manage applications]()
-   [Archive Maintenance application](../applicationsarchivemaintenance)
-   [Audit Log Maintenance application](../applicationsauditlogmaintenance)
-   [Axway Sentinel Link Data Maintenance application](../applicationssentinellinkdatamaintenance)
-   [Basic Application](../applicationsbasic)
-   [File Transfer via File Services Interface application](../applicationstransferfileservicesinterface)
-   [Human to System application](../applicationsh2s)
-   [Log Entry Maintenance application](../applicationslogentrymaintenance)
-   [Login Threshold Maintenance application](../applicationsloginthresholdmaintenance)
-   [Package Retention Maintenance application](../applicationspackageretentionmaintenance)
-   [Shared Folder application](../applicationssharedfolder)
-   [Site Mailbox application](../applicationssitemailbox)
-   [Standard Router application](../applicationsstandardrouter)
-   [Transfer Log Maintenance application](../applicationstransferlogmaintenance)
-   [Unlicensed Accounts Maintenance application](../applicationsunlicensedacctsmaintenance)
