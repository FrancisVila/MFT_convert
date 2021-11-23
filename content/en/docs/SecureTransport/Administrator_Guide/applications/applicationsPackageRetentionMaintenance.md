{
    "title": "Package Retention Maintenance application",
    "linkTitle": "Package Retention Maintenance application",
    "weight": "280"
}The Package Retention Maintenance applicaiton deletes expired file packages from ad hoc file transfers.

You must enable the `PackageRetentionMaintApp` rules package in the Transaction Manager before you can use a Package Retention Maintenance application. For more information, see [Manage rules packages](../transaction_manager/t_st_rulesPackages.htm#EnableRulesPackage#Enable).

> **Note:**
>
> It is still possible to download anonymous attachments after message expiration, if they have not yet been deleted by any scheduled Package Retention Maintenance Applications.

Use the following procedure to create a Package Retention Maintenance application.

1.  Select **Application** and click **Add New**.  
    The *New Application* page is displayed.

2.  Select **Package Retention Maintenance** from the mandatory **Application Type** list.

3.  Enter a unique **Application Name**. You cannot enter spaces-only values in this field. For more information, see [Spaces in required fields](../../accounts/useraccounts/t_st_create_user_account#Spaces).  

    > **Note:**
    >
    > The application name cannot include any forward slash (/) characters.

4.  (Optional) Use the **Assign** and **Remove** buttons to assign business units for the application. The **Business Unit List** contains the names of business units you have created. For details, see [Business units](../../c_st_advancedaccountadministration/c_st_businessunits#Advanced_Accounts_2036285406_1127756).

5.  (Optional) Enter an application **Description**.

6.  In the **Stop running after: \_\_\_\_ minutes** field, enter the maximum number of minutes the application runs each time it is started.

7.  (Optional) In the *Schedule* pane, click **Configure** to[Configure a schedule for a maintenance application](#ConfigureMaintSchedule).

8.  (Optional) Set **Additional attributes**: you can use the group of fields to add (or remove) custom attributes as *attribute:value* pairs. To add a new attribute: click **Add Attribute**, input entries for the attribute and value pair and click the Save (![](/Images/SecureTransport/SaveIcon.png)) icon to store your input. To remove an attribute: select the corresponding checkbox and click **Delete**. You can also edit either entry (for attribute or value) of an existing attribute. See [Additional attributes](../../c_st_setup/t_st_mailtemplates/c_st_mail_template_commands_variables#Addition).

9.  Click **Create Application**.

  
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
-   [Shared Folder application](../applicationssharedfolder)
-   [Site Mailbox application](../applicationssitemailbox)
-   [Standard Router application](../applicationsstandardrouter)
-   [Transfer Log Maintenance application](../applicationstransferlogmaintenance)
-   [Unlicensed Accounts Maintenance application](../applicationsunlicensedacctsmaintenance)
