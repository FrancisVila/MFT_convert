{
    "title": "Troubleshoot SFTP",
    "linkTitle": "Troubleshoot SFTP",
    "weight": "200"
}T**he supported operating systems are listed in the** [Platform features](../../datasheet) **table.**

## Start Transfer CFT issues

### Error when starting Transfer CFT

If the following error displays:

CFTN05E SFTP bind() failed: ECDSA, DSA, or RSA host key file must be set.

Check the SRVPRIVKEY ID (CFTSSH direct=server) parameter. Presently, only the RSA algorithm is supported; even if ECDSA and DSA are mentioned in the error message, these algorithms are not supported.

## Authentication issues

### Server authentication issues

Client does not accept the server's public key

The following is an example of a public key authentication issue where the client does not accept the server's public key.

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>Client side</p>
            <p>CATALOG </p>
            <p>CLIENT_S SFH TH BIN J0219374 0 0 264 KEY</p>
            <p> </p>
            <p>LOG </p>
            <p>CFTT75E Network connect reject &lt;IDTU=A000000W PART=CLIENT_SFTP_WIN IDF=BIN IDT=J0219374 DIAGI=264&gt;</p>
            <p>CFTT82E Transfer aborted &lt;IDTU=A000000W PART=CLIENT_SFTP_WIN IDF=BIN IDT=J0219374 DIAGI=264&gt;</p>         </td>
      </tr>
   </tbody>
</table>

### Client authentication issues

Invalid users or password issues

Transfer CFT client authentication mismatches can lead to the following errors:

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>LOG </p>
            <p>CFTT75E Incorrect user or password &lt;IDTU=A000000I PART=CLIENT_SFTP_WIN IDF=BIN IDT=J0218294 DIAGI=433&gt;</p>
            <p>CFTT82E Transfer aborted &lt;IDTU=A000000I PART=CLIENT_SFTP_WIN IDF=BIN IDT=J0218294 DIAGI=433&gt;</p>
            <p> </p>
            <p>CATALOG</p>
            <p>CLIENT_S SFH TH BIN J0218294 0 0 433 00000001</p>         </td>
      </tr>
   </tbody>
</table>

You may require a [trace](#Perform) on the Transfer CFT server for additional information (to see if the issue is user or password).

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>Invalid user:</p>
            <p>CFTSFTP CFT.SFTP [3] S50000: User SERV_SFTP wants to authenticate with method SYSTEM</p>
            <p>CFTSFTP CFT.SFTP [1] S50000: User SERV_SFTP not allowed to connect to the server</p>
            <p> </p>
            <p>Invalid password:</p>
            <p>CFTSFTP CFT.SFTP [3] S50000: User serv_SFTP wants to authenticate with method PASSWORD</p>
            <p>CFTSFTP CFT.SFTP [1] S50000: User serv_SFTP not allowed to connect to the server</p>         </td>
      </tr>
   </tbody>
</table>

SFTP client case sensitivity

Remember that NSPART and NRPART are case sensitive when they are enclosed in quotes " ". For example, if the user name is `login`, then the CFTPART ID=PART,NSPART="login" and NRPART=login.

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>Error: Authentication failed.</p>
            <p>Error: Critical error: Could not connect to server.</p>         </td>
      </tr>
   </tbody>
</table>

### Transfer fails

#### Enable implicit mode

You must define CFTSEND IDF=&lt;idf>,IMPL=YES when in server mode. Failing to do so leads to the following type of message:

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>CFTT16I _ No implicit send &lt;PART=&lt;part&gt; IDF=&lt;idf&gt; &gt; :         </td>
      </tr>
   </tbody>
</table>

#### Working directory

Here the connection is interrupted because of a workingdir issue when connecting to the Transfer CFT SFTP via an SFTP client:

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>Error: Unable to open .: received failure with description 'The working directories in CFTSEND and CFTRECV for the IDF are not the same'</p>
            <p>Error: Received unexpected end-of-file from SFTP server</p>
            <p>Error: Cannot recover the folder contents</p>         </td>
      </tr>
   </tbody>
</table>

#### SAUTH/RAUTH

These parameters check the authorized IDF for the user. For example, in the following messages an error occurred because when performing a RECV (get) command, the IDF was not included in the remote authorization list.

Server

No catalog record, and in the log:

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>CFTT25E _ IDF not authorized &lt;PART=SERV_SFTP IDF=AUSTIN&gt;</p>
            <p>CFTT82E Transfer aborted &lt;IDTU=00000000 PART= IDF= IDT= DIAGI=413&gt;</p>         </td>
      </tr>
   </tbody>
</table>

Client

Catalog record:

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>diagi=610 diagp=00000000</p>         </td>
      </tr>
   </tbody>
</table>

Log:

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>CFTF02E Remote file selection error &lt;IDTU=A0000005 PART=CLIENT_SFTP_UNIX IDF=F
LOW IDT=J0913570&gt;</p>
            <p>CFTT82E Transfer aborted &lt;IDTU=A0000005 PART=CLIENT_SFTP_UNIX IDF=
FLOW IDT=J0913570 DIAGI=610&gt;</p>         </td>
      </tr>
   </tbody>
</table>

#### Open mode not allowed

When open mode is not enabled on a non-Transfer CFT client, a generic message displays:

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>Command: put "C:\Users\...\MyFile.jpg" "MyFile.jpg"</p>
            <p>Error: Received unexpected end-of-file from SFTP server</p>
            <p>Error: File transfer failed</p>         </td>
      </tr>
   </tbody>
</table>

On the server side, additional information can be found in the log:

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>CFTT01E IDTU=00000000 PART=SERV_SFTP IDF=FLOW01 IDT= _ Open mode not allowed</p>
            <p>CFTT82E Transfer aborted &lt;IDTU=00000000 PART=SERV_SFTP IDF=FLOW01 IDT= DIAGI=404&gt;</p>         </td>
      </tr>
   </tbody>
</table>

Catalog:

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>Diagi=110 with diagp=00000013</p>         </td>
      </tr>
   </tbody>
</table>

#### Client key does not correspond to server key

When using Transfer CFT as a client, the server's public key referenced by SRVPUBKEY (CFTSSH direct=Client) does not correspond to the server key.

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>CFTT82E+ DIAGP=KEY DIAGC=The client key doesn't correspond to the server key         </td>
      </tr>
   </tbody>
</table>

Check that the public key stored in the PKI database corresponds with the server's (SRVPUBKEY value). This issue may occur due to a Transfer CFT limitation where when an SFTP server refers to multiple hostkeys (located in `etc/ssh/sshd_config`), the Transfer CFT related hostkey must be placed in the first position.

As shown in the following example, the Transfer CFT public key references the ssh\_host\_rsa\_key, an error occurs:

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>HostKey /etc/ssh/ssh_host_rsa_key_not_in_CFT</p>
            <p>HostKey /etc/ssh/ssh_host_rsa_key</p>         </td>
      </tr>
   </tbody>
</table>

### Resources

[Diagi:Diagnostic codes](../../Troubleshooting/Messages_and_Codes/diagi_diagnostic_codes.htm). Codes with a value between 001 and 499 indicate a local issue; values between 501 and 999 correspond to a fault reported by the partner. Therefore when troubleshooting if the code is greater than 500 it refers to a remote issue.

## Check updates to the configuration (delay)

The parameters used by SFTP in CFTPARM and CFTPART files are loaded in memory when Transfer CFT starts and updated every 10 seconds if there is a change in the file.

## <span id="Perform"></span>Perform a trace

If you were not able to remedy the issue as described in the previous sections, you may want to perform an SFTP trace. After performing the following commands, you must restart Transfer CFT.

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p><span>Windows</span></p>
            <p>set XTRACE_CFT_SFTP_LEVEL=5</p>
            <p>set XTRACE_OUTPUT_FILENAME=sftptrace.txt</p>
            <p> </p>
            <p><span>UNIX</span></p>
            <p>export XTRACE_CFT_SFTP_LEVEL=5</p>
            <p>export XTRACE_OUTPUT_FILENAME=sftptrace.txt</p>         </td>
      </tr>
   </tbody>
</table>
