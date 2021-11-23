{
    "title": "Log Entry Maintenance application",
    "linkTitle": "Log Entry Maintenance application",
    "weight": "260"
}The Log Entry Maintenance application automatically deletes server log records that are older than a specified number of days. You can schedule how often to run this application and configure it to export these records before deletion.

You must enable the `LogEntryMaintApp` rules package in the Transaction Manager before you can use a Log Entry Maintenance application. For more information, see [Manage rules packages](../transaction_manager/t_st_rulesPackages.htm#EnableRulesPackage#Enable).

> **Note:**
>
> For Microsoft SQL Server, the number of the pre-created partitions depends on the Partition.DaysToPrebuild server configuration option. For heavy loaded environments, Axway recommends the value of this option to be greater than 7. This will help you avoid serious deadlocks in case the needed partition is not created.

Use the following procedure to create a Log Entry Maintenance application:

1.  Select **Application** and click **Add New**.  
    The *New Application* page is displayed.

2.  Select **Log Entry Maintenance** from the mandatory **Application Type** list.

3.  Enter a unique **Application Name**. You cannot enter spaces-only values in this field. For more information, see [Spaces in required fields](../../accounts/useraccounts/t_st_create_user_account#Spaces).  

    > **Note:**
    >
    > The application name cannot include any forward slash (/) characters.

4.  (Optional) Use the **Assign** and **Remove** buttons to assign business units for the application. The **Business Unit List** contains the names of business units you have created. For details, see [Business units](../../c_st_advancedaccountadministration/c_st_businessunits#Advanced_Accounts_2036285406_1127756).

5.  (Optional) Enter an application **Description**.

6.  In the **Delete log entries when** field, specify the period after which the log entries are deleted from the database. For external databases, the retention period is in days. For embedded databases, you can specify a period in days, hours, or minutes.  
    You cannot enter spaces-only values in this field. For more information, see [Spaces in required fields](../../accounts/useraccounts/t_st_create_user_account#Spaces).

7.  (Optional) Configure the export of the Server log entries before deletion. The procedure differs depending on the database you use. For complete instructions, see [Configure the Server log records export before deletion](#Configur)

8.  (Optional) In the *Schedule* pane, click **Configure** to [Configure a schedule for a maintenance application](#ConfigureMaintSchedule).

9.  (Optional) Set **Additional attributes**: you can use the group of fields to add (or remove) custom attributes as *attribute:value* pairs. To add a new attribute: click **Add Attribute**, input entries for the attribute and value pair and click the Save (![](/Images/SecureTransport/SaveIcon.png)) icon to store your input. To remove an attribute: select the corresponding checkbox and click **Delete**. You can also edit either entry (for attribute or value) of an existing attribute. See [Additional attributes](../../c_st_setup/t_st_mailtemplates/c_st_mail_template_commands_variables#Addition).

10. Click **Create Application**.

 

<span id="Configur"></span>

## Configure the Server log records export before deletion

You can optionally configure the Log Entry Maintenance application to export the old server log records before deleting them. This procedure differs depending on the type of your database.

### Export from Microsoft SQL Enterprise Edition database

Using export functionality for Microsoft SQL Server might compromise your backup strategy as it backs up/ re-initializes the TransactionLog. Use it with caution on databases that have other backup strategy.

To configure the application to export the Server log records before deletion, use the following procedure:

1.  In the **Export folder** field, specify where the export files are stored. You must enter the absolute directory path.
2.  Complete the following steps on the Microsoft SQL server:  
    1.  Create an export directory .

    2.  Create a new filegroup:  
        `ALTER DATABASE databaseuser ADD FILEGROUP [ST_SERVERLOG_ARCHIVE]`

    3.  Create a file:  


            ALTER DATABASE databaseuser
                 ADD FILE
                 (NAME = N'ST_SERVERLOG _ARCHIVE_databaseuser',
                 FILENAME = N'<EXPORT_DIR>\ST_SERVERLOG_ARCHIVE_databaseuser.ndf',
                 SIZE = 10MB,
                 MAXSIZE = 100MB,
                 FILEGROWTH = 1MB)
                 TO FILEGROUP [ST_SERVERLOG_ARCHIVE]
            GO

    4.  Grant all permissions on the `<EXPORT_DIR>` directory created in step "a" to the database user.

    5.  Grant the database user **Backup database** and **Backup log** permissions.  

        > **Note:**
        >
        > The Backup log permission is only required if the database is in Full recovery mode.
3.  In the **Delete exported files when data is: \_\_\_\_ days old** field, specify the period in days exported files remain in the export directory before they are deleted. If you leave this field empty or specify zero, {{< SecureTransport/componentshortname >}} does not delete the files.
4.  In the **Number of records per file** field, specify the maximum number of records that can exist in an exported file. When this value is exceeded, {{< SecureTransport/componentshortname >}} starts to export the server log entries in a new file.

> **Note:**
>
> You can also use the log\_export command-line utility to export server log entries.

### Export from Oracle database

When your server uses an Oracle database, {{< SecureTransport/componentshortname  >}} uses a partitioned table for the log entries. Your Oracle DBA can implement data export using Oracle functionality. If export database procedures are not deployed, the **Enable logs export** checkbox is disabled.

1.  Select the **Enable logs export** check box.
2.  In the **Export folder** field, specify where the export files to be stored. You must enter an absolute directory path. You must fill in the name of the directory defined in the Oracle database (for example, `ST_DMPDIR`).
3.  Complete the following steps on the database server on the Oracle Server:  
    1.  Create the directory where the logs will be exported and make sure that the Oracle user has permissions.
    2.  Log in into Oracle as SYSDBA and create the `ST_DMPDIR` directory using the following syntax:  
        `CREATE DIRECTORY ST_DMPDIR AS '/YOUR_DIRECTORY_HERE';`
    3.  Grant all privileges on the directory to the ST user:  
        `GRANT ALL PRIVILEGES ON DIRECTORY ST_DMPDIR TO ST_DATABASE_USER`
    4.  Grant create table privileges to the ST user:  
        `GRANT CREATE TABLE TO ST_DATABASE_USER;`
4.  In the **Parallelism Degree** field, specify the number of processors to use during an export operation. You can specify any value for one to the number of processors available on the server. You can limit the effect of the export on database performance by limiting the number of processors used.

<span id="Export"></span>

### Export from PostgreSQL database

With PostgreSQL, {{< SecureTransport/componentshortname  >}} uses partitioned tables for storing log data. During installation, three tables are created for storing the server log data, named *logging\_event*,*logging\_event\_exception*, and *logging\_event\_property*. Each table is partitioned daily.

For exporting records from a PostgreSQL database, {{< SecureTransport/componentshortname  >}} uses the *pg\_dump* utility that ships with PostgreSQL.

Use the following procedure to configure the application to export old server log records before deletion. Note that the database user must be either a superuser or a member of `pg_execute_server_program`.

1.  Make the local socket connections trusted or password protected (an encrypted local connection for exports is not supported).  
    On the PostgreSQL Server, open the *pg\_hba.conf* file for editing and modify/add the following line:  
    -   on Unix-based platforms: `local      all          all          trust` or `local all all password` )
    -   on Windows OS: `host all all 127.0.0.1/32 trust` or `host all all 127.0.0.1/32 password`
2.  On the PostgreSQL Server, create the directory where the logs will be exported and make sure that the PostgreSQL user has permissions.
3.  In the Log Entry Maintenance application settings, select the **Enable logs export** check box.
4.  In the **Export folder** field, input the absolute path to the directory you created at Step 2.
5.  In the **path to pg\_dump utility** field, enter the absolute path to the *pg\_dump* utility including the file name (`pg_dump.exe` on Windows, `pg_dump` on Unix). Usually it's in the PostgreSQL's `bin` directory on the filesystem of the database server.
6.  Save the application settings.

  
See parent topic: [Applications](../) and follow shortcuts to other applications you need to create or configure.

**Related topics:**

-   [Manage applications]()
-   [Applications](../)
