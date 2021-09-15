{
    "title": "Account export and import",
    "linkTitle": "Account export and import",
    "weight": "160"
}SecureTransport 5.5 supports import from the following releases only, patched to the latest patch or service pack – 5.4, 5.3.6, 5.3.5, 5.3.3, 5.3.1, 5.3.0, and 5.2.1. Accounts can be imported from export files produced by the same or another SecureTransport deployment.

SecureTransport provides a way to export or import all account information, such as account templates, user accounts, service accounts, business units, administrators, and site templates. Exported account template, user account, and service account information includes: user settings, transfer sites, transfer profiles, certificates, certificate requests, subscriptions, applications, business units, route packages, route package templates and their adjacent routes and steps, and those certificates that apply to all of the system.

You can use the command line interface or the Administration Tool to export and import the account information. Accounts can be exported to use as a template, to create a backup, to move from a test to a production environment, or to move from one platform to another.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">Only a master administrator or a delegated administrator with the appropriate privileges can use the Administration Tool to import or export accounts. For more information, see <a href="../c_st_delegatedadministration" xrefformat="{paratext}">Delegated administration</a>. Any administrator who can access the server can use the command line to import or export accounts.<br/>         </td>
      </tr>
</table>

Information is exported to and imported from an XML file. This file can be edited and re-imported. Sensitive information such as private keys and passwords are encrypted during the export process, and you are asked to create a password to protect the sensitive information. When you import the account information, you are asked for the password to allow the sensitive information to be decrypted.

The following topics describe the account XML schema and how to edit the account XML schema. They also provide how-to instructions for exporting and importing accounts.

-   [Account XML schema](c_st_account_xml_schema) - Describes the account XML schema.
-   [Edit an XML file](c_st_edit_xml_file) - Describes how to edit an XML file.
-   [Export and import accounts](t_st_importandexportaccounts) - Provides how-to instructions for exporting and importing accounts.
