{
    "title": "Transfer Log Maintenance application",
    "linkTitle": "Transfer Log Maintenance application",
    "weight": "320"
}The Transfer Log Maintenance automatically deletes transfer log records that are older than a specified number of days (30 days by default). You can schedule how often to run this application and configure it to optionally export these records before deletion.

You must enable the `TransferLogMaintApp` rules package in the Transaction Manager before you can use a Transfer Log Maintenance application. For more information, see <a href="../transaction_manager/t_st_rulesPackages.htm#EnableRulesPackage#Enable" class="MCXref xref">Manage rules packages</a>.

> **Note:**
>
> For Microsoft SQL Server, the number of the pre-created partitions depends on the Partition.DaysToPrebuild server configuration option. For heavy loaded environments, Axway recommends the value of this option to be greater than 7. This will help you avoid serious deadlocks in case the needed partition is not created.

Use the following procedure to create a Transfer Log Maintenance application.

> **Note:**
>
> You can also use the log\_export command-line utility to export transfer log entries.

1.  Select **Application** and click **Add New**.  
    The *New Application* page is displayed.

2.  Select **Transfer Log Maintenance** from the mandatory **Application Type** list.

3.  Enter a unique **Application Name**. You cannot enter spaces-only values in this field. For more information, see <a href="../../accounts/useraccounts/t_st_create_user_account#Spaces" class="MCXref xref">Spaces in required fields</a>.  

    > **Note:**
    >
    > The application name cannot include any forward slash (/) characters.

4.  (Optional) Use the **Assign** and **Remove** buttons to assign business units for the application. The **Business Unit List** contains the names of business units you have created. For details, see <a href="../../c_st_advancedaccountadministration/c_st_businessunits#Advanced_Accounts_2036285406_1127756" class="MCXref xref">Business units</a>.  

    > **Note:**
    >
    > Assigning business units to the application controls which delegated administrators can manage the application. It does not control to be processed by the Transfer Log Maintenance application.

5.  (Optional) Enter an application **Description**.

6.  In the **Delete transfer log when \_\_\_\_ days old** field, specify how old in days transfer log entries will be when they are deleted. The application computes the age of transfer log entries to midnight of the day it is run. For example, if the value of this field is `1` and the application runs at 4:00 AM., the application deletes entries created before midnight on at the beginning of the previous day. It does not delete entries created between midnight and 4:00 AM. on the previous day. This field is mandatory.  
    You cannot enter spaces-only values in this field. For more information, see <a href="../../accounts/useraccounts/t_st_create_user_account#Spaces" class="MCXref xref">Spaces in required fields</a>.

7.  (For MSSQL only) In the **Delete in-progress transfers that started more than \_\_\_\_ days ago** field, specify a period in days after which the in-progress transfers to be deleted. Consider using the same value for finished and in-progress transfers. Otherwise, the result could be performance degradation a failure to execute the application.

8.  (Optional) Configure the export of the Server log entries before deletion. The procedure differs depending on the database you use. For complete instructions, see <a href="#Configur" class="MCXref xref">Configure transfer log exports</a>

9.  (Optional) In the *Schedule* pane, click **Configure** to <a href="#ConfigureMaintSchedule" class="MCXref xref">Configure a schedule for a maintenance application</a>.

10. (Optional) Set **Additional attributes**: you can use the group of fields to add (or remove) custom attributes as *attribute:value* pairs. To add a new attribute: click **Add Attribute**, input entries for the attribute and value pair and click the Save (![](/Images/SecureTransport/SaveIcon.png)) icon to store your input. To remove an attribute: select the corresponding checkbox and click **Delete**. You can also edit either entry (for attribute or value) of an existing attribute. See <a href="../../c_st_setup/t_st_mailtemplates/c_st_mail_template_commands_variables#Addition" class="MCXref xref">Additional attributes</a>.

11. Click **Create Application**.

<span id="Configur"></span>

## Configure transfer log exports

You can optionally configure the Transfer Log Maintenance application to export the old transfer log records before deleting them. This procedure differs depending on the type of your database.

### Export from Microsoft SQL Server database

Using export functionality for Microsoft SQL server might compromise your backup strategy as it backs up/ re-initializes the TransactionLog. Use it with caution on databases that have other backup strategy.

To export logs from an embedded database or an external Microsoft SQL Server database:

1.  Select **export data before deletion** as **Data export option**.
2.  In the **Export folder** field, specify where the export files are stored. You must enter a full directory path.
3.  Complete the following steps on the Microsoft SQL server:
    1.  Create an export directory.

    2.  Create a new filegroup:

    3.  `ALTER DATABASE databaseuser ADD FILEGROUP [ST_FILETRACKING_ARCHIVE]`

    4.  Create a file:

    5.  ALTER DATABASE databaseuser
                 ADD FILE
                 (NAME = N'ST_FILETRACKING_ARCHIVE_databaseuser',
                 FILENAME = N'<EXPORT_DIR>\ST_FILETRACKING_ARCHIVE_databaseuser.ndf',
                 SIZE = 10MB,
                 MAXSIZE = 100MB,
                 FILEGROWTH = 1MB)
                 TO FILEGROUP [ST_FILETRACKING_ARCHIVE]
            GO

    6.  Grant all permissions on the `<EXPORT_DIR>` directory created in step "a" to the database user.

    7.  Grant the database user **Backup database** and **Backup log** permissions.

    8.  **Note:**
        >
        > The Backup log permission is only required if the database is in Full recovery mode.
4.  In the **Delete exported files when data is: \_\_\_\_ days old** field, type the period of time (in days) exported files remain in the export directory before they are deleted. If you leave this field empty or specify zero, {{< SecureTransport/componentshortname >}} does not delete the files.
5.  In the **Number of records per file: \_\_\_\_ thousands** field, specify the maximum number of records (in thousands) that can exist in an exported file. When this value is exceeded, {{< SecureTransport/componentshortname >}} starts to export the transfer log entries in a new file.

### Export from Oracle database

To export logs from an external Oracle database:

1.  Select **Enable logs export**.
2.  In the **Export folder** field, specify where the export files are stored. You must fill in the name of the directory defined in the Oracle database (for example, `ST_DMPDIR`).
3.  Complete the following steps on the Oracle Server:
    1.  Create the directory where the logs will be exported and make sure that the Oracle user has permissions.
    2.  Log in into Oracle as SYSDBA and create the `ST_DMPDIR` directory using the following syntax:
    3.  `CREATE DIRECTORY ST_DMPDIR AS '/YOUR_DIRECTORY_HERE';`
    4.  Grant all privileges on the directory to the ST user:
    5.  `GRANT ALL PRIVILEGES ON DIRECTORY ST_DMPDIR TO ST_DATABASE_USER`
    6.  Grant create table privileges to the ST user:
    7.  `GRANT CREATE TABLE TO ST_DATABASE_USER;`
4.  In the **Parallelism Degree** field, specify the number of processors to use during an export operation. You can specify any value for one to the number of processors available on the server. You can limit the effect of the export on database performance by limiting the number of processors used.

<span id="Export"></span>

### Export from PostgreSQL database

With Postgre, {{< SecureTransport/componentshortname  >}} uses partitioned tables for storing log data. During installation, five tables are created for storing transfer log data, named *subtransmissionstatus*, *transferdata*, *transferdetails*, *transferresubmitdata*, and *transferprotocolcommands*. Each table is partitioned daily.

For exporting records from a PostgreSQL database, {{< SecureTransport/componentshortname  >}} uses the *pg\_dump* utility that ships with PostgreSQL.

Use the following procedure to configure the application to export old transfer log records before deletion. Note that the database user must be either a superuser or a member of `pg_execute_server_program`.

1.  Make the local socket connections trusted or password protected (an encrypted local connection for exports is not supported).  
    On the PostgreSQL Server, open the *pg\_hba.conf* file for editing and modify/add the following line:  
    -   on Unix-based platforms: `local      all          all          trust` or `local all all password` )
    -   on Windows OS: `host all all 127.0.0.1/32 trust` or `host all all 127.0.0.1/32 password`
2.  On the PostgreSQL Server, create the directory where the logs will be exported and make sure that the PostgreSQL user has permissions.
3.  In the Transfer Log Maintenance application settings, select the **Enable logs export** check box.
4.  In the **Export folder** field, input the absolute path to the folder you created at Step 2.
5.  In the **path to pg\_dump utility** field, enter the absolute path to the *pg\_dump* utility including the file name (`pg_dump.exe` on Windows, `pg_dump` on Unix). Usually it's in the PostgreSQL's `bin` directory on the filesystem of the database server.
6.  Save the application settings.

  
See parent topic: <a href="../" class="MCXref xref">Applications</a> and follow shortcuts to other applications you need to create or configure.
