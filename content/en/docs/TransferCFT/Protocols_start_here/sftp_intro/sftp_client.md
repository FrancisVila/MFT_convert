{
    "title": "Configure Transfer CFT as an SFTP client",
    "linkTitle": "Configure the Transfer CFT SFTP client",
    "weight": "170"
}T**he supported operating systems are listed in the** [Platform features](../../datasheet) **table.**

To configure a Transfer CFT SFTP client:

1.  Define the SFTP protocol.
2.  Add the server public key in client profile.
3.  Add the client key in the PKI database.
4.  Define an SSH client profile.
5.  Define a partner to use in a flow.
6.  Set the type authentication.

## Define the protocol (CFTPROT) for the Transfer CFT client

The following parameters are used to define the client's SFTP protocol:

-   TYPE: SFTP
-   SSH: Link to the CFTSSH object (DIRECT=CLIENT)
-   NET: link to the CFTNET 

Example

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>cftprot id = SFTP,</p>
<blockquote>
            <p>TYPE = 'SFTP',</p>
            <p>SSH = 'SSH_DEFAULT',</p>
            <p>NET = NET0,</p>
</blockquote>
            <p>   ...</p>         </td>
      </tr>
   </tbody>
</table>

## Add the server public key in the client profile

Use the PKIKEY command to add the server public key in the database.

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>PKIKEY id=SRV_PUB_KEY, ikname='serv.pub', ikform=ssh         </td>
      </tr>
   </tbody>
</table>

## Add the client key in the PKI database (PKIKEYGEN or PKIKEY)

You can use either the PKIKEYGEN command or the PKIKEY command to add the client key in the server database if you are using key authentication (or dual authentication). For more information, see [Generate and manage keys](new_pki_keys_use).

Example

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>PKIKEYGEN id=MY_KEY, keylen=2048</p>         </td>
      </tr>
   </tbody>
</table>

## Define the SSH client profile (CFTSSH)

This section you use CFTSSH to define a SSH profile in Transfer CFT. The CFTSSH definition contains the SSH parameter connection for SFTP in client mode. For more information, please see [Define CFTSSH](../../c_intro_userinterfaces/web_copilot_ui/cftssl/cftssh)
(SFTP).

-   ID: Identifier of the object
-   DIRECT=CLIENT
-   SRVPUBKEY=Identifier of the key used to authenticate the server
-   CLIPRIVKEY: Key Id of the client private key to use with key authentication.

Example

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>CFTSSH id = SSH_DEFAULT,</p>
<blockquote>
            <p>DIRECT = CLIENT,</p>
            <p>CLIPRIVKEY = MY_KEY,</p>
            <p>SRVPUBKEY = ,</p>
            <p>...</p>
</blockquote>         </td>
      </tr>
   </tbody>
</table>

## Define the partner (CFTPART) for a flow

A CFTPART object represents an application, with one SFTP user per application (CFTPART = one application). To define a CFTPART object in client mode using SFTP:

-   NSPART: Corresponds to your client login
-   SAP: The remote SFTP server port
-   HOST:The remote SFPT server host
-   PROT: Refers to the SFTP protocol

<table data-cellpadding="0" data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td data-valign="top">         </td>
         <td data-valign="top"><span><strong>Note</strong></span>         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">The following sections describe the type of partner authentication.         </td>
      </tr>
   </tbody>
</table>

## Set the type of authentication

Select the appropriate type of authentication to use from the options listed in this section. For more information, see [SSH concepts](sftp_keys_concepts).

### <span id="Password"></span>Password authentication

Use  one of the following methods to configure the client password:

-   Clear text: When NSPASSW=&lt;the user password>, the client password is in clear text.

<!-- -->

-   Uconf definition: When NSPASSW=\_AUTH\_, authentication is specified in uconf:cft.server.authentication\_method is used.

<table data-cellpadding="0" data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td data-valign="top">         </td>
         <td data-valign="top"><span><strong>Note</strong></span>         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">If you do not define NSPASSW, <span>Transfer CFT</span> does not send a password to the server.         </td>
      </tr>
   </tbody>
</table>

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>CFTPART id = USER1,</p>
<blockquote>
            <p>prot = SFTP,</p>
            <p>sap = 1763,</p>
            <p>nspart = "user1",</p>
            <p>nspassw = "TheUser1Password", ...</p>
</blockquote>
            <p>CFTTCP id = USER1,</p>
<blockquote>
            <p>host = &lt;server host&gt;,
...</p>
</blockquote>         </td>
      </tr>
   </tbody>
</table>

![Client NSPART arrow to Server Login, Cient NSPASSW arrow to server Password](/Images/TransferCFT/sftp_client.png)

### <span id="Key"></span>Key authentication

To configure how the client sends the key (CFTSSH):

-   Identifier: CLIPRIVKEY refers to an identifier in the local PKI database.

This is how the client decides the CLIPRIVKEY to use for the SSH profile:

-   To use a specific SSH profile, you must define it in CFTPART 
-   If you do not define a specific SSH profile, then the client will use the one defined by default in CFTPROT 

This example illustrates a specific SSH profile (SSH\_USER2 below).

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>CFTPART id = USER2,</p>
<blockquote>
            <p>ssh = SSH_USER2,</p>
            <p>sap = 1763,</p>
            <p>prot = SFTP,</p>
            <p>nspart = "user2", ...</p>
</blockquote>
            <p> </p>
            <p>CFTTCP id = USER2,</p>
            <p>host = &lt;remote host&gt;, ...</p>
            <p> </p>
            <p>CFTSSH id = SSH_USER2,</p>
<blockquote>
            <p>direct = CLIENT,</p>
            <p>cliprivkey = USER2, ...</p>
</blockquote>         </td>
      </tr>
   </tbody>
</table>

### Password and key authentication

When using **password and key** authentication:

-   NSPASSW: Use one of the methods to configure how the client sends its password, as described [here](#Password)
-   CLIPRIVKEY: Use this to configure how the client sends its key, as described [here](#Key)

<!-- -->

-   <table data-cellspacing="0">
       <tbody>
          <tr class="odd">
             <td>            <p>CFTPART id = USER3,</p>
    <blockquote>
                <p>ssh = USER3,</p>
                <p>sap = 1763,</p>
                <p>prot = SFTP,</p>
                <p>nspart = "user3",</p>
                <p>nspassw = "TheUser3Password",...</p>
    </blockquote>
                <p> </p>
                <p>CFTTCP id = USER3,</p>
    <blockquote>
                <p>host = &lt;remote host&gt;, ...</p>
    </blockquote>
                <p> </p>
                <p>CFTSSH id = USER3,</p>
    <blockquote>
                <p>direct = CLIENT,</p>
                <p>cliprivkey = USER3, ...</p>
    </blockquote>         </td>
          </tr>
       </tbody>
    </table>

## <span id="Transcod"></span>Transcoding parameters

You can configure the conversion using FCHARSET/NCHARSET or FCODE/NCODE, where transcoding is performed if FCODE differs from NCODE, or if FCHARSET differs from NCHARSET. The FCHARSET/NCHARSET parameters, however, take precedence over FCODE/NCODE if both are defined. Additionally:

-   The charset and transferred file code are exchanged between the requester and server for two Transfer CFTs.
-   A transfer restart is forbidden if the FCHARSET/NCHARSET conversion is done at the server level.
-   The NCODE parameter is available in CFTRECV as with CFTSEND.

See also, [Transcoding concepts](transfercft/protocols_start_here/sftp_intro).

Related topics

[CFTSSH - Security profile](../../c_intro_userinterfaces/web_copilot_ui/cftssl/cftssh)
