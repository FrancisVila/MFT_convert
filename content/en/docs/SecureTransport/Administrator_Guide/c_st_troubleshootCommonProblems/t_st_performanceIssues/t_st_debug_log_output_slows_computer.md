{
    "title": "Debug log output slows computer",
    "linkTitle": "Debug log output slows computer",
    "weight": "380"
}You might need to set the log level for one or more of the SecureTransport logs configured in files in the `<FILEDRIVEHOME>/conf/` directory to `debug` to produce a detailed log for problem isolation. If you leave a log set to `debug`, it can produce a very large volume of log output. Because this keeps the database and disk busy, it can affect the performance of all processes running on the computer.

-   Always reset the log level after using `debug` to gather log information for problem isolation.
-   Never set a log level to `debug` for routine operation.

**Related topics:**

-   [Evaluate performance issues](../t_st_evaluate_performance_issues)
-   [DNS settings](../t_st_dns_settings)
-   [Firewall issues](../t_st_firewall_issues)
-   [Other services using to much CPU or memory](../t_st_other_services_using_to_much_cpu_memory)
-   [Installation on network drive](../t_st_installation_on_network_drive)
