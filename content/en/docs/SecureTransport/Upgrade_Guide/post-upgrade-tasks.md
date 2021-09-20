{
    "title": "Post-upgrade tasks",
    "linkTitle": "Post-upgrade tasks",
    "weight": "70"
}After you upgrade, complete the following tasks:

-   If the Administration tool is not loading after upgrading to 5.5 GA, it is likely that the admin service fails to start normally. Check the corresponding catalina.out file (`FILEDRIVEHOME/tomcat/admin/logs`) for the following log message: "java.lang.NoClassDefFoundError: org/apache/tomcat/JarScanFilter". If it is present, the issue can be resolved in two ways:
    -   Stop the Administration Tool and AS2 servers and delete both `tomcat-util-scan.jar` and `tomcat-websocket.jar` from `FILEDRIVEHOME/tomcat/lib` folder. Then, start the services again.
    -   Apply the latest SecureTransport 5.5 Update.

      
    
    Axway recommends checking also the catalina.out log file for the AS2 server (`FILEDRIVEHOME/tomcat/as2/logs`) for the error stated above. If it is present, you can fix it in the same way.
-   Start the protocol servers and services on the SecureTransport Edges to establish the Transaction Manager protocol and proxy server communication. For additional information, refer to the <span cshid="admin" data-version="5.3.5">*SecureTransport Administrator's Guide*</span>.
-   On Windows systems, go to the `<AxwayHome>/Java/<OS>` directory and delete the *jre8\_u231\_64* folder.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">During the upgrade to version 5.5, all <span>SecureTransport</span> cronjobs along with their schedules will be migrated to the <code>monitord</code> configuration and then deleted from cron. All non-SecureTransport related cronjobs will be preserved. This goes for all operating systems you install and run <span>SecureTransport</span> on.         </td>
      </tr>
</table>
