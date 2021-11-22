{
    "title": "Improve server resiliency in case of Oracle RAC node failure",
    "linkTitle": "Improve server resiliency in case of Oracle RAC node failure",
    "weight": "220"
}> **Note:**
>
> The following procedure might affect SecureTransport Server performance.

Adjust the {{< SecureTransport/componentshortname  >}} connection pool settings per the following procedure.

1.  Set the C3P0 connection pools configured in `<FILEDRIVEHOME>/conf/configuration.xml` (set for each component) as follows:  
    `hibernate.c3p0.testConnectionOnCheckout=true`  
    `hibernate.c3p0.preferredTestQuery=select 1 from DUAL`
2.  The DBCP connection pool is used for Quartz scheduling component. Set the DBCP settings configured in `<FILEDRIVEHOME>/conf/scheduler.properties` as follows:  
    `org.quartz.dataSource.DS.validationQuery=select 1 from DUAL`  
    `org.quartz.dataSource.DS.testOnBorrow=true`

> **Note:**
>
> Please note that the name of dataSource can be different than DS, for example, if SecureTransport database was migrated from an embedded database to external Oracle database, the name of dataSource will be DS2-migrate, and configuration options will be:org.quartz.dataSource.DS2-migration.validationQuery=select 1 from DUALorg.quartz.dataSource.DS2-migration.testOnBorrow=true
