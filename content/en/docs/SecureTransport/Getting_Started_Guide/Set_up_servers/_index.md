{
    "title": "Set up servers",
    "linkTitle": "Set up servers",
    "weight": "100"
}Setup step 6 requires you to define the settings for HTTP, FTP, AS2, SSH, PeSIT, and TM Server.

The **Configure &gt; 6-Set Up Servers** page displays the FTP, HTTP, AS2, SSH, PeSIT, TM, and Monitor server settings. You can use this page to change the protocol ports, specify the protocol SSL key aliases, enable and disable services, and start or stop the services. When you are setting up an Edge server, you can also configure the Proxy server settings. When logged in as the Setup Administrator on {{< SecureTransport/componentshortname  >}} Server, the following settings are displayed:

<img src="/Images/SecureTransport/setup_servers_server.png" class="maxWidth" alt="Set Up Servers - Server Control - View and maintain servers." />

> **Note:**
>
> When you log in to the Administration Tool using the admin account, you can access this page by selecting Operations &gt; Server Control. For more information about managing the servers, refer to the SecureTransport Administrator's Guide.

## Set the SSL key alias

When you set up FTPS, HTTPS, AS2 (SSL), SSH, or PeSIT, you select a key alias to specify the certificate to use to secure the communications. You create the alias on Setup step 4 - Generate certificates. For more information, see [Generate certificates](../generate_certificates).

## Set the FIPS transfer mode

For client-initiated transfers using the AS2, FTPS, HTTPS, SSH (SFTP/SCP), or PeSIT protocols, you can select **Enable FIPS Transfer Mode** to restrict the {{< SecureTransport/componentshortname  >}} server to use only FIPS 140-2 Level 1 certified cryptographic libraries. This mode requires the sender and the recipient (clients and partner servers) to use only the approved algorithms, ciphers, and cipher suites listed in the and assures that the entire transfer is secure at FIPS 140-2 Level 1.

> **Note:**
>
> If FIPS transfer mode is enabled for a protocol server, however the respective client does not provide the required FIPS cipher or cipher suite, SecureTransport will not complete the transfer.

## Configure FTP servers

To use FTP in non-streaming environments, specify the FTP settings for the {{< SecureTransport/componentshortname  >}} Server. In streaming environments, specify the FTP settings for the {{< SecureTransport/securetransportname  >}} Edge.

1.  Select **Enable FTP**. Additionally, if needed, select **Enable FTPS**.

2.  If FTP is already running on port 21 (8021) at the OS level, change the **FTP Port** to use a port number other than the default setting of 21 for root installations and 8021 for non-root installations.  

    > **Note:**
    >
    > Additionally, to avoid a port conflict, disable FTP at the OS level or assign it a different port number instead of changing the port number in SecureTransport.

3.  If you enabled FTPS, select an **SSL Key Alias** from the drop-down list, for example, **ftpd**.

4.  If you enabled FTPS, to restrict FTPS connections to FIPS 140-2 Level 1 certified cryptographic libraries, select the **Enable FIPS Transfer Mode** check box.

5.  Click **Start**.

> **Note:**
>
> Configuring the FTP servers does not enable plain FTP. By default, the Secure Socket Layer (SSL) is enabled for all protocols. To enable plain FTP, an SSL user rule with encryption optional must be created. For information on creating SSL user rules, refer to the SecureTransport Administrator's Guide.

## Configure HTTP servers

To use HTTP, specify the HTTP settings for both the {{< SecureTransport/componentshortname  >}} Edge and {{< SecureTransport/componentshortname  >}} Server.

1.  Select one or both of **Enable HTTP** and **Enable HTTPS**. If you select Enable HTTPS, by default **Enable HSTS** will also be selected. You can also deselect **Enable HSTS** once **Enable HTTPS** is selected. When HSTS is enabled, a HSTS response will always be sent, redirecting the plain HTTP connection to HTTPS. Enabling HSTS requires a HTTP server restart.
2.  The default HTTP port number is 80 for root installations and 8080 for non-root installations. The default HTTPS port number is 443 for root installations and 8443 for non-root installations. If a default port is in use, {{< SecureTransport/componentshortname >}} displays a message and you must change the **Port** to use a port number other than the default setting.
3.  If you enabled HTTPS, select an **SSL Key Alias** from the drop-down list, for example, **httpd**.
4.  If you enabled HTTPS, to restrict HTTPS connections to FIPS 140-2 Level 1 certified cryptographic libraries, select the **Enable FIPS Transfer Mode** check box.
5.  Click **Start**.

## Configure AS2 servers

If an AS2 license is available, enable the AS2 service. Specify the AS2 settings on both {{< SecureTransport/componentshortname  >}} Server and {{< SecureTransport/componentshortname  >}} Edge.

1.  Select **Enable AS2 (non-SSL)** and/or **Enable AS2 (SSL)**. If you select **Enable AS2 (SSL)**, by default **Enable HSTS** will also be selected. You can also deselect **Enable HSTS** once **Enable AS2 (SSL)** is selected. When HSTS is enabled, a HSTS response will always be sent, redirecting the plain AS2 connection to SSL. Enabling HSTS requires a AS2 server restart.
2.  Enter a port for each protocol you enabled.
3.  If you enabled AS2 (SSL), select an **SSL Key Alias** from the drop-down list.
4.  If you enabled AS2 (SSL), to restrict AS2 (SSL) connections to FIPS 140-2 Level 1 certified cryptographic libraries, select the **Enable FIPS Transfer Mode** check box.
5.  In the **AS2 Shutdown Port field,** enter a shutdown port for AS2 server.
6.  Click **Start**.

## Configure SSH servers

If you are using SSH, specify the SSH settings for both the {{< SecureTransport/componentshortname  >}} Edge and {{< SecureTransport/componentshortname  >}} Server.

1.  Select **Enable Secure File Transfer Protocol (SFTP)** and/or **Enable Secure Copy (SCP)**.
2.  Enter a port to assign.
3.  If the operating system SSH server is using port 22, assign a different port number. To avoid a port conflict, you can disable SSH at the OS level or assign it a different port number instead of changing the port number in {{< SecureTransport/componentshortname >}}. By default, the operating system SSH port for {{< SecureTransport/companyname >}} appliances is 10022.
4.  Select an **SSH Key Alias** from the drop-down list.
5.  To restrict SSH (SFTP/SCP) connections to FIPS 140-2 Level 1 certified cryptographic libraries, select the **Enable FIPS Transfer Mode** check box.
6.  Click **Start**.

To view the SSH Server Public Key Fingerprint, click **View Fingerprint**.

> **Note:**
>
> View Fingerprint does not work until a key alias has been assigned and the page is updated.

## Configure PeSIT servers

If you are using PeSIT, specify the PeSIT server settings for both the {{< SecureTransport/componentshortname  >}} Edge and {{< SecureTransport/componentshortname  >}} Server.

1.  Select one or more of the PeSIT transmission options:
    -   **Enable PeSIT over Plain Socket** – Select to enable non-secure PeSIT transfers.
    -   **Enable PeSIT over Secured Socket** – Select to enable secure PeSIT transfers.
    -   **Enable PeSIT over pTCP Plain Socket** – Select to enable non-secure PeSIT transfers over pTCP.
    -   **Enable PeSIT over pTCP Secured Socket** – Select to enable secure PeSIT transfers over pTCP.
    -   **Enable PeSIT over Secured Socket (Legacy)** – Select to enable transfers with remote partners using SSL Legacy.
    -   **Enable PeSIT over Secured Socket (legacy § comp)** – Select to enable the automatic detection of the used SSL/TLS mode (Legacy or Comp) when {{< SecureTransport/componentshortname >}} acts as a server.
2.  If you are not using the default port, type a port for each option you selected.
3.  If you enabled either SSL option, select an **SSL Key Alias** from the drop-down list.
4.  If you enabled either SSL option, to restrict PeSIT SSL connections to FIPS 140-2 Level 1 certified cryptographic libraries, select the **Enable FIPS Transfer Mode** check box.
5.  Click **Start**.

For information about more PeSIT settings, refer to the .

## Start the Transaction Manager server on SecureTransport Server

The Transaction Manager (TM) server runs on {{< SecureTransport/componentshortname  >}} Server. To start it, click the corresponding *Actions* dropdown list and select **Start**.

## Start the Monitor server

The Monitor server checks that the {{< SecureTransport/componentshortname  >}} services are running and restarts them if they terminate. However, the Monitor server does not restart a service if a dependent service is not running. The Monitor server can run on {{< SecureTransport/componentshortname  >}} Server or {{< SecureTransport/componentshortname  >}} Edge.

To start it, click the corresponding **Start** button.

## Configure the Proxy Server on SecureTransport Edge

On the {{< SecureTransport/componentshortname  >}} Edge, specify the port for the {{< SecureTransport/componentshortname  >}} proxy server. The proxy port is used by {{< SecureTransport/componentshortname  >}} Server to handle outgoing connections passed through a {{< SecureTransport/componentshortname  >}} Edge.

1.  Enter a port number to assign for a **Proxy Port**.
2.  Click **Start**.

For the remaining proxy configuration on the {{< SecureTransport/componentshortname  >}} Server and the {{< SecureTransport/componentshortname  >}} Edge, refer to the .
