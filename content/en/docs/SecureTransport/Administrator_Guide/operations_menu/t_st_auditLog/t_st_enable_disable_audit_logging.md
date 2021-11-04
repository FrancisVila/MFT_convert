{
    "title": "Enable or disable audit logging",
    "linkTitle": "Enable or disable audit logging",
    "weight": "150"
}Audit logging is enabled by default. You can disable or enable it by setting the following server configuration parameters:

-   To disable logging of changes made by the Administration Tool, set the `AuditLog.Enabled.Admin` server configuration parameter to `false`. The default value is `true`.
-   To enable logging of changes made by the Transaction Manager, set the `AuditLog.Enabled.TM` server configuration parameter to `true`. The default value is `false`.

To change these parameters, see <a href="../../c_st_serverconfiguration/t_st_serverconfigurationparameters#top" class="MCXref xref">View and change server configuration parameters</a>.

**Related topics:**

-   <a href="../t_st_search_view_audit_log_contents" class="MCXref xref">Search and view audit log contents</a>
-   <a href="../t_st_export_results_audit_log_search" class="MCXref xref">Export the results of an audit log search</a>
-   <a href="../t_st_add_edit_audit_log_entry_comment" class="MCXref xref">Add or edit an audit log entry comment</a>
-   <a href="../t_st_display_audit_log_entry_details" class="MCXref xref">Display audit log entry details</a>
-   <a href="../t_st_compare_audit_log_entries" class="MCXref xref">Compare audit log entries</a>
-   <a href="../t_st_link_to_audit_log" class="MCXref xref">Link to the audit log</a>
-   <a href="../c_st_audit_log_maintenance_application" class="MCXref xref">Audit Log Maintenance application</a>
