{
    "title": "SFTP",
    "linkTitle": "SFTP",
    "weight": "210"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Protocols

[SFTP](#sftp_intro)

[Using SFTP in Gateway](#using_sftp_in_gateway)

<span id="sftp_intro"></span>

## SFTP Introduction

The SSH File Transfer Protocol (SFTP) is an application-level protocol used as a generic protocol for communication between users, proxies, or gateways and other Internet systems.

Gateway supports SFTP versions 0, 1, 2, 3 and 6 in client and server modes. SFTP is defined as standard file transfer with SSH (Secure SHell) providing secure login over an insecure network. SFTP has no inherent identification mechanism and therefore relies on the SSH (version 2) protocol for user authentication and a secure connection.

The SSH and SFTP protocols are separate and technically different, but are used together exclusively in Gateway. The SFTP layer is above the three protocol layers used by SSH (the TLP, UAP and CP).

To [configure an SFTP/SSH link](sftp_config), you configure several compatible objects in Gateway:

-   Remote Site
-   Network Profile object (*netprof*)
-   SSH Profile object (*sshprof*)

SSH provides the following services:

-   <span style="font-weight: bold;">[Authentication](#Authentication)</span>: Verifies the claimed identity of the host server or client user via a private/public key pair, using either of these key exchange algorithms:
    -   DSA
    -   RSA
    -   Keys included in an x.509 v3 certificate (client mode only)
    -   Diffie-Hellman exchange (diffie-hellman-group1-sha1 or diffie-hellman-group14-sha1) or preliminary exchange of new groups (diffie-hellman-group-exchange-sha1 or diffie-hellman-group-exchange-sha256)
    -   Elliptic Curves Diffie Hellman over predefined prime groups (ecdh-sha2-nistp256, ecdh-sha2-nistp384, ecdh-sha2-nistp521)
-   <span style="font-weight: bold;">Note:</span> Gateway does not support Kerberos or GSSAPI authentication in either SFTP server or client mode.
-   **Integrity:** Adds a message abstract (also referred to as a *hash code* or *message digest*) to the data to ensure that it arrives at its destination intact. In SSH the hash code, referred to as **MAC** (Message Authentication Code), is added to each message sent using the standard hash functions **SHA-1** or **MD5**.
    See the *Security Guide > [Certificates and keys](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/Managing_Security/Certificates_and_keys/certificates_and_keys_start_here.htm)* for further information (requires login).
-   **Confidentiality** (also referred to as Privacy): Prevents third parties from accessing data that is not intended for them. Typically, data is protected using either **symmetrical** or **asymmetrical** encryption techniques.
    See the *Security Guide > [Gateway security features](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/SecurityGuide/Security_features.htm)* for further information (requires login).

<span style="font-weight: bold;">Note:</span> Although both protocols can serve the same purpose, SFTP with SSH and FTP with SSL do not function in the same way.
See the *Security Guide &gt; [SSH protocol](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/Managing_Security/SSH/ssh_protocol_about.htm)* and *Security Guide &gt; [SSL and TLS protocols](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/Managing_Security/TLS/ssl_and_tls_protocols_about.htm)* for further information

<span id="using_sftp_in_gateway"></span>

## Using SFTP in Gateway

<span id="About_SFTP_processing"></span>

### About SFTP processing

SFTP is generally used for remote file access rather than file transfer. SFTP dialogue is composed of client requests and server responses (the server never takes the initiative in the dialog). In Gateway, the terms client and server are replaced with Initiator and Responder.

The SFTP syntax is based on system primitives that allow access to files and directories on UNIX or Windows.

Use SFTP commands to:

-   Open, create and close files
-   Read and write files
-   Display directory paths
-   Read and modify file attributes
-   Delete and rename files in both client and server mode (RDF only)
-   Delete and create and rename directories (RDF only)
-   Read and create symbolic links
-   Restart transfers
-   Transfer multiple files (MPUT and MGET)

<span style="font-weight: bold;">Note:</span> Gateway only supports those SFTP commands mentioned in this document.

<span id="Availability_of_protocol_specific_commands"></span>

### Availability of protocol-specific commands

Gateway provides different sets of functions for client and server mode. On the server side, replies to client requests are dependent on environment compatibility. The table below summarizes the functions available for each mode.

<span style="font-weight: bold;">Note:</span> You cannot read or create symbolic links in the Gateway implementation of SFTP.

<table>
         
         
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Function         </th>
<th class="HeadE-Column1-Header1">Client and Server         </th>
<th class="HeadE-Column1-Header1">Server Only – in Real File Directories (RFD)         </th>
<th class="HeadD-Column1-Header1">Client Only         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Open file</p>         </td>
         <td><p>YES</p>         </td>
         <td><p>-</p>         </td>
         <td><p>-</p>         </td>
      </tr>
      <tr>
         <td><p>Create file</p>         </td>
         <td><p>YES</p>         </td>
         <td><p>-</p>         </td>
         <td><p>-</p>         </td>
      </tr>
      <tr>
         <td><p>Close file</p>         </td>
         <td><p>YES</p>         </td>
         <td><p>-</p>         </td>
         <td><p>-</p>         </td>
      </tr>
      <tr>
         <td><p>Read file</p>         </td>
         <td><p>YES</p>         </td>
         <td><p>-</p>         </td>
         <td><p>-</p>         </td>
      </tr>
      <tr>
         <td><p>Write file</p>         </td>
         <td><p>YES</p>         </td>
         <td><p>-</p>         </td>
         <td><p>-</p>         </td>
      </tr>
      <tr>
         <td><p>Display directory path</p>         </td>
         <td><p>YES</p>         </td>
         <td><p>-</p>         </td>
         <td><p>-</p>         </td>
      </tr>
      <tr>
         <td><p>Read file attributes</p>         </td>
         <td><p>YES</p>         </td>
         <td><p>-</p>         </td>
         <td><p>-</p>         </td>
      </tr>
      <tr>
         <td><p>Modify file attributes (In Real File Directories (<strong>RFD</strong>) only)</p>         </td>
         <td><p>YES</p>         </td>
         <td><p>-</p>         </td>
         <td><p>-</p>         </td>
      </tr>
      <tr>
         <td><p>Delete file</p>         </td>
         <td><p>-</p>         </td>
         <td><p>YES</p>         </td>
         <td><p>YES</p>         </td>
      </tr>
      <tr>
         <td><p>Rename file</p>         </td>
         <td><p>-</p>         </td>
         <td><p>YES</p>         </td>
         <td><p>YES</p>
<p>Files can only be renamed in a post-transfer command.</p>         </td>
      </tr>
      <tr>
         <td><p>Delete directory</p>         </td>
         <td><p>-</p>         </td>
         <td><p>YES</p>         </td>
         <td><p>-</p>         </td>
      </tr>
      <tr>
         <td><p>Create directory</p>         </td>
         <td><p>-</p>         </td>
         <td><p>YES</p>         </td>
         <td><p>-</p>         </td>
      </tr>
   </tbody>
</table>

<span id="SFTP_extensions"></span>

### SFTP extensions

SFTP is customized in Gateway via extensions to the protocol, negotiated during the SFTP initialization phase. They are used only between Gateway Sites for transfer verification and data code conversion.

Extended requests contain a string field in the format <span class="code">name@domain</span>, where the domain is the DNS of the organization defining the extension. All extensions provided by Axway are therefore in the format <span class="code">name@axway.com</span>

Using this syntax, you can add extensions in the file attributes to:

-   Indicate whether or not the Remote Site is a <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span>
-   Introduce external functionality with exits

<span id="Authentication"></span>

### Authentication

Authentication is the process of verifying a claimed identity. The most widely used authentication mechanisms are:

-   <span style="font-weight: bold;">Password request:</span> Associated with user login requests: When the user sends a login name, the password request is displayed.
-   <span style="font-weight: bold;">Proof request:</span> Associated with asymmetrical encryption mechanisms. The user sends the public key (or any information relevant enough to get the public key, such as a certificate), and then receives a random encrypted message. To decrypt the message, the user must own the unique private key associated with the public key. This means that if the user can decrypt the message, the users identity is authenticated.

When using TLS and SSL protocols, the client encrypts the symmetrical key with the public key for the server. If the server can decrypt the key, the client is as claimed. Otherwise, dialogue is not possible and the connection is closed. When requested, the server uses a signature process to authenticate the client.
See the *Security Guide &gt; [SSL and TLS protocols](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/Managing_Security/TLS/ssl_and_tls_protocols_about.htm)* for further information.

<span id="Code_conversion"></span>

### Code conversion

SFTP does not transform data during a transfer. However, you can use Gateway to send or receive data in a data code other than the server default.

Gateway code conversion allows you to transform data, particularly carriage returns, when using SFTP.

#### Example: Transforming a text file from UNIX format to Windows, and vice versa

To implement this type of transformation, you must create a Transfer Request in text mode and ensure that the SFTP Transfer Request file type matches that on the remote server.

-   Set the Application field **Data code** (<span class="code">-data\_code</span>) to text mode (ASCII).
-   Set the Transfer Request field **Newline convention** (<span class="code">-newline\_convention</span>) to the file type of the remote server:
    -   Windows (or W)
    -   UNIX (or U)

      
    If you use this option regularly, you can also set the Remote Site field **Newline convention** (<span class="code">-newline\_convention</span>) to the remote server default file type:
    -   Windows (or W)
    -   UNIX (or U)

<span id="Indicating_end_of_transfer"></span>

### Indicating end of transfer

SFTP considers a transfer ended when you close the file in question. There is no particular command to indicate that a transfer is terminated or to validate a transaction.

Since the client does not send an ABORT type primitive, it is also difficult to detect the interruption of a transfer. Only when the client closes the dedicated SSH channel is the transfer deemed terminated.

The table below summarizes how transfer status is determined.

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Transfer direction</p>         </th>
<th class="HeadD-Column1-Header1"><p>Description</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Client to server</p>         </td>
         <td><p>The server has no information about the file that it will receive. The client decides:</p>
<ul>
<li>How to send the file, for example, by blocks of data (sequenced or random), or without sending blank characters (that the server will complete automatically)</li>
<li>When the transfer is ended, without advising the server</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Server to client</p>         </td>
         <td><p>The server can consider that the transfer is invalid if the client has not read the entire file</p>         </td>
      </tr>
      <tr>
         <td><p>Both</p>         </td>
         <td><p>A transfer is considered ended when:</p>
<ul>
<li>The client closes the SSH channel</li>
<li>A second file is opened before the end of the current transfer</li>
</ul>         </td>
      </tr>
   </tbody>
</table>

#### Resuming interrupted transfers

SFTP does not have an explicit command to indicate that a file access request refers to an interrupted transfer.  Resuming a file transfer is only possible because the read and write requests include an offset and a length in their parameters. By selecting packet size and defining the start location, an SFTP client can read or write:

-   Parts of a file in any order
-   Only part of a file, suspend the transfer and resume it later

You can use the following methods to resume a transfer:

-   Extended syntax with file names to link an FXP\_OPEN request to a suspended transfer.
-   The VFD syntax (local identifier with file name) also allows you to link an open file request with a transfer.
-   In monitored RFD mode, interpretation of file open options allows you to identify the Transfer Request type either as the resumption of a suspended Transfer or the creation of a new one.
-   In RFD non-monitored mode, there is no transfer tracking.

<span id="Transfer_phases"></span>

### Transfer phases

SFTP comprises a set of commands that allow you to manipulate files and directories. An SFTP client can read or write parts of a file in any order, and suspend and resume transfers.

The phases of a transfer (in an error-free scenario) are:

<table>
         
         
         
         
   
   <thead>
      <tr>
<th colspan="3" class="HeadD-Column1-Header1"><p>Transfer phases</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p><strong>Initialization phase</strong></p>         </td>
         <td><p>Exchange of version number and protocol extensions (All)</p>         </td>
      </tr>
      <tr>
         <td><p>1</p>         </td>
         <td><p>Client sends SSH_FXP_INIT to the server.</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Server sends SSH_FXP_VERSION to the client.</p>         </td>
      </tr>
      <tr>
         <td><p>Transfer phase (Core)</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>If the client requests to read from or write to a file, it sends the open command (SSH_FXP_OPEN).</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>The client receives the handle attribution (SSH_FXP_HANDLE).</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Transfer phase (Case 1)</strong></p>         </td>
         <td><p>Client to server file transfer complete server file path known</p>         </td>
      </tr>
      <tr>
         <td><p> </p>         </td>
         <td><p>The write (SSH_FXP_WRITE) and status (SSH_FXP_STATUS) commands are repeated until the file is written.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Transfer phase (Case 2)</strong></p>         </td>
         <td><p>Server to client file transfer - complete server file path known</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>The read (SSH_FXP_READ) and status (SSH_FXP_STATUS) commands are repeated until the file is read. The client can also search for the attributes of the remote file.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Transfer phase (Case 3)</strong></p>         </td>
         <td><p>Directory path request</p>
<p>If the client requests to read the directory path, the name and the attributes of any file or directory present in the open directory can be retrieved. The client can also request the attributes of the remote files in the directories.</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>The read (SSH_FXP_READ) and status (SSH_FXP_NAME) commands are repeated until the directory is read and directory file names are all listed.</p>         </td>
      </tr>
   </tbody>
</table>

Related topics

[<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span> specific SFTP commands](sftp_gateway_specific_commands)

[Configuring SFTP](sftp_config)

[SFTP security](sftp_security) using SSH

[Submitting an SFTP Transfer Request](sftp_submitting_transfer)

[Transferring multiple files with SFTP](sftp_multiple_file_transfer) (MPUT and MGET)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
