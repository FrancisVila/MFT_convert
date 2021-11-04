{
    "title": "Modify SSH daemon configuration",
    "linkTitle": "Modify SSH daemon configuration",
    "weight": "130"
}After starting <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span>, the SSH daemon runs with its default configuration, specified in the SSHD configuration file (`/etc/ssh/sshd_config`). Administrators with permissions to access to the *Server Control* and *SSH Settings* page (configurable through the [Administrative role settings](../../../c_st_advancedaccountadministration/c_st_administrativeroles/r_st_add_administrative_role)) can modify several settings to alter the behavior of the daemon. Those include:

-   select the preferred cryptographic provider
-   limit the maximum number of SSH connections
-   set up a login message banner

To access those settings, go to the *Server Control* page and locate the **SSH servers** panel. Click the "gear" icon:![](/Images/SecureTransport/gearwheel-icon.png) in the panel header.  
The *Edit Daemon* box pops up.

Once you have finished editing the daemon settings, click **Save**. Then, restart the SSH server for the changes to take effect.

> **Note:**
>
> The options to edit daemon's configuration are also exposed as REST API endpoints: /daemons/{name}.

### Select BouncyCastle as preferred provider

The default cryptographic provider in SecureTransport is BouncyCastle. It is determined by the selection of the **Prefer BouncyCastle Crypto provider** checkbox, which is checked by default. The BouncyCastle cryptographic library is FIPS-certified, and contains more algorithms and cipher suites than the Sun library. Therefore, if you want maximum security for your SSH servers, we suggest using the default settings.

In the cases where you do not need FIPS, you can deselect the **Prefer BouncyCastle Crypto provider** checkbox to speed up system performance. By doing so, Sun becomes the preferred provider and BouncyCastle is used as a fallback.

In order to change the preferred provider from BouncyCastle to Sun, FIPS mode must be disabled on all SSH servers, as Sun is not FIPS-compliant. For more information, see <a href="ext_servercontrol-add-ssh" class="MCXref xref">Manage the SSH server</a>.

### **Limit the Maximum Number of Connections**

Type the maximum number of SSH clients that can simultaneously connect to the SSH server. If the maximum number of connections is reached, <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> prevents any further connections before the user is authenticated. If you increase the value of **Maximum Number of Connections**, you must also increase the value of `SSH_JAVA_MEM_MAX` in the `<FILEDRIVEHOME>/bin/start_sshd` script.

The script uses the `SSH_JAVA_MEM_MAX` value to set the maximum heap size for the Java Virtual Machine (JVM). The SSH server allocates memory in the heap for each connection (and frees it when the connection is closed). To avoid SSH service interruptions when no memory is available in the Java heap, you must configure `SSH_JAVA_MEM_MAX` to the desired **Maximum Number of Connections** (as defined in the previous step) multiplied by 10,000 Kibibytes. However, in the script file, you must convert this result to Megabytes (10,000 Kibibytes is equivalent to 10.24 Megabytes). For example, 500 concurrent connections would require a value of 500 \* 10,000 KiB = 5,000,000 KiB. This is equivalent to 5120 Megabytes, so enter this in the script file as:

`SSH_JAVA_MEM_MAX="5120M"`

Use `M` to specify Megabytes. Do not insert a space between the number and the `M`

### **Set up a Message Banner**

The SSH daemon can be modified to present a custom banner to the users when they log in via SSH. The content of this banner is entered in the **Message Banner** text field. For example, you can enter a legal notice, a disclaimer, or a welcome message.

 

The following topics shows how to bind SSH and SSHD to the same port number and debug SSH issues:

-   <a href="../../../c_st_troubleshootcommonproblems/t_st_bind_ssh_sshd_same_port_number" class="MCXref xref">Bind SSH and SSHD to the same port number</a>
-   <a href="../../../c_st_troubleshootcommonproblems/t_st_debug_ssh_issues" class="MCXref xref">Debug SSH issues</a>
