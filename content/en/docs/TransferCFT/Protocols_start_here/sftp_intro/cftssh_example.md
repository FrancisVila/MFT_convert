{
    "title": "SFTP use case examples",
    "linkTitle": "SFTP examples",
    "weight": "190"
}T

## {{< TransferCFT/transfercftname  >}} acting as a SFTP client

Put command

The equivalent command for SFTP on Linux:

Get command

Mput command

Mget command

The {{< TransferCFT/componentlongname  >}} server mustbe using open mode.

## Transfer CFT client with a Transfer CFT server

This example sends an acknowledgment following a file transfer (`cft_flow` in the example).

On the Transfer CFT 1

On {{< TransferCFT/componentlongname  >}} 2

Execute the send on Transfer CFT 1

Execute the acknowledgment from Transfer CFT 2

### Transfer CFT requester downloading multiple files

This example demonstrates receiving multiple files from a Transfer CFT SFTP server and is the equivalent of an `mget file*`.

On the Transfer CFT server

If you do not define the workingdir, the default value is the runtime directory.

On {{< TransferCFT/componentlongname  >}} requester

This results in downloading all remote files in the `test `folder with the path relative to the workingdir.

## Transfer CFT client with a SecureTransport server

On the Transfer CFT side

On the SecureTransport

Server Control: the SSH server is running with **Enable Secure File Transfer Protocol (SFTP)**

Accounts: the Account Name is `st_sftp Active` with the Login `Name=st_sftp` and `Password=st_sftp`

## Transfer CFT server with multiple client keys

In this use case, the clients are using the key authentication method where the key is different for each client. This requires a separate partner definition and dedicated SSH profile for each user.

On the Transfer CFT server side

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
