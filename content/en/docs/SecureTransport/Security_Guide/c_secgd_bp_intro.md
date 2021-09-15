{
    "title": "Security best practices",
    "linkTitle": "Security best practices",
    "weight": "100"
}When using this product, follow these security best practices:

-   Always use TLS secured connections; see [Secure connections](#secure).
-   Don’t use the sample certificates provided with the installation of the product; see [Sample certificates](#sample).
-   Don’t use self-signed certificates; see [Self-signed certificates](#self-sig).
-   Maintain a list of users with privileged access; see [Privileged access user list](#privileg).
-   Limit as much as possible number of Internet access points; see [Internet access limitation](#internet).
-   Have the correct procedure to upgrade the product; see [Correct upgrade procedure](#correct).
-   Don’t define generic or anonymous users; see [Generic or anonymous users](#generic).
-   Be sure to enforce a reasonably strong password policy; see [Password policy](#password).
-   Make sure default authentication accounts are disabled or deleted; see [Default authentication account](#default).
-   Always change default passwords after installation; see [Default passwords](#default2).
-   Limit your remote connections; see [Remote connections](#remote).
-   SecureTransport supports configurations for logging, audit, and alerting; see [Logging, audit, and alerts rules](#logging,).
-   Protect your sensitive files and databases; see [Sensitive files and databases](#sensitiv).
-   Use cryptographically strong protocols and ciphers; see [Use cryptographically strong protocols and ciphers](#use).
-   Use basic authorization and Base64 encoding of username and password; see [Password encoding and BASIC authentication](#password2).
-   If you are deploying plug-ins, keep in mind that they may have their security settings.
-   Use External Script routing step with caution; see [Password encoding and BASIC authentication](#password2).

## <span id="Secure"></span>Secure connections

Axway deems it mandatory that all connections with external networks be secure and secure connections are recommended for internal connections. For example, connections between an SSO proxy and an application must always be SSL/TLS-secured with mutual authentication to avoid anyone connecting with the proxy header without any credentials.

## <span id="Sample"></span>Sample certificates

Axway provides sample certificates with the product. These certificates should be used for test purposes only. As soon as the product goes live, or as soon as real data is managed by the product, you must use your own certificates. Using sample certificates is a security risk as all Axway customers have the same certificates with the same private keys.

The following sample certificates are delivered with the product. These certificates should be used only for test purposes and must be replaced with your own certificates as soon as possible. These certificates are self-signed. They expire within a month after installation.

-   Internal CA (alias – ca)
-   Administrator UI (alias – admind). A certificate with the `admind` alias must always exist; Otherwise, the Administration Tool server won't start.

## <span id="Self-sig"></span>Self-signed certificates

Using self-signed certificates may also be a security risk for many reasons, including:

-   Anyone can generate his own certificate and you need a very secure process to receive/send these certificates to make sure they are coming from the right partner. When using CA-signed certificates, you can rely on the CA.
-   If self-signed certificates are not securely stored, anyone can change them. CA-signed certificates also must be securely stored, but no one can change them.
-   There is no way to revoke self-signed certificates.

## <span id="Privileg"></span>Privileged access user list

To be customized for every product depending on predefined privileges.

Maintain a list of users with privileged access. At a minimum, maintain a list of administrators and a list of users with access to multiple functions.

## <span id="Internet"></span>Internet access limitation

As much as possible, limit the number of internet access points. Do not open useless Internet connections and limit interconnections with external networks as much as possible. This reduces the risk of external attacks and makes it easier to audit the product.

## <span id="Correct"></span>Correct upgrade procedure

In the event of a possible vulnerability discovered in the product, you must be able to apply the patch or service pack as soon as possible. Make sure you have the correct procedure to complete the upgrade. Always use the latest version of the product, if possible, as it contains fixes to known vulnerabilities.

## <span id="Generic"></span>Generic or anonymous users

The term “generic users” means that the password is shared among multiple specific users. This makes it easier for an attacker to retrieve this password. In addition, the procedure to change shared passwords can be complicated and risky. In case of an incident, these generic or anonymous users make it impossible to determine who completed the erroneous action.

## <span id="Password"></span>Password policy

Password policy refers to size and complexity of the password, as well as to all the rules to manage this password. The size and complexity is important. The policy should define that the length be a minimum of 8 characters, contain a mix of alphabetic characters with numbers and special characters, and be case-sensitive.

Your password policy:

-   Must force passwords to be changed periodically.
-   Should prohibit reuse of a password before n number of different passwords and within a certain period of time.
-   Must define how the password is created differently from the old one (such as: at least a certain number of different characters).
-   Must limit the number of failed attempts.

## <span id="Default"></span>Default authentication account

The product is delivered with the following default administrators:

-   Master administrator (admin/admin)
-   Account manager (account/account)
-   Application manager (application/application)
-   Database administrator (dbsetup/dbsetup)
-   Setup administrator (setup/setup)

Your first task after login with this user must be to create your own administrator account and to delete the default one, or at least change the default administrator password.

## <span id="Default2"></span>Default passwords

The product is delivered with the following default passwords:

-   Keystore password (tumbleweed)
-   Database password (tumbleweed)

## <span id="Remote"></span>Remote connections

You should limit your remote connections in the following ways:

-   If no one needs to access the product remotely, make sure that the UI ports are closed in your firewall.
-   If someone needs to connect remotely only occasionally, set a procedure to open the port only on demand.
-   If there are regular remote users, make sure that the connections are as secure as possible, such as using HSTS or VPN.

## <span id="Logging,"></span>Logging, audit, and alerts rules

SecureTransport supports configurations for logging, audit, and alerting.

1.  SecureTransport has its own mechanisms for logging, auditing, and alerting. They are represented by the following features:
    -   Audit Log (**Operations > Audit Log**) - Provides the administrator with information about the configuration changes in SecureTransport. The administrator is able to get information about the entities that changed the database, as well as information about the exact time the changes happened.
    -   Server Log (**Operations > Server Log**) - Provides log messages from the following SecureTransport components: the Transaction Manager (TM) and the processes that implement the FTP, HTTP, SSH (SCP and SFTP), AS2 , PeSIT, and SOCKS5 protocols, the Administration Tool interface (ADMIN), and auditing.
    -   File Tracking (**Operations > File Tracking**) - Provides log of the statuses and attributes for each transfer.
    -   Email notifications (Refer to <span cshid="admin" data-version="5.3.5">*SecureTransport Administrator's Guide*</span> for additional information.)
2.  SecureTransport integrated with Axway Sentinel - Once SecureTransport is configured to send file transfer and processing events to Sentinel, data is collected and displayed on a dashboard.

## <span id="Sensitiv"></span>Sensitive files and databases

You must protect your sensitive files and databases. The configuration file contains information that can be useful to a hacker. Even if part of this information is encrypted, access to this file must be restricted by your local access management. Only the product and one or two administrators should have access to this file in any mode (read, update, and delete).

The file containing the password used to generate encryption keys must be protected as well. This file is encrypted, but access to this file should only be granted to the product.

The product database also contains sensitive data; you should also prohibit access to this database from any other tools or applications using the API, with the exception of one or two administrators.

## <span id="Use"></span>Use cryptographically strong protocols and ciphers

Refrain from using protocols and ciphers that are deemed insecure by today’s industry standards. We strongly suggest the use of TLS 1.2.

## <span id="Password2"></span>Password encoding and BASIC authentication

Basic authentication and Base64 encoding of username and password are required but can be exploited if not properly configured. Use of BASIC authentication by itself, is not a vulnerability; however, when combined with other factors such as not using TLS and improper no-cache response headers, it can be exploited.

If the server is configured to use TLS, the HTTP header containing the BASIC authentication header will be encrypted. If TLS is not enabled, then Base64 will provide absolutely no protection, nor was it designed to do so. It is essential however, that when BASIC authentication is used, that self-signed certificates are not. A certificate from a trusted CA is the only adequate protection of BASIC authentication credentials. Also, login attempts should be limited when using BASIC authentication.

BASIC authentication should not be enabled by default for API authentication; but should be an option, in order to integrate the API with existing systems.

## <span id="Password2"></span>External Script execution

Advanced Routing External Script step provides the functionality to run a script from the underlying file system. From version 5.5 and above, the External Script routing step exposes a property in the form of а checkbox which adds extra functionality in the external script execution.

By default, when running SecureTransport as an operating system superuser ("root"), external scripts are executed with impersonating the user account which has triggered the routing step, thus limiting the set of commands and scripts which can be run due to the lack of permissions.

When enabling the "Execute script as root administrator" checkbox, SecureTransport will use the system superuser to run the specified script and will not impersonate the user account.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top"><span>SecureTransport</span> administrators must be fully aware that running external scripts with operating system superuser permissions grants privileges to execute a full scope of commands which might harm the server irrevocably.         </td>
      </tr>
</table>

Axway recommends running external scripts without root permissions.
