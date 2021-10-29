{
    "title": "SFTP use case examples",
    "linkTitle": "SFTP examples",
    "weight": "190"
}T**he supported operating systems are listed in the** [Platform features](../../datasheet) **table.**

## Transfer CFT acting as a SFTP client

Put command

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>CFTPART id=app1,nspart=login,nspassw=passw,prot=sftp,...</p>
            <p>CFTTCP id=app1,host=host</p>
            <p>send part=app1, idf=flow01, fname=localfiletosend, nfname=remotefile</p>         </td>
      </tr>
   </tbody>
</table>

The equivalent command for SFTP on Linux:

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>sftp login@host</p>
            <p>sftp&gt; put localfiletosend remotefile</p>         </td>
      </tr>
   </tbody>
</table>

Get command

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>recv part=app1, idf=flow01, fname=localfiletowrite, nfname=remotefile</p>
            <p> </p>
            <p>The equivalent command for SFTP:</p>
            <p>sftp&gt; get remotefile localfiletowrite</p>         </td>
      </tr>
   </tbody>
</table>

Mput command

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>send part=app1,idf=groupoffiles,fname=(@/#)file*</p>
            <p> </p>
            <p>The equivalent command for SFTP:</p>
            <p>sftp&gt; mput file*</p>         </td>
      </tr>
   </tbody>
</table>

Mget command

The Transfer CFT server must be using open mode.

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>recv part=app1,idf=groupoffiles,nfname=(@/#)file*,file=all</p>
            <p> </p>
            <p>The equivalent command for SFTP:</p>
            <p>sftp&gt; mget file*</p>         </td>
      </tr>
   </tbody>
</table>

## Transfer CFT client with a Transfer CFT server

This example sends an acknowledgment following a file transfer (cft\_flow in the example).

On the Transfer CFT 1

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>CFTPART ID=CFT_2_SFTP,nspart="cft_1_sftp",nspassw=cft_1_sftp,nrpart="cft_2_sftp",nrpassw=cft_2_sftp,sap=&lt;CFT_2_SFTP_PORT&gt;,prot=SFTP</p>
            <p>CFTTCP ID=CFT_2_SFTP,host=&lt;CFT_2_HOST&gt;</p>         </td>
      </tr>
   </tbody>
</table>

On Transfer CFT 2

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>CFTPART ID=CFT_1_SFTP,nspart="cft_2_sftp",nspassw=cft_2_sftp,nrpart="cft_1_sftp",nrpassw=cft_1_sftp,sap=&lt;CFT_1_SFTP_PORT&gt;,prot=SFTP</p>
            <p>CFTTCP ID=CFT_1_SFTP,host=&lt;CFT_1_HOST&gt;</p>         </td>
      </tr>
   </tbody>
</table>

Execute the send on Transfer CFT 1

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>send part=CFT_2_SFTP,idf=<strong>cft_flow</strong>,fname=localfiletosend,nfname=remotefile         </td>
      </tr>
   </tbody>
</table>

Execute the acknowledgment from Transfer CFT 2

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>send part=CFT_1_SFTP,idm=cft_ack,type=reply, msg=completed, idt=&amp;idt(of the <strong>cft_flow</strong>)         </td>
      </tr>
   </tbody>
</table>

### Transfer CFT requester downloading multiple files

This example demonstrates receiving multiple files from a Transfer CFT SFTP server and is the equivalent of an mget file\*.

On the Transfer CFT server

If you do not define the workingdir, the default value is the runtime directory.

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>cftsend id=groupoffiles,impl=yes,fname=&amp;nfname</p>         </td>
      </tr>
   </tbody>
</table>

On Transfer CFT requester

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>recv part=app1,idf=groupoffiles,nfname=(@/#)test/file*,file=all</p>         </td>
      </tr>
   </tbody>
</table>

This results in downloading all remote files in the test folder with the path relative to the workingdir.

## Transfer CFT client with a SecureTransport server

On the Transfer CFT side

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>CFTPART ID=ST_SFTP,nspart="st_sftp",nspassw=st_sftp,sap=&lt;ST_SFTP_PORT&gt;,prot=SFTP</p>
            <p>CFTTCP ID=ST_SFTP,host=&lt;ST_HOST&gt;</p>         </td>
      </tr>
   </tbody>
</table>

On the SecureTransport

Server Control: the SSH server is running with **Enable Secure File Transfer Protocol (SFTP)**

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>Port=&lt;ST_SFTP_PORT&gt;</p>         </td>
      </tr>
   </tbody>
</table>

Accounts: the Account Name is st\_sftp Active with the Login Name=st\_sftp and Password=st\_sftp

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>send part=ST_SFTP,idf=st_flow,fname=localfiletosend,nfname=remotefile</p>         </td>
      </tr>
   </tbody>
</table>

## Transfer CFT server with multiple client keys

In this use case, the clients are using the key authentication method where the key is different for each client. This requires a separate partner definition and dedicated SSH profile for each user.

On the Transfer CFT server side

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>For each user define a CFTPART (in this example there are two users USER1 and USER2) as follows:</p>
            <p> </p>
            <p>CFTPART ID=<strong>USER1</strong>,NRPART=USER1,SSH=USER1_SSH,PROT=SFTP,...</p>
            <p>CFTSSH ID=USER1_SSH,DIRECT=SERVER,CLIPUBKEY=USER1_PUB, ...</p>
            <p> </p>
            <p>CFTPART ID=<strong>USER2</strong>,NRPART=USER2,SSH=USER2_SSH,PROT=SFTP,...</p>
            <p>CFTSSH ID=USER2_SSH,DIRECT=SERVER,CLIPUBKEY=USER2_PUB,...</p>
            <p> </p>
            <p>CFTPROT ID=SFTP,TYPE=SFTP,SSH=SSH_DEFAULT,SAP=1763,...</p>
            <p> </p>
            <p>CFTSSH ID=SSH_DEFAULT,SRVPRIVKEY=CFT_SSH_PRIV,CLIPUBKEY='',... (where '' indicates that the key is not set allowing multiple users)</p>
            <p> </p>
            <p>To import the USER1_PUB and USER2_PUB keys, use the PKIUTIL command. For example, import the SSH keys as follows, where 'CFT' is the password value you entered in the CFTPARM object:</p>
            <p>PKIUTIL PKIKEY ID=USER1_PUB, IKNAME=USER1_PUB.KEY, IKFORM=SSH</p>
            <p>PKIUTIL PKIKEY ID=USER2_PUB, IKNAME=USER2_PUB.KEY, IKFORM=SSH</p>
            <p> </p>         </td>
      </tr>
   </tbody>
</table>

For each of the various clients

The client must log in as USER1 or USER2, in this example, and provide the corresponding private key as required for server connection.

## Transfer CFT transcoding when using Central Governance

This example uses two Transfer CFT applications in Central Governance, where the Source application is a UNIX machine and the Target is a z/OS system. On these applications, navigate to the indicated sections in the flow definition and define the following parameters to enable the transcoding.

On the Source

*File properties &gt; File encoding* &gt; File Type= Text , Encoding = ASCII , Transcoding = EBCDIC

In the SFTP protocol

*SFTP properties &gt;* Transfer mode = ASCII

On the Target

*File properties &gt; File encoding* &gt; File Type= Text , Encoding = EBCDIC , Transcoding = EBCDIC

Related topics

[CFTSSH - Security profile](../../c_intro_userinterfaces/web_copilot_ui/cftssl/cftssh)
