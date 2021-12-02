{
    "title": "SFTP use case examples",
    "linkTitle": "SFTP examples",
    "weight": "190"
}T

## {{< TransferCFT/transfercftname  >}} acting as a SFTP client

Put command

```
CFTPART id=app1,nspart=login,nspassw=passw,prot=sftp,...
CFTTCP id=app1,host=host
send part=app1, idf=flow01, fname=localfiletosend, nfname=remotefile
```

The equivalent command for SFTP on Linux:

```
sftp login@host
sftp> put localfiletosend remotefile
```

Get command

```
recv part=app1, idf=flow01, fname=localfiletowrite, nfname=remotefile
 
The equivalent command for SFTP:
sftp> get remotefile localfiletowrite
```

Mput command

```
send part=app1,idf=groupoffiles,fname=(@/#)file\*
 
The equivalent command for SFTP:
sftp> mput file\*
```

Mget command

The {{< TransferCFT/componentlongname  >}} server mustbe using open mode.

```
recv part=app1,idf=groupoffiles,nfname=(@/#)file\*,file=all
 
The equivalent command for SFTP:
sftp> mget file\*
```

## Transfer CFT client with a Transfer CFT server

This example sends an acknowledgment following a file transfer (`cft_flow` in the example).

On the Transfer CFT 1

```
CFTPART ID=CFT\_2\_SFTP,nspart="cft\_1\_sftp",nspassw=cft\_1\_sftp,nrpart="cft\_2\_sftp",nrpassw=cft\_2\_sftp,sap=<CFT\_2\_SFTP\_PORT>,prot=SFTP
CFTTCP ID=CFT\_2\_SFTP,host=<CFT\_2\_HOST>
```

On {{< TransferCFT/componentlongname  >}} 2

```
CFTPART ID=CFT\_1\_SFTP,nspart="cft\_2\_sftp",nspassw=cft\_2\_sftp,nrpart="cft\_1\_sftp",nrpassw=cft\_1\_sftp,sap=<CFT\_1\_SFTP\_PORT>,prot=SFTP
CFTTCP ID=CFT\_1\_SFTP,host=<CFT\_1\_HOST>
```

Execute the send on Transfer CFT 1

```
send part=CFT\_2\_SFTP,idf=**cft\_flow**,fname=localfiletosend,nfname=remotefile
```

Execute the acknowledgment from Transfer CFT 2

```
send part=CFT\_1\_SFTP,idm=cft\_ack,type=reply, msg=completed, idt=&idt(of the **cft\_flow**)
```

### Transfer CFT requester downloading multiple files

This example demonstrates receiving multiple files from a Transfer CFT SFTP server and is the equivalent of an `mget file*`.

On the Transfer CFT server

If you do not define the workingdir, the default value is the runtime directory.

```
cftsend id=groupoffiles,impl=yes,fname=&nfname
```

On {{< TransferCFT/componentlongname  >}} requester

```
recv part=app1,idf=groupoffiles,nfname=(@/#)test/file\*,file=all
```

This results in downloading all remote files in the `test `folder with the path relative to the workingdir.

## Transfer CFT client with a SecureTransport server

On the Transfer CFT side

```
CFTPART ID=ST\_SFTP,nspart="st\_sftp",nspassw=st\_sftp,sap=<ST\_SFTP\_PORT>,prot=SFTP
CFTTCP ID=ST\_SFTP,host=<ST\_HOST>
```

On the SecureTransport

Server Control: the SSH server is running with **Enable Secure File Transfer Protocol (SFTP)**

```
Port=<ST\_SFTP\_PORT>
```

Accounts: the Account Name is `st_sftp Active` with the Login `Name=st_sftp` and `Password=st_sftp`

```
send part=ST\_SFTP,idf=st\_flow,fname=localfiletosend,nfname=remotefile
```

## Transfer CFT server with multiple client keys

In this use case, the clients are using the key authentication method where the key is different for each client. This requires a separate partner definition and dedicated SSH profile for each user.

On the Transfer CFT server side

```
For each user define a CFTPART (in this example there are two users USER1 and USER2) as follows:
 
CFTPART ID=**USER1**,NRPART=USER1,SSH=USER1\_SSH,PROT=SFTP,...
CFTSSH ID=USER1\_SSH,DIRECT=SERVER,CLIPUBKEY=USER1\_PUB, ...
 
CFTPART ID=**USER2**,NRPART=USER2,SSH=USER2\_SSH,PROT=SFTP,...
CFTSSH ID=USER2\_SSH,DIRECT=SERVER,CLIPUBKEY=USER2\_PUB,...
 
CFTPROT ID=SFTP,TYPE=SFTP,SSH=SSH\_DEFAULT,SAP=1763,...
 
CFTSSH ID=SSH\_DEFAULT,SRVPRIVKEY=CFT\_SSH\_PRIV,CLIPUBKEY='',... (where '' indicates that the key is not set allowing multiple users)
 
To import the USER1\_PUB and USER2\_PUB keys, use the PKIUTIL command. For example, import the SSH keys as follows, where 'CFT' is the password value you entered in the CFTPARM object:
PKIUTIL PKIKEY ID=USER1\_PUB, IKNAME=USER1\_PUB.KEY, IKFORM=SSH
PKIUTIL PKIKEY ID=USER2\_PUB, IKNAME=USER2\_PUB.KEY, IKFORM=SSH
 
```

For each of the various clients

The client must log in as USER1 or USER2, in this example, and provide the corresponding private key as required for server connection.

## {{< TransferCFT/componentlongname  >}} transcoding when using

This example uses two {{< TransferCFT/componentlongname  >}} applications in , where the Source application is a UNIX machine and the Target is a z/OS system. On these applications, navigate to the indicated sections in the flow definition and define the following parameters to enable the transcoding.

On the Source

*File properties &gt; File encoding* &gt; File Type= Text , Encoding = ASCII , Transcoding = EBCDIC

In the SFTP protocol

*SFTP properties &gt;* Transfer mode = ASCII

On the Target

*File properties &gt; File encoding* &gt; File Type= Text , Encoding = EBCDIC , Transcoding = EBCDIC

Related topics

[CFTSSH - Security profile](../../../c_intro_userinterfaces/web_copilot_ui/cftssl/cftssh)
