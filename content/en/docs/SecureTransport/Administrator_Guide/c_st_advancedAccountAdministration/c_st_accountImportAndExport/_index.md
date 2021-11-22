{
    "title": "Account export and import",
    "linkTitle": "Account export and import",
    "weight": "150"
}{{< SecureTransport/securetransportname  >}} {{< SecureTransport/componentversion  >}} supports import from the following releases only, patched to the latest patch or service pack – 5.4, 5.3.6, 5.3.5, 5.3.3, 5.3.1, 5.3.0, and 5.2.1. Accounts can be imported from export files produced by the same or another {{< SecureTransport/componentshortname  >}} deployment.

{{< SecureTransport/componentshortname  >}} provides a way to export or import all account information, such as account templates, user accounts, service accounts, business units, administrators, and site templates. Exported account template, user account, and service account information includes: user settings, transfer sites, transfer profiles, certificates, certificate requests, subscriptions, applications, business units, route packages, route package templates and their adjacent routes and steps, and those certificates that apply to all of the system.

You can use the command line interface or the Administration Tool to export and import the account information. Accounts can be exported to use as a template, to create a backup, to move from a test to a production environment, or to move from one platform to another.

> **Note:**
>
> Only a master administrator or a delegated administrator with the appropriate privileges can use the Administration Tool to import or export accounts. For more information, see Delegated administration. Any administrator who can access the server can use the command line to import or export accounts.

Information is exported to and imported from an XML file. This file can be edited and re-imported. Sensitive information such as private keys and passwords are encrypted during the export process, and you are asked to create a password to protect the sensitive information. When you import the account information, you are asked for the password to allow the sensitive information to be decrypted.

The following topics describe the account XML schema and how to edit the account XML schema. They also provide how-to instructions for exporting and importing accounts.

-   <a href="c_st_account_xml_schema" class="MCXref xref">Account XML schema</a> - Describes the account XML schema.
-   <a href="c_st_edit_xml_file" class="MCXref xref">Edit an XML file</a> - Describes how to edit an XML file.
-   <a href="t_st_importandexportaccounts" class="MCXref xref">Export and import accounts</a> - Provides how-to instructions for exporting and importing accounts.
