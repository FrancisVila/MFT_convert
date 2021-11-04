{
    "title": "Connect to an Oracle database using Kerberos authentication",
    "linkTitle": "Connect to Oracle database using Kerberos Authentication",
    "weight": "210"
}This topic describes how to configure SecureTransport to connect to an Oracle database using Kerberos authentication. It assumes that the Oracle database has already been kerberized. To use this functionality, you will need to be running <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> 5.5 October 2020 Update or later. It also requires additional configuration actions to be done on both the SecureTransport and the database server.

<span id="Prerequi"></span>

## Prerequisites

Before you configure the machine where SecureTransport runs (or will be installed) for Kerberos authentication to an Oracle database, make sure the following prerequisites are fulfilled: 

-   Your Oracle database has been configured for Kerberos Authentication. For step-by-step instructions, refer to the Oracle's [Security Guide](https://docs.oracle.com/en/database/oracle/oracle-database/19/dbseg/configuring-kerberos-authentication.html#GUID-DF84261F-457A-4B9F-AE41-CDE6FE9178C4).

-   On the database server, verify that the following parameters in the *sqlnet.ora* file are set:   



        SQLNET.KERBEROS5_KEYTAB = /etc/krb5.keytab

        SQLNET.AUTHENTICATION_SERVICES= (BEQ, KERBEROS5)

        SQLNET.KERBEROS5_CLOCKSKEW = 6000

        SQLNET.KERBEROS5_CONF = /etc/krb5.conf

        SQLNET.KERBEROS5_CONF_MIT = true

        SQLNET.AUTHENTICATION_KERBEROS5_SERVICE = oracle

-   You have a running Key Distribution Center (KDC), such as Windows Active Directory, and realm setup

-   You have created an externally authenticated oracle user that corresponds to the Kerberos user to be used

-   The virtual machine, on which you install SecureTransport, has a resolvable FQDN (Fully Qualified Domain Name). If it doesn't, edit the */etc/hostname* file to add the following line: `<hostname>.yourrealm.com`

-   All participants in a Kerberos realm have accurate system clocks

**SecureTransport configuration**

The following are the high-level steps on configuring Kerberos authentication for a connection to an Oracle database. This section points out only the settings that you need to know or change for <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span>. The procedure is platform-dependant.

1.  Install the Kerberos client packages on the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> machine.

2.  Edit the */etc/krb5.conf* file to reflect your realm setup.

3.  Obtain a forwardable TGT ticket for the Kerberos/Oracle user.

4.  Configure SecureTransport to use Kerberos authentication when connecting to the database.

    1.  Select the **Use Kerberos Authentication** checkbox.

    2.  Specify the location of the Kerberos credential cache file.

    3.  Specify the location of the Kerberos configuration file:

    4.  -   When **Use Kerberos configuration file** is unchecked (default), <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> uses the default `/etc/krb5.conf` file. In this case, <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> keeps the file locally and synchronizes it between nodes. The application monitors the `krb5.conf` for changes but uses the locally stored file after a restart. All changes to the `krb5.conf` file must be done through the *Server Configuration Files* page. To access the page, go to **Operations > Server Configuration** and click the **Configuration Files** button.
        -   When **Use Kerberos configuration file** is checked, <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> refers to the Kerberos configuration file directly using its file path. In this case, <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> does not copy the file locally or synchronize it between nodes; instead, you specify a configuration file per node. Whenever there is a change in the Kerberos configuration file, Secure Transport automatically reloads the Kerberos configuration.

    > **Note:**
    >
    > Caution   In an Enterprise Cluster setup, execute all the steps on all of theSecureTransport servers.

5.  For more information on configuring fresh installations, refer to the *SecureTransport Installation Guide*. To change the database configuration on existing systems, refer to <a href="../t_st_oracle" class="MCXref xref">Change the Oracle database configuration</a>.

> **Note:**
>
> Caution  
> In an Enterprise Cluster setup, execute all the steps on all of the SecureTransport servers.

### Troubleshooting

-   When using separate databases for the Server Log and the Transfer log, you need a dedicated Kerberos user for each. The users must use their own Kerberos cache file.
-   When a Kerberos credential expires, the TGT is not renewed by <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span>. Ensure that a valid Ticket is always present; otherwise, the connection to the database will be lost.
-   The Oracle database server may incorrectly interpret requests from SecureTransport as a replay attack ("Request is a replay" error message). This issue is resolved in Oracle 19.8 Patch 31716873. On previous Oracle database versions , the available workaround is to disable the Replay Cache mechanism.
