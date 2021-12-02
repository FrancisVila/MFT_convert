{
    "title": "SFTP quick start!",
    "linkTitle": "SFTP quick start!",
    "weight": "140"
}T

This page provides a bare-bones configuration for you to begin to explore using SFTP for file transfers. When you are ready for a more advanced configuration, refer to the [Client configuration](../sftp_client) and [Server configuration](../sftp_server) pages.

## What you need

An installed Transfer CFT that acts as the server, and FileZilla (or similar) to use as the client.

## Step overview

1.  Generate and import the server keys.
2.  Interpret the template for the server configuration.
3.  Use the provided connection details in the client.
4.  Drag and drop your file!

## Tasks on the {{< TransferCFT/transfercftname  >}} server

### 1. Generate and import keys

Generate the server's public/private key pair using the `pkikeygen `utility, which automatically puts the key pair in the PKI database (CFTPKU).

### 2. Interpret the predefined SFTP template

From the runtime directory, interpret the `cft-sftp.conf` template (click [here]() to view the template). Remember, Transfer CFT and the Transfer CFT Copilot server must be stopped.

This example uses the most basic type of authentication. However, the `cft-sftp.conf` template includes examples of multiple types of authentication, as described in detail in [SSH concepts](../sftp_keys_concepts).

## Tasks on the FileZilla client

### 3. Enter server connection details

1.  Start Filezilla and enter the following connection details:

-   Host: sftp://&lt;host address of the {{< TransferCFT/transfercftname >}} server>

-   Port: 1763 (if you used the SAP from the template)

-   Username: user1

-   Password: TheUser1Password  

    > **Note:**
    >
    > Tip  
    > The username and password are case sensitive.

Click **Quickconnect** to connect.

Click **OK** to accept the pop-up to accept the key.  
<img src="/Images/TransferCFT/fz_client_popup.png" class="mediumWidth" />

### 4. Perform a file transfer

Drag and drop files to `FLOW01 `or `FLOW02 `to perform file transfers.

<img src="/Images/TransferCFT/fz_client.png" class="mediumWidth" />

You can check the Transfer CFT log for details.
