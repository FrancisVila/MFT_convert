{
    "title": "SFTP quick start!",
    "linkTitle": "SFTP quick start!",
    "weight": "140"
}T**he supported operating systems are listed in the** [Platform features](../../datasheet) **table.**

This page provides a bare-bones configuration for you to begin to explore using SFTP for file transfers. When you are ready for a more advanced configuration, refer to the [Client configuration](sftp_client) and [Server configuration](sftp_server) pages.

## What you need

An installed Transfer CFT that acts as the server, and FileZilla (or similar) to use as the client.

## Step overview

1.  Generate and import the server keys.
2.  Interpret the template for the server configuration.
3.  Use the provided connection details in the client.
4.  Drag and drop your file!

## Tasks on the Transfer CFT server

### 1. Generate and import keys

Generate the server's public/private key pair using the pkikeygen utility, which automatically puts the key pair in the PKI database (CFTPKU).

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>PKIUTIL pkikeygen id=SRV_PRIV_KEY, keylen=2048         </td>
      </tr>
   </tbody>
</table>

### 2. Interpret the predefined SFTP template

From the runtime directory, interpret the cft-sftp.conf template (click [here](#) to view the template). Remember, Transfer CFT and the Transfer CFT Copilot server must be stopped.

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>cftinit conf/cft-sftp.conf         </td>
      </tr>
   </tbody>
</table>

This example uses the most basic type of authentication. However, the cft-sftp.conf template includes examples of multiple types of authentication, as described in detail in [SSH concepts](sftp_keys_concepts).

## Tasks on the FileZilla client

### 3. Enter server connection details

Start Filezilla and enter the following connection details:

-   Host: sftp://&lt;host address of the Transfer CFT server>
-   Port: 1763 (if you used the SAP from the template)
-   Username: user1
-   Password: TheUser1Password  
    <table data-cellpadding="0" data-cellspacing="0">
       <tbody>
          <tr class="odd">
             <td data-valign="top">         </td>
             <td data-valign="top"><span><strong>Tip  </strong></span>         </td>
             <td data-mc-autonum="&lt;b&gt;Tip  &lt;/b&gt;" data-valign="top">The username and password are case sensitive.         </td>
          </tr>
       </tbody>
    </table>

Click **Quickconnect** to connect.

Click **OK** to accept the pop-up to accept the key.  
![](/Images/TransferCFT/fz_client_popup.png)

### 4. Perform a file transfer

Drag and drop files to FLOW01 or FLOW02 to perform file transfers.

![](/Images/TransferCFT/fz_client.png)

You can check the Transfer CFT log for details.

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>00 19/03/26 10:42:52 CFTY51I SSH server session established CTX=32000 PROT=SFTP Version=SSH2</p>
            <p>Cipher in=aes256-ctr Cipher out=aes256-ctr Key</p>
            <p>00 19/03/26 10:42:52 CFTY51I+exchange=curve25519-sha256@libssh.org hmac in=hmac-sha2-256</p>
            <p>hmac out=hmac-sha2-256</p>
            <p>00 19/03/26 10:42:52 CFTT70I The user user1 is connecting with method Password</p>
            <p>00 19/03/26 10:42:52 CFTY53I SFTP server session established CTX=32000 PROT=SFTP Version=3</p>
            <p>Authentication=Password CFT Client=No</p>
            <p>00 19/03/26 10:42:52 CFTH56I SFTP Server session opened &lt;PART=USER1 IDS=32000</p>
            <p>HOST=127.0.0.1&gt;</p>
            <p>00 19/03/26 10:43:08 CFTY51I SSH server session established CTX=33000 PROT=SFTP Version=SSH2</p>
            <p>Cipher in=aes256-ctr Cipher out=aes256-ctr Key</p>
            <p>00 19/03/26 10:43:08 CFTY51I+exchange=curve25519-sha256@libssh.org hmac in=hmac-sha2-256</p>
            <p>hmac out=hmac-sha2-256</p>
            <p>00 19/03/26 10:43:08 CFTT70I The user user1 is connecting with method Password</p>
            <p>00 19/03/26 10:43:08 CFTY53I SFTP server session established CTX=33000 PROT=SFTP Version=3</p>
            <p>Authentication=Password CFT Client=No</p>
            <p>00 19/03/26 10:43:08 CFTH56I SFTP Server session opened &lt;PART=USER1 IDS=33000</p>
            <p>HOST=127.0.0.1&gt;</p>
            <p>00 19/03/26 10:43:08 CFTW09I CFTRECV FLOW01 &lt;IDTU=A0000001 PART=USER1 IDF=FLOW01</p>
            <p>IDT=C2610430 NIDF=FLOW01&gt;</p>
            <p>00 19/03/26 10:43:08 CFTT53I Server file created &lt;IDTU=A0000001 PART=USER1 IDF=FLOW01</p>
            <p>IDT=C2610430&gt;</p>
            <p>00 19/03/26 10:43:08 CFTT55I Server file opened &lt;IDTU=A0000001 PART=USER1 IDF=FLOW01</p>
            <p>IDT=C2610430&gt;</p>
            <p>00 19/03/26 10:43:08 CFTT57I Server transfer started &lt;IDTU=A0000001 PART=USER1 IDF=FLOW01</p>
            <p>IDT=C2610430 IDS=33000&gt;</p>
            <p>00 19/03/26 10:43:08 CFTT58I Server transfer ended &lt;IDTU=A0000001 PART=USER1 IDF=FLOW01</p>
            <p>IDT=C2610430 IDS=33000&gt;</p>
            <p>00 19/03/26 10:43:08 CFTT58I Transfer deselected &lt;PART=USER1 IDS=33000 IDF=FLOW01</p>
            <p>IDT=C2610430&gt;</p>
            <p>00 19/03/26 10:43:08 CFTT56I Server file closed &lt;IDTU=A0000001 PART=USER1 IDF=FLOW01</p>
            <p>IDT=C2610430&gt;</p>
            <p>00 19/03/26 10:43:08 CFTT54I Server file deselected &lt;IDTU=A0000001 PART=USER1 IDF=FLOW01</p>
            <p>IDT=C2610430&gt;</p>
            <p>00 19/03/26 10:43:08 CFTT88I+&lt;IDTU=A0000001 WORKINGDIR=sftp/user1/flow01</p>
            <p>FNAME=FLOW01/stdio NBC=147998 DURATION=0s&gt;</p>         </td>
      </tr>
   </tbody>
</table>
