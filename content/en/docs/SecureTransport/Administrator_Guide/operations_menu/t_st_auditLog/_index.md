{
    "title": "Audit log",
    "linkTitle": "Audit log",
    "weight": "130"
}Use the *Audit Log* page to view, compare, and export log entries that SecureTransport records when any change is made to the SecureTransport configuration. The audit log entries record:

-   Changes made using the Administration Tool
-   Changes made using the administration REST API
-   Changes due to user actions, such as new user enrollment and password change
-   Changes that result from a change on another SecureTransport Server in a cluster or on another synchronized SecureTransport Edge
-   Changes to configuration objects, such as accounts, business units, and network zones
-   Changes to server configuration parameters, whether they are made on the *Server Configuration* page or on other Administration Tool pages

In an active/active Standard Cluster (SC), SecureTransport forwards audit log updates from the secondary servers to the primary server, so the audit log on the secondary servers includes local changes only and the audit log on the primary server includes changes to all servers in the cluster.

Many Administration Tool pages include a **Last Modified** link that you can use to display in the audit log the entry that records the last change for that page. From the audit log, you can compare that entry with the last one to see what changes were made or with any previous entry for that object or parameter.

You can filter the log using one or more of eight criteria to find an entry.

Each line in the log display includes the following information:

-   Time - The date and time the entry was logged. This column includes a drop-down menu indicated by an inverted caret that you can use to display more detailed information or compare log entries.
-   User Name - The name of the administrator or user who made the change.
-   Remote Address - The IP address of the client that made the configuration change – either a browser running the Administration Tool or a program using the administrator resources of the REST API.
-   Object Type - The type of the object changed. Possible values are:
    -   `Account` – for user account, unlicensed user account, service account and account template
    -   `Administrator`
    -   `AdministrativeRole`
    -   `Application`
    -   `BusinessUnit`
    -   `Certificate` – for certificate and trusted CA
    -   `CertificateSigningRequests`
    -   `ClusterNode`
    -   `HolidaySchedule`
    -   `LdapDomain`
    -   `LdapHomeFolderPrefix`
    -   `LdapUidRangeMapping`
    -   `MailTemplate`
    -   `NetworkZone`
    -   `PasswordVault`
    -   `Route`
    -   `ServerConfigurationParameter` – for changes that are not represented internally as objects by SecureTransport
    -   `SiteTemplate`
    -   `UserClass`
-   Object ID - A unique identifier for the object changed. For most configuration objects, the object ID is an internal ID.  
    For server configuration parameters, the object ID includes the server configuration parameter name, a node ID, and a profile ID. In a cluster, the node ID (`mNode`) identifies the server where a local server configuration parameters is changed. Otherwise, the value is `UNSPECIFIED`. SecureTransport 5.5 does not implement the feature that uses the profile ID (`mProfile`), so the value is always `Default`.
-   Object Name - The name of the object changed.
-   Operation - The type of operation that changed the object. The value can be `Create`, `Delete`, `Overwrite`, or `Update`.  
    When you add a user class, it is added as the first user class as shown on the *User Classes* page. The audit log shows an update for each user classes, because adding a class changes the `Order` attribute for every class.
-   Comment - Additional information added by SecureTransport or the administrator who made the change.
-   All Audit Log actions are reported into the Server Log as audit information messages and administrators can configure the audit messages to be logged into the SecureTransport database or a flat file using standard `log4j` configurations. The audit information messages in the Server Log can be machine read and analyzed, while the messages on the *Audit Log* page require interaction to identify what property has changed. The audit messages in the Server Log can also be filtered by the AUDIT component filter. For additional Server Log information, refer to [Server log](../t_st_serverlog).

The audit information messages are based on the `auditLogEntry` object data. The audit information messages are in the following format:

`<username> <operation> <objectType> <objectName> <description> [<list of properties>]`

Where:

-   `<username>` - The name of the user which performed the audit operation.
-   `<operation>` - The name of the operation performed. It could be one of the following – create, update, delete, or create\_or\_update.
-   `<objectType>`- The object type being audited.
-   `<objectName>` - The name of the object being audited.
-   `<description>` (optional) - The description defined for the given `auditLogEntry`. If a description is defined, it will be displayed.
-   `[list of properties]` - Contains the mapping between the property name and the old and new value. Only changed properties will be visible in this map. If there is nothing to compare with, all new properties will be visible.

The following topics describe managing the audit logs:

-   [Search and view audit log contents](t_st_search_view_audit_log_contents) - Describes viewing and searching the audit log contents.
-   [Enable or disable audit logging](t_st_enable_disable_audit_logging) - Provides how-to instructions on enabling and disabling audit logging.
-   [Export the results of an audit log search](t_st_export_results_audit_log_search) - Provides how-to instructions on exporting the results of an audit log search.
-   [Add or edit an audit log entry comment](t_st_add_edit_audit_log_entry_comment) - Provides how-to introductions on adding or editing an audit log entry comment.
-   [Display audit log entry details](t_st_display_audit_log_entry_details) - Provides how-to instructions on displaying audit log entry details.
-   [Compare audit log entries](t_st_compare_audit_log_entries) - Provides how-to instructions on comparing audit log entries.
-   [Link to the audit log](t_st_link_to_audit_log) - Describes the SecureTransport Administration Tool links to the audit log.
-   [Audit Log Maintenance application](c_st_audit_log_maintenance_application) - Describes the Audit Log Maintenance application.
