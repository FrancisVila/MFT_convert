{
    "title": "File archiving global configuration",
    "linkTitle": "File archiving global configuration",
    "weight": "300"
}The global file archiving configuration provides the inheritable file archiving configuration for users accounts and business units. For additional information on the inheritance of the file archiving configuration, refer to [File archiving](..//securetransport/administrator_guide/c_st_setup/c_st_file_archiving)

To enable and configure the global file archiving configuration:

1.  Navigate to **Setup > File Archiving**.  
    The *File Archiving* page is displayed.
2.  Select **Enable File Archiving**.  
    The additional field and menus on the *File Archiving* page become active.
3.  In the *File Archiving Settings* pane:
    1.  (Optional) Determine the default *Global archiving policy* to be applied by selecting either **Enabled** or **Disabled**. The default is **Disabled**. The policy configured here can be overridden at Business Unit or Account level.

    2.  Complete the **Archive folder** field by entering the absolute path to the global archive folder. The folder location can be overridden at Business Unit level.

    3.  (Optional) Determine whether or not to encrypt the global archive folder by selecting **Do not encrypt** or which configured certificate to use for encryption from the *Encryption Certificate* menu. The default is **Do not encrypt**. The chosen certificate can be overridden at Business Unit level. The encryption certificate must be a local x.509 certificate. For information on adding local certificates, refer to [Manage local certificates and certificate signing requests](../../c_st_certificates/t_st_localcertificatesandcsrs).

    4.  <table cellpadding="0" cellspacing="0">   <col/>   <col/>   <col/>      <tr>         <td valign="top">         </td>         <td valign="top"><span><b>Note</b></span>         </td>         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top"> When you delete or overwrite a certificate which previously was used for encryption, all files encrypted with  this certificate will be useless and can't be restored.         </td>      </tr></table>

        <table cellpadding="0" cellspacing="0">   <col/>   <col/>   <col/>      <tr>         <td valign="top">         </td>         <td valign="top"><span><b>Note</b></span>         </td>         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">When changing the encryption certificate, the Transaction Manager should be restarted in order for the changes to be applied.         </td>      </tr></table>

    5.  Set the options for **Delete files older than** field. You can specify days or hours and any number equal to or greater than 1. Files older than the configured period will be deleted by the maintenance job (if enabled).

    6.  Set the **Maximum file size allowed to archive** in Kilobytes. If the file is bigger or equal than the file size limit, it will not be archived. Empty or zero value means that no file size limit applies.
4.  Click Save.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">You must also configure maintenance job schedule for the Archive Maintenance application instance. For information on configuring the Archive Maintenance application instance, refer to <a href="../../../applications/applicationsarchivemaintenance" xrefformat="{paratext}">Archive Maintenance application</a>.         </td>
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
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">If you disable the File Archiving after being enabled and saved, the fields will stay populated with the old values, so if you enable it again you do not need to enter anything. If a certificate is selected, you cannot delete or overwrite it, even if file archiving is enabled or disabled. If you want to delete or overwrite it, you have to change the certificate option on the <em>File Archiving</em> page to another certificate or to <strong>Do not encrypt</strong>.         </td>
      </tr>
</table>