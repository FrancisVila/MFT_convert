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

If there has been no change to the object or objects since <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> was installed or upgraded to a version that includes the audit log, the link indicates `No tracked change`.

<span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> stores configuration that you change on other pages of the Administration Tool in sever configuration parameters. Some pages save values that are not changed when you make a change, so the audit log might include entries for the corresponding server configuration parameters in addition to the ones for the fields you changed.

When you click a link on a page, <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> opens the *Audit Log* page and displayed the entry for the update that the link represents.

**Related topics:**

-   <a href="../t_st_search_view_audit_log_contents" class="MCXref xref">Search and view audit log contents</a>
-   <a href="../t_st_enable_disable_audit_logging" class="MCXref xref">Enable or disable audit logging</a>
-   <a href="../t_st_export_results_audit_log_search" class="MCXref xref">Export the results of an audit log search</a>
-   <a href="../t_st_add_edit_audit_log_entry_comment" class="MCXref xref">Add or edit an audit log entry comment</a>
-   <a href="../t_st_display_audit_log_entry_details" class="MCXref xref">Display audit log entry details</a>
-   <a href="../t_st_compare_audit_log_entries" class="MCXref xref">Compare audit log entries</a>
-   <a href="../c_st_audit_log_maintenance_application" class="MCXref xref">Audit Log Maintenance application</a>
