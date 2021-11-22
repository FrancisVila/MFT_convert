{
    "title": "Monitor server",
    "linkTitle": "Manage the Monitor server",
    "weight": "170"
}In this topic you will learn how to:

-   <a href="#Use" class="MCXref xref">Monitor server</a>

The Monitor Server uses the `monitord` monitoring service to perform periodical checks and identify if the {{< SecureTransport/componentshortname  >}} servers are functional or not. If one or more monitored servers are not responding, the monitoring service automatically restarts them. There are few exceptions to this: monitord does not restart a server if the DB server is not running; or if the server is manually stopped by an administrator.

Before version 5.5, {{< SecureTransport/componentshortname  >}} Server was using cron for monitoring purposes. With {{< SecureTransport/componentshortname  >}} version 5.5 and later, the Monitor Server relies on `monitord` as a separate process that uses the Quartz Job Scheduling Library.

The Monitor Server and `monitord` monitoring service can run with {{< SecureTransport/componentshortname  >}} Server or {{< SecureTransport/componentshortname  >}} Edge.

## Start Monitor servers and monitord service

In order to make use of this functionality, you must have both the Monitor Server and `monitord` service started and running.

-   To start the Monitor Server, go to **Operations > Server Control**, scroll down to **Monitor Server** and click **Start**.
-   To start the `monitord` monitoring service, use the following script: `<FILEDRIVEHOME>/bin/start_monitord`.

Monitoring is applicable to all {{< SecureTransport/componentshortname  >}} services. Whatever service you start, it attempts to start the `monitord` service (unless it is already running).

> **Note:**
>
> The monitord service must use a non-SSL connection to check the PeSIT server,
> so you must select Enable PeSIT (no SSL) on the Server Control page for
> monitoring. To prevent non-SSL PeSIT connections, restrict access to the
> non-SSL port you configure to the system where the PeSIT server and the
> Monitor server are running.

You can set up a monitoring schedule of each service by editing the `monitor.schedule.properties` file located in the `<FILEDRIVEHOME>/conf` folder. To exclude any of the servers for monitoring, you must remove its entry from the `monitor.schedule.properties` file.

You can configure number of times and intervals between consecutive attempts for `monitord` to restart each server by changing local configuration parameters.

The parameters apply to a respective server with its server name: `ADMIN`, `AS2D`, `DB` (embedded database only), `FTPD`, `HTTPD`, `SSHD`, and `TM` or `Proxy`, as follows:

-   `Monitor.<server>.retryCount` – the number of times the Monitor server tries to restart the server. The default value varies depending on the server.
-   `Monitor.<server>.retryDelay` – the time in seconds that the Monitor server waits between consecutive attempts to restart the server. The default value varies depending on the server.

These parameters are also editable in the `monitor.properties` file located in the `<FILEDRIVEHOME>/conf` folder. It is recommended to edit their values from the Administration tool.

The monitoring service logs the status of each monitored service in a dedicated "out" file in the following location: `<FILEDRIVEHOME>/var/logs/`. The format of each file includes the service name in its filename, as follows: `monitor_<service>.out`

Besides manually starting `monitord`, the administrator can also stop and observe the server status by executing the respective script:

-   `<FILEDRIVEHOME>/bin/stop_monitord` – stop the monitoring service
-   `<FILEDRIVEHOME>/bin/status_monitord` – display monitoring service status

The log file of the `monitord` service is stored at the following location – `<FILEDRIVEHOME>/var/logs/monitord.log`

When you make a change to any monitored service, you must stop and start the `monitord` service in order to reflect these changes.

During an upgrade, all {{< SecureTransport/componentshortname  >}} cronjobs along with their schedules will be migrated to the `monitord` configuration and then deleted from cron. All non-SecureTransport related cronjobs will be preserved. This goes for all operating systems you install and run SecureTransport on.

> **Note:**
>
> With previous versions of SecureTransport on Windows server, the monitoring service was scheduled to run every 5 minutes. With version 5.5 onward, a fresh SecureTransport installation on Windows server is scheduled to run every 1 minute.
