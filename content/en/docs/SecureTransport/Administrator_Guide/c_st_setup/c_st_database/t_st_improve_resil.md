{
    "title": "Improve server resiliency in case of Oracle RAC node failure",
    "linkTitle": "Improve server resiliency in case of Oracle RAC node failure",
    "weight": "230"
}<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">The following procedure might affect <span>SecureTransport</span> Server performance.         </td>
      </tr>
</table>

Adjust the SecureTransport connection pool settings per the following procedure.

1.  Set the C3P0 connection pools configured in `<FILEDRIVEHOME>/conf/configuration.xml` (set for each component) as follows:  
    `hibernate.c3p0.testConnectionOnCheckout=true`
      
    `hibernate.c3p0.preferredTestQuery=select 1 from DUAL`
2.  The DBCP connection pool is used for Quartz scheduling component. Set the DBCP settings configured in `<FILEDRIVEHOME>/conf/scheduler.properties` as follows:  
    `org.quartz.dataSource.DS.validationQuery=select 1 from DUAL`
      
    `org.quartz.dataSource.DS.testOnBorrow=true`

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">Please note that the name of dataSource can be different than DS, for example, if SecureTransport database was migrated from an embedded database to external Oracle database, the name of dataSource will be DS2-migrate, and configuration options will be:<br><code>org.quartz.dataSource.DS2-migration.validationQuery=<b>select 1 from DUAL</b></code><br><code>org.quartz.dataSource.DS2-migration.testOnBorrow=<b>true</b></code></br></br>         </td>
      </tr>
</table>
