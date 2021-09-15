{
    "title": "Data pump database management system",
    "linkTitle": "Data pump database management system",
    "weight": "130"
}Before installation, you can set the `DATA_PUMP` system environment variable to either **false** or **true** depending upon if you want to *disable* or *enable* the data pump. By default, if data pump system environment variable is not set, the data pump will be enabled and export database functionality procedures will be deployed.

Execute the following command to set the `DATA_PUMP` system environment variable to false:

`export DATA_PUMP=false`

When the `DATA_PUMP` system environment variable is set to `false`, the installer will detect that the data pump is disabled and a warning message will be displayed in the `install.log` file with the following content:

    DEBUG [external_db_configuration] 2016-07-05 15:47:25,761 EEST WARN [main] com.tumbleweed.st.server.appframework.util.OracleDatabaseConfigurator - DataPump capabilities are disabled. The configuration will proceed without deploying the data pump procedures.

When the data pump disabled, the installer will not deploy the database procedures to export partitions. Microsoft SQL Server to Oracle database migrations will assume that the target database and user have data pump available. When deploying on multiple databases, all databases inherit the same data pump behavior as the first one. On upgrade, also valid for all patches and service packs, data pump will be enabled by default and you cannot change it.

**Related topics:**

-   [Requirements for Oracle databases](..//securetransport/installation_guide/prereqs_overview/database_installation_prerequisites/requirements_for_oracle_databases)
-   [Requirements for Microsoft SQL Server databases](../../requirements_for_sql_databases)
