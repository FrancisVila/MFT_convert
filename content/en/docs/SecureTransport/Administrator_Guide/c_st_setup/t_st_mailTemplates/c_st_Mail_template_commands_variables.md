{
    "title": "Mail template commands and variables",
    "linkTitle": "Mail template commands and variables",
    "weight": "260"
}When you create a custom mail template, make sure to include the CSS in the `<style>` element in the default file, `AdhocDefault.xhtml`. You can download the default mail template, rename it, customize it and upload your custom mail template.

The following topics lists the notification type and information variables and provide an email template variable example:

-   [Notification type variables](#notification_type)
-   [Notification information variables](#notification_info)
-   [Additional attributes](#addition)
-   [Flow and subscription attributes](#flow)
-   [Email template variable example](#email)

## <span id="Notification_type"></span>Notification type variables

Reference the following variables in the `display` property of the `style` attribute of an XHTML element in the mail template to select what information is included:

-   `$DISPLAY_ENROLLMENT` – Enrollment notification
-   `$DISPLAY_DELIVERY` – Delivery success or failure notification
-   `$DISPLAY_PKG_INFO` – Message information including the sender, the recipient, and the message text
-   `$DXAGENT_CORE_ID` – File identifier ([coreID)](../../../operations_menu/c_st_filetransfertracking/t_st_viewfiletransferinfo) of the transferred file(s)
-   `$DXAGENT_FORMATTED_END_EVENT_TIME` – Date and time of the event that triggered the notification. Timestamp Format: `MM/dd/yyyy HH:mm:ss.SSS`
-   `$DISPLAY_FAILURE_ENROLLMENT` – Enrollment failed
-   `$DISPLAY_FAILURE_FORBIDDEN` – Delivery was forbidden based on the delivery method
-   `$DISPLAY_FAILURE_GENERAL` – General delivery failure
-   `$DISPLAY_FAILURE_RECIPIENT` – Delivery to the recipient failed
-   `$DISPLAY_FAILURE_UNRESOLVED` – The recipient could not be resolved

If the value of a variable is the empty string, the information is displayed. If the value is `none`, the information is not displayed.

## <span id="Notification_info"></span>Notification information variables

The following variables contain information used in account enrollment notifications:

-   `$ENROLL_USERNAME` – User name for enrollment
-   `$ENROLL_PASSWORD` – Password for enrollment
-   `$ENROLL_LOGINURL` – URL
    for enrollment using `$ENROLL_USERNAME` and `$ENROLL_PASSWORD`

The following variables contain information used in package delivery failure notifications:

-   `$PKG_FAILURE_ENROLLMENT` – Error message for an account enrollment failure
-   `$PKG_FAILURE_FORBIDDEN` – Error message for a forbidden delivery failure
-   `$PKG_FAILURE_GENERAL` – Error message for a general delivery failure
-   `$PKG_FAILURE_RECIPIENT` – Error message when the email cannot be delivered to a recipient
-   `$PKG_FAILURE_UNRESOLVED` – Error message when an account cannot be resolved
-   `$PKG_TO` – Recipients from the TO list
-   `$PKG_CC` – Recipients from the CC list
-   `$PKG_BODY` – Text of the message
-   `$PKG_ATTACHMENTS` – Names of the files attached to the message

## <span id="Addition"></span>Additional attributes

You can add custom attributes to several *objects* in SecureTransport (for example *user accounts*, or *business units*, or *applications*) added as *custom properties* in the format of *key:value* parameters. Additional attributes are available with the following objects: user accounts, service accounts, unlicensed users, account templates, transfer sites, transfer profiles, business units, site templates, route packages, route package templates, login restriction policies, applications and certificates.

Additional attributes can be classified to ones pertinent to *accounts* and *account templates*, and all the others. The biggest difference is that you can use Expression Language (EL) with attributes for *accounts* and *account templates*, whereas this option is not available with all the others.

In the SecureTransport Administration Tool, all attributes are defined using the prefix `userVars` (user variables).

### Additional attributes for Accounts and Account templates

You can use these custom attributes to include in your email templates. Additional attributes with accounts and account templates can be used with Expression Language (EL). The respective screen for each provides the controls to create, delete and edit them: see [user accounts](../../../accounts/useraccounts/t_st_create_user_account) and [account templates](../../../c_st_advancedaccountadministration/c_st_accounttemplates/t_st_accounttemplates).

After you have set additional attributes, you can use them with email notifications. You can assign any attribute:value pair that serves your purposes, for example:

<table cellspacing="0">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Attribute</th>
         <th>Value</th>
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

##### **User variables with email notifications**

To use `userVars` for email notifications, you must create your own mail template and specify the desired value with the following expression:

`$DXAGENT_ACCOUNT_ATTR_USERVARS_{KEY}`

Where `KEY` is the additional attribute key.

For example, if you want a *user name* defined in the Additional Attributes, you must type:

`$DXAGENT_ACCOUNT_ATTR_USERVARS_NAME`

##### **Using '.' in key names**

If the key of an additional attribute contains period characters '`.`' in its name, when using this attribute in an email template, you must replace all period characters with underscores '`_`'.

For example:

To use `userVars.name.first` in an email template you must type:

`$DXAGENT_ACCOUNT_ATTR_USERVARS_NAME_FIRST`

If there is a collision between Additional Attribute keys after they are used for email template notifications, the value to which they will be evaluated in email template is not determined.

For example:

`userVars.name_first` and `userVars.name.first` are both used as:

`$DXAGENT_ACCOUNT_ATTR_USERVARS_NAME_FIRST`

It is not definitive to which value this expression is going to be evaluated.

### Usage specifics with all other additional attributes

Apart from Account and account templates, you can set additional attributes on the following screens in the SecureTransport Administration tool:

-   [Transfer sites](../../../accounts/transfersites)
-   [Transfer profiles](../../../accounts/t_st_transferprofiles)
-   [Manage business units](t_st_businessunits.htm)
-   [Manage site templates](../../../c_st_advancedaccountadministration/c_st_sitetemplates/t_st_sitetemplates)
-   [Manage Route Package Templates](../../../c_st_advanced_routing/c_st_configuration/t_st_manage_route_package_templates)
-   [Manage Login Restriction Policies](../../../c_st_accesscontrol/c_st_loginrestictions/t_st_manloginrestictions)
-   [Applications](../../../applications)
    (applicable to all application types)

You cannot use these in email templates and they are not available for use in EL expressions: these cannot be accessed via `userVars`. Everything else is the same: the UI to create, delete and edit attributes; the format and validation rules apply in the same fashion.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">Additional attributes are per object and are not inherited from parent objects.          </td>
      </tr>
</table>

#### Additional attributes of certificates

With certificates, there is no UI in the SecureTransport Administration Tool to create, edit or delete attributes. You can only set to use these with the SecureTransport admin REST API. See the [Swagger REST API documentation]() for reference. While generally referring to certificates, these attributes are available for:

-   [Certificate Management page](../../c_st_certificates/c_st_certificate_management_page)
-   [Manage login certificates](../../../accounts/c_st_usercertificates/t_st_usercertificates)
-   [Manage partner certificates](../../../accounts/c_st_usercertificates/manage-user-partner-certificates)
-   [Manage private certificates](../../../accounts/c_st_usercertificates/manage-user-private-certificates)

## <span id="Flow"></span>Flow and subscription attributes

Flow and subscription attribute user variables (`userVars`) are defined per subscription in the *Flow/Subscription Attributes* pane. See [Subscribe an account to an application](../../../accounts/c_st_subscriptions/t_st_subscriptions).

To use `userVars` for email notifications, you must create your own mail template and specify the desired value with following expression:

`$DXAGENT_SUBSCRIPTION_ATTR_USERVARS_{KEY}`

Where `KEY` is the flow attribute key.

For example, if you want a user name defined in the Flow Attributes, you must type:

`$DXAGENT_SUBSCRIPTION_ATTR_USERVARS_NAME`

If the key of a flow attribute contains periods (`.`) in its name, you must replace all periods with underscores (`_`) when using this attribute in an email template.

For example:

To use `userVars.name.first` in an email template you must type:

`$DXAGENT_SUBSCRIPTION_ATTR_USERVARS_NAME_FIRST`

If there is a collision between Flow Attributes keys after they are used for email template notifications, the value to which they will be evaluated in the email template is not determined.

For example:

`userVars.name_first` and `userVars.name.first` are both used as:

`$DXAGENT_SUBSCRIPTION_ATTR_USERVARS_NAME_FIRST`

It is not clear to which value this expression is going to be evaluated.

## <span id="Email"></span>Email template variable example

The following example from the default email template uses a variable to select a row of a table that includes information from another variable.

    <tr >
       <th>To</th>
       <td >$PKG_DELIVERY_TO</td>
    </tr>

**Related topics:**

-   [Add, delete, upload or download a mail template](t_st_add_mail_template.htm)
-   [Download a mail template](t_st_download_%20mail_template.htm)
-   [Upload an updated mail template](t_st_upload_updated_mail_template.htm)
-   [Delete mail templates](t_st_delete_mail_templates.htm)