{
    "title": "Post-upgrade tasks",
    "linkTitle": "Post-upgrade tasks",
    "weight": "70"
}After you upgrade, complete the following tasks:

-   If the Administration tool is not loading after upgrading to 5.5 GA, it is likely that the admin service fails to start normally. Check the corresponding catalina.out file (`FILEDRIVEHOME/tomcat/admin/logs`) for the following log message: "java.lang.NoClassDefFoundError: org/apache/tomcat/JarScanFilter". If it is present, the issue can be resolved in two ways:
    -   Stop the Administration Tool and AS2 servers and delete both `tomcat-util-scan.jar` and `tomcat-websocket.jar` from `FILEDRIVEHOME/tomcat/lib` folder. Then, start the services again.
    -   Apply the latest <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> 5.5 Update.

      
    Axway recommends checking also the catalina.out log file for the AS2 server (`FILEDRIVEHOME/tomcat/as2/logs`) for the error stated above. If it is present, you can fix it in the same way.
-   Start the protocol servers and services on the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Edges to establish the Transaction Manager protocol and proxy server communication. For additional information, refer to the <span class="redirect_st_ag" cshid="admin" data-version="5.3.5">*<span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Administrator's Guide*</span>.
-   On Windows systems, go to the `<AxwayHome>/Java/<OS>` directory and delete the *jre8\_u231\_64* folder.

> **Note:**
>
> During the upgrade to version 5.5, all SecureTransport cronjobs along with their schedules will be migrated to the monitord configuration and then deleted from cron. All non-SecureTransport related cronjobs will be preserved. This goes for all operating systems you install and run SecureTransport on.