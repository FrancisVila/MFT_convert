{
    "title": "Manage account templates",
    "linkTitle": "Manage account templates",
    "weight": "230"
}Use the *Account Templates* page to perform account templates.

The following topics provide example and how-to instructions for managing account templates:

-   <a href="#Add" class="MCXref xref">Add an account template</a>
-   <a href="#Enable" class="MCXref xref">Enable an account template</a>
-   <a href="#Disable" class="MCXref xref">Disable an account template</a>
-   <a href="#Certificates" class="MCXref xref">Certificates for an account template</a>
-   <a href="#Configure" class="MCXref xref">Configure transfer sites for an account template</a>
-   <a href="#Configure_transfer" class="MCXref xref">Configure transfer profiles for an account template</a>
-   <a href="#Configure_routes" class="MCXref xref">Configure routes for an account template</a>
-   <a href="#Configur" class="MCXref xref">Configure subscriptions for an account template</a>
-   <a href="#Examples" class="MCXref xref">Examples of expressions in an account template</a>
-   <a href="#Export" class="MCXref xref">Export an account template</a>

**Related topics:**

-   <a href="../c_st_account_templates_external_users" class="MCXref xref">Account templates and external users</a>
-   <a href="../c_st_account_template_required_values" class="MCXref xref">Account template required values</a>

<span id="Add"></span>

## Add an account template

Use the following procedure to add an account template.

1.  Select **Accounts > Account Templates**.  
    The *Account Templates* page is displayed.

2.  Click **New Account Template** to open a new account template.  
    The *New Account Template* page is displayed.  

    > **Note:**
    >
    > The Address Book Settings are only displayed if the Address Book feature is enabled (the value of the AddressBook.Enabled configuration option is set to true). For Address Book account level configuration instructions, refer to Address Book account level configuration.

      
    <img src="/Images/SecureTransport/Account_Template_New.png" class="maxWidth" alt="New Account Template" />  
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

      

    > **Note:**
    >
    > If the global file archiving policy is disabled, or if this account is assigned to a business unit with Allow File Archiving Policy modifying unchecked, then this option cannot be modified.

10. Select **File Maintenance policy**. When file maintenance is enabled, there are specifics in constructing the account home folder.  
    This field determines the file maintenance policy.

    -   When **Default** is selected, then the following apply:
        1.  If the account is assigned to a business unit, it will inherit <a href="#" class="MCXref xref">Manage business units</a>.
        2.  Otherwise, the <a href="../../../applications/applicationsfilemaintenance" class="MCXref xref">File Maintenance application</a> applies.
    -   When **Custom** is selected, the panel expands with a *Custom settings* pane that allows you to modify the global <a href="../../../applications/applicationsfilemaintenance#Configur" class="MCXref xref">File Maintenance application</a>. The customized policy applies to the accounts assigned to this account template only.
    -   When **Disabled** is selected, file maintenance will be disabled for this account.

      

    > **Note:**
    >
    > If the global file maintenance policy is disabled, or if this account is assigned to a business unit with Allow File Maintenance Policy modifying unchecked, then this option cannot be modified.

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
    -   **Enroll Licensed** – If the ad hoc file recipient does not have a user account, the recipient must enroll and create an account before retrieving the files. The ad hoc file recipient becomes a <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> user with all the attributes specified in the default enrollment template. The ST Web Client option is **Allow recipients to enroll as new Full Licensed Users**.

13. The **Implicit Enrollment Type** value controls which option ST Web Client selects initially in the *User Access* window and which enrollment type is used by the <span class="mc-variable axway_variables.Company_Name variable">Axway</span> Email Plug-ins. The choices depend on the enrollment types enabled by the **Delivery Methods** and **Enrollment Types** fields.

14. Select **Allow reply to packages** in **Unlicensed Accounts** to allow an unlicensed user associated with this template to reply to emails.

15. Specify **Login Settings**.
    1.  Select **Allow this account to login by email** to allow the user to log in using with the value of the **Email Contact** field as well as the **Login Name**. A user of one of the <span class="mc-variable axway_variables.Company_Name variable">Axway</span> Email Plug-ins must have **Allow this account to login by email** selected.
    2.  Select **Allow this account to submit transfers using the ST RESTful API** to enable calls from the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> REST file transfer API authenticated with the credentials from this account. When this option is selected, the account will be allowed to trigger server initiated transfers using the Transfers RESTful API resource and retrieve the tracking information for these transfers.

16. Enter a value or expression for the **Email Contact**.  
    When this email address is the recipient of an ad hoc file transfer email sent from ST Web Client or one of the <span class="mc-variable axway_variables.Company_Name variable">Axway</span> Email Plug-ins, <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> determines that this user is the recipient. If the user is allowed to log in by email, this is the value used in the **User Name** field of the login page.  

    > **Note:**
    >
    > You can access the SSO email attribute that was previously mapped to fdxEmail with the expression
    > ${sess.STSESSION\_SSO.email}.

    > **Note:**
    >
    > Accessing Single Sign-On (SSO) attributes is not possible when using SSO with Kerberos authentication protocol. It is only possible with SAML.

17. Enter a value or expression for the **Phone Contact**.

18. Enter a value or expression for the numeric user ID of the user in the **UID** field.  
    On Windows platforms, this field is named **Real User** and is optional.  

    > **Note:**
    >
    > You can access the SSO UID attribute that was previously mapped to fdxUid with the expression
    > ${sess.STSESSION\_SSO.uid}.

    > **Note:**
    >
    > Accessing Single Sign-On (SSO) attributes is not possible when using SSO with Kerberos authentication protocol. It is only possible with SAML.

19. Enter a value or expression for the numeric group ID for the user account in the **GID** field. The account uses the system access rights and privileges valid for this user group on the system.  

    > **Note:**
    >
    > You can access the SSO GID attribute that was previously mapped to fdxGid with the expression
    > ${sess.STSESSION\_SSO.gid}.

    > **Note:**
    >
    > Accessing Single Sign-On (SSO) attributes is not possible when using SSO with Kerberos authentication protocol. It is only possible with SAML.

20. Enter values or expressions for the home folder in the **Change Home To** fields for the account as an absolute path. <span id="FileMaintenanceFactors"></span>When File Maintenance is enabled, consider the following important factors:

    -   The base folder must be different than the global one. Otherwise, file maintenance will be performed on the whole global directory.
    -   When the account home folder is constructed using an EL expression, the File Maintenance application cannot calculate the real path of the subscription folder and will delete it if it's left empty after the maintenance.

      

    > **Note:**
    >
    > You can access the SSO username attribute with the expression ${sess.STSESSION\_SSO.userName}.

    > **Note:**
    >
    > Accessing Single Sign-On (SSO) attributes is not possible when using SSO with Kerberos authentication protocol. It is only possible with SAML.

21. Select **Access Level**. The home folder access level determines whether and which other accounts are able to publish to the home folder of the current account.

    -   **Private** – The access level is private. Only the current account is able to publish files to its home folder.
    -   **Business Unit** – Account home folder access is limited to the account’s business unit. The current account and all accounts in the current account’s business unit can publish to this account’s home folder.
    -   **Public** – Access to the account is public. All accounts are able to publish to this account’s home folder.

      

    > **Note:**
    >
    > Access level is applicable only when Advanced Routing feature is used. For more information see Advanced Routing.

22. Select **Password for enrolled accounts is stored internally** in **AdHoc Settings** to generate the account's password during enrollment. If **Password for enrolled accounts is stored internally** is not selected, no password will be generated and stored in the <span class="mc-variable suite_variables.SecureTransportName variable">SecureTransport</span> database. When a new account with external password is enrolled, <span class="mc-variable suite_variables.SecureTransportName variable">SecureTransport</span> will send out an email notification; but will not send a temporary password.  

    > **Note:**
    >
    > For SSO end-users you need to uncheck this option.

23. Enter a value or expression for the text description of the user account in the **Notes** field.

24. Select the **Login Restriction Policy**. The Login Restriction Policy defines rules for allow or deny login to users based on the client IP or host and other conditions. For additional information, refer to <a href="../../../c_st_accesscontrol/c_st_loginrestictions" class="MCXref xref">Login restrictions</a>.  
    If a Login Restriction Policy is selected as the global default policy, it will be the inherited default selection for the user account.  
    If a Login Restriction Policy is not selected as the global default policy and the Business Unit has a Login Restriction Policy selected, it will be the inherited default selection for the user account.  
    If neither a global default Login Restriction Policy or a Business Unit Login Restriction Policy is selected, then the policy selected for the users account will be in effect.  

    > **Note:**
    >
    > The default inherited Login Restriction Policy can be overridden by selecting a Login Restriction Policy from On Account Template.

25. In the *Bandwidth limits* pane select either **Bandwidth Limits Policy** to apply:
    -   Default – the current account template inherits its bandwidth limits from the parent business unit or the global bandwidth
    -   Custom – the panel expands with two additional options for you to configure: **Inbound limit** and **Outbound limit** (both values in kb/s per user)
    -   Disabled – no bandwidth limits are applied to the users assigned to the current account template  

26. To add an attribute, click **Add Attribute**. For additional information on Additional Attributes, refer to <a href="../../../c_st_setup/t_st_mailtemplates/c_st_mail_template_commands_variables#Addition" class="MCXref xref">Additional attributes</a>.
    1.  Enter the attribute and value in the **Attribute** and **Value** fields.

    2.  **Add Attribute** enables the administrator to add custom properties (Key=Value). Also the administrator will be able to access the custom properties (named Attributes) using in any fields in Advanced Routing.

    3.  Some examples of Attributes are:

    4.  <table>
           <thead>
              <tr>
        <th class="HeadE-Column1-Header1">Attribute         </th>
        <th class="HeadD-Column1-Header1">Value         </th>
              </tr>
           </thead>
           <tbody>
              <tr>
                 <td>userVars.1         </td>
                 <td>internalEmail@axway.com         </td>
              </tr>
              <tr>
                 <td>userVars.2         </td>
                 <td>ReportsMonitor         </td>
              </tr>
           </tbody>
        </table>

    5.  To access attributes, see the following examples:

    6.  `${account.attributes['userVars.1']}`

    7.  `${account.attributes['userVars.2']}`

    8.  For example, the `account.attributes` is the selector for attributes of the account used to execute the current route - it has to be written exactly as shown.

    9.  The `userVars.` prefix must be prepended to attribute name.

    10. All this should be written as an EL expression: `${...}`

    11. Click the attribute Save (![](/Images/SecureTransport/SaveIcon.png)) icon.

27. Once you have completed the information in the *Settings* pane, click **Save** to create the account template.

28. To enable the account template, click **Enable Account Template**.  
    Select the **Certificates**,**Transfer Sites**, **Transfer Profiles**, or **Subscriptions** tabs to add additional information to the template. Those pages are similar to the pages for an account, but permit expressions in some fields.

29. To return to the *Account Templates* page, click **Close** or select **Accounts > Account Templates**.

<span id="Enable"></span>

## Enable an account template

Once you have created the template, you must enable it to use it.

1.  Select **Accounts > Account Templates**.  
    The *Account Templates* page is displayed.
2.  Click the name of the template you want to enable to view the template settings.
3.  Click **Enable Template** to make the template active.
4.  To return to the *Account Templates* page, click **Close**.

<span id="Disable"></span>

## Disable an account template

You can also disable an already created template.

1.  Select **Accounts > Account Templates**.  
    The *Account Templates* page is displayed.
2.  Click the name of the template you want to enable to view the template settings.
3.  Click **Disable Template** to make the template active.
4.  To return to the *Account Templates* page, click **Close** or select **Accounts > Account Templates**.

<span id="Certificates"></span>

## Certificates for an account template

Like a user account, an account template can have partner certificates and private certificates. It cannot have login certificates.

For more information, see <a href="../../../accounts/c_st_usercertificates/t_st_usercertificates#AccountsMenu_2253641766_1090701" class="MCXref xref">Manage login certificates</a>.

<span id="Configure"></span>

## Configure transfer sites for an account template

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

> **Note:**
>
> If an account template and its transfer site are defined using expressions, you cannot restart failed transfers for that account template using the Resubmit button on the File Tracking page.

<span id="Configure_transfer"></span>

## Configure transfer profiles for an account template

An account template can have transfer profiles. You can use expressions in the **Files To Send** and **Receive Files As** fields.

For more information, see <a href="../../../accounts/t_st_transferprofiles#AccountsMenu_2253641766_1248932" class="MCXref xref">Transfer profiles</a>.

<span id="Configure_routes"></span>

## Configure routes for an account template

Prior to configuring a route for an account template, the account template should have an <span class="mc-variable my_project_variables.Advanced_Routing variable">Advanced Routing</span> application instance subscription. For account template subscription information, refer to <a href="#Configur" class="MCXref xref">Configure subscriptions for an account template</a> and to <a href="../../../c_st_advanced_routing/c_st_configuration/t_st_subscribe_advanced_routing_application" class="MCXref xref">Subscribe to Advanced Routing application</a>. Additionally, route package templates must be available for assignment. For information on creating and managing route package templates, refer to <a href="../../../c_st_advanced_routing/c_st_configuration/t_st_manage_route_package_templates" class="MCXref xref">Manage Route Package Templates</a>.

1.  With the account template open, select **Routes**, select a route package template, and click **Assign Route**.  
    The *Create Route Package* page is displayed. You can navigate to the *Edit Route Package Template* page for the selected route package template by clicking the **Created From** link.

2.  In the **Route Name** field, type the desired name of the route. The route name can contain 254 characters or less.  

    > **Note:**
    >
    > You cannot use the following characters in the route name: \* &lt; > ? " / \\ | :

3.  (Optional) Enter a **Description**.

4.  In the *Subscriptions* pane:
    1.  Click **Assign** to assign an available <span class="mc-variable my_project_variables.Advanced_Routing variable">Advanced Routing</span> application folder to the route.
    2.  The Available Subscriptions page is displayed.
    3.  On the *Available Subscriptions* page, select the checkbox for a folder from the *Subscriptions Folder* list and click **OK** to assign a folder to the route.
    4.  The assigned folder is now listed in the *Subscriptions List*.
    5.  To unassign an application folder, select the checkbox for the folder and click **Unassign**.

5.  In the *Inherited Settings* pane:
    1.  Select the check box for a Template Route and click **Disable** to disable an enabled inherited route.

    2.  Select the check box for a Template Route and click **Enable** to enable a disabled inherited route.

    3.  **Note:**
        >
        > The inherited Execution Rule cannot be changed.

6.  In the *Specific Settings* pane:
    1.  Determine the **Execution Rule**. Select either **All Matching Routes** (default) or **First Matching Route**.
    2.  When **All Matching Routes** is selected, all matching Routes are executed. When **First Matching Route** is selected, only the first matching Route is executed.
    3.  Click **New Route**.
    4.  The *New Route Entry* page is displayed. For Route configuration information, refer to <a href="../../../c_st_advanced_routing/c_st_configuration/t_st_manage_routes" class="MCXref xref">Manage Routes</a>.
    5.  You can also enable, disable, reorder, and delete Routes in the *Specific Settings* pane. For information on enabling, disabling, reordering, or deleting Routes, refer to <a href="../../../c_st_advanced_routing/c_st_configuration/t_st_manage_route_package_templates" class="MCXref xref">Manage Route Package Templates</a>.

7.  In the *Notifications* pane:
    1.  Select **Notify following e-mails on route failure** to be notified on route failure and enter a notification email address, a list of mail addresses, or an expression. For additional email configuration information, refer to <a href="../../../c_st_setup/c_st_miscellaneousconfiguration/t_st_smtpconfiguration" class="MCXref xref">SMTP configuration</a>.
    2.  Select the **Mail Template** from the menu to be used for route failure notifications. For email template configuration information, refer to <a href="../../../c_st_setup/t_st_mailtemplates" class="MCXref xref">Mail templates</a>.
    3.  Select **Notify following e-mails on route success** to be notified on route success and enter a notification email address, a list of mail addresses, or an expression.
    4.  Select the **Mail Template** from the menu to be used for route success notifications.
    5.  Select **Notify following e-mails on route triggering** to be notified on route triggering and enter a notification email address, a list of mail addresses, or an expression.
    6.  Select the **Mail Template** from the menu to be used for route triggering notifications.

8.  Click **Save**.

<span id="Configur"></span>

## Configure subscriptions for an account template

1.  With the account template open, select **Subscriptions**, select an application, and click **Subscribe**.  
    Subscriptions in an account template do not support applications of type Standard Router, so they are not include in the drop-down list.
2.  In the *Flow Settings* pane, select the **Existing flow attributes**.  
    If **Preserve** is selected, the attributes defined in the *Flow Attributes* pane will be applied only for newly received files which do not have associated flow attributes.  
    If **Overwrite** is selected, the attributes defined in the *Flow Attributes* pane will overwrite any existing attributes for incoming files (for example, files published to this folder from another subscription folder).  
    When **Append** is selected, only the attributes which are not defined for incoming files will be applied. Existing attributes will be preserved.
3.  In the *Flow/Subscription Attributes* pane:
    1.  To add an attribute, click **Add Attribute**. For additional information, refer to <a href="../../../c_st_setup/t_st_mailtemplates/c_st_mail_template_commands_variables#Flow" class="MCXref xref">Flow and subscription attributes</a>.

    2.  **Add Attribute** enables the administrator to add custom properties (Key=Value). Flow attributes can be used for expression evaluation in Advanced Routing only when the application operates with files. Subscription attributes are bound to the subscription, therefore, they can be used for expression evaluation in all Advanced Routing fields.

    3.  Some examples of Attributes are:

    4.  <table>
           <thead>
              <tr>
        <th class="HeadE-Column1-Header1">Attribute         </th>
        <th class="HeadD-Column1-Header1">Value         </th>
              </tr>
           </thead>
           <tbody>
              <tr>
                 <td>userVars.1         </td>
                 <td>internalEmail@axway.com         </td>
              </tr>
              <tr>
                 <td>userVars.2         </td>
                 <td>ReportsMonitor         </td>
              </tr>
           </tbody>
        </table>

    5.  To access attributes, see the following examples:

    6.  `${account.attributes['userVars.1']}`

    7.  `${account.attributes['userVars.2']}`

    8.  For example, the `account.attributes` is the selector for attributes of the account used to execute the current route - it has to be written exactly as shown.

    9.  The `userVars.` prefix must be prepended to attribute name.

    10. All this should be written as an EL expression: `${...}`

    11. Click the attribute Save (![](/Images/SecureTransport/SaveIcon.png)) icon.
4.  Type values or expressions for the required fields and the optional fields needed to define the subscription.  
    Subscriptions in an account template do not support server-initiated downloads, so the fields used for them do not appear.  
    You can use expressions in the fields indicated by a vertical yellow bar.
5.  To use expressions for additional fields including the checkboxes, select **Advanced Expressions**.  
    The fields and checkboxes are replaced by fields with a vertical yellow bar.
    -   In each field that replaces a check box, type 1 for selected (true) or 0 for deselected (false) or an expression that evaluates to 0 or 1.
    -   In the other fields, type a value or an expression that evaluates to the value required.
    -   In the **Compression Type** field for applications that have the **Encrypt File** option such as application of type Basic Application and Site Mailbox, type one of the following values that represent available compression algorithms or an expression that evaluates to one them:
        <table>
           <thead>
              <tr>
        <th class="HeadE-Column1-Header1">Type         </th>
        <th class="HeadD-Column1-Header1">Value         </th>
              </tr>
           </thead>
           <tbody>
              <tr>
                 <td>Use preferred (algorithm obtained from PGP key)         </td>
                 <td>-1         </td>
              </tr>
              <tr>
                 <td>Uncompressed         </td>
                 <td>0         </td>
              </tr>
              <tr>
                 <td>ZIP         </td>
                 <td>1         </td>
              </tr>
              <tr>
                 <td>ZLIB         </td>
                 <td>2         </td>
              </tr>
              <tr>
                 <td>BZIP2         </td>
                 <td>3         </td>
              </tr>
           </tbody>
        </table>
    -   In the **Compression Level** field, type an integer between 1 and 9, where 1 represents the least compressed but fastest level and 9 represents the most compressed but slowest level or an expression that evaluates to an integer between 1 and 9. The values that correspond to the levels available when **Advanced Expressions** is not selected are:
        <table>
           <thead>
              <tr>
        <th class="HeadE-Column1-Header1">Level         </th>
        <th class="HeadD-Column1-Header1">Value         </th>
              </tr>
           </thead>
           <tbody>
              <tr>
                 <td>Fast         </td>
                 <td>2         </td>
              </tr>
              <tr>
                 <td>Normal         </td>
                 <td>5         </td>
              </tr>
              <tr>
                 <td>Good         </td>
                 <td>7         </td>
              </tr>
              <tr>
                 <td>Best         </td>
                 <td>9         </td>
              </tr>
           </tbody>
        </table>
6.  Click **Add** to add the subscription to the account template.

<span id="Examples"></span>

## Examples of expressions in an account template

You can use expressions on the *Settings* pane, *Transfer Sites* pane, and *Subscription*s pane when creating an account template. The following examples show some of the expressions you can use.

The following table gives examples of expressions in account settings:

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Field         </th>
<th class="HeadE-Column1-Header1">Expression         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>UID         </td>
         <td><code>${sess['STSESSION_LDAP_DIR_uidNumber']}</code>         </td>
         <td>Returns the UID from the LDAP session.         </td>
      </tr>
      <tr>
         <td>GID         </td>
         <td><code>${sess['STSESSION_LDAP_DIR_gidNumber']}</code>         </td>
         <td>Returns the GID from the LDAP session.         </td>
      </tr>
      <tr>
         <td>Home Folder         </td>
         <td><code>${sess['STSESSION_LDAP_DIR_homeDirectory']}</code>         </td>
         <td>Returns the home folder specified in the LDAP session.         </td>
      </tr>
      <tr>
         <td>When you have attribute maps configured, you can use the following named variable expressions instead:         </td>
      </tr>
      <tr>
         <td>UID         </td>
         <td><code>${stenv.useruid}</code>         </td>
         <td>Returns the UID.         </td>
      </tr>
      <tr>
         <td>GID         </td>
         <td><code>${stenv.usergid}</code>         </td>
         <td>Returns the GID.         </td>
      </tr>
      <tr>
         <td>HomeDir         </td>
         <td><code>${stenv.homedir}</code>         </td>
         <td>Returns the home folder.         </td>
      </tr>
      <tr>
         <td>If the account template is for licensed or unlicensed users enrolled after receiving notification of an ad hoc file transfer:         </td>
         <td>If the account template is for licensed or unlicensed users enrolled after receiving notification of an ad hoc file transfer:         </td>
         <td>If the account template is for licensed or unlicensed users enrolled after receiving notification of an ad hoc file transfer:         </td>
      </tr>
      <tr>
         <td>Email Contact         </td>
         <td><code>${stenv.recipient_email}</code>         </td>
         <td>Returns the email address for recipient of the ad hoc file transfer.         </td>
      </tr>
      <tr>
         <td>Home Folder         </td>
         <td><code>${stenv.recipient_email}</code>         </td>
         <td>Returns the email address for recipient of the ad hoc file transfer to create a unique home folder.         </td>
      </tr>
   </tbody>
</table>

The following table gives examples of expressions in transfer sites:

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Field         </th>
<th class="HeadE-Column1-Header1">Expression         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>Upload Folder         </td>
         <td><code>/upload/${stenv.loginname}</code>         </td>
         <td>Returns the subfolder based on the user login name in the upload folder.         </td>
      </tr>
      <tr>
         <td>User Name         </td>
         <td><code>${stenv.loginname}</code>         </td>
         <td>Returns the user login name.         </td>
      </tr>
      <tr>
         <td>Certificate         </td>
         <td><code>x509_${stenv.loginname}</code>         </td>
         <td>Returns the user login certificate.         </td>
      </tr>
      <tr>
         <td>With Advanced Expressions selected, you can use the following complex expressions:         </td>
      </tr>
      <tr>
         <td>Upload Folder         </td>
         <td><code>/${stenv['target'].</code><br />
<code>replace('^(.*)_(.*)_(.*)$','$2')}</code>or<br />
<code>/upload/${stenv['target'].</code><br />
<code>matches('.*\\.((jpg)|(gif)|(txt))$') ? stenv['target'].</code><br />
<code>replace('^.*\\.((txt)|(jpg)|(gif))$','$1') : 'general/'}</code>         </td>
         <td>Returns the upload folder based on the match and replace expression criteria.         </td>
      </tr>
      <tr>
         <td>Enable SSL         </td>
         <td><code>${stenv['target'].matches('^(ssl).*')}</code>         </td>
         <td>Returns a 0 (false) or 1 (true) based on the match criteria.         </td>
      </tr>
   </tbody>
</table>

> **Note:**
>
> You can also use regular expressions such as ${stenv.target}only to return the file name or ${filename(stenv.target)}-${random} to change the file name.

The following table gives examples of expressions in subscriptions:

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Field         </th>
<th class="HeadE-Column1-Header1">Expression         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>Subscription Folder         </td>
         <td><code>mailbox_el_${stenv.useruid}</code>         </td>
         <td>Returns the folder using the UID.         </td>
      </tr>
      <tr>
         <td><code>${flow.attributes['userVars.ATTRIBUTE_NAME']}</code>         </td>
         <td>Returns the folder using the attribute name.         </td>
      </tr>
      <tr>
         <td>Receive Options<br />
Decrypt PGP File As:         </td>
         <td><code>${stenv.loginname}_${embedded}</code>         </td>
         <td>Returns a file name based on the login name and the embedded file name.         </td>
      </tr>
      <tr>
         <td>Keep Original As:         </td>
         <td><code>archive/${date('yyyy.MM.dd')}/</code><br />
<code>${filename(stenv.transformation_input)}</code>         </td>
         <td>Returns the location and file name based on the date and the PGP file name.         </td>
      </tr>
      <tr>
         <td>With Advanced Expressions selected, you can use the following complex expressions:         </td>
      </tr>
      <tr>
         <td>Send Options<br />
Send Files Directly To:         </td>
         <td><code>${stenv.loginname}_ftp</code>         </td>
         <td>Returns a location based on the user login name.         </td>
      </tr>
      <tr>
         <td>Receive Options<br />
Decrypt PGP File:         </td>
         <td><code>${stenv['target'].</code><br />
<code>matches('.*((\\.pgp)|(\\.gpg)|(\\.asc))')}</code>         </td>
         <td>Returns a 0 (false) or 1 (true) based on the match criteria.         </td>
      </tr>
      <tr>
         <td>As:         </td>
         <td><code>${empty embedded ? filename(stenv.transformation_input).replace('(\\.pgp)|(\\.gpg)|(\\.asc)') : embedded}</code>         </td>
         <td>Returns the file name to which the decrypted file is saved.         </td>
      </tr>
      <tr>
         <td>Keep Original:         </td>
         <td><code>1</code>         </td>
         <td>The value <code>1</code> represents true. <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> recognizes the field as being selected.         </td>
      </tr>
      <tr>
         <td>As:         </td>
         <td><code>archive/${date('yyyy.MM.dd')}/</code><br />
<code>${filename(stenv.transformation_input)}</code>         </td>
         <td>Returns the file name based on the original PGP file name.         </td>
      </tr>
      <tr>
         <td>Use Data Compression         </td>
         <td><code>${extension(filename(stenv.transformation_input))</code><br />
<code>.matches('(\\.jpg)|(\\.mov)') ? 0 : 1}</code>         </td>
         <td>Returns a <code>0</code> when the file extension is .<code>jpg</code> or <code>.mov</code>. These file types are already compressed and do not require compression.         </td>
      </tr>
      <tr>
         <td>Compression Type         </td>
         <td><code>2</code>         </td>
         <td>Compresses the file using ZLIB.         </td>
      </tr>
      <tr>
         <td>Compression Level         </td>
         <td><code>5</code>         </td>
         <td>Compresses the file using the Normal setting.         </td>
      </tr>
   </tbody>
</table>

<span id="Export"></span>

## Export an account template

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
