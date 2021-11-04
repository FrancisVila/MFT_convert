{
    "title": "Configure AS2 server settings",
    "linkTitle": "Configure AS2 server settings",
    "weight": "110"
}Using the *AS2 Settings* page, you can configure the following AS2 settings that apply to all partnerships:

-   Server authentication (enable or disable). By default, server authentication is disabled.
-   Sending to and receiving from all partnerships (enable or disable). By default, sending and receiving is enabled for all partnerships.
-   Maximum file sizes for sending and receiving. The default maximum file sizes are 50 megabytes.
-   Asynchronous Receipt Receiver for HTTP and HTTPS.

For detailed information about AS2 transfers, see <a href="../../c_st_as2transfers" class="MCXref xref">AS2 transfers</a>.

## Configure AS2 transfer settings

Use the following procedure to configure AS2 transfer settings.

1.  Select **Setup > AS2 Settings**.  
    The *AS2 Settings* page is displayed.

2.  Select the check box for **Enable Server Authentication for sending** to request server authentication for outbound transfers.  

    > **Note:**
    >
    > If server authentication is enabled, the local SecureTransport AS2 server authenticates the remote (partner) server during the SSL connection. This is an additional layer of security to that provided by AS2. To be authenticated, the remote server must present a certificate signed by a certificate authority that is trusted by SecureTransport. For information about importing trusted CA certificates for indirect trust of partner server certificates, see Import a trusted CA certificate.

3.  Select the check box for **Disable sending to ALL Partnerships** to turn off all outbound transfers to AS2 partner sites.

4.  Select the check box for **Disable receiving from ALL Partnerships** to turn off all inbound transfers from AS2 partner sites.

5.  Set the **Maximum Send File Size** for outbound traffic. The file size is measured in MB.  
    To allow unlimited file sizes, enter 0 (zero). However, to transfer files larger than 2 GB, the remote partner site must support chunking and have it enabled in its Send Options.

6.  Set the **Maximum Receive File Size** for inbound traffic. The file size is measured in MB.  
    To allow unlimited file sizes, enter 0 (zero).

7.  Enter host names and port numbers for the HTTP and HTTPS protocols for the **Asynchronous Receipt Receiver**.  
    Outgoing AS2 messages are sent by the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Server. If an asynchronous receipt is requested from a partner, the partner server tries to reach the AS2 port on the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Server. In a two-layer architecture, asynchronous receipts should be delivered to <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Edge. In that case, host and port numbers in these fields should be set to AS2 server on <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Edge.

8.  When you complete editing the settings, click **Update**.