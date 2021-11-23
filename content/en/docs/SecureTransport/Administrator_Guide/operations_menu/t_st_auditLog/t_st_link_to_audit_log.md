{
    "title": "Link to the audit log",
    "linkTitle": "Link to the audit log",
    "weight": "200"
}The following Administration Tool pages have a **Last Modified** link that gives the date and time of the last update to any object listed:

-   Operations menu:
    -   Cluster Management – Enterprise Cluster only, indicates changes to the configuration of the cluster nodes only
    -   Server Configuration
-   Setup menu:
    -   Local Certificates
    -   Trusted CAs
    -   Internal CA
    -   Holiday Schedule
    -   Mail Template Repository
    -   File Archiving
    -   Network Zone List
    -   Edit Network Zone entry
-   Authentication menu:
    -   Login Settings
    -   LDAP Domains
    -   LDAP Domain
    -   User Type Ranges
    -   Home Folders
-   Accounts menu:
    -   User Account
    -   Unlicensed User Account
    -   Service Account
    -   Administrators
    -   Edit Administrator
    -   Administrative Roles
    -   Edit Administrative Role
    -   Account Template
    -   Passwords Files
    -   Edit Password File
    -   Business Units
    -   Business Units Settings
-   Access menu:
    -   User Classes
-   Application:
    -   Applications
    -   Application Details

If there has been no change to the object or objects since {{< SecureTransport/componentshortname  >}} was installed or upgraded to a version that includes the audit log, the link indicates `No tracked change`.

{{< SecureTransport/componentshortname  >}} stores configuration that you change on other pages of the Administration Tool in sever configuration parameters. Some pages save values that are not changed when you make a change, so the audit log might include entries for the corresponding server configuration parameters in addition to the ones for the fields you changed.

When you click a link on a page, {{< SecureTransport/componentshortname  >}} opens the *Audit Log* page and displayed the entry for the update that the link represents.

**Related topics:**

-   [Search and view audit log contents](../t_st_search_view_audit_log_contents)
-   [Enable or disable audit logging](../t_st_enable_disable_audit_logging)
-   [Export the results of an audit log search](../t_st_export_results_audit_log_search)
-   [Add or edit an audit log entry comment](../t_st_add_edit_audit_log_entry_comment)
-   [Display audit log entry details](../t_st_display_audit_log_entry_details)
-   [Compare audit log entries](../t_st_compare_audit_log_entries)
-   [Audit Log Maintenance application](../c_st_audit_log_maintenance_application)
