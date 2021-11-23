{
    "title": "Axway Sentinel Link Data Maintenance application",
    "linkTitle": "Axway Sentinel Link Data Maintenance application",
    "weight": "200"
}The Axway Sentinel Link Data Maintenance application removes all SentinelLinkData entries to files that do not exist anymore, based on a schedule you define.

Use the following procedure to create an {{< SecureTransport/companyname  >}} Sentinel Link Data Maintenance type application.

1.  Select **Application** and click **Add New**.  
    The *New Application* page is displayed.

2.  Select **{{< SecureTransport/companyname >}} Sentinel Link Data Maintenance** from the mandatory **Application Type** list.

3.  Enter a unique **Application Name**. You cannot enter spaces-only values in this field. For more information, see [Spaces in required fields](../../accounts/useraccounts/t_st_create_user_account#Spaces).  

    > **Note:**
    >
    > The application name cannot include any forward slash (/) characters.

4.  (Optional) Use the **Assign** and **Remove** buttons to assign business units for the application. The **Business Unit List** contains the names of business units you have created. For details, see [Business units](../../c_st_advancedaccountadministration/c_st_businessunits#Advanced_Accounts_2036285406_1127756).

5.  (Optional) Enter an application **Description**.

6.  (Optional) In the *Schedule* pane, click **Configure** to [Configure a schedule for a maintenance application](#ConfigureMaintSchedule).

7.  (Optional) Set **Additional attributes**: you can use the group of fields to add (or remove) custom attributes as *attribute:value* pairs. To add a new attribute: click **Add Attribute**, input entries for the attribute and value pair and click the Save (![](/Images/SecureTransport/SaveIcon.png)) icon to store your input. To remove an attribute: select the corresponding checkbox and click **Delete**. You can also edit either entry (for attribute or value) of an existing attribute. See [Additional attributes](../../c_st_setup/t_st_mailtemplates/c_st_mail_template_commands_variables#Addition).

8.  Click **Create Application**.

  
See parent topic: [Applications](../) and follow shortcuts to other applications you need to create or configure.
