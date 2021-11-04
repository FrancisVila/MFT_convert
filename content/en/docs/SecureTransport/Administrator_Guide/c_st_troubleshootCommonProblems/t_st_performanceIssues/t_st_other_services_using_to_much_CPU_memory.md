{
    "title": "Other services using to much CPU or memory",
    "linkTitle": "Other services using to much CPU or memory",
    "weight": "350"
}One possible reason performance deteriorates can be caused by other services using too many system resources. Perform the following procedures to fine tune performance.

-   Look at the memory and CPU usage for any other services running on the same computer. If you turn off all the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> services, but you still see high memory usage, you might need to add more memory or assign a dedicated memory amount to <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span>. If the CPU usage is still too high, you need to move some of the services to another computer or turn them off. If you can configure the services to use less CPU resources, do so.

Because <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> is a CPU-intensive application, during peak demand times, it can consume most or all of the CPU resources. This can reduce the performance of other services. To provide sufficient processor resources for <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> and other services, allocate a computer with higher processing power to <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span>. For example, employ a computer with multiple processors.

**Related topics:**

-   <a href="../t_st_evaluate_performance_issues" class="MCXref xref">Evaluate performance issues</a>
-   <a href="../t_st_dns_settings" class="MCXref xref">DNS settings</a>
-   <a href="../t_st_firewall_issues" class="MCXref xref">Firewall issues</a>
-   <a href="../t_st_installation_on_network_drive" class="MCXref xref">Installation on network drive</a>
-   <a href="../t_st_debug_log_output_slows_computer" class="MCXref xref">Debug log output slows computer</a>
