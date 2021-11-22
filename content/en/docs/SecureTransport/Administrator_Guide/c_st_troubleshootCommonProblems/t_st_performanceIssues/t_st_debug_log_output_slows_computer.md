{
    "title": "Debug log output slows computer",
    "linkTitle": "Debug log output slows computer",
    "weight": "370"
}You might need to set the log level for one or more of the {{< SecureTransport/componentshortname  >}} logs configured in files in the `<FILEDRIVEHOME>/conf/` directory to `debug` to produce a detailed log for problem isolation. If you leave a log set to `debug`, it can produce a very large volume of log output. Because this keeps the database and disk busy, it can affect the performance of all processes running on the computer.

-   Always reset the log level after using `debug` to gather log information for problem isolation.
-   Never set a log level to `debug` for routine operation.

**Related topics:**

-   <a href="../t_st_evaluate_performance_issues" class="MCXref xref">Evaluate performance issues</a>
-   <a href="../t_st_dns_settings" class="MCXref xref">DNS settings</a>
-   <a href="../t_st_firewall_issues" class="MCXref xref">Firewall issues</a>
-   <a href="../t_st_other_services_using_to_much_cpu_memory" class="MCXref xref">Other services using to much CPU or memory</a>
-   <a href="../t_st_installation_on_network_drive" class="MCXref xref">Installation on network drive</a>
