{
    "title": "Unlicensed Accounts Maintenance application",
    "linkTitle": "Unlicensed Accounts Maintenance application",
    "weight": "340"
}The Unlicensed Accounts Maintenance application deletes inactive unlicensed user accounts older than a specified number of days (60 days by default). You can schedule how often to run this application.

You must enable the `UnlicensedAccountMaintApp` rules package in the Transaction Manager before you can use a Unlicensed Account Maintenance application. For more information, see [Manage rules packages](../../c_st_setup/c_st_tm_settings/t_st_rulespackages).

Use the following procedure to create an Unlicensed Accounts Maintenance application.

1.  Select **Application** and click **Add New**.  
    The *New Application* page is displayed.

2.  Select **Unlicensed Accounts Maintenance** from the mandatory **Application Type** list.

3.  Enter a unique **Application Name**. You cannot enter spaces-only values in this field. For more information, see [Spaces in required fields](../../accounts/useraccounts/t_st_create_user_account).  
    

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

6.  In the **Delete unlicensed accounts when inactive for** field, specify how long in days an unlicensed account must be inactive before it is deleted.  
    You cannot enter spaces-only values in this field. For more information, see [Spaces in required fields](../../accounts/useraccounts/t_st_create_user_account).

7.  (Optional) In the *Schedule* pane, click **Configure** to[Configure a schedule for a maintenance application](manage_applications.htm#configuremaintschedule).

8.  (Optional) Set **Additional attributes**: you can use the group of fields to add (or remove) custom attributes as *attribute:value* pairs. To add a new attribute: click **Add Attribute**, input entries for the attribute and value pair and click the Save (![](SaveIcon.png)) icon to store your input. To remove an attribute: select the corresponding checkbox and click **Delete**. You can also edit either entry (for attribute or value) of an existing attribute. See [Additional attributes](../../c_st_setup/t_st_mailtemplates/c_st_mail_template_commands_variables).

9.  Click **Create Application**.

  
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
-   [Login Threshold Maintenance application](../applicationsloginthresholdmaintenance)
-   [Package Retention Maintenance application](../applicationspackageretentionmaintenance)
-   [Shared Folder application](../applicationssharedfolder)
-   [Site Mailbox application](../applicationssitemailbox)
-   [Standard Router application](../applicationsstandardrouter)
-   [Transfer Log Maintenance application](../applicationstransferlogmaintenance)
-   [File Maintenance application](../applicationsfilemaintenance)
