{
    "title": "ICAP settings",
    "linkTitle": "ICAP settings",
    "weight": "250"
}The Internet Content Adaptation Protocol (ICAP) settings allow the administrator to configure ICAP engines to be used as part of the {{< SecureTransport/securetransportname  >}} file transfer processes so that data loss prevention (DLP) is achieved and anti-virus (AV) scans are completed. {{< SecureTransport/securetransportname  >}} allows the administrator to use the ICAP connector to set up a {{< SecureTransport/securetransportname  >}} server to scan (with external DLP engine) files and AdHoc messages when delivering them to the recipient folder or mailbox. ICAP server scan is executed when a file is going to be (therefore before it is) delivered.

Prior to configuring ICAP scanning, verify that ICAPScan is enabled. For information on enabling ICAPScan, refer to [Enable a rules package](../c_st_tm_settings/t_st_rulespackages#EnableRulesPackage).

> **Note:**
>
> The SecureTransport administrator can edit the entire DLP/AV ICAP URL in the following format icap://dlpav-address:port/servicename. Both the Symantec anti-virus AVSCAN and AVSCANREQ are supported, though AVSCANREQ is preferred.

> **Note:**
>
> SecureTransport will scan received AdHoc messages and attachments when recipients open a message or download an attachment. - An AdHoc message, identified as blocked by the DLP policy, will be displayed but the content will be changed to a notification stating that you are not allowed to view this message because it was blocked by the DLP policy. Subjects of messages remain changed. - When downloading message attachments, identified as blocked by DLP policy, they will be successfully downloaded but the content will be changed to a notification stating that you are not allowed to view the file because it is blocked by the DLP policy. This applies for all file types regardless if they are text files or not. File extensions will not be changed.

## The ICAP Server(s) provide

-   Multiple ICAP servers
-   Incoming and outgoing ICAP scanning for all file and message transfers
-   Scanning policy support
-   ICAP headers reporting: `X-Authenticated-User`, `X-Client-IP`, `X-Server-IP`  

> **Note:**
>
> X-Server-Icap header reports the SecureTransport local IP address with each scanning request. If multiple network interfaces are available on the machine, the reported IP may not match the actual one.

-   Custom HTTP headers reporting
-   Certain variables are now exposed to Advanced Routing

## Setup of ICAP servers

Multiple ICAP servers can be configured: there is no limitation. Scanning is performed only by ICAP servers which are enabled. There is no prioritization – all the servers will be used for scanning files and messages. If a server along the chain returns a negative result from scanning - the transfer will be denied.

Navigate to **Setup** &gt; **ICAP Settings**. The *ICAP Servers List* page presents a list of ICAP servers with basic management controls plus the option to create (add) a new server.

Click **Add new ICAP server** to open the *ICAP Server Settings* page with multiple sets of options.

### Basic ICAP settings

-   Enter the **ICAP server name**. It must be unique and there cannot be two ICAP servers with the same name.
-   Enter the **ICAP server type**. It can be INCOMING, OUTGOING or BOTH.  
    -   **INCOMING** means that scanning will be performed by this ICAP server for all Incoming transfers: File upload, AdHoc message creation, Server-initiated pull (for example from a Transfer Site)  
    -   **OUTGOING** means that scanning will be performed by this ICAP server for all Outgoing transfers: File download, Reading of an AdHoc message, Server-initiated push (for example in the Advanced Router step: Send to Partner or Publish to Account)  
    -   **BOTH** means that scanning will be performed by this ICAP server for all types of transfers
-   Enter the **ICAP URL**. Enter the DLP/AV ICAP URL in the following format:  
    `icap://dlpav-address:port/servicename`  
    The `servicename` can be the same as the mode of operation - `REQMOD` or `RESPMOD`, or something custom and vendor-specific.  
    For the exact `servicename`, refer to the Data Loss Prevention (DLP) or Anti-virus (AV) documentation.  
    If the default ICAP port (1344) is used, leave the port blank - it will be auto-populated.  
    Examples:  
    `icap://dlpav-address:1344/AVSCAN`  
    `icap://dlpav-address:1344/REQMOD`  
    `icap://dlpav-address:1344/RESPMOD`
    -   **Use Secure ICAP connection** for a secure connection to the ICAP server.
    -   Select **Verify certificate** to use certificate verification to secure the connection to the ICAP server.
    -   Select **Enable FIPS Transfer Mode** to enable transfers to the ICAP server to be in accordance with the Federal Information Processing Standard (FIPS).  
        **Note**: Verify certificate and Enable FIPS Transfer Mode can be selected together or individually depending on the level of security needed for the ICAP server connection.
-   Enter **Max file size** (MB).  
    The default maximum file size is 10 MB. If the actual file size is larger than the maximum file size, {{< SecureTransport/componentshortname >}} will send up to the maximum configured file size to the ICAP server.
-   Enter **Preview Size** (KB).  
    The default preview size is 10 KB. If the ICAP server requires more data, {{< SecureTransport/componentshortname >}} will send it up to the maximum configured file size.
    -   Select **Deny file transfer on connection error**.  
        If the **Deny file transfer on connection error** option is selected, file transfers will be denied on a connection error to the ICAP server
    -   Select **Enable e-mail notifications on ICAP error**.  
        If the **Enable e-mail notifications on ICAP error** is selected, notification emails will be sent when there is a connection failure to the ICAP server.
-   Select **Enable e-mail notifications on ICAP denied**.  
    If the **Enable e-mail notifications on ICAP denied** is selected, notification emails will be sent when there is a deny by the ICAP server.
-   Select **Put scanned file name in request's header**  
    If **Put scanned file name in request's header** is selected, the name of the file to be scanned will be included in HTTP request line and filename header. For example, the request might look like: "*GET http://base\_url/filename.example HTTP/1.1*".  
    If the checkbox is not selected, the request will contain the static string "*GET /resource HTTP/1.1*"

### ICAP scan filtering settings

Select **Scan Policy Expression** if you want to perform scanning only under specific circumstances.  
When you select the **Scan Policy Expression** checkbox, the text box field allows you to use {{< SecureTransport/componentshortname  >}} Expression Language. If both settings are disabled, scanning will always be performed. Sample usage - do not scan if the transfer is taking place over SSH protocol: `${session.protocol ne 'ssh'}`  
Refer to the [ICAP scan policy expression language](icap_el_vars) subtopic for the complete list of available expressions.

Select **Perform scanning only if there is a partner recipient**.  
This field enables or disables ICAP scanning for AdHoc messages if at least one of the recipients is external. User type - *internal* or *external*- is controlled by the account setting **Account Type**. Possible values are **Internal** - internal accounts - and **Partner** - external accounts.  
If the type of a recipient cannot be identified or is set to **Unspecified**, the account will be considered **External**. If both the filtering settings are enabled, this particular setting will be applied over AdHoc messages.

Select **Scan Without BU** to choose whether or not to enable ICAP scanning for accounts with no Business Unit assigned.

**Ignored File Types** Enter a list of file extensions, separated by comma. Files with these extensions will not be scanned.

### Custom ICAP header settings

This allows you to specify any additional custom headers that must be passed to the ICAP server when making requests, along with their values. The **Header value** fields can either have a static value or a ST expression-based one. Expressions allow you to dynamically set a value, based on a specific context, by utilizing the {{< SecureTransport/componentshortname  >}} session or environment variables.  
By default, there aren't any custom headers configured, but you can add any number of headers by selecting **Add custom headers mapping**.  
If a header value is not present or can’t be resolved, the header will be added with an empty or null value, when sending the request.  
Example:

-   Header Name: `X-Account-Name`  
-   Header Value: `${account.name}`  
-   If a user with name - user1 has logged in and the ICAP scan is performed, the `Header:Value` will be evaluated to `X-Account-Name = user1` and it will be reported to the ICAP server(s).

### Advanced connection settings

-   By selecting **Show advanced connection settings** you can see the additional server configuration options for connection.
-   **Connection timeout**. This is the maximum connection timeout in seconds that the server will wait until it stops trying to reconnect.
-   **Retry Attempts**. This is the number of retries in case of connectivity timeout.
-   **Retry delay (in ms)**. This is the delay in milliseconds between each retry.  
-   **Read timeout**. This is the maximum read timeout in seconds.
-   **Enabled Ciphers**. This is a list of ciphers to be used for an SSL connection. The ciphers must be comma-separated.
-   **Enabled Protocols**. This is a list of SSL protocols to be enabled. The protocols must be comma separated.  
    Default value for newly created ICAP servers after updating to 5.5-20210930: `TLSv1.2, TLSv1.3`.  
    Default value for existing ICAP servers: `TLSv1.2`. To enable the TLSv1.3 protocol support, edit the **Enabled Protocols** field to add `TLSv1.3`. Then, add TLSv1.3 supported values to the configured list of enabled cipher suites.

### Advanced ICAP settings

-   By selecting **Show advanced ICAP settings** you can see the additional server configuration options.
    -   Select **Enable WindowsNt format**. With this setting you can choose whether or not to report X-Authenticated-User in WinNT format in case of LDAP authentication.
    -   X-Authenticated-User  
        X-Authenticated-User is reported with each LDAP request. The header is reported differently depending on user type. Below are the supported X-Authenticated-User formats:  
        -   User with a local account and a locally stored password: Local://&lt;account name>

        -   Real OS user: Local://&lt;login name>

        -   Non LDAP user mapped to a template (SiteMinder or SSO): Local://&lt;login name>

        -   LDAP user options:

            -   If WinNT format is not enabled for the server: LDAP://&lt;LDAP domain name>/&lt;user DN>\*
            -   If WinNT format is enabled for the server: WinNT://&lt;LDAP domain name>/&lt;login name>

            > **Note:**
            >
            > For more information about user DN format, see ICAP settings.
    -   Select **Stop transfers modify or not handled** to choose whether or not to stop the transfer if ICAP server returns a MODIFY result or an unhandled status.
    -   Select **Treat modify as Block** to choose whether or not to treat the ICAP MODIFIED action as block.
-   To enable or disable an ICAP server, mark the preferred ICAP server and select the **Enable** or **Disable** button.
-   To delete an ICAP server, mark the preferred ICAP server and select the **Delete** button.
-   To edit an ICAP server, click on the record in the list of ICAP servers displayed on the page.
