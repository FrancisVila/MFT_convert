{
    "title": "Standard Router application",
    "linkTitle": "Standard Router application",
    "weight": "310"
}The Standard Router application provides basic options to automate flows for file transformations, routing and transfers between an account and internal systems.

You must enable the `StandardRouter` rules package in the Transaction Manager before you can use a Standard Router application. For more information, see [Manage rules packages](../transaction_manager/t_st_rulesPackages.htm#EnableRulesPackage#Enable).

Use the following procedure to create a Standard Router application.

> **Note:**
>
> A Standard Router application triggers a schedule, even if it is not subscribed to a user account.

When a Standard Router application is used, a file integrity check of receipts generated generates a message that there was no successful MDN comparison in the following cases:

-   When a file is uploaded in the user account outbox folder: The file is moved to the submit folder of the service account.
-   When the service account pulls a file from its transfer site: The file is moved from the receive folder of the service account to the inbox folder of the user account.

> **Note:**
>
> You can set up the Standard Router as a one-way configuration by selecting only one of the two choices: Allow Subscribers to Submit files to this Application or Send files to Subscribers. When you set up a one-way configuration, you do not need to specify a folder.

1.  Select **Application** and click **Add New**.  
    The *New Application* page is displayed.

2.  Select **Standard Router** from the mandatory **Application Type** list.

3.  Enter a unique **Application Name**. You cannot enter spaces-only values in this field. For more information, see [Spaces in required fields](../../accounts/useraccounts/t_st_create_user_account#Spaces).  

    > **Note:**
    >
    > The application name cannot include any forward slash (/) characters.

4.  (Optional) Use the **Assign** and **Remove** buttons to assign business units for the application. The **Business Unit List** contains the names of business units you have created. For details, see [Business units](../../c_st_advancedaccountadministration/c_st_businessunits#Advanced_Accounts_2036285406_1127756).

5.  (Optional) Enter an application **Description**.

6.  (Optional) Select **Allow Subscribers to Submit files in this Application** to permit incoming file transfers from the subscriber parties to the application. If you enable this option, continue specifying values for the parameters in the pane.
    1.  In the **Submit folder** field, type the name of the folder where incoming transferred files are submitted via subscriptions. The application only processes files stored in the submit folder. Any files stored outside the submit folder are not routed for transferring. The submit folder is created as a sub-folder of the subscription folder. The subscription folder is specified during the creation of the respective subscription. For details, see [Transfer sites](../../accounts/transfersites).
    2.  In the **File Submission Settings** group, select the **Require Secure Connection for transfer** option to enable SSL for the incoming transfers.
    3.  In the **File Submission Settings** group, select the **Rename submitted files to include Subscriber ID** option to add a prefix to the file name identifying the sender before it is sent to the internal system. The subscriber ID is specified during the creation of the respective subscription.
    4.  Then, in the **New Filename** field, define the format of the new file name. By default, the file is renamed in the format `<ID> <FILENAME>` where, `<ID>` is the Subscriber ID specified when the subscription is created and `<FILENAME>` is the original name of the transferred file.
    5.  The use of the placeholders, `<ID>` and `<FILENAME>,` in the new file name format is mandatory. The character you use to separate `<ID>` from `<FILENAME>` must not be included in the `<ID>` string.
    6.  In **Service Account**, select a service account to which you want to send submitted files.
    7.  In the **put in folder** field, type the name of the folder to be used by the service account you specified.
    8.  (Optional) Click **Send Options** to display the *Send Options* dialog box.
    9.  Define the settings for sending files to the service account. Choose one or more of the following options, and then click **OK** in the *Send Options* dialog box.
    10. **Encrypt File As** – Select this check box to require that files submitted are encrypted.
    11. **Send files directly to** &lt;transfer site> – Select this check box to send files directly to the transfer site you select from the drop-down list.
    12. **Post Transmission Settings** – Select which action you want {{< SecureTransport/componentshortname >}} to take when the transfer fails or succeeds.

7.  (Optional) Select the **Send files to Subscribers** check box to permit outgoing file transfers from the application to the subscribed parties. If you enable this option, continue specifying values for the parameters in the pane.
    1.  In the **Receive folder** field, type the name of the folder where outgoing transferred files are submitted to the subscriber. The receive folder is created as a sub-folder of the subscription folder.
    2.  Select a service account to receive files from in the **Service Accounts** list.
    3.  In the **get from folder** field, type the name of the folder to be used by the service account you specified.
    4.  (Optional) Click **Receive Options** to display the *Receive Options* dialog box and configure the settings for receiving files from this service account. Choose one or more of the following options and enter the maximum number of parallel transfers, and then click **OK** in the *Receive Options* dialog box.
    5.  **Automatically retrieve files from** – Select this check box and select a transfer site from the drop-down list to automatically retrieve files from the transfer site when they arrive.
    6.  **Maximum number of parallel transfers** – Enter a number to limit the number parallel transfers. If you enter a value greater than zero, SecureTransport executes only the specified number of transfers in parallel. If the value is null or zero, the maximum number of parallel transfers is limited by system capacity.
    7.  **Post Transmission Settings** – Select which action you want {{< SecureTransport/componentshortname >}} to take when the transfer has a temporary failure, a permanent failure, or succeeds.
    8.  **Decrypt PGP File As** – Select this check box to require that files are decrypted after the transfer is complete.
    9.  In the **Routing Settings** group, specify a pattern in the **ID Pattern** box to define the ID of the subscriber to whom files are routed. By default, the pattern is `<ID>_<FILENAME>` where, `<ID>` is a regular expression corresponding to the Subscriber ID specified when the subscription is created and `<FILENAME>` is the original name of the transferred file.
    10. The use of the placeholders, `<ID>` and `<FILENAME>,` in the new file name format is mandatory.

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
-   [Package Retention Maintenance application](../applicationspackageretentionmaintenance)
-   [Shared Folder application](../applicationssharedfolder)
-   [Site Mailbox application](../applicationssitemailbox)
-   [Transfer Log Maintenance application](../applicationstransferlogmaintenance)
-   [Unlicensed Accounts Maintenance application](../applicationsunlicensedacctsmaintenance)
