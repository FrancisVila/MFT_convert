{
    "title": "Connect and configure Oracle DB ",
    "linkTitle": "Connect and configure Oracle DB ",
    "weight": "100"
}Follow these instructions if you will be using Oracle DB with your {{< SecureTransport/componentshortname  >}} deployment. If you will be using PostgreSQL, see <a href="../connect-postgre" class="MCXref xref">Connect and configure PostgreSQL</a>.

## Connect to your Oracle database

1.  Navigate to AWS console -> Services.
2.  Go to the Database section and select **RDS**.
3.  Navigate to **Instances**.
4.  Select your newly created Database and then go to Instance Actions -> See Details.
5.  Under the Security and network section, see Endpoint: you will need to copy & paste it in the next step.  
    ![](/Images/SecureTransport/db-endpoint.PNG)
6.  Use Oracle SQL Developer on your Administration Host.  
    Add new connection and provide values for the following options:
    -   **Connection Name**: type a name that describes the connection
    -   **Username**: name of the database administrator
    -   **Password**: password for the database administrator
    -   **Hostname**: paste the Endpoint
    -   **Port**: 1521
    -   **SID**: ORCL

For further reference, see [Connecting to Oracle DB](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_ConnectToOracleInstance.html) in the AWS documentation.

## Create tables and set ownership of the Oracle DB

Use the following script:



    CREATE SMALLFILE TABLESPACE "ST_DATA"
    DATAFILE SIZE 5000M AUTOEXTEND ON NEXT 12K MAXSIZE 8000M
    LOGGING EXTENT MANAGEMENT LOCAL SEGMENT SPACE MANAGEMENT AUTO;
    CREATE SMALLFILE TABLESPACE "ST_FILETRACKING"
    DATAFILE SIZE 5000M AUTOEXTEND ON NEXT 12K MAXSIZE 8000M
    LOGGING EXTENT MANAGEMENT LOCAL SEGMENT SPACE MANAGEMENT AUTO;
    CREATE SMALLFILE TABLESPACE "ST_SERVERLOG"
    DATAFILE SIZE 5000M AUTOEXTEND ON NEXT 12K MAXSIZE 8000M
    LOGGING EXTENT MANAGEMENT LOCAL SEGMENT SPACE MANAGEMENT AUTO;
    CREATE USER ST IDENTIFIED BY ST;
       grant connect to ST;
       grant create operator to ST;
       grant create procedure to ST;
       grant create sequence to ST;
       grant create session to ST;
       grant create table to ST;
       alter user ST quota unlimited on ST_DATA;
       alter user ST quota unlimited on ST_FILETRACKING;
       alter user ST quota unlimited on ST_SERVERLOG;
       alter user ST quota unlimited on USERS;

## Obtain the Oracle DB certificate and a Distinguished Name

Execute the following command from one of your RHEL Instances which have access to the database:



    openssl s_client -connect <host>:<ssl_port>

where `<host>` is the Endpoint.

## Create directories for the exported files for Oracle DB

If you would like to run Maintenance applications and export logs, you will have to create a directory on the RDS service. This directory will contain the exported files.

To create a new directory, you can use the Amazon RDS procedure `dsadmin.rdsadmin_util.create_directory`.

The following example creates a new directory named `ST_DMPDIR`:


    exec rdsadmin.rdsadmin_util.create_directory(p_directory_name => 'ST_DMPDIR');

You can list the directories by querying `DBA_DIRECTORIES`. The system chooses the actual host pathname automatically. The following example gets the directory path for the directory named `ST_DMPDIR`:


    select DIRECTORY_PATH 
    from DBA_DIRECTORIES 
    where DIRECTORY_NAME='ST_DMPDIR';

The master user for the DB instance has read and write privileges in the new directory, and can grant access to other users. You will need to grant read and write privileges to your SecureTransport user.

Execute privileges are not available for directories on a DB instance. Directories are created in your main data storage space and will consume space and I/O bandwidth.

### List Files in an Oracle DB Instance Directory

You can use the Amazon RDS procedure `rdsadmin.rds_file_util.listdir` to list the files in a directory.

The following example lists the files in the directory named `ST_DMPDIR`:


    select * from table
     (rdsadmin.rds_file_util.listdir(p_directory => 'ST_DMPDIR'));

Learn more about [Creating directories in RDS](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Appendix.Oracle.CommonDBATasks.Misc.html#Appendix.Oracle.CommonDBATasks.NewDirectories) in the AWS documentation.
