{
    "title": "Login Threshold Maintenance application",
    "linkTitle": "Login Threshold Maintenance application",
    "weight": "280"
}The Login Threshold Maintenance application unlocks accounts locked according to the selected "Lock account after N successful logins" option in the *Account settings* and sends a report to specified email contacts.

Use the following procedure to create a Login Threshold Maintenance application.

1.  Select **Application** and click **Add New**.  
    The *New Application* page is displayed.

2.  Select **Login Threshold Maintenance** from the mandatory **Application Type** list.

3.  Enter an unique **Application Name**. You cannot enter spaces-only values in this field. For more information, see [Spaces in required fields](../../accounts/useraccounts/t_st_create_user_account).  
    

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

4.  (Optional) Use the **Assign** and **Remove** buttons to assign business units for the application. The **Business Unit List** contains the names of business units you have created. For details, see [Business units](../../c_st_advancedaccountadministration/c_st_businessunits).

5.  (Optional) Enter an application **Description**.

6.  (Optional) Select **Enable unlock functionality**. **Enable unlock functionality** is selected by default.

7.  (Optional) Select **Send Report**. If **Send Report** is selected, a report will be sent to the specified email addresses.
    -   If **Enable unlock functionality** is selected, the report will contain a list of unlocked users.
    -   If **Enable unlock functionality** is not selected, the report will contain a list of locked, due to login threshold functionality, users.

8.  Enter the email address or addresses to deliver the report to in the **Email Contact(s)** field. Email addresses can be separated by either a comma or a semicolon.

9.  Select the email template for the report from the **Report Email Template** list. The `LoginThresholdReport.xhtml` template is the default template for the Login Threshold Maintenance application.

10. (Optional) In the *Schedule* pane, click **Configure** to [Configure a schedule for a maintenance application](manage_applications.htm#configuremaintschedule).

11. (Optional) Set **Additional attributes**: you can use the group of fields to add (or remove) custom attributes as *attribute:value* pairs. To add a new attribute: click **Add Attribute**, input entries for the attribute and value pair and click the Save (![](SaveIcon.png)) icon to store your input. To remove an attribute: select the corresponding checkbox and click **Delete**. You can also edit either entry (for attribute or value) of an existing attribute. See [Additional attributes](../../c_st_setup/t_st_mailtemplates/c_st_mail_template_commands_variables).

12. Click **Create Application**.

  
See parent topic: [Applications](..//securetransport/administrator_guide/applications) and follow shortcuts to other applications you need to create or configure.

**Related topics:**

-   [Manage applications](manage_applications.htm)
-   [Archive Maintenance application](../applicationsarchivemaintenance)
-   [Audit Log Maintenance application](../applicationsauditlogmaintenance)
-   [Axway Sentinel Link Data Maintenance application](../applicationssentinellinkdatamaintenance)
-   [Axway Transfer CFT application](../applicationstransfercft)
-   [Basic Application](../applicationsbasic)
-   [File Transfer via File Services Interface application](../applicationstransferfileservicesinterface)
-   [Human to System application](../applicationsh2s)
-   [Log Entry Maintenance application](../applicationslogentrymaintenance)
-   [Package Retention Maintenance application](../applicationspackageretentionmaintenance)
-   [Shared Folder application](../applicationssharedfolder)
-   [Site Mailbox application](../applicationssitemailbox)
-   [Standard Router application](../applicationsstandardrouter)
-   [Transfer Log Maintenance application](../applicationstransferlogmaintenance)
-   [Unlicensed Accounts Maintenance application](../applicationsunlicensedacctsmaintenance)
