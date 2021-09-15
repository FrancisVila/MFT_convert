{
    "title": "Account Maintenance application",
    "linkTitle": "Account Maintenance application",
    "weight": "180"
}In SecureTransport 5.5, you can define an Account Maintenance policy to automatically delete, disable, or purge accounts based on account inactivity or age. You can configure account maintenance schedule and emails notifications, as well as email alerts for password and certificate expiration.

An Account maintenance policy can be set at three levels:

-   Global – by creating an Account Maintenance application without assigning it to a specific business unit. Only one instance of the Account Maintenance application can be created.
-   Business Unit – by modifying or disabling the global policy for a specific business unit (**Accounts > Business Unit > Account Maintenance**)
-   Account – by modifying or disabling the global or a business unit-level policy for a specific user account (**Accounts > User Account** section **&gt; Account Maintenance**)

An account or a business unit policy takes precedence over the global one. The account-level policy overrides any value defined for the same policy in the Business Unit settings.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">The Account Maintenance policy does not apply to unlicensed user accounts. For more information, see <a href="../applicationsunlicensedacctsmaintenance" xrefformat="{paratext}">Unlicensed Accounts Maintenance application</a>         </td>
      </tr>
</table>

Before you create an Account Maintenance application, make sure that the `AccountMaintenanceApp` rules package is enabled in the Transaction Manager. For more information, see [Manage rules packages](../../c_st_setup/c_st_tm_settings/t_st_rulespackages).

Use the following procedure to create an Account Maintenance application.

Select **Application** and click **Add New**.  
The *New Application* page is displayed.

Select **Accounts Maintenance** from the mandatory **Application Type** list.

Enter a unique **Application Name**. You cannot enter spaces-only values in this field. For more information, see [Spaces in required fields](../../accounts/useraccounts/t_st_create_user_account).  


<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">The application name cannot include any forward slash (<code>/</code>) characters.         </td>
      </tr>
</table>

(Optional) Use the **Assign** and **Remove** buttons to assign business units for the application. The **Business Unit List** contains the names of business units you have [Business units](../../c_st_advancedaccountadministration/c_st_businessunits). To create a global policy, do not assign a business unit.   


<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">If a business unit is assigned to the application, the Account Maintenance policy  will be applied ONLY to the accounts in this business unit and will NOT be applied to  accounts that don't belong to any business unit.           </td>
      </tr>
</table>

(Optional) Enter an application **Description**.

Define the *Account Maintenance Criteria*:  


-   account age   
    Select the **X day(s) after account creation or first maintenance job run** check box, and specify the period, in days, from the account creation date before a maintenance action is performed on that account. If an account does not have a creation date set, the first maintenance job run will be used instead.  
-   account inactivity  
    Select the **X day(s) of inactivity** check box and you specify the time period, in days, from the last login time of an account before a maintenance action is performed on that account. If current account doesn't have last login date set, the first maintenance job run will be used instead.

In the *Account Maintenance action* pane, select the action to be performed on the accounts that meet the criteria. You can choose to:  


-   **Delete account**  
-   **Delete and purge account**: deletes the account and the account home folder
-   **Disable account**
    -   When the **Disabled account** check box is selected, you can also specify a period, in days, after which the accounts disabled from Account Maintenance will be deleted. When a disabled account awaits deletion, a warning message will be notifying you on the account edit page.

Specify when an email notification about an upcoming maintenance action to be sent, its contents and recipients:  


-   Select the **Send email notifications X day(s) before action** check-box and specify how many days before the expected action execution date the notification to be sent. You can also input comma-separated values for the notifications period. For example, if you input *1,2,3*, then the email will be sent to user exactly 3 days, 2 days, 1 day before action execution.  
    **Note** The email notification will be sent to current account the first time it matches an Account maintenance criteria.
-   Select an **Email Template** from the drop-down to be used for the notification email. You can configure email template `AccountManagementNotification.xhtml` in **Setup** **&gt;** **Mail Templates**.

<!-- -->

-   Select **To (comma-separated list of emails)** to add a list of email addresses to which the notification to be sent. This option is not available at the account level.
-   Select the **To account email** to send the notification to the account's email address.

Configure additional email notifications to be sent when the account doesn't match maintenance criteria and no action is performed:  
  


Select the **Send additional email notifications for user password that is expiring after X day(s)** check box and specify when a password expiration notification to be sent. The timing of your notification is defined as the number of days before the expected password expiration date. You can also input comma-separated values for the notifications period.

The email password notification is sent to the specified account(s) once a day.

-   Use **Email Templatе** to select the template for user password expiration emails, and specify the notification recipients.

Select **Send additional email notifications for user certificates expiring after X day(s)** check box and specify the number of days after which additional email notifications for user certificates expiration will be sent. The timing of your notification is defined as the number of days before expected certificate expiration date. You can also input comma-separated values for the notifications period.

The email certificate notification will be sent to the specified account(s) once a day.

-   Use **Email Templatе** to select the template for user certificate expiration emails, and specify the notification recipients.

(Optional) In the *Schedule* pane, click **Configure** to[Configure a schedule for a maintenance application](manage_applications.htm#configuremaintschedule).

(Optional) Set **Additional attributes**: you can use the group of fields to add (or remove) custom attributes as *attribute:value* pairs. To add a new attribute: click **Add Attribute**, input entries for the attribute and value pair and click the Save (![](SaveIcon.png)) icon to store your input. To remove an attribute: select the corresponding checkbox and click **Delete**. You can also edit either entry (for attribute or value) of an existing attribute. See [Additional attributes](../../c_st_setup/t_st_mailtemplates/c_st_mail_template_commands_variables).

Click **Create Application**.

  
See parent topic: [Applications](..//securetransport/administrator_guide/applications) and follow shortcuts to other applications you need to create or configure.
