{
    "title": "Archive Maintenance application",
    "linkTitle": "Archive Maintenance application",
    "weight": "190"
}The Archive Maintenance application automatically deletes archived files based on a schedule you define.

You must enable the `ArchiveMaintApp` rules package in the Transaction Manager before you can use an Archive Maintenance application. For more information, see [Manage rules packages](../../c_st_setup/c_st_tm_settings/t_st_rulespackages).

The configuration for an Archive Maintenance application is stored in the database.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">If the database partition feature is not available because the export database feature is not installed, a warning message will be displayed. For additional information, refer to the <em><span>SecureTransport</span> Installation Guide</em>.         </td>
      </tr>
</table>

The Archive Maintenance application defines the file archiving maintenance job schedule. Archive settings and retention policy can be configured on the **Setup &gt; File Archiving** page and for each individual business unit.

For information on configuring the file archiving global configuration, see [File archiving global configuration](../../c_st_setup/c_st_file_archiving/t_st_file_archiving_conf).

1.  Select **Application** and click **Add New**.  
    The *New Application* page is displayed.

2.  Select **Archive Maintenance** from the mandatory **Application Type** list.

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

6.  (Optional) In the *Schedule* pane, click **Configure** to [Configure a schedule for a maintenance application](manage_applications.htm#configuremaintschedule).

7.  (Optional) Set **Additional attributes**: you can use the group of fields to add (or remove) custom attributes as *attribute:value* pairs. To add a new attribute: click **Add Attribute**, input entries for the attribute and value pair and click the Save (![](SaveIcon.png)) icon to store your input. To remove an attribute: select the corresponding checkbox and click **Delete**. You can also edit either entry (for attribute or value) of an existing attribute. See [Additional attributes](../../c_st_setup/t_st_mailtemplates/c_st_mail_template_commands_variables).

8.  Click **Create Application**.  
    To use the Archive Maintenance application, make sure that the `ArchiveMaintApp` and the `ArchiveAgent` rules packages are enabled in the *Rules Packages* page.

  
See parent topic: [Applications](..//securetransport/administrator_guide/applications) and follow shortcuts to other applications you need to create or configure.
