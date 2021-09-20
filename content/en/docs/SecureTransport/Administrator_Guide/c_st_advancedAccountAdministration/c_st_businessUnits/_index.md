{
    "title": "Business units",
    "linkTitle": "Business units",
    "weight": "230"
}Use business units to encapsulate certain information necessary for transfers into a single entity. When you create accounts and templates, you can specify a business unit to represent a particular set of information about the transfer. When you create a delegated administrator, you can specify business units (including users assigned to that business unit) to be managed by the delegated administrator. For more information, see [Delegated administration](../c_st_delegatedadministration).

The information contained in a business unit includes business unit name, base folder, a parent business unit, whether administrators are allowed to modify the base folder or the home folder, and which HTML template to use when users belonging to this business unit log in using the web client.

Use the *Business Units* page to see the available business units, search the list, delete business units, and invoke the editing process.

Use the *Business Units Settings* page to edit settings for a business unit.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">Only master administrators and delegated administrators with permissions for managing business units can create and delete business units and modify business a business unit's properties.         </td>
      </tr>
</table>

The following topics provide how-to instructions for managing business units:

-   See available business units
-   [Create or edit a business unit](#create)
-   [Delete a business unit](#delete)

## <span id="Display"></span>See available business units

Use the following procedure to display a list of business units.

1.  Select **Accounts > Business Units**.  
    The *Business Units* page is displayed. Business units that have child business units associated with them are called *parent business units* and are displayed with a plus sign (+).
2.  (Optional) To display child business units, click the plus sign next to a parent business unit.  
    The child business units are displayed under their respective parent units.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">Delegated administrators do not see business units as parents and children. All business units associated with a delegated administrator are displayed at the same level on the page.         </td>
      </tr>
</table>

## <span id="Create"></span>Create or edit a business unit

Use the following procedure to create or edit a business unit.

Select **Accounts &gt; Business Units**.  
The *Business Units* page is displayed.

Click **New Business Unit** or click the name of the business unit you want to edit.  
The *Business Units Settings* page is displayed.  


<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">The <em>Address Book Settings</em> pane is only displayed if the Address Book feature is enabled (the value of the <code>AddressBook.Enabled</code> configuration option is set to <strong>true</strong>).         </td>
      </tr>
</table>

If you are creating a business unit, enter a value in the **Name** field.  


<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">Business unit names are not case sensitive.         </td>
      </tr>
</table>

In the **Base Folder** field, specify a folder that is to contain the home directories of new accounts belonging to this business unit.

Select the **Allow Base Folder modifying** check box to allow administrators to change the base folder when creating an account.

Select the **Allow Home Folder modifying** check box to allow administrators to change the account name suffix when creating an account.

In the **Parent Business Unit** drop-down list, select the name of the parent business unit. If you do not want this business unit to be a child, select `None`, the default.  


<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">If the Business unit assigned to Delegated Administrator has child Business unit, the child Business Unit will be also assigned to this Delegated Administrator. 
			If Business unit does not have child, but another Delegated Administrator adds child, the newly added child will be automatically assigned to the first Delegated Administrator. If the child Business Unit is removed from the parent Business Unit but continues to exist, the Delegated Administrator will not be linked anymore.         </td>
      </tr>
</table>

In the **Network Zone** field, select the network zone that defines the public URL prefix for users in this business unit.  
Select **Default** to use the setting in the default network zone, or choose a specific network zone to use the setting defined for that zone  
For more information, see [Manage the communication across Transaction Manager, protocol and proxy servers](../../c_st_setup/c_st_networkzones/t_st_networkzones).

<span id="HTML_template_bu"></span>In the *HTML Template Settings* pane:   


1.  From the **HTML Template** drop-down, select the HTML template you want to use for accounts and account templates that belong to this business unit.
2.  Select the **Allow HTML Template modifying** check box to allow administrators to change the HTML template when editing or creating an account for this business unit.

In the *End user Transfers API* settings pane:  


1.  Select **Allow this account to submit transfers using the Transfers RESTful API** to enable calls from the SecureTransport REST file transfer API authenticated with the credentials from accounts in the business unit. When this option is selected, the account will be allowed to trigger server initiated transfers using the Transfers RESTful API resource and retrieve the tracking information for these transfers.
2.  Select **Allow end user to modify Transfers RESTful API settings** to allow a delegated administrator to modify this fields for users in the business unit.

In the *AdHoc Settings* pane:  


1.  Select **Login by email** to allow users in the business unit to log in using the value of the **Email Contact** field as well as the **Login Name**. A user of one of the Axway Email Plug-ins must be able to login by email.  
2.  Select the **Allow Login by Email modifying** check box to allow administrators to change the **Allow this account to login by email** field when editing or creating an account for this business unit.
3.  Select the **Allow Delivery Method modifying** check box to allow administrators to change the delivery method values when editing or creating an account for this business unit.
4.  Select the **Delivery Method** . The value controls the options that ST Web Client displays in the *User Access* window.
    See [Default Package Delivery Method](../../c_st_setup/t_st_adhocconfiguration).
5.  The **Implicit Enrollment Type** value controls which option ST Web Client selects initially in the *User Access* window and which enrollment type is used by the Axway Email Plug-ins. The choices depend on the enrollment types enabled by the **Delivery Methods** and **Enrollment Types** fields.
6.  Select the **Enrollment Template** for this business unit. When a user is enrolled based on an ad hoc file transfer from a user in this business unit, the selected account template is used. You specify the default enrollment template on the *AdHoc Settings* page.
7.  Select the **Email Notification Template** for this business unit. When a user is enrolled based on an ad hoc file transfer from a user in this business unit, the selected email notification template is used. You specify the [Provide the information as described in the following table:](../../c_st_setup/t_st_adhocconfiguration) on the *AdHoc Settings* page.

In the *Shared Folders Settings* pane, select the **Allow Shared Folders collaboration** check box to allow shared folders collaboration.  
This option is inherited from the business unit by the children of the business unit. When checked user accounts may collaborate using, creating, and sharing folders based on the following criteria:

1.  If the user accounts are not in the same BU but they have common ancestor then the business unit setting of the lowest common ancestor is used for deciding if sharing is allowed or not.
2.  If the user accounts are in one and the same business unit then the shared folder setting of the business unit is used for deciding if sharing is allowed or not.
3.  If the user accounts have business units assigned but there is no common ancestor then the global setting is used for deciding if sharing is allowed or not. See [View and change server configuration parameters](../../operations_menu/c_st_serverconfiguration/t_st_serverconfigurationparameters) for information on setting global parameters.
4.  If the owner account or the collaborator account (or both of them) has no assigned business unit then the global server setting is used for deciding if sharing is allowed or not. See [View and change server configuration parameters](../../operations_menu/c_st_serverconfiguration/t_st_serverconfigurationparameters) for information on setting global parameters.

To enable of disable ICAP servers for a specific Business Unit, select **Enable ICAP scan with server 'servername'**, from the list of all ICAP servers in the **ICAP Settings**, and the specified ICAP server will be enabled for this particular Business Unit.  
**Note:** Importing Legacy Business Unit Accounts (from any version before 5.4) will not import the Business Unit ICAP server selection/s. They must be manually activated after the import.  
  
For ICAP server configuration information, see [ICAP settings](../../c_st_setup/t_st_icap_settings).  

In the *File Archiving Settings* pane:

1.  Select the **File archiving policy** from the menu.

2.  -   When **Default** is selected, business unit inherits either its parent’s policy or the [File archiving global configuration](../../c_st_setup/c_st_file_archiving/t_st_file_archiving_conf) if it is a top level business unit.
    -   When **Enabled** is selected, file archiving will be enabled for all accounts from this business unit.
    -   When **Disabled** is selected, file archiving will be disabled for all accounts from this business unit.

3.  <table cellpadding="0" cellspacing="0">   <col/>   <col/>   <col/>      <tr>         <td valign="top">         </td>         <td valign="top"><span><b>Note</b></span>         </td>         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">This option will be disabled if the <strong>Enable File Archiving</strong> option from the global <em>File Archiving</em> page is turned off.         </td>      </tr></table>

4.  Use **Allow File archiving policy modifying** to enable or disable modification of the File Archiving policy [File archiving policydrop-down list](../../accounts/useraccounts/t_st_create_user_account).
    -   When **checked**, all the accounts that are assigned to this business unit can have their own file archiving policy.
    -   When **unchecked**, the corresponding option in account settings page will be disabled and accounts will inherit the business unit policy.

5.  Select the **Archive Folder** from the menu.
    -   When **Default** is selected, the business unit inherits its parent’s folder. If it's a top level business unit, the global file maintenance policy applies.
    -   When **Custom** is selected, the business unit defines its archive folder.

6.  <table cellpadding="0" cellspacing="0">   <col/>   <col/>   <col/>      <tr>         <td valign="top">         </td>         <td valign="top"><span><b>Note</b></span>         </td>         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">When you select this option, you must also provide archive folder absolute path. This option will be disabled  if the <strong>Enable File Archiving</strong> option from the global <em>File Archiving</em> page is turned off.         </td>      </tr></table>

7.  Select the **Encryption certificate** from the menu. The encryption certificate must be a local x.509 certificate. See [Manage local certificates and certificate signing requests](../../c_st_setup/c_st_certificates/t_st_localcertificatesandcsrs).
    -   When **Default** is selected, the business unit inherits either its parent’s encryption certificate or the global encryption certificate if it is a top level business unit.
    -   When **Disabled** is selected, archived files for accounts in this business unit won’t be encrypted.
    -   When **Custom** is selected, a dedicated encryption certificate can be selected for this business unit.

8.  Select the **Maximum file size to archive** from the menu.  

9.  -   When **Default** is selected, business unit inherits either its parent’s policy or the global file size limit policy if it is a top level business unit.
    -   When **Custom** is selected, file size limit will be enabled for all accounts from this business unit.
    -   When **Disabled** is selected, file size limit will be disabled for all accounts from this business unit.  

(Optional) In the *File Maintenance Settings* pane:  


1.  <span id="Select"></span>Select the **File Maintenance policy** from the menu.
    -   When **Default** is selected, the business unit inherits its parent’s policy. If it's a top level business unit, the global file maintenance policy applies.
    -   When **Disabled** is selected, File Maintenance will be disabled for this business unit.
    -   When **Custom** is selected, the panel expands with a *Custom settings* pane that allows you to modify the global [File Maintenance application](../../applications/applicationsfilemaintenance). The customized policy applies to the accounts in this business unit only.
2.  Use the **Allow File Maintenance policy modifying:** check box to enable or disable modification of the file maintenance policy at [File Maintenance policydrop-down list](../../accounts/useraccounts/t_st_create_user_account).
    -   When checked, all the accounts that are assigned to this business unit can have their own File Maintenance policy.
    -   When unchecked, the corresponding option in the user account settings page is disabled and the accounts inherit their business unit policy.

(Optional) In the *Account Maintenance Settings* pane:

1.  Select the **Account Maintenance policy** from the menu.

2.  -   When **Default** is selected, the business unit inherits its parent’s policy. In case of a top level business uni, the global Account Maintenance policy applies.
    -   When **Disabled** is selected, Account Maintenance is disabled for this business unit.
    -   When **Custom** is selected, the panel expands with a **Custom settings** pane that allows you to modify the existing [Account Maintenance application](../../applications/applicationsaccountmaintenance). The customized policy applies to accounts in this business unit only. Only at Business Unit level, you can select a specific date on which Account Maintenance will be performed for all accounts under this business unit.

3.  Use the **Allow Account Maintenance policy modifying** check box to enable or disable modification of the Account Maintenance policy at [Account Maintenance policydrop-down list](../../accounts/useraccounts/t_st_create_user_account).
    -   When checked, all the accounts that are assigned to this business unit can have their own Account Maintenance policy.
    -   When unchecked, the corresponding option in the user account settings page is disabled and the accounts inherit their business unit policy.

4.  <table cellpadding="0" cellspacing="0">   <col/>   <col/>   <col/>      <tr>         <td valign="top">         </td>         <td valign="top"><span><b>Note</b></span>         </td>         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">This option will be disabled  if the <strong>Enable File Archiving</strong> option from the global <em>File Archiving</em> page is turned off.         </td>      </tr></table>

(Optional) When the Address Book feature is enabled, the *Address Book Settings* pane is displayed. To configure the business unit Address Book settings:

1.  Select the Address Book source.
    -   **Default** - The business unit inherits either its parent's Address Book policy or the global Address Book policy if it is a top level business unit.
    -   **Custom** - A custom Address Book policy configuration will be set for this business unit only and the following will be configurable:
        -   Enable or disable Address Book sources for the business unit.
        -   Specify the parent groups for Address Book sources.
        -   Specify the domain for LDAP Address Book sources.
        -   Specify **All Business Units** or **User's own business unit** for local and custom Address Book sources.
    -   **Disabled** - The Address Book policy is set to disabled for this business unit.
2.  Specify whether or not to Allow collaboration with non-Address Book recipients. If Address Book functionality is disabled, this setting does not affect user collaboration.
    -   When **checked**, accounts that use the Address Book policy defined on the business unit level will be allowed to send email packages and share folders with users that do not exist the defined Address Book.
    -   When **unchecked**, accounts that use the Address Book policy defined on the business unit level will be allowed to send email packages and share folders only with users that exist in the defined Address Book.
3.  This business unit setting overrides the global Address Book policy setting for collaboration. This setting can be overridden on the account level if **Allow modifying of the 'Allow Address Book Collaboration' setting** is checked.
4.  Select **Allow modifying of the Collaboration setting** to enable modifying the **Allow Address Book collaboration** setting at the account level.
5.  Select Allow Address Book source settings to enable modifying of the Allow Address Book Policy modification at the account level. See [Address Book business unit level configuration](../../c_st_setup/address_book/address_book_conf).

In the *Login Restriction Policy* pane:

Select the **Business Unit Login Restriction Policy** from menu.

-   If **None (No Restriction)** is selected, the Global Login Restriction Policy (if configured) is the default Business Unit Login Restriction Policy.
-   If one of the configured Login Restriction Policies is selected, it becomes the default Business Unit Login Restriction Policy.

Select **Allow Login Restriction Policy modifying** to enable modifying of the Login Restriction Policy at the account level.  

In the *Bandwidth limits* pane:  

Select a **Bandwidth Limits Policy** to apply:  

-   **Default** – the current business unit inherits its bandwidth limits from the parent business unit or the global bandwidth
-   **Custom** – the panel expands with two additional options for you to configure: **Inbound limit** and **Outbound limit** (both values in kb/s per user)
-   **Disabled** – no bandwidth limits are applied to the users assigned to the current business unit

Select **Allow Bandwidth Limits Policy modifying** and the bandwidth limits on the account template and accounts level will be applicable to the accounts assigned to the current business unit. Deselect this option and bandwidth limits on the account template and accounts level will not override the business unit bandwidth limits.  

Click **Save**.

## <span id="Delete"></span>Delete a business unit

Use the following procedure to delete a business unit.

1.  Before you delete a business unit, make sure that it is not associated with any account, administrator, application, or route and that it does not have any child business units.
2.  Select **Accounts > Business Units**. The *Business Units* page is displayed.
3.  Using the checkboxes, select the business units to delete. To select or clear all the checkboxes, select or clear the check box in the table header.
4.  Click **Delete**. A confirmation window is displayed.
5.  Click **OK** to delete the selected business units.
