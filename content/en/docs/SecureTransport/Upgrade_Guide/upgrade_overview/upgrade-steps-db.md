{
    "title": "Upgrade steps for Oracle databases",
    "linkTitle": "Upgrade steps for Oracle databases",
    "weight": "110"
}The following upgrade steps are optional and pertain to Oracle databases only.

## Export data from old Audit log and import it to the new one

The recommended method of migrating old data from the old Audit log table (AUDITLOG\_OLD in the example) to the new Audit log table (AUDITLOG in the example) is to use Oracle Data Pump.

Run the following commands as a user with DATA\_PUMP privileges:

    expdp [db_user]/[PASSWORD]  tables=<ST_SCHEMA>.AUDITLOG_OLD content=all dumpfile=AUDITLOG_OLD.dmp directory=[DB_DIRECTORY]impdp [db_user]/[PASSWORD] directory=[DB_DIRECTORY] remap_table=auditlog_old:auditlog dumpfile=AUDITLOG_OLD.dmp table_exists_action=append

 

 

    expdp [ST_SCHEMA_OWNER]/[ST_SCHEMA_OWNER_PASSWORD] directory=[DB_DIRECTORY] tables=auditlog_old content=all dumpfile=AUDITLOG_OLD.dmpimpdp [ST_SCHEMA_OWNER]/[ST_SCHEMA_OWNER_PASSWORD] directory=[DB_DIRECTORY] remap_table=auditlog_old:auditlog dumpfile=AUDITLOG_OLD.dmp table_exists_action=append
