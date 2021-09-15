{
    "title": "Export and import accounts",
    "linkTitle": "Export and import accounts",
    "weight": "200"
}Use the *Import or Export Accounts* page and command-line utilities to export and import SecureTransport accounts.

The following topics provide how-to instructions for exporting and importing accounts:

-   [Export accounts using the Administration Tool](#export_accounts)
-   [Export accounts from the command line](#export)
-   [Import accounts using the Administration Tool](#import_accounts)
-   [Import accounts from the command line](#import_accounts_com)

## <span id="Export_accounts"></span>Export accounts using the Administration Tool

You can export accounts using the SecureTransport Administration Tool. When you use the *Import or Export Accounts* page, all the account information on the server is exported. This includes user accounts, service accounts, account templates, certificates, application instances, business units, administrators, administrative roles, site templates, route packages, and route package templates. To export a single account from the Administration Tool, see [Export a single user account](../../../accounts/useraccounts/t_st_export_single_user_account). To control which account information is exported, see [Export accounts from the command line](#export).

The exported file is written to the `<FILEDRIVEHOME>/var/tmp/export_accounts.xml` file. This file is overwritten every time you export account information.

1.  Select **Accounts > Import/Export**.  
    The *Import or Export Accounts* page is displayed.

2.  Select **Export Accounts**.

3.  Enter a password in the **Password** field, then type the same password in the **Re-enter Password** field. The password must contain at least eight characters.

4.  Click **Export**. SecureTransport creates an export file in `<FILEDRIVEHOME>/var/tmp/export_accounts.xml` and displays a message indicating that the export was successful.

5.  To save the exported account information to a new location, click **Download Exported Accounts**. A dialog box displays prompting you to **Save** or **Open** the XML file.  
    

    <table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">You can download the exported file multiple times to the same or a new location. The Export Complete message with the <strong>Download Exported Accounts</strong> button remains, enabling you to download again, until you change tabs, select an option in the navigation bar at the left, or click <strong>Back</strong> twice.         </td>
      </tr>
</table>

6.  (Optional) To refresh the *Import or Export Accounts* page, select **Accounts > Import/Export** or click **Back** twice.

## <span id="Export"></span>Export accounts from the command line

Using the command line, you can export a single account or all the accounts. Exported account information includes: user accounts, administrators, administrative roles, transfer sites, site templates, transfer profiles, partner certificates, certificate requests, applications, subscriptions, and routes.

Run the `xml_export` utility in the `<FILEDRIVEHOME>/bin` directory from the command line to export account information into an XML file.

The form of the command is:

`./xml_export `\[`options`\] \[`fileNameAndPath`\] on a UNIX-based system

or

`xml_export `\[`options`\] \[`fileNameAndPath`\] on a Windows system

where `options` can be:

-   `-help` means display the usage information and exit.
-   `-acc=accountName` where *`accountName`* is the name of the account template, user or service account to export.
-   `-adm=adminName` where `adminName` is the name of the administrator account to export.
-   `-role=adminRoleName` where `adminRoleName` is the name of administrative role to export.
-   `-bu=buName` where `buName` is the name of the business unit to export.
-   `-st=stName` where `stName` is the name of the site template to export.
-   `-crt=certName` where `certName` is the name of the certificate to export.
-   `-app=appname` where `appName` is the name of the application to export.
-   `-pwd=passwordFile` where `passwordFile` is a file containing the password used to encrypt or decrypt sensitive information stored in the XML file. The text in this file is not encrypted. You can create the file using any text editor. If you do not use this option, the utility prompts you to type the password in the command window.
-   `-route=routeName` where routeName is the name of the route package template or global route package or orphan simple route to export.

and `fileNameAndPath` is the name and location of the XML file to write containing the exported data, such as `/user/XMLExport/ST_Acct_Export.XML`. If `fileNameAndPath` is not specified, `xml_export` writes the XML output to the standard output.

To export specific information, use only the option for the information you want. To export all items of one type, set the option to `*`, such as `-acc="*"`. To export all accounts, administrator accounts (including delegated administrators), administrative roles, business units, site templates, applications, and global certificates, do not use any of the `‑acc`, `‑adm`, `‑role`, `-bu`, `-st`, `‑crt`, or `‑app` options.

### Exporting a single account using the command line

When you export a single account the following items are not exported:

-   Applications
-   Business units
-   Global certificates
-   Site templates
-   Route package templates

It is best to use the single account export to create an XML template for account import only.

1.  On a UNIX-based system, change to the `<FILEDRIVEHOME>/bin` directory.
2.  Type the following command:  
    `./xml_export -acc=accountName fileNameAndPath` on a UNIX-based system   
    or  
    `xml_export -acc=accountName fileNameAndPath` on a Windows system   
    where `accountName` is the name of the account template, user account, or service account you want to export and `fileNameAndPath` is the XML file name and location where you want to store the exported data.
3.  When prompted, type a password for the exported information. This password is requested when you import the account from the file.
4.  Confirm the password by typing it again when prompted.  
    The XML file is created in the specified location.

### Export information using a specific option

You can use the command line to export only the information for a specific option such as global certificates or application instances.

### Export global certificates

1.  On a UNIX-based system, change to the `<FILEDRIVEHOME>/bin` directory.
2.  Type the following command:  
    `./xml_export -crt=certName FileNameAndPath` on a UNIX-based system   
    or  
    `xml_export -crt=certName FileNameAndPath` on a Windows system   
    where `certName` is the name of the global certificate you want to export or \* to export all global certificates and `FileNameAndPath` is the XML file name and location where you want to store the exported data. Multiple certificates may use the same name.
3.  When prompted, type a password for the exported information. This password is requested when you import the global certificates from the file.
4.  Confirm the password by typing it again when prompted.  
    The XML file is created in the specified location.

### Export an application

1.  On a UNIX-based system, change to the `<FILEDRIVEHOME>/bin` directory.
2.  Type the following command:  
    `./xml_export -app=appName FileNameAndPath` on a UNIX-based system   
    or  
    `xml_export -app=appName FileNameAndPath` on a Windows system   
    where `appName` is the name of the application you want to export or \* to export all the application instances and `FileNameAndPath` is the XML file name and location where you want to store the exported data.
3.  When prompted, type a password for the exported information. This password is requested when you import the application from the file.
4.  Confirm the password by typing it again when prompted.  
    The XML file is created in the specified location.

### Export a business unit

1.  On a UNIX-based system, change to the `<FILEDRIVEHOME>/bin` directory.
2.  Type the following command:  
    `./xml_export -bu=buName FileNameAndPath` on a UNIX-based system   
    or  
    `xml_export -bu=buName FileNameAndPath` on a Windows system   
    where `buName` is name of the business unit you want to export or \* to export all the business units and `FileNameAndPath` is the XML file name and location where you want to store the exported data.
3.  When prompted, type a password for the exported information. This password is requested when you import the business unit from the file.
4.  Confirm the password by typing it again when prompted.  
    The XML file is created in the specified location.

### Export a site template

1.  On a UNIX-based system, change to the `<FILEDRIVEHOME>/bin` directory.
2.  Type the following command:  
    `./xml_export -st=stName FileNameAndPath` on a UNIX-based system   
    or  
    `xml_export -st=stName FileNameAndPath` on a Windows system   
    where `stName` is name of the site template you want to export or \* to export all the site templates and `FileNameAndPath` is the XML file name and location where you want to store the exported data.
3.  When prompted, type a password for the exported information. This password is requested when you import the site template from the file.
4.  Confirm the password by typing it again when prompted.  
    The XML file is created in the specified location.

### Export a route package template, global route package, or orphan simple route

1.  On a UNIX-based system, change to the `<FILEDRIVEHOME>/bin` directory.
2.  Type the following command:  
    `./xml_export -route=routeName FileNameAndPath` on a UNIX-based system  
    or  
    `xml_export -route=routeName FileNameAndPath` on a Windows system  
    where `routeName` is the name of the route package template, global route package or orphan simple route you want to export or \* to export all the route package instances and `FileNameAndPath` is the XML file name and location where you want to store the exported data.
3.  When prompted, type a password for the exported information. This password is requested when you import the route from the file.
4.  Confirm the password by typing it again when prompted.  
    The XML file is created in the specified location.

### Export all the information using the command line

You can generate an XML file that contains all the account, global and account certificate, application, business unit, delegated administrator, and site template information to use as a backup or to move information from a test environment to a production environment.

1.  On a UNIX-based system, change to the `<FILEDRIVEHOME>/bin` directory.
2.  Type the following command:  
    `./xml_export FileNameAndPath` on a UNIX-based system   
    or  
    `xml_export FileNameAndPath` on a Windows system   
    where `FileNameAndPath` is the XML file name and location where you want to store the exported data.
3.  When prompted, type a password for the exported information. This password is requested when you import the information from the file.
4.  Confirm the password by typing it again when prompted.  
    The XML file is created in the specified location.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">To save and restore delegated administrator accounts correctly, you must export and import both server configuration and accounts.         </td>
      </tr>
</table>

## <span id="Import_accounts"></span>Import accounts using the Administration Tool

SecureTransport 5.5 supports import from the following releases only, patched to the latest patch or service pack – 5.4, 5.3.6, 5.3.5, 5.3.3, 5.3.1, 5.3.0, and 5.2.1. Accounts can be imported from export files produced by the same or another SecureTransport deployment.

You can import account information using the SecureTransport Administration Tool. The account information is imported as an XML file containing user settings, transfer sites, transfer profiles, account certificates, certificate requests, subscriptions, and route packages. You can also import business units, administrators, administrative roles, site template settings, applications, route package templates, and certificates. You must know the password assigned to the file when it was exported by SecureTransport. If you are creating an XML file from scratch, you must assign a password to the file.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">On SecureTransport installations with an embedded database, the import of accounts containing multiple objects may overload the Audit Log. Before you start importing, be sure to disable audit logging by changing the <code>AuditLog.Enabled.Import</code> configuration option value to <code>false</code>. After the account import completes, change it back to <code>true</code>.         </td>
      </tr>
</table>

Use the following procedure to import accounts using the Administration tool:

1.  Select **Accounts > Import/Export**.  
    The *Import or Export Accounts* page is displayed.
2.  Select **Import Accounts**.
3.  Type the name of the XML file you are importing in the **File Account** field or click **Browse** and locate the file in your system.  
    The system automatically validates the XML schema. If the schema is invalid, a warning message is displayed. For more information, see [Account XML schema](../c_st_account_xml_schema).  
    If the XML document is valid, the import process starts.
4.  In **Duplicated Accounts**, select **Overwrite** to overwrite the previous account settings or **Skip** to skip such accounts.  
    If an account\_export.xml, containing route templates instantiated by accounts with route packages, is imported with **Skip** option selected, to target SecureTransport Server, already configured with route templates, accounts and route packages, the corresponding imported route templates, accounts and route packages are rejected during the import if there are already objects with the same names in the target SecureTransport Server.
5.  Type the password created for the exported account file in the **Password** field.
6.  To stop the import process when an error occurs, select **Cancel Import on Error**.
7.  Click **Import**.  
    The import process begins. When the import is finished, a status message is displayed.

Account import will fail on the first error, and SecureTransport will not attempt to process it further, which means that there may still be more issues. Only one error is logged per import attempt; you can view it in the `<FILEDRIVEHOME>/var/tmp/rejected_import_records.xml` file. This error needs to be fixed before you try to import accounts again.

## <span id="Import_accounts_com"></span>Import accounts from the command line

SecureTransport 5.5 supports import from the following releases only, patched to the latest patch or service pack – 5.4, 5.3.6, 5.3.5, 5.3.3, 5.3.1, 5.3.0, and 5.2.1. Accounts can be imported from export files produced by the same or another SecureTransport deployment.

You can import accounts to move from one platform to another or to create a large number of accounts without creating them one at a time. Using an exported account as a template, you can create a list of new accounts that can be imported into SecureTransport.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">On SecureTransport installations with an embedded database, the import of accounts containing multiple objects may overload the Audit Log. Before you start importing, be sure to disable audit logging by changing the <code>AuditLog.Enabled.Import</code> configuration option value to <code>false</code>. After the account import completes, change it back to <code>false</code>.         </td>
      </tr>
</table>

Run the `xml_import` utility in the `<FILEDRIVEHOME>/bin` directory from the command line to import account information from an XML file. The utility has the following options and parameters:

The form of the command is:

`./xml_import [options] FileNameAndPath` on a UNIX-based system

or

`xml_import [options] FileNameAndPath` on a Windows system

where `options` can be:

-   `-dup=[overwrite|skip]` where `overwrite` overwrites duplicate account entries and `skip` does not import duplicate accounts. If no option is specified, the default setting is `overwrite`.
-   `-err=[continue|exit]` where `continue` continues importing the accounts when an error occurs and `exit` stops the utility when an error occurs. If no option is specified, the default setting is `exit`. Errors are written to the `admin.log` file
-   `-pwd=passwordFile` where `passwordFile` is a file containing the password used to encrypt or decrypt sensitive information stored in the XML file. You can use this file instead of typing the password from the command line. The text in this file is not encrypted. You can create the file using any text editor.
-   `-sync=[y|n]` where `y` synchronizes the imported accounts with all Servers in a Standard Cluster (SC) or Enterprise Cluster (EC) after the import and `n` only imports the accounts to the Server where the command is run. If no option is specified, the default setting is `y`.  
    Use `-sync=n` to reduce the time to import large numbers of accounts or accounts with many transfer sites or other features. Then restart the Transaction Manager and the Administration Tool server on the other Servers in the Standard Cluster or Enterprise Cluster to synchronize.

and `FileNameAndPath` is the location and file name of XML file containing the accounts you want to import, such as `/user/XMLExport/ST_Acct_Export.XML`.

### Import accounts from an XML file

1.  Make sure the Administration Tool server is running on all Servers in the Standard Cluster or Enterprise Cluster.
2.  On a UNIX-based system, change to the `<FILEDRIVEHOME>/bin` directory.
3.  Type the `xml_import` command.
4.  Type the password for the XML file at the prompt.  
    The accounts are imported into SecureTransport.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">Synchronization requires that the Administration Tool server  is running on all Servers in the cluster.         </td>
      </tr>
</table>

### Set the location of the overwrite file

If you set the `dup` option to `overwrite`, and a specific account, certificate, template, or application cannot be imported, the information is written to the following location:

`<FILEDRIVEHOME>`/var/tmp/rejected\_import\_records.xml

To store the overwrite information in a different directory relative to `<FILEDRIVEHOME>`, set the value of the `Directories.Directory.exportHome.path` parameter on the *Server Configuration* page to the relative path name for the directory. The default value is `/var/tmp`.

To store the overwrite information in a different directory not relative to `<FILEDRIVEHOME>`, clear the value of `Directories.Directory.exportHome.relative` and set the value of `Directories.Directory.exportHome.path` to the absolute path name for the directory.

 

**Related topics:**

-   [Account XML schema](../c_st_account_xml_schema)
-   [Edit an XML file](../c_st_edit_xml_file)
