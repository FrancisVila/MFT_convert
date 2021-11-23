{
    "title": "File Maintenance application",
    "linkTitle": "File Maintenance application",
    "weight": "230"
}In {{< SecureTransport/componentshortname  >}} {{< SecureTransport/componentversion  >}}, you can create a file maintenance policy that deletes files from the account home folder based on a specified retention or expiration period. You can schedule the maintenance and configure notifications to be sent to specific recipients before or/and after the deletion of files.

A File Maintenance policy can be set at four levels:

-   Global – by creating a File Maintenance application without assigning it to a specific business unit. Only one instance of the File Maintenance application can be created.
-   Business Unit – by modifying or disabling the global policy for a specific business unit (**Accounts > Business Unit > File Maintenance policy settings**)
-   Account – by modifying or disabling the global or a business unit-level policy for a specific account (**Accounts > User Account** section **&gt; File Maintenance policy**)
-   Account template – by modifying or disabling the global policy for accounts assigned to a specific account template (**Accounts > Account templates** settings **&gt; File Maintenance policy**)

An account or a business unit File Maintaining policy takes precedence over the global one. The account-level policy overrides any value defined for the same policy in the Business Unit settings.

File Maintenance is not performed on the following content:

-   Anonymous AdHoc accounts configured in **Setup > AdHoc Settings**
-   Service accounts
-   The account\`s mailbox and STFS folders
-   Shared folders not owned by the user
-   Files in a Shared Folder application subscription folder

Before you create a File Maintenance application, make sure that the `FileMaintenanceApp` rules package is enabled in the Transaction Manager. For more information, see [Manage rules packages](../transaction_manager/t_st_rulesPackages.htm#EnableRulesPackage#Enable).

Use the following procedure to create a File Maintenance application.

1.  Select **Application** and click **Add New**.  
    The *New Application* page is displayed.

2.  Select **File Maintenance** from the mandatory **Application Type** list.

3.  Enter a unique **Application Name**. You cannot enter spaces-only values in this field. For more information, see [Spaces in required fields](../../accounts/useraccounts/t_st_create_user_account#Spaces).  

    > **Note:**
    >
    > The application name cannot include any forward slash (/) characters.

4.  (Optional) Use the **Assign** and **Remove** buttons to assign business units to the application. The **Business Unit List** contains the names of the business units you have [Business units](../../c_st_advancedaccountadministration/c_st_businessunits#Advanced_Accounts_2036285406_1127756). To create a global policy, do not assign a business unit.  

    > **Note:**
    >
    > If a business unit is assigned to the application, the File Maintenance policy will be applied ONLY to the accounts in this business unit and will NOT be applied to the accounts that don't belong to any business unit.

5.  (Optional) Enter an application **Description**.

6.  In the *Purge settings* pane:  
    1.  In the **Delete all files older than** field, specify the number of days files should be retained in the account home folder. This field is mandatory.  
        You cannot enter spaces-only values in this field. For more information, see [Spaces in required fields](../../accounts/useraccounts/t_st_create_user_account#Spaces).

    2.  Select the **Only if file name matches pattern** check box and specify a file name pattern to identify files to be deleted.

    3.  Select the **Delete all files based on file expiration period** check box to enable the deletion of files based on their expiration period. The expiration period is set in epoch time (in milliseconds) as a flow attribute named `EXPIRE.ON`. If an expiration period is not set for a file, it will be deleted based on the retention period set in the File Maintenance application.

    4.  Select the **Remove folders** check box to enable the deletion of any subfolder of the account home folder that has been left empty after file maintenance.  

        > **Note:**
        >
        > File Maintenance will not delete empty Subscription folders, except in the case that the users are assigned to an account template and their home folders are constructed using Expression Language.

7.  (Optional) In the *Purge notifications* pane, select the notification method and threshold:  
    1.  Select the **Send to Sentinel Alert** check box to enable sending of a *TO\_BE\_DELETED* state to Sentinel. To avoid event redundancy, even if the application is configured to run several times a day, only one *TO\_BE\_DELETED* state will be sent to Sentinel.
    2.  Select **Send email notifications** to enable the sending of email notifications. Then, specify the contents and the recipients of the notification:  
        -   Select the **Email Template** from the drop-down to be used for the pending file deletion email. For details on configuring email templates, see [Mail templates](../../c_st_setup/t_st_mailtemplates).
        -   Select the **To account email** to send a pending file deletion notification to the account's email address. The user will receive one email per day containing all files pending for deletion.
        -   Select **To (comma-separated list of emails)** to add a list of email address to which the notification to be sent. The notification will contain all files pending for deletion files per each account. It will be sent upon each execution of the application. This option is not available at the account level.
    3.  In the **Threshold** field, specify the file age, after which a notification to be send. This field is active only after a notification method is selected. The threshold value should be either a positive integer less than the one specified in **Delete all files older than** or a comma-separated list of positive integers.

8.  In the *Deleted files notifications*, select **Send email notifications for deleted files** to enable the sending of an email report on deleted files. Then, specify the contents and the recipients of the notification:  
    1.  Select the **Email Template** from the menu to be used for file deletion reports. For details on configuring email templates, see [Mail templates](../../c_st_setup/t_st_mailtemplates).
    2.  Select **To account email** to send a list of the deleted files to the account email. The notification is sent once per day, even if the application is configured to run several times a day. This setting can be overridden at a business unit level only.
    3.  Select **To (comma-separated list of emails)** to add a list of email addresses to which the notification to be sent. A notification is sent upon each execution of the application and contains all the files deleted files per account. This option is not available at the account level.

9.  (Optional) In the *Schedule* pane, click **Configure** to[Configure a schedule for a maintenance application](#ConfigureMaintSchedule).

10. (Optional) Set **Additional attributes**: you can use the group of fields to add (or remove) custom attributes as *attribute:value* pairs. To add a new attribute: click **Add Attribute**, input entries for the attribute and value pair and click the Save (![](/Images/SecureTransport/SaveIcon.png)) icon to store your input. To remove an attribute: select the corresponding checkbox and click **Delete**. You can also edit either entry (for attribute or value) of an existing attribute. See [Additional attributes](../../c_st_setup/t_st_mailtemplates/c_st_mail_template_commands_variables#Addition).

11. Click **Create Application**.

  
See parent topic: [Applications](../) and follow shortcuts to other applications you need to create or configure.
