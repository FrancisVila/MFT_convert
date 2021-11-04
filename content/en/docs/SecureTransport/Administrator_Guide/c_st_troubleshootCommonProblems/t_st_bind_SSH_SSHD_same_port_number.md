{
    "title": "Bind SSH and SSHD to the same port number",
    "linkTitle": "Bind SSH and SSHD to the same port number",
    "weight": "290"
}When you need to use port 22 for an AIX server and for <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span>, use the following steps:

1.  On the server hosting <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span>, edit the SSHD configuration file, for example, `/etc/ssh/sshd_config`. (To find the location on your system, refer to `man 5 sshd_config`.) Set the `ListenAddress` directive, then find the `sshd` process ID and use the command `kill -HUP`. You should perform these steps directly on the server so you must have a keyboard and monitor for the computer.
2.  Log on to the Administration Tool and select **Operations > Server Configuration**.
3.  On the *Server Configuration* page, search for the `SSH.Host` parameter and sets its value to the actual IP address of the host.
4.  Restart the SSH server.

**Related topic:**

-   <a href="../t_st_debug_ssh_issues" class="MCXref xref">Debug SSH issues</a>