{
    "title": "Enable or disable audit logging",
    "linkTitle": "Enable or disable audit logging",
    "weight": "160"
}Audit logging is enabled by default. You can disable or enable it by setting the following server configuration parameters:

-   To disable logging of changes made by the Administration Tool, set the `AuditLog.Enabled.Admin` server configuration parameter to `false`. The default value is `true`.
-   To enable logging of changes made by the Transaction Manager, set the `AuditLog.Enabled.TM` server configuration parameter to `true`. The default value is `false`.

To change these parameters, see [View and change server configuration parameters](../../c_st_serverconfiguration/t_st_serverconfigurationparameters).

**Related topics:**

-   [Search and view audit log contents](../t_st_search_view_audit_log_contents)
-   [Export the results of an audit log search](../t_st_export_results_audit_log_search)
-   [Add or edit an audit log entry comment](../t_st_add_edit_audit_log_entry_comment)
-   [Display audit log entry details](../t_st_display_audit_log_entry_details)
-   [Compare audit log entries](../t_st_compare_audit_log_entries)
-   [Link to the audit log](../t_st_link_to_audit_log)
-   [Audit Log Maintenance application](../c_st_audit_log_maintenance_application)
