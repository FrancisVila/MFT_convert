{
    "title": "Connect to Oracle database using Kerberos Authentication",
    "linkTitle": "Connect to Oracle database using Kerberos Authentication",
    "weight": "220"
}This topic describes how to configure SecureTransport to connect to an Oracle database using Kerberos authentication. It assumes that the Oracle database has already been kerberized. To use this functionality, you will need to be running SecureTransport 5.5 October 2020 Update or later. It also requires additional configuration actions to be done on both the SecureTransport and the database server.

## <span id="Prerequi"></span>Prerequisites

Before you configure the machine where SecureTransport runs (or will be installed) for Kerberos authentication to an Oracle database, make sure the following prerequisites are fulfilled: 

-   Your Oracle database has been configured for Kerberos Authentication. For step-by-step instructions, refer to the Oracle's [Security Guide](https://docs.oracle.com/en/database/oracle/oracle-database/19/dbseg/configuring-kerberos-authentication.html#GUID-DF84261F-457A-4B9F-AE41-CDE6FE9178C4).

-   On the database server, verify that the following parameters in the *sqlnet.ora* file are set:   
    

    <table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p><code>SQLNET.KERBEROS5_KEYTAB = /etc/krb5.keytab</code>
</p>
            <p><code>SQLNET.AUTHENTICATION_SERVICES= (BEQ, KERBEROS5)</code>
</p>
            <p><code>SQLNET.KERBEROS5_CLOCKSKEW = 6000</code>
</p>
            <p><code>SQLNET.KERBEROS5_CONF = /etc/krb5.conf</code>
</p>
            <p><code>SQLNET.KERBEROS5_CONF_MIT = true</code>
</p>
            <p><code>SQLNET.AUTHENTICATION_KERBEROS5_SERVICE = oracle</code>
</p>
         </td>
      </tr>
   </tbody>
</table>

-   You have a running Key Distribution Center (KDC), such as Windows Active Directory, and realm setup

-   You have created an externally authenticated oracle user that corresponds to the Kerberos user to be used

-   The virtual machine, on which you install SecureTransport, has a resolvable FQDN (Fully Qualified Domain Name). If it doesn't, edit the */etc/hostname* file to add the following line: `<hostname>.yourrealm.com`

-   All participants in a Kerberos realm have accurate system clocks

**SecureTransport configuration**

The following are the high-level steps on configuring Kerberos authentication for a connection to an Oracle database. This section points out only the settings that you need to know or change for SecureTransport. The procedure is platform-dependant.

1.  Install the Kerberos client packages on the SecureTransport machine.

2.  Edit the */etc/krb5.conf* file to reflect your realm setup.

3.  Obtain a forwardable TGT ticket for the Kerberos/Oracle user.

4.  Configure SecureTransport to use Kerberos authentication when connecting to the database.

    -   Set **Use Kerberos mode** to true
    -   Specify the location of the Kerberos configuration file:  
        a) If you want SecureTransport to persist the Kerberos configuration file and synchronize it between nodes:  
        On fresh install, uncheck the "Use Kerberos configuration file" checkbox, then specify the location of the file. SecureTransport will copy the file locally.  
        If SecureTransport is already installed and running, go to Server Configuration -> Configuration Files and upload the krb5.conf file.  
        b) If you want SecureTransport to refer to the Kerberos configuration file directly, check the "Use System Kerberos configuration file" checkbox during installation or database configuration. When this option is selected, SecureTransport will not copy the file locally and will not synchronize it between nodes.
    -   Specify the location of the Kerberos credential cache file.

5.  For more information on configuring fresh installations, refer to the *SecureTransport Installation Guide*. To change the database configuration on existing systems, refer to [Change the Oracle database configuration](../t_st_oracle).

**Caution**: In an Enterprise Cluster setup, execute all the steps on all of the SecureTransport servers.

### Troubleshooting

-   When using separate databases for the Server Log and the Transfer log, you need a dedicated Kerberos user for each. The users must use their own Kerberos cache file.
-   When a Kerberos credential expires, the TGT is not renewed by SecureTransport. Ensure that a valid Ticket is always present; otherwise, the connection to the database will be lost.
-   The Oracle database server may incorrectly interpret requests from SecureTransport as a replay attack ("Request is a replay" error message). This issue is resolved in Oracle 19.8 Patch 31716873. On previous Oracle database versions , the available workaround is to disable the Replay Cache mechanism.
