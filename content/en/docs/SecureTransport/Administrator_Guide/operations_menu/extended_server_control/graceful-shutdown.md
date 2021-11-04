{
    "title": "Graceful shutdown ",
    "linkTitle": "Graceful shutdown",
    "weight": "160"
}This topic discusses the concept of performing graceful shutdown of the different <span class="mc-variable suite_variables.SecureTransportName variable">SecureTransport</span> components and specifics.

<span id="Graceful3"></span>

## Graceful shutdown of protocol servers

> **Note:**
>
> The current subtopic contains general information and instructions to perform graceful shutdown on any of the available protocol servers, except where noted otherwise. The option to gracefully shut down protocol servers is available on both SecureTransport Server and Edge.

Graceful shutdown is an option to initiate a shutdown of any or all protocol servers without abrupt cancellation of the currently ongoing client-initiated transfer (CIT) sessions. Once initiated, the graceful shutdown waits for the specified grace period before stopping the selected server. This grace period defines the time allowed for existing transfers to get completed before shutting down. You can set its value to the dedicated configuration option parameter per protocol server:

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Protocol         </th>
<th class="HeadE-Column1-Header1">Server option         </th>
<th class="HeadD-Column1-Header1">Default value         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>FTP         </td>
         <td><code>Ftpd.GracefulShutdownTimeout</code>         </td>
         <td><code>86400s</code>         </td>
      </tr>
      <tr>
         <td>HTTP         </td>
         <td><code>Http.GracefulShutdownTimeout</code>         </td>
         <td><code>30s</code> – if not previously modified (see note)         </td>
      </tr>
      <tr>
         <td>AS2         </td>
         <td><code>As2.GracefulShutdownTimeout</code>         </td>
         <td><code>86400s</code>         </td>
      </tr>
      <tr>
         <td>SSH         </td>
         <td><code>Ssh.GracefulShutdownTimeout</code>         </td>
         <td><code>86400s</code>         </td>
      </tr>
      <tr>
         <td>PeSIT         </td>
         <td><code>Pesit.GracefulShutdownTimeout</code>         </td>
         <td><code>86400s</code>         </td>
      </tr>
   </tbody>
</table>

> **Note:**
>
> With HTTP, the Http.GracefulShutdownTimeout server option has been available prior to introducing the graceful shutdown functionality. In case its default value has been modified, the input value is stored.

Note that during the graceful shutdown period:

-   Existing CITs are allowed to complete within the specified timeout period.
-   Any new attempts for file operations are rejected. This includes not only file uploads and downloads but also: directory listing, deleting or renaming files, as well as deleting or creating directories.

### Perform protocol server graceful shutdown

> **Note:**
>
> Before you proceed with graceful shutdown initiation, the Monitor Server must be stopped.

To initiate this process using the Administration Tool, go to the **Actions** drop-down list of the selected protocol server, click to expand it and select **Graceful Shutdown**. The process will wait for the countdown period as defined in the corresponding configuration option before it starts.

You can also perform this action using a console command in the following format: `stop_<protocol_daemon> -g -timeout <interval_in_seconds>`.

-   the `-g` parameter can be used to stop the daemon gracefully while using the specific daemon default configuration timeout;
-   the `-timeout <interval_in_seconds>` parameter is optional and can be used in conjunction with `-g` to offset graceful shutdown with the defined interval (different than the default one, as defined in the server configuration option for the respective protocol). If you omit this parameter, graceful shutdown will be performed using the respective configuration option value.

For example, if you want to initiate graceful shutdown after 60 seconds using the console command for the respective protocol daemon, enter:

-   `stop_ftpd -g -timeout 60` for the FTP daemon
-   `stop_httpd -g -timeout 60` for the HTTP daemon
-   `stop_as2d -g -timeout 60` for the AS2 daemon
-   `stop_sshd -g -timeout 60` for the SSH daemon
-   `stop_pesitd -g -timeout 60` for the PeSIT daemon

The option to shut down gracefully a protocol server is also exposed as a REST API resource. For more information, refer to the [Admin API Swagger documentation](http://apidocs.axway.com/swagger-ui/index.html?productname=SecureTransport&productversion=5.4&filename=securetransport-program-server-ws-5.4.0-5-st-ws-admin-docs-v14.json "SecureTransport Admin API Swagger documentation").

> **Note:**
>
> With HTTP, when you initiate graceful shutdown during active file uploads with the ST Web Client, these uploads will be processed until the current chunk upload is completed. The chunk size is defined as the value of the uploadChunkSize parameter in the ST Web Client configuration. By default, its value is 100 MB, which means that in all cases uploads of files with sizes smaller than 100 MB will be completed during the graceful shutdown. With larger files, uploads might be completed as well; or could be stopped depending on the current chunk upload.

### Graceful shutdown logging

The server log displays information about active connections during an initiated graceful shutdown. For better visibility, a dedicated server option is introduced: `GracefulShutdown.Logging.Interval`. By default its value is `60s` which means that active transfer information will be logged once every 60 seconds until all transfers are completed. Note that the graceful shutdown logging interval applies to all protocol servers.

<span id="Graceful"></span>

## Graceful shutdown of Transaction Manager

Graceful shutdown is a feature that allows you to have a planned Transaction Manager (TM) stop without abrupt cancellation of:

-   current SITs
-   post routing, post transformation, and post processing actions
-   Advanced Routing actions

Once initiated, the graceful shutdown waits for the specified grace period before stopping the selected server. This grace period defines the time allowed for existing transfers to get completed before shutting down. You can set its value (in seconds) to the dedicated configuration option parameter: `TransactionManager.GracefulShutdownTimeout`.

To perform Graceful shutdown of the Transaction Manager server, scroll to the bottom of the extended *Server Control* page, then select **Actions** -> **Graceful Shutdown**. The Transaction Manager will be stopped after timeout expiry.

You can also perform this action using a console command in the following format: `stop_tm -g -timeout <interval_in_seconds>`. For example, `stop_tm -g -timeout 60` will shut down the Transaction Manager after 60 seconds.

It is recommended that you configure the timeout period for no less than 30 seconds: otherwise there is a risk that shutdown would not be "graceful".

The option to shut down the Transaction Manager gracefully is also exposed as a REST API resource. For more information, refer to the [Admin API Swagger documentation](http://apidocs.axway.com/swagger-ui/index.html?productname=SecureTransport&productversion=5.4&filename=securetransport-program-server-ws-5.4.0-5-st-ws-admin-docs-v14.json "SecureTransport Admin API Swagger documentation").

**Note:** Before performing Graceful Shutdown, make sure all protocol servers plus Monitor server are stopped. Make sure that there is no active streaming connection to an Edge server in order to successfully perform TM graceful shutdown.

<span id="Graceful2"></span>

## Graceful shutdown of <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Server node

> **Note:**
>
> Remember that before you proceed with graceful shutdown initiation, the Monitor Server must be stopped.

Expand the **Actions** drop-down list on top of the extended *Server Control* page and select the **Shutdown Node Gracefully** to initiate a Graceful shutdown of the entire <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Server node.

This process undergoes three consecutive steps:

1.  Stop the Folder Monitor server and Scheduler server.
2.  Gracefully stop all protocol servers.
3.  Gracefully stop the Transaction Manager server.

> **Note:**
>
> Make sure that there is no active streaming connection to an Edge server in order to successfully perform TM graceful shutdown.

Each step will be executed after successful completion of the previous one. The extended *Server Control* page will have messages displayed, providing status on <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Server node components shutdown.

After completion of step 3, the current <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Server will not be processing any transfers until all services are restarted. You must perform these steps manually and no particular order is required.

The option to shut down the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Server node gracefully is also exposed as a REST API resource. For more information, refer to the [Admin API Swagger documentation](http://apidocs.axway.com/swagger-ui/index.html?productname=SecureTransport&productversion=5.4&filename=securetransport-program-server-ws-5.4.0-5-st-ws-admin-docs-v14.json "SecureTransport Admin API Swagger documentation").

> **Note:**
>
> When you initiate Graceful shutdown of SecureTransport Server node using the SecureTransport Administration Tool, you must not close or refresh the extended Server Control page until all three steps are completed. If you need to perform actions on other screens in the SecureTransport Administration Tool, it is recommended to open a new tab with the selected SecureTransport screen.

<span id="Graceful2"></span>

## Graceful shutdown of <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Edge node

> **Note:**
>
> Remember that before you proceed with graceful shutdown initiation, the Monitor Server must be stopped.

Graceful shutdown on Edge is similar to that on <span class="mc-variable suite_variables.SecureTransportName variable">SecureTransport</span> Server. Note that there is no Folder Monitor, Scheduler or Transaction Manager component on Edge; however there is the Proxy server.

As with Server, expand the **Actions** drop-down list on top of the extended *Server Control* page and select the **Shutdown Node Gracefully**.

This process undergoes two basic consecutive steps:

1.  Gracefully stop all protocol servers.
2.  Stop the Proxy server.
