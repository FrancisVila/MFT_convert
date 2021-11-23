{
    "title": "Debug SSH issues",
    "linkTitle": "Debug SSH issues",
    "weight": "280"
}If you are trying to determine an issue with SSH, changing the `mchange` and `ehcache` logger parameters in the `sshd-log4j.xml` file to `Debug` can prevent SSH from receiving connections. To work around this issue, you can reset `sshd-log4j.xml` to send log messages to a file instead of the database. Follow the steps in [Redirect log4j output from the database](../../c_st_serverlogs/r_st_logfiledetails/t_st_redirect_log4j_output_from_database#AppServerLogs_558321163_1039943) to change the log.

> **Note:**
>
> When log messages are stored in the database, they are displayed in the Server Log page. When you store the log messages in a file, they are not displayed in the Server Log page.

**Related topic:**

-   [Bind SSH and SSHD to the same port number](../t_st_bind_ssh_sshd_same_port_number)
