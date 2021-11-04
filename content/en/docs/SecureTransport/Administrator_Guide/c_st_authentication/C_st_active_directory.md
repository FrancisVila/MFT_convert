{
    "title": "Configure  Kerberos as an Identity Provider in SecureTransport",
    "linkTitle": "Configure a Kerberos as an Identity Provider in SecureTransport",
    "weight": "220"
}This topic describes the configuration of Kerberos as an Identity Provider and the configuration of SecureTransport as a Service provider. In order to setup Kerberos to work with SecureTransport you need to have three files; the Kerberos configuration file, the `.keytab` file, and the `sso-enduser.xml` file.

## Generate a Kerberos keytab file on Windows

For information about how to configure the Kerberos for UNIX-like systems, refer to the official Kerberos documentation.

A `keytab` file contains pairs of Kerberos principals and encrypted keys that are derived from the Kerberos password. You can use a `keytab` file for resource authentication without entering a password.

1.  Open CMD on your Domain Controller.
2.  Use the `ktpass` command to set up an identity mapping for the service principal:

`ktpass -princ HTTP/<FQDN>@<realm> -mapuser <SPN> -pass <password> -out <PATH_TO_KEYTAB_FILE> -ptype KRB5_NT_PRINCIPAL -crypto AES256-SHA1`

Where:

-   FQDN - Fully qualified domain name of the Microsoft Windows Server machine (the command is case-sensitive, therefore make sure you precisely enter the FQDN of your Windows machine)
-   Realm - Domain Name (**with UPPERCASE letters**). In case there are multiple domains that have Active Directory replication, use the primary domain name instead of the sub domain.
-   SPN - Service Principal Name (the user name of a user created in the Active directory of your Domain Controller)

Path to keytab file – Enter a valid path on your Domain Controller Windows machine for the `keytab` file to be generated to. Example: `C:\key.keytab`

The selected encryption may be different.

After the command is successfully executed, the `keytab` file is generated in the specified location.

## Create a Kerberos configuration file


    com.sun.security.jgss.krb5.accept {
        com.sun.security.auth.module.Krb5LoginModule required
        principal="<HTTP/FQDN@REALM>"
        keyTab="ABSOLUTE_PATH_TO_KEYTAB_FILE"  
        useKeyTab=true
        storeKey=true
        isInitiator=false
        doNotPrompt=true;
    };

> **Note:**
>
> In a Standard Cluster or Enterprise Cluster environment, you have to specify the login modules for all Cluster nodes inside the Kerberos configuration file.

Main attributes:

-   FQDN - Fully qualified domain name of the Microsoft Windows Server machine on which SecureTransport is installed (as entered in the `ktpass` command)
-   Realm - Domain Name (as entered in the `ktpass` command)
-   `keyTab` - The path to which the SSO configuration files are uploaded in SecureTransport. If SecureTransport is installed in C drive of your Windows machine, the path would be: `C:/Axway/SecureTransport/STServer/conf/sso/key.keytab`

## Edit the sso-enduser.xml file

In order to use Kerberos as IdP for end-users you need to edit and upload the `sso-enduser.xml` file.

Verify that it contains Kerberos Identity Provider. Example:


    <KerberosIdentityProvider 
    entityId="kerberos" configurationUrl="C:/Axway/SecureTransport/STServer/conf/sso/krb5Login.conf">
    </KerberosIdentityProvider>

`configurationUrl` - The absolute path to the `krb5Login.conf` file location after the SSO configuration files are uploaded to <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span>. If <span class="mc-variable suite_variables.SecureTransportName variable">SecureTransport</span> is installed on the C drive of your Windows machine, the path would be the same as the one in the example.

## Configure supported browser authentication

For a list of SecureTransport supported browsers, refer to <a href="../../overview/r_st_axway_and_third-party_software_support#Browsers" class="MCXref xref">Browsers</a>.

To use Kerberos with SecureTransport the browsers will need some fine tuning.

**For example:**

For Microsoft Internet Explorer:

1.  The SecureTransport instance should be added to the *Trusted sites* list.

2.  Navigate to **Internet Options > Security tab > Trusted sites > Custom level**. Scroll all the way to bottom under *User Authentication* and *Logon*, select **Automatic logon with current user name and password**.  

    > **Note:**
    >
    > This action will prevent the additional authentication pop up.

 

For Firefox:

Navigate to the **about:config** URL in Firefox and set *http://,https://* to the following properties:

`network.negotiate-auth.trusted-uris`

`network.automatic-ntlm-auth.trusted-uris`

For Chrome:

Google Chrome in Windows will use the Internet Explorer settings, so configure within Internet Explorer's Tools.

For Safari:

Mac OS supports SPNEGO with Kerberos as an authentication mechanism if Mac OS is joined to the Active directory.

## Verify SSO authentication

To verify end-user SSO authentication, log onto a Windows machine joined to the same domain used as a realm in the SSO configuration, with a user existing in the Active directory. The Windows machine should be different from the one SecureTransport is installed to. Configure your browser for Kerberos authentication, and enter the URL of the ST Web Client (STWC) using the fully qualified domain name. You should be logged into STWC automatically with the same user account that you logged onto the Windows machine.
