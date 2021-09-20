{
    "title": "Manage account templates",
    "linkTitle": "Manage account templates",
    "weight": "240"
}Use the *Account Templates* page to perform account templates.

The following topics provide example and how-to instructions for managing account templates:

-   [Add an account template](#add)
-   [Enable an account template](#enable)
-   [Disable an account template](#disable)
-   [Certificates for an account template](#certificates)
-   [Configure transfer sites for an account template](#configure)
-   [Configure transfer profiles for an account template](#configure_transfer)
-   [Configure routes for an account template](#configure_routes)
-   [Configure subscriptions for an account template](#configur)
-   [Examples of expressions in an account template](#examples)
-   [Export an account template](#export)

**Related topics:**

-   [Account templates and external users](../c_st_account_templates_external_users)
-   [Account template required values](../c_st_account_template_required_values)

## <span id="Add"></span>Add an account template

Use the following procedure to add an account template.

1.  Select **Accounts > Account Templates**.   
    The *Account Templates* page is displayed.

2.  Click **New Account Template** to open a new account template.  
    The *New Account Template* page is displayed.  
    

    <table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">The <em>Address Book Settings</em> are only displayed if the Address Book feature is enabled (the value of the <code>AddressBook.Enabled</code> configuration option is set to <strong>true</strong>). For Address Book account level configuration instructions, refer to <a href="../../../c_st_setup/address_book/address_book_conf">Address Book account level configuration</a>.         </td>
      </tr>
</table>

      
    
    ![New Account Template](SaveIcon.png)
      
    Use hardcoded values, expressions in the supported expression language, or a combination of both to complete the fields for the account settings. Required fields are marked by an asterisk. Fields that accept either hardcoded values or expressions are indicated by a vertical yellow bar.

3.  Enter a name for the template in the **Account Template Name** field.

4.  Enter a pattern that uses question mark (`?`) to match one character and asterisk (`*`) to match any string of characters in the **User Class** field. This account template is associated with users in all classes whose names are matched by the pattern. For example, to associate the template with all users, enter `*`.

5.  To place users in a **Business Unit**, select a business unit from the list. Leave the setting as `No Business Unit` if users are not part of a business unit.

6.  To specify an HTML template to be used when users log in using the web client, select a value from the **HTML template** drop down.

7.  Select **Encrypt Mode**.  
    This field can enable repository encryption for users associated with this template.  
    
    -   **Unspecified** (default) – Repository encryption is enabled based on the `EncryptClass` user class evaluation.
    -   **Enabled** – Repository encryption is enabled for users associated with this template.

8.  Select **Subscription Folder Discovery**  
    This field determines the subscription folder discovery mode. For accounts with multiple subscriptions,
    the number of subscriptions and the target folder depth may impact performance.
    -   **Iterable** (default): Subscription folder discovery is performed by iteration over all of
        the account's subscriptions while trying to match the target folder.  
        Tip: choose this mode when the number of subscriptions is
        small and the target folder depth is large.
    -   **Recursive**: Subscription folder discovery is performed by recursive traversal of the target folder hierarchy -
        the target folder is checked first and if no match is found, then its parent folder is checked. The process continues
        until a match is found or there are no more folders to check.  
        Tip: choose this mode when the number of subscriptions is large
        and the target folder depth is shallow.

9.  Select **File archiving policy**.  
    This field determines the file archiving policy.

    -   When **Default** is selected, then the following apply:
        1.  If the account is assigned to a business unit, it will inherit its policy.
        2.  Otherwise, the global archiving policy applies.
    -   When **Enabled** is selected, file archiving will be enabled for this account.
    -   When **Disabled** is selected, file archiving will be disabled for this account.

      
    

    <table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top"> If the global file archiving policy is disabled, or if this account is assigned to a business unit with <strong>Allow File Archiving Policy modifying</strong> unchecked, then this option cannot be modified.         </td>
      </tr>
</table>

10. Select **File Maintenance policy**. When file maintenance is enabled, there are specifics in constructing the account home folder.   
    This field determines the file maintenance policy.

    -   When **Default** is selected, then the following apply:
        1.  If the account is assigned to a business unit, it will inherit [Manage business units](t_st_businessunits.htm).
        2.  Otherwise, the [File Maintenance application](../../../applications/applicationsfilemaintenance) applies.
    -   When **Custom** is selected, the panel expands with a *Custom settings* pane that allows you to modify the global [File Maintenance application](../../../applications/applicationsfilemaintenance). The customized policy applies to the accounts assigned to this account template only.
    -   When **Disabled** is selected, file maintenance will be disabled for this account.

      
    

    <table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top"> If the global file maintenance policy is disabled, or if this account is assigned to a business unit with <strong>Allow File Maintenance Policy modifying</strong> unchecked, then this option cannot be modified.         </td>
      </tr>
</table>

11. The **Delivery Method** value controls the options that ST Web Client displays in the *User Access* window.
    -   **Disabled** – The user cannot send files using ad hoc file transfers.
    -   **Default** – Use the delivery method specified in the account template, if any, or in the **Default Package Delivery Method** field of the *AdHoc Setting* page.
    -   **Anonymous** – The sender can choose Anonymous or Challenge.
    -   **Account Without Enrollment** – The sender can choose Anonymous, Challenge, or Existing Account.
    -   **Account With Enrollment** – The sender can choose Anonymous, Challenge, Existing Account, Enroll Unlicensed, or Enroll Licensed.
    -   **Custom** – Select the allowed enrollment types in the **Enrollment Types** field. The sender can chose any of the selected enrollment types.

12. For a custom delivery method, select one or more allowed enrollment types in the **Enrollment Types** field:
    -   **Anonymous** – The ad hoc file recipient receives a link to retrieve the files and is not enrolled as a user. The ST Web Client option is **Send attachment link only**.
    -   **Challenge** – The ad hoc file recipient receives a link and must answer correctly a challenge question specified by the sender to retrieve the files. The recipient is not enrolled as a user. The ST Web Client option is **Protect attachment link with security question**.
    -   **Existing Account** – Do not enroll ad hoc file recipients. Only existing users can receive files. The ST Web Client option is **Send to existing users only**.
    -   **Enroll Unlicensed** – If the ad hoc file recipient does not have a user account, the recipient must enroll and create an account before retrieving the files. The ad hoc file recipient becomes an unlicensed user who can only reply once to the email and retrieve the files. Other user attributes are defined by the enrollment template. The ST Web Client option is **Allow recipients to enroll as new Unlicensed Users**.
    -   **Enroll Licensed** – If the ad hoc file recipient does not have a user account, the recipient must enroll and create an account before retrieving the files. The ad hoc file recipient becomes a SecureTransport user with all the attributes specified in the default enrollment template. The ST Web Client option is **Allow recipients to enroll as new Full Licensed Users**.

13. The **Implicit Enrollment Type** value controls which option ST Web Client selects initially in the *User Access* window and which enrollment type is used by the Axway Email Plug-ins. The choices depend on the enrollment types enabled by the **Delivery Methods** and **Enrollment Types** fields.

14. Select **Allow reply to packages** in **Unlicensed Accounts** to allow an unlicensed user associated with this template to reply to emails.

15. Specify **Login Settings**.
    1.  Select **Allow this account to login by email** to allow the user to log in using with the value of the **Email Contact** field as well as the **Login Name**. A user of one of the Axway Email Plug-ins must have **Allow this account to login by email** selected.
    2.  Select **Allow this account to submit transfers using the ST RESTful API** to enable calls from the SecureTransport REST file transfer API authenticated with the credentials from this account. When this option is selected, the account will be allowed to trigger server initiated transfers using the Transfers RESTful API resource and retrieve the tracking information for these transfers.

16. Enter a value or expression for the **Email Contact**.  
    When this email address is the recipient of an ad hoc file transfer email sent from ST Web Client or one of the Axway Email Plug-ins, SecureTransport determines that this user is the recipient. If the user is allowed to log in by email, this is the value used in the **User Name** field of the login page.  
    

    <table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">You can access the SSO email attribute that was previously mapped to <code>fdxEmail</code> with the expression 
				<code>${sess.STSESSION_SSO.email}</code>.         </td>
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
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">Accessing Single Sign-On (SSO) attributes is not possible when using SSO with Kerberos authentication protocol. It is only possible with SAML.         </td>
      </tr>
</table>

17. Enter a value or expression for the **Phone Contact**.

18. Enter a value or expression for the numeric user ID of the user in the **UID** field.  
    On Windows platforms, this field is named **Real User** and is optional.  
    

    <table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">You can access the SSO UID attribute that was previously mapped to <code>fdxUid</code> with the expression 
				<code>${sess.STSESSION_SSO.uid}</code>.         </td>
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
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">Accessing Single Sign-On (SSO) attributes is not possible when using SSO with Kerberos authentication protocol. It is only possible with SAML.         </td>
      </tr>
</table>

19. Enter a value or expression for the numeric group ID for the user account in the **GID** field. The account uses the system access rights and privileges valid for this user group on the system.  
    

    <table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">You can access the SSO GID attribute that was previously mapped to <code>fdxGid</code> with the expression 
				<code>${sess.STSESSION_SSO.gid}</code>.         </td>
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
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">Accessing Single Sign-On (SSO) attributes is not possible when using SSO with Kerberos authentication protocol. It is only possible with SAML.         </td>
      </tr>
</table>

20. Enter values or expressions for the home folder in the **Change Home To** fields for the account as an absolute path. <span id="FileMaintenanceFactors"></span>When File Maintenance is enabled, consider the following important factors:

    -   The base folder must be different than the global one. Otherwise, file maintenance will be performed on the whole global directory.
    -   When the account home folder is constructed using an EL expression, the File Maintenance application cannot calculate the real path of the subscription folder and will delete it if it's left empty after the maintenance.

      
    

    <table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">You can access the SSO username attribute with the expression <code>${sess.STSESSION_SSO.userName}</code>.         </td>
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
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">Accessing Single Sign-On (SSO) attributes is not possible when using SSO with Kerberos authentication protocol. It is only possible with SAML.         </td>
      </tr>
</table>

21. Select **Access Level**. The home folder access level determines whether and which other accounts are able to publish to the home folder of the current account.

    -   **Private** – The access level is private. Only the current account is able to publish files to its home folder.
    -   **Business Unit** – Account home folder access is limited to the account’s business unit. The current account and all accounts in the current account’s business unit can publish to this account’s home folder.
    -   **Public** – Access to the account is public. All accounts are able to publish to this account’s home folder.

      
    

    <table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">Access level is applicable only when <span>Advanced Routing</span> feature is used. For more information see <a href="../../../c_st_advanced_routing">Advanced Routing</a>.         </td>
      </tr>
</table>

22. Select **Password for enrolled accounts is stored internally** in **AdHoc Settings** to generate the account's password during enrollment. If **Password for enrolled accounts is stored internally** is not selected, no password will be generated and stored in the SecureTransport database. When a new account with external password is enrolled, SecureTransport will send out an email notification; but will not send a temporary password.  
    

    <table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">For SSO end-users you need to uncheck this option.         </td>
      </tr>
</table>

23. Enter a value or expression for the text description of the user account in the **Notes** field.

24. Select the **Login Restriction Policy**. The Login Restriction Policy defines rules for allow or deny login to users based on the client IP or host and other conditions. For additional information, refer to [Login restrictions](../../../c_st_accesscontrol/c_st_loginrestictions).  
    If a Login Restriction Policy is selected as the global default policy, it will be the inherited default selection for the user account.  
    If a Login Restriction Policy is not selected as the global default policy and the Business Unit has a Login Restriction Policy selected, it will be the inherited default selection for the user account.  
    If neither a global default Login Restriction Policy or a Business Unit Login Restriction Policy is selected, then the policy selected for the users account will be in effect.  
    

    <table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">The default inherited  Login Restriction Policy can be overridden by selecting a  Login Restriction Policy from <strong>On Account Template</strong>.         </td>
      </tr>
</table>

25. In the *Bandwidth limits* pane select either **Bandwidth Limits Policy** to apply:
    -   Default – the current account template inherits its bandwidth limits from the parent business unit or the global bandwidth
    -   Custom – the panel expands with two additional options for you to configure: **Inbound limit** and **Outbound limit** (both values in kb/s per user)
    -   Disabled – no bandwidth limits are applied to the users assigned to the current account template  

26. To add an attribute, click **Add Attribute**. For additional information on Additional Attributes, refer to [Additional attributes](../../../c_st_setup/t_st_mailtemplates/c_st_mail_template_commands_variables).
    1.  Enter the attribute and value in the **Attribute** and **Value** fields.

    2.  **Add Attribute** enables the administrator to add custom properties (Key=Value). Also the administrator will be able to access the custom properties (named Attributes) using in any fields in Advanced Routing.

    3.  Some examples of Attributes are:

    4.  <table cellspacing="0">   <col/>   <col/>   <thead>      <tr>         <th>Attribute</th>         <th>Value</th>      </tr>   </thead>   <tbody>      <tr>         <td>userVars.1         </td>         <td>internalEmail@axway.com         </td>      </tr>      <tr>         <td>userVars.2         </td>         <td>ReportsMonitor         </td>      </tr>   </tbody></table>

    5.  To access attributes, see the following examples:

    6.  `${account.attributes['userVars.1']}`

    7.  `${account.attributes['userVars.2']}`

    8.  For example, the `account.attributes` is the selector for attributes of the account used to execute the current route - it has to be written exactly as shown.

    9.  The `userVars.` prefix must be prepended to attribute name.

    10. All this should be written as an EL expression: `${...}`

    11. Click the attribute Save (![](SaveIcon.png)) icon.

27. Once you have completed the information in the *Settings* pane, click **Save** to create the account template.

28. To enable the account template, click **Enable Account Template**.  
    Select the **Certificates**,**Transfer Sites**, **Transfer Profiles**, or **Subscriptions** tabs to add additional information to the template. Those pages are similar to the pages for an account, but permit expressions in some fields.

29. To return to the *Account Templates* page, click **Close** or select **Accounts > Account Templates**.

## <span id="Enable"></span>Enable an account template

Once you have created the template, you must enable it to use it.

1.  Select **Accounts > Account Templates**.  
    The *Account Templates* page is displayed.
2.  Click the name of the template you want to enable to view the template settings.
3.  Click **Enable Template** to make the template active.
4.  To return to the *Account Templates* page, click **Close**.

## <span id="Disable"></span>Disable an account template

You can also disable an already created template.

1.  Select **Accounts > Account Templates**.  
    The *Account Templates* page is displayed.
2.  Click the name of the template you want to enable to view the template settings.
3.  Click **Disable Template** to make the template active.
4.  To return to the *Account Templates* page, click **Close** or select **Accounts > Account Templates**.

## <span id="Certificates"></span>Certificates for an account template

Like a user account, an account template can have partner certificates and private certificates. It cannot have login certificates.

For more information, see [Manage login certificates](../../../accounts/c_st_usercertificates/t_st_usercertificates).

## <span id="Configure"></span>Configure transfer sites for an account template

Use the following procedure to configure transfer sites for an account template.

1.  With the account template open, select **Transfer Sites** and click **Add New**.  
    You must define the transfer site completely. Transfer sites in an account template do not support site templates.
2.  Type a **Site Name**.
3.  Select a **Site Type**.
4.  In the **Add Transfer Site** box, select the **Transfer Protocol**.  
    To comply with AS2 protocols, it is not available.
5.  Type values or expressions for the required fields and the optional fields needed to define the transfer site.  
    Transfer sites in an account template do not support server-initiated downloads, so the fields used for them are not displayed.  
    You can use expressions in the fields indicated by a vertical yellow bar.
6.  To use expressions for the checkboxes, select **Use Expression Language**, and, in each field that replaced a checkbox, type `true `for selected or `false `for cleared, or an expression that evaluates to true or false.
7.  Click **Add** to save the transfer site.

For example, to select **Use FTPS** for the transfer site depending on the whether the `target` variable contains the string `class`, type the following in the **Use FTPS** field:

`${stenv['target'].matches('.*class.*')}`

This expression tests the value of `target `and returns `true `if it contains the string class, `false `if not.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">If an account template and its transfer site are defined using expressions, you cannot restart failed transfers for that account template using the <strong>Resubmit</strong> button on the <em>File Tracking</em> page.         </td>
      </tr>
</table>

## <span id="Configure_transfer"></span>Configure transfer profiles for an account template

An account template can have transfer profiles. You can use expressions in the **Files To Send** and **Receive Files As** fields.

For more information, see [Transfer profiles](../../../accounts/t_st_transferprofiles).

## <span id="Configure_routes"></span>Configure routes for an account template

Prior to configuring a route for an account template, the account template should have an Advanced Routing application instance subscription. For account template subscription information, refer to [Configure subscriptions for an account template](#configur) and to [Subscribe to Advanced Routing application](../../../c_st_advanced_routing/c_st_configuration/t_st_subscribe_advanced_routing_application). Additionally, route package templates must be available for assignment. For information on creating and managing route package templates, refer to [Manage Route Package Templates](../../../c_st_advanced_routing/c_st_configuration/t_st_manage_route_package_templates).

1.  With the account template open, select **Routes**, select a route package template, and click **Assign Route**.  
    The *Create Route Package* page is displayed. You can navigate to the *Edit Route Package Template* page for the selected route package template by clicking the **Created From** link.

2.  In the **Route Name** field, type the desired name of the route. The route name can contain 254 characters or less.  
    

    <table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">You cannot use the following characters in the route name: <code>* &lt; &gt; ? " / \ | :</code>         </td>
      </tr>
</table>

3.  (Optional) Enter a **Description**.

4.  In the *Subscriptions* pane:
    1.  Click **Assign** to assign an available Advanced Routing application folder to the route.
    2.  The Available Subscriptions page is displayed.
    3.  On the *Available Subscriptions* page, select the checkbox for a folder from the *Subscriptions Folder* list and click **OK** to assign a folder to the route.
    4.  The assigned folder is now listed in the *Subscriptions List*.
    5.  To unassign an application folder, select the checkbox for the folder and click **Unassign**.

5.  In the *Inherited Settings* pane:
    1.  Select the check box for a Template Route and click **Disable** to disable an enabled inherited route.

    2.  Select the check box for a Template Route and click **Enable** to enable a disabled inherited route.

    3.  <table cellpadding="0" cellspacing="0">   <col/>   <col/>   <col/>      <tr>         <td valign="top">         </td>         <td valign="top"><span><b>Note</b></span>         </td>         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">The inherited Execution Rule cannot be changed.         </td>      </tr></table>

6.  In the *Specific Settings* pane:
    1.  Determine the **Execution Rule**. Select either **All Matching Routes** (default) or **First Matching Route**.
    2.  When **All Matching Routes** is selected, all matching Routes are executed. When **First Matching Route** is selected, only the first matching Route is executed.
    3.  Click **New Route**.
    4.  The *New Route Entry* page is displayed. For Route configuration information, refer to [Manage Routes](../../../c_st_advanced_routing/c_st_configuration/t_st_manage_routes).
    5.  You can also enable, disable, reorder, and delete Routes in the *Specific Settings* pane. For information on enabling, disabling, reordering, or deleting Routes, refer to [Manage Route Package Templates](../../../c_st_advanced_routing/c_st_configuration/t_st_manage_route_package_templates).

7.  In the *Notifications* pane:
    1.  Select **Notify following e-mails on route failure** to be notified on route failure and enter a notification email address, a list of mail addresses, or an expression. For additional email configuration information, refer to [SMTP configuration](../../../c_st_setup/c_st_miscellaneousconfiguration/t_st_smtpconfiguration).
    2.  Select the **Mail Template** from the menu to be used for route failure notifications. For email template configuration information, refer to [Mail templates](../../../c_st_setup/t_st_mailtemplates).
    3.  Select **Notify following e-mails on route success** to be notified on route success and enter a notification email address, a list of mail addresses, or an expression.
    4.  Select the **Mail Template** from the menu to be used for route success notifications.
    5.  Select **Notify following e-mails on route triggering** to be notified on route triggering and enter a notification email address, a list of mail addresses, or an expression.
    6.  Select the **Mail Template** from the menu to be used for route triggering notifications.

8.  Click **Save**.

## <span id="Configur"></span>Configure subscriptions for an account template

1.  With the account template open, select **Subscriptions**, select an application, and click **Subscribe**.  
    Subscriptions in an account template do not support applications of type Standard Router, so they are not include in the drop-down list.
2.  In the *Flow Settings* pane, select the **Existing flow attributes**.  
    If **Preserve** is selected, the attributes defined in the *Flow Attributes* pane will be applied only for newly received files which do not have associated flow attributes.  
    If **Overwrite** is selected, the attributes defined in the *Flow Attributes* pane will overwrite any existing attributes for incoming files (for example, files published to this folder from another subscription folder).  
    When **Append** is selected, only the attributes which are not defined for incoming files will be applied. Existing attributes will be preserved.
3.  In the *Flow/Subscription Attributes* pane:
    1.  To add an attribute, click **Add Attribute**. For additional information, refer to [Flow and subscription attributes](../../../c_st_setup/t_st_mailtemplates/c_st_mail_template_commands_variables).

    2.  **Add Attribute** enables the administrator to add custom properties (Key=Value). Flow attributes can be used for expression evaluation in Advanced Routing only when the application operates with files. Subscription attributes are bound to the subscription, therefore, they can be used for expression evaluation in all Advanced Routing fields.

    3.  Some examples of Attributes are:

    4.  <table cellpadding="0" cellspacing="0">   <col/>   <col/>   <col/>      <tr>         <td valign="top">         </td>         <td valign="top"><span><b>Note</b></span>         </td>         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">Subscription attributes can be accessed using the following expression:  <code>${subscription.attributes['userVars.ATTRIBUTE_NAME'].</code><br> Flow attributes can be accessed using the following expression: <code>${flow.attributes[‘userVars.ATTRIBUTE_NAME’]}.</code></br>         </td>      </tr></table>

    5.  To access attributes, see the following examples:

    6.  `${account.attributes['userVars.1']}`

    7.  `${account.attributes['userVars.2']}`

    8.  For example, the `account.attributes` is the selector for attributes of the account used to execute the current route - it has to be written exactly as shown.

    9.  The `userVars.` prefix must be prepended to attribute name.

    10. All this should be written as an EL expression: `${...}`

    11. Click the attribute Save (![](SaveIcon.png)) icon.
4.  Type values or expressions for the required fields and the optional fields needed to define the subscription.  
    Subscriptions in an account template do not support server-initiated downloads, so the fields used for them do not appear.  
    You can use expressions in the fields indicated by a vertical yellow bar.
5.  To use expressions for additional fields including the checkboxes, select **Advanced Expressions**.  
    The fields and checkboxes are replaced by fields with a vertical yellow bar.
    -   In each field that replaces a check box, type 1 for selected (true) or 0 for deselected (false) or an expression that evaluates to 0 or 1.

    -   In the other fields, type a value or an expression that evaluates to the value required.

    -   In the **Compression Type** field for applications that have the **Encrypt File** option such as application of type Basic Application and Site Mailbox, type one of the following values that represent available compression algorithms or an expression that evaluates to one them:

        <table cellspacing="0">   <col/>   <col/>   <thead>      <tr>         <th>Attribute</th>         <th>Value</th>      </tr>   </thead>   <tbody>      <tr>         <td>userVars.1         </td>         <td>internalEmail@axway.com         </td>      </tr>      <tr>         <td>userVars.2         </td>         <td>ReportsMonitor         </td>      </tr>   </tbody></table>

    -   In the **Compression Level** field, type an integer between 1 and 9, where 1 represents the least compressed but fastest level and 9 represents the most compressed but slowest level or an expression that evaluates to an integer between 1 and 9. The values that correspond to the levels available when **Advanced Expressions** is not selected are:

        <table cellspacing="0">   <col/>   <col/>   <thead>      <tr>         <th>Type</th>         <th>Value</th>      </tr>   </thead>   <tbody>      <tr>         <td>Use preferred (algorithm obtained from PGP key)         </td>         <td>-1         </td>      </tr>      <tr>         <td>Uncompressed         </td>         <td>0         </td>      </tr>      <tr>         <td>ZIP         </td>         <td>1         </td>      </tr>      <tr>         <td>ZLIB         </td>         <td>2         </td>      </tr>      <tr>         <td>BZIP2         </td>         <td>3         </td>      </tr>   </tbody></table>
6.  Click **Add** to add the subscription to the account template.

## <span id="Examples"></span>Examples of expressions in an account template

You can use expressions on the *Settings* pane, *Transfer Sites* pane, and *Subscription*s pane when creating an account template. The following examples show some of the expressions you can use.

The following table gives examples of expressions in account settings:

<table cellspacing="0">   <col/>   <col/>   <thead>      <tr>         <th>Level</th>         <th>Value</th>      </tr>   </thead>   <tbody>      <tr>         <td>Fast         </td>         <td>2         </td>      </tr>      <tr>         <td>Normal         </td>         <td>5         </td>      </tr>      <tr>         <td>Good         </td>         <td>7         </td>      </tr>      <tr>         <td>Best         </td>         <td>9         </td>      </tr>   </tbody></table>

The following table gives examples of expressions in transfer sites:

<table cellspacing="0">
   <col/>
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Field</th>
         <th>Expression</th>
         <th>Description</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>UID         </td>
         <td><code>${sess['STSESSION_LDAP_DIR_uidNumber']}</code>
         </td>
         <td>Returns the UID from the LDAP session.         </td>
      </tr>
      <tr>
         <td>GID         </td>
         <td><code>${sess['STSESSION_LDAP_DIR_gidNumber']}</code>
         </td>
         <td>Returns the GID from the LDAP session.         </td>
      </tr>
      <tr>
         <td>Home Folder         </td>
         <td><code>${sess['STSESSION_LDAP_DIR_homeDirectory']}</code>
         </td>
         <td>Returns the home folder specified in the LDAP session.         </td>
      </tr>
      <tr>
         <td colspan="3">When you have attribute maps configured, you can use the following named variable expressions instead:         </td>
      </tr>
      <tr>
         <td>UID         </td>
         <td><code>${stenv.useruid}</code>
         </td>
         <td>Returns the UID.         </td>
      </tr>
      <tr>
         <td>GID         </td>
         <td><code>${stenv.usergid}</code>
         </td>
         <td>Returns the GID.         </td>
      </tr>
      <tr>
         <td>HomeDir         </td>
         <td><code>${stenv.homedir}</code>
         </td>
         <td>Returns the home folder.         </td>
      </tr>
      <tr>
         <td>If the account template is for licensed or unlicensed users enrolled after receiving notification of an ad hoc file transfer:         </td>
         <td>If the account template is for licensed or unlicensed users enrolled after receiving notification of an ad hoc file transfer:         </td>
         <td>If the account template is for licensed or unlicensed users enrolled after receiving notification of an ad hoc file transfer:         </td>
      </tr>
      <tr>
         <td>Email Contact         </td>
         <td><code>${stenv.recipient_email}</code>
         </td>
         <td>Returns the email address for recipient of the ad hoc file transfer.         </td>
      </tr>
      <tr>
         <td>Home Folder         </td>
         <td><code>${stenv.recipient_email}</code>
         </td>
         <td>Returns the email address for recipient of the ad hoc file transfer to create a unique home folder.         </td>
      </tr>
   </tbody>
</table>

<table cellspacing="0">
   <col/>
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Field</th>
         <th>Expression</th>
         <th>Description</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>Upload Folder         </td>
         <td><code>/upload/${stenv.loginname}</code>
         </td>
         <td>Returns the subfolder based on the user login name in the upload folder.         </td>
      </tr>
      <tr>
         <td>User Name         </td>
         <td><code>${stenv.loginname}</code>
         </td>
         <td>Returns the user login name.         </td>
      </tr>
      <tr>
         <td>Certificate         </td>
         <td><code>x509_${stenv.loginname}</code>
         </td>
         <td>Returns the user login certificate.         </td>
      </tr>
      <tr>
         <td colspan="3">With Advanced Expressions selected, you can use the following complex expressions:         </td>
      </tr>
      <tr>
         <td>Upload Folder         </td>
         <td><code>/${stenv['target'].</code>
<br><code>replace('^(.*)_(.*)_(.*)$','$2')}<br/></code>or<br><code>/upload/${stenv['target'].</code><br><code>matches('.*\\.((jpg)|(gif)|(txt))$') ? stenv['target'].</code><br><code>replace('^.*\\.((txt)|(jpg)|(gif))$','$1') : 'general/'}</code></br></br></br></br>         </td>
         <td>Returns the upload folder based on the match and replace expression criteria.         </td>
      </tr>
      <tr>
         <td>Enable SSL         </td>
         <td><code>${stenv['target'].matches('^(ssl).*')}</code>
         </td>
         <td>Returns a 0 (false) or 1 (true) based on the match criteria.         </td>
      </tr>
   </tbody>
</table>

The following table gives examples of expressions in subscriptions:

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">You can also use regular expressions such as <code>${stenv.target}</code>only to return the file name or <code>${filename(stenv.target)}-${random}</code> to change the file name.         </td>
      </tr>
</table>

## <span id="Export"></span>Export an account template

You can export an account template to an XML file.

1.  Select **Accounts > Account Templates**.  
    The *Account Templates* page is displayed.
2.  In the first column, select the account template to export.
3.  Click **Export an Account Template**.  
    The *Export Account* page is displayed.
4.  Type a password in the **Password** field. This password is used to encrypt the sensitive information contained in the template account. You must use this password when you import the template account to decrypt the sensitive information.
5.  Retype the password in the **Re-enter Password** field.
6.  Click **Export**.
7.  When the XML file with the exported account template is ready, click **Download Exported Accounts** and save the file to your local computer.
