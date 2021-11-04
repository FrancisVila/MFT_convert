{
    "title": "SecureTransport troubleshooting tools",
    "linkTitle": "SecureTransport troubleshooting tools",
    "weight": "210"
}If problems still exist after troubleshooting with the SiteMinder tools, use the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> log files to try to ascertain the problem.

To use the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> log files effectively to troubleshoot the SiteMinder integration issues, consider the following recommendations:

-   Increase the log level of `com.tumbleweed.st.server.siteminder` log generator in `<FILEDRIVEHOME>/conf/tm-log4j.xml` to `debug`. Increase the log levels of other log generators in this file as well.
-   Increase all the log levels in &lt;`FILEDRIVEHOME>/conf/tm-log4j.xml` from `warn` to `debug`.
-   Check the &lt;`FILEDRIVEHOME>/var/logs/tm.log` file and the *Server Log* page for any messages when a SiteMinder login fails.

After increasing the logging level settings, restart Transaction Manager to apply the changes.

**Related topic:**

-   <a href="../c_st_siteminder_troubleshooting_tools" class="MCXref xref">SiteMinder troubleshooting tools</a>

## Restart Transaction Manager

Use the following procedure to restart the Transaction Manager.

1.  Select **Operations > Server Control**.  
    The *Server Control* page is displayed.
2.  Under **TM Server**, click **Stop** and then click **Start**.