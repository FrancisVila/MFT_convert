{
    "title": "Manage subscriptions",
    "linkTitle": "Manage subscriptions",
    "weight": "230"
}Use the *Subscriptions* pane of the *User Account* window to manage subscriptions.

The following sections provide how-to instructions for managing subscriptions:

-   [Subscribe an account to an application](#subscrib)
-   [Considerations for subscriptions and AS2 transfer sites](#consider)
-   [Human to System type application](#human)
-   [Scheduled downloads and tasks](#schedule)
-   [Set up a scheduled transfer task for a subscription](#set)
-   [Retrieve files now](#retrieve)
-   [Purge a subscription folder](#purge)
-   [Unsubscribe an account from an application](#unsubscribe)
-   [Unsubscribe an account and delete the subscription folder](#unsubscribe2)

## <span id="Subscrib"></span>Subscribe an account to an application

Before creating a subscription for an account, you must create at least one application for the system.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">PGP decryption and encryption paths, regardless of whether you use a relative or an absolute path type, are relative and restricted to the directory where the file resides.         </td>
      </tr>
</table>

**Prerequisites**

-   Create an application. For details, see [Manage applications](manage_applications.htm).
-   If the account is to have server-initiated transfers associated with it, you must create at least one transfer site for the account. For details, see [Transfer sites](../../transfersites).

**Workflow**

1.  [Select a user account](#select)
2.  [Configure general settings](#configur)
3.  [Configure files received settings](#configur2)
4.  [Configure files sent settings](#configur3)
5.  [Complete the subscription](#complete)

### <span id="Select"></span>Select a user account

1.  Select **Accounts > User Accounts**. The *User Accounts* page is displayed.

2.  Click the name of the account for which you want to create a subscription.  
    The *User Account Settings* page is displayed with details for the selected account.

3.  Click the **Subscriptions** tab for the selected account.

4.  Select the application you want to subscribe the account to from the **Subscribe to** list.

5.  Click **Subscribe**.  
    The settings page for the subscription is displayed.  
    

    <table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">Some applications do not include all the fields described here.         </td>
      </tr>
</table>

### <span id="Configur"></span>Configure general settings

In the *General Settings* pane:

1.  In the **Subscription Folder** field, type the full path to the subscription folder or use the default folder name. The subscription folder name can contain 254 characters or less.  
    

    <table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">Axway does not recommend you to add leading or trailing space intervals to your subscription folder name as you may experience unexpected behavior with different SFTP / FTPS clients (although leading spaces are accepted with certain SFTP clients). You cannot use the following characters in the subscription folder name: <code>* &lt; &gt; ? " / \ | : </code>         </td>
      </tr>
</table>

2.  Select the **Encrypt mode**. Selecting the **Encrypt mode** allows you to configure repository encryption for accounts at the per-subscription level. For additional information, refer to [Repository encryption certificate](../../../c_st_setup/c_st_certificates/t_st_repository_encryption_certificate)*.*  
    Select **Default** to inherit the encryption mode for the subscription folder from the account or the global settings.  
    Select **Enable** to encrypt all files uploaded to the subscription folder.  
    Select **Disable** to upload unencrypted files to the subscription folder.  
    You can subscribe multiple accounts to the application. Some accounts may have repository encryption enabled for the subscription folder and others may have it disabled. As a result, the files uploaded from some accounts are encrypted while from other accounts the uploaded files are not encrypted.  
    For example if:
    -   **User1** has encryption **enabled** and is subscribed to **Shared Folder Application A**.
    -   **User2** has encryption **disabled** and is subscribed to **Shared Folder Application B**.
    -   **User3** is subscribed to both **Shared Folder Application A** and **Shared Folder Application B** and has encryption **enabled** for **Application A** and **disabled** for **Application B**.

      
    
    SecureTransport applies encryption to files that **User3** uploads and **User1** can download all files because they have repository encryption **enabled** for **Application A**. **User2** can only download unencrypted files because they have repository encryption setting **disabled** for **Application B**. In this example, **User1** and **User3** can download all shared folder files because they have identical settings for repository encryption. **User1** and **User2** files are encrypted or not based on their repository encryption setting.  
    
    For example, three users are subscribed to a Shared Folder Application:  
    
    -   **UserA** - Subscription repository encryption is set to **Enable**
    -   **UserB** - Subscription repository encryption is set to **Disable**
    -   **UserC** - Subscription repository encryption is set to **Disable**

      
    
    **Upload actions:**
    -   **UserA** uploads a file to the subscription folder – The file is **encrypted**.
    -   **UserB** uploads a file to the subscription folder – The file is **unencrypted**.
    -   **UserC** uploads a file to the subscription folder – The file is **unencrypted**.

      
    **Result:**
      
    The subscription folder that the three users share contains both **unencrypted** and **encrypted** files.  
    **Download actions:**
    -   **UserA** can download all files from the subscription folder.
    -   **UserB** and **UserC** can only download unencrypted files from the subscription folder.

3.  If you selected the Standard Router application type, Enter an ID in the **Subscriber ID** field.  
    When the **Rename submitted files to include Subscriber ID** check box is selected during the application definition, the uploaded file is renamed before it is sent to the internal system. The file is renamed in the format `<ID> <FILE_NAME>` where `<ID>` is the `Subscriber ID` that is specified here for the current Subscription, and `<FILE_NAME>` is original file name. For details, see [Standard Router application](../../../applications/applicationsstandardrouter).

4.  In the *Flow Settings* pane, select the **Existing flow attributes**.  
    If **Preserve** is selected, the attributes defined in the *Flow Attributes* pane will be applied only for newly received files which do not have associated flow attributes.  
    If **Overwrite** is selected, the attributes defined in the *Flow Attributes* pane will overwrite any existing attributes for incoming files (for example, files published to this folder from another subscription folder).  
    When **Append** is selected, only the attributes which are not defined for incoming files will be applied. Existing attributes will be preserved.

5.  In the *Flow/Subscription Attributes* pane:
    1.  To add an attribute, click **Add Attribute**. For additional information on Flow Attributes, refer to [Flow and subscription attributes](../../../c_st_setup/t_st_mailtemplates/c_st_mail_template_commands_variables).  
        **Add Attribute** enables the administrator to add custom properties (Key=Value). Their values can be set using Expression Language. Administrators can use flow attributes, session and environment variables that are evaluated at the time a file is transferred through the subscription.  
        Examples:

        -   `${env.DXAGENT_ACCOUNT_EMAIL}`
        -   `${sess.STSESSION_LDAP_DOMAIN_ID}`
        -   `${flow.userVars.sampleKey1}` if set in a previous step
        -   `${flow.MetaDataKey1}` if set in an external transfer site

          
        Flow attributes are bound to files; Subscription attributes are bound to subscriptions.  

        <table cellpadding="0" cellspacing="0">   <col/>   <col/>   <col/>      <tr>         <td valign="top">         </td>         <td valign="top"><span><b>Caution  </b></span>         </td>         <td data-mc-autonum="&lt;b&gt;Caution  &lt;/b&gt;" valign="top">With pulls that do not return files, no flow attributes are available as no files are actually transferred. In this case, only Subscription attributes are set.         </td>      </tr></table>

        <table cellpadding="0" cellspacing="0">   <col/>   <col/>   <col/>      <tr>         <td valign="top">         </td>         <td valign="top"><span><b>Caution  </b></span>         </td>         <td data-mc-autonum="&lt;b&gt;Caution  &lt;/b&gt;" valign="top">Expressions, used in attribute values, cannot evaluate a subscription attribute, i.e., <code>${subscription....}</code>. This is because the subscription attribute is bound to the subscription itself and is not transferred with the file to a new subscription.         </td>      </tr></table>

          
        Flow attributes can be accessed using the following expression: `${flow.attributes[‘userVars.ATTRIBUTE_NAME’]}.` Note that flow attributes can be used for expression evaluation in Advanced Routing only when the application operates with files.  
        Subscription attributes can be accessed using the following expression: `${subscription.attributes['userVars.ATTRIBUTE_NAME'].` Subscription attributes can be used for expression evaluation in all Advanced Routing fields.  
        Examples of Attributes:

        <table cellspacing="0">   <col/>   <col/>   <thead>      <tr>         <th>Attribute</th>         <th>Value</th>      </tr>   </thead>   <tbody>      <tr>         <td>userVars.1         </td>         <td>internalEmail@axway.com         </td>      </tr>      <tr>         <td>userVars.2         </td>         <td>ReportsMonitor         </td>      </tr>   </tbody></table>

        To access attributes, see the following examples:  
        `${account.attributes['userVars.1']}`  
        `${account.attributes['userVars.2']}`  
        For example, the `account.attributes` is the selector for attributes of the account used to execute the current route - it has to be written exactly as shown.  
        The `userVars.` prefix must be prepended to attribute name.  
        All this should be written as an EL expression: `${...}`

    2.  Click the attribute Save (![](SaveIcon.png)) icon.

### <span id="Configur2"></span>Configure files received settings

In the *For Files Received from this Account or its Partners* pane:

1.  To set a schedule for automatic retrieval of the transferred files, select the **Automatically Retrieve Files From** check box and then select the respective transfer site from the drop down list. If you select a PeSIT transfer site, you can select a **Transfer Profile** from the list or leave the field empty to use the default PeSIT transfer profile. For more information, see [Transfer profiles](../../t_st_transferprofiles).  
    The *Schedule* pane is displayed.  
    A subscription that retrieves files from an AS2 transfer site does not use a schedule. To retrieve files from an AS2 transfer site, see
    [Considerations for subscriptions and AS2 transfer sites](#consider).  
    For a subscription that retrieves files from a Folder Monitor transfer site, to configure scheduled Folder Monitor operation, you must select **Set explicit FolderMonitor Schedule**.

2.  (Optional) Click **Configure** in the *Schedule* pane to set up a future one time event or a recurring schedule.  
    The *Configure Schedule* dialog box is displayed.  
    

    <table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">If you configure a schedule and save it after the scheduled start time, the task will not be executed. You must save your configured schedule before the scheduled start time.         </td>
      </tr>
</table>

3.  Specify the desired schedule. For details, see [Set up a scheduled transfer task for a subscription](#set).

4.  (Optional) Enter the **Maximum number of parallel transfers**. If you enter a value greater than zero, SecureTransport executes only the specified number of transfers in parallel. If the value is null or zero, the maximum number of parallel transfers is limited by system capacity.  
    
    The maximum number of parallel transfers limit is applied cluster wide. The limit for files transferred from the client will not be exceeded. Due to limitations in Standard Cluster communication mode, the parallel pulls limit can be exceeded when there are several connections. If you want to force the limit, then the `force.standard.cluster.sit.pulls.sync=true` system property should be added to the `start_tm_console`. Adding the property to the `start_tm_console` has a performance penalty due to increased cluster communication.

5.  (Optional) Click the **Retrieve Files Now** button to immediately trigger a one time file
    pull. For details, see [Retrieve files now](#retrieve).

6.  (Optional) In the *Post Transmission Settings* pane, set the failure and success options. For details, see [Post-transmission actions](../r_st_post_transmission_actions).

7.  To decrypt the transferred files, select **Decrypt PGP File As** and enter a file name or expression.

8.  (Optional) Select or clear the **Require Trusted Signature** and **Require Encryption** options as needed for incoming transfers.

9.  (Optional) Select **Keep Original As** to save the encrypted file. You can move the file to a different folder, rename the file, or both using either hard-coded text or by entering an expression.

### <span id="Configur3"></span>Configure files sent settings

In the *For Files Sent to this Account or its Partners* pane:

1.  Select or clear **Encrypt File As** for outgoing transfers. Enter a file name or an expression for the encrypted file.  
    If you selected **Encrypt File As**, additional fields display. You must select either **Encrypt Using PGP Key** or **Sign using PGP Key** and select a PGP key.

2.  Select or clear **Encrypt Using PGP Key** for outgoing transfers. If you turn this option on, you must select the PGP key used for encryption of outbound transfers from the list.

3.  Select or clear **Sign using PGP Key** for outgoing transfers. If you turn this option on, you must select the PGP key used for signing of outbound transfers from the list.

4.  (Optional) Select or clear **Use Data Compression** for outgoing transfers. If you turn this option on, you must select a data compression **Type** from the list. You must also select a **Compression Level**.

5.  (Optional) Select or clear **Encode Using ASCII Armor** for outgoing transfers.

6.  (Optional) Select **Keep Original As** to move the file to a different folder, rename the file, or both using either hard-coded text or by entering an expression.

7.  (Optional) To set automatic sending of the files, select **Send Files Directly To** and choose one or more transfer sites from the drop-down list. Press either the Shift or Ctrl key while selecting the transfer sites to choose more than one site. All files in the outbox of the subscription folder are automatically sent to the selected transfer sites. If you select a PeSIT transfer site, you can select a **Transfer Profile** from the list or leave the field empty to use the default PeSIT transfer profile. For more information, see [Transfer profiles](../../t_st_transferprofiles).  
    

    <table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">Enable the <code>SendToSite</code> rules package to upload files without subscribing an account to an application. For more information, see .         </td>
      </tr>
</table>

8.  (Optional) Under *Post Transmission Settings*, set the failure and success options.  
    

    <table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">If you configure two or more sites in <strong>Send Files Directly To</strong>, do not configure <strong>Post Transmission Settings</strong>.
<br>If you select an AS2 transfer site, see <a href="#consider">Considerations for subscriptions and AS2 transfer sites</a>.</br>         </td>
      </tr>
</table>

### <span id="Complete"></span>Complete the subscription

To complete the subscription, Click **Add**.

## <span id="Consider"></span>Considerations for subscriptions and AS2 transfer sites

You can set independently the options to enable or disable automatic sending to and receiving files from an AS2 transfer site. For example, for a particular site, you can enable the **Automatically Retrieve Files From** option and disable the **Send Files Directly To** option.

Also, you can specify different AS2 transfer sites for each of the options. For example, you can send files directly to one AS2 transfer site and automatically receive files from a different AS2 transfer site.

When you specify an AS2 transfer site in the **Automatically Retrieve Files From** list for a subscription, you cannot reuse the AS2 transfer site again in a different subscription.

If you specify an AS2 transfer site in the **Automatically Retrieve Files From** list for a subscription, the **On Temporary Failure** option is not displayed. This setting is not applicable for AS2 incoming transfers as they are never retried.

## <span id="Human"></span>Human to System type application

Use a subscription to a Human to System type application to specify email addresses that represent destinations for files sent in emails from ST Web Client or from an email client using one of the Axway Email Plug-ins. When SecureTransport receives an email for one of these addresses, it process the files sent as you specify in the *Package Routing Rules* list in the subscription. SecureTransport applies all the rules that match the email.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">An account can have at most one subscription to a Human to System type application.         </td>
      </tr>
</table>

1.  In the **Subscription Folder** field, type the path to a folder that the application uses for temporary files or use the default folder name. The path is relative to the account home folder. The subscription folder name can contain 254 characters or less.
2.  Create one or more package routing rules.
    1.  Click **New Rule**.
    2.  In the **Recipient Pattern** field, type a regular expression that matches the email addresses that this rule applies to. For example, `invoices@example\.com`.
    3.  In the **File Filter Pattern** field, type a regular expression that matches the names of the files that this rules applies to. For example, `*\.xls`.
    4.  In the **Target Folder** field, type the path to the folder that receives the files that arrive at a matching address and with a matching file name. The path is relative to the account home folder.
3.  The new rules are enabled by default.
4.  Click **Add**.

## <span id="Schedule"></span>Scheduled downloads and tasks

The SecureTransport scheduler feature allows you to schedule file downloads and tasks initiated by the server. You can schedule jobs in two ways, either per [subscription](#set) or per [application](manage_applications.htm#configuremaintschedule). You can access the scheduler page by creating or editing any application or subscription with a transfer site that supports scheduled transfers. Only file downloads can be scheduled. REST API endpoints are also available for configuring scheduled tasks for applications and subscriptions.

When you create a scheduled transfer, for example, when creating a subscription connecting an account to an application where you are transferring files from a remote site or an internal system, you can set the following configuration options:

-   Start Date and Time
-   Perform the task once or perform recurring tasks at configurable regular intervals.
-   Do not perform the scheduled task if it falls on a holiday.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">For information about regular expressions, see <a href="../../../c_st_regularexpressions">Regular expressions</a>.         </td>
      </tr>
</table>

Before queuing a new task, the server checks if a previous instance of same periodic task is still pending. If there is an instance of the same periodic scheduled task is pending, the new task is not scheduled.

If the server goes down and then restarts, the scheduler does not execute any scheduled tasks missed during the server down time.

You can set up holiday dates and use them later when creating scheduled transfers or tasks.

## <span id="Set"></span>Set up a scheduled transfer task for a subscription

When you subscribe a specific account to an application, depending on the transfer site protocol used you can schedule server-initiated downloads from a particular transfer site.

1.  Click **Accounts > User Accounts** and click the account you want to subscribe.
2.  Click **Subscriptions > Subscribe to &lt;application\_name>**.  
    The *Subscription to &lt;application name>* page is displayed.
3.  To set the schedule conditions, click **Configure.**  
    The *Configure Schedule* dialog box is displayed.
4.  In the *Configure Schedule* dialog box, specify the desired conditions for the scheduled server‑initiated download.  
    If the schedule is set on a recurring basis, the **Recurrence** options dynamically change with respect to the recurrence condition: **Hourly**, **Daily**, **Weekly**, **Monthly**, **Yearly**, or **CRON expression**. You can add multiple cron expressions, each on a new line.  
    To schedule an immediate recurrent task, select **Schedule events on a recurring basis** and then select **Start now** in the *Length of Recurrence* pane. The task will begin on the next minute.
5.  Choose whether the task should be performed if it falls on a day specified as a holiday in the [Holiday Schedule](../../../c_st_setup/t_st_holidayschedule). Note that the Holiday Schedule functionality does not allow for executing a scheduled task on the next working day if the specified date happens to be a holiday – when this occurs, the tasks are not executed.
6.  Click **OK** when finished setting the schedule.

## <span id="Retrieve"></span>Retrieve files now

When you have already subscribed an account to an application, depending on the transfer site protocol used, you can initiate an immediate download from the selected transfer site by clicking the **Retrieve Files Now** button.

1.  Click **Accounts > User Accounts** and click the account you want to subscribe.

2.  Click **Subscriptions > Subscribe to &lt;application\_name>**.  
    The *Subscription to &lt;application name>* page is displayed.

3.  Select the **Automatically Retrieve Files From** check box and then select the respective transfer site from the drop down list. If you select a PeSIT transfer site, you can select a **Transfer Profile** from the list or leave the field empty to use the default PeSIT transfer profile. For more information, see [Transfer profiles](../../t_st_transferprofiles).  
    The **Retrieve Files Now** button is displayed.

4.  Click **Retrieve Files Now** to immediately trigger a one-time file
    pull.  
    

    <table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">The scheduler cannot be used for AS2 transfer sites.         </td>
      </tr>
</table>

      
    

    <table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">The <strong>Schedule</strong> pane is displayed only if the <strong>Automatically retrieve files from:</strong> check box is selected and a transfer site is selected.         </td>
      </tr>
</table>

    .

## <span id="Purge"></span>Purge a subscription folder

You can delete the contents of the subscription folder specified for an account.

1.  Click **Accounts > User Accounts** and click the account containing the subscription.

2.  Click **Subscriptions** and click the subscription you want to edit.

3.  Click **Purge Folder** to remove the contents of the current subscription folder.

4.  A message asking you to confirm the deletion of the folder contents is displayed. Click **OK** to remove the folder contents or click **Cancel** to do nothing.  
    

    <table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">
                    If the server goes down for some time and restarts, the scheduler does not execute any scheduled tasks missed during the server down time.
                         </td>
      </tr>
</table>

## <span id="Unsubscribe"></span>Unsubscribe an account from an application

Use the following procedure to unsubscribe an account from an application.

1.  Click **Accounts > User Accounts** and click the account containing the subscription.
2.  Click the **Subscriptions** tab and select the check box next to the subscription you want to remove.
3.  Click **Unsubscribe**. A message asking you to confirm the deletion of the subscription is displayed. Click **OK** to remove the folder contents or click **Cancel** to do nothing.

## <span id="Unsubscribe2"></span>Unsubscribe an account and delete the subscription folder

You can remove a subscription and delete the associated subscription folder, including any subfolders.

1.  Click **Accounts > User Accounts** and click the account containing the subscription.
2.  Click the **Subscriptions** tab and select the check box next to the subscription you want to remove.
3.  Click **Unsubscribe and Purge**. A message asking you to confirm the deletion of the subscription and the subscription folder is displayed. Click **OK** to remove the folder contents or click **Cancel** to do nothing.

**Related topics:**

-   [Encryption options](../r_st_encryption_options)
-   [Post-transmission actions](../r_st_post_transmission_actions)
