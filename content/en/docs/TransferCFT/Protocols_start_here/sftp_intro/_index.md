{
    "title": "SFTP protocol",
    "linkTitle": "SFTP protocol",
    "weight": "120"
}T**he supported operating systems are listed in the** [Platform features](../../datasheet) **table.**

The SSH File Transfer Protocol (SFTP) is a protocol that transfers files over an encrypted SSH channel. Transfer CFT supports the SFTP versions 3, 4, 5 and 6 for both client and server functionality.

The following sections describe the Transfer CFT SFTP feature:

-   [Supported operations](#supporte)
-   [Supported Transfer CFT features](#supporte2)
-   [Use cases](#use)
-   [Configuration template](#configur)
-   [Limitations](#limitati)
-   Transcoding
-   Protocol, partner, and flow definition
-   [PKI formats and use](pki_keys_use.htm)
-   [SFTP examples](cftssh_example)
-   [Troubleshoot SFTP](sftp_troubleshoot)

## <span id="Supporte"></span>Supported operations

The Transfer CFT in server mode supports the following SFTP commands:

-   Upload (put) and download (get)
-   Get directory listings
-   Create, remove, change directory
-   Rename, remove file
-   Change file mode

The Transfer CFT in client mode supports the following SFTP commands:

-   Upload (put) and download (get)

## <span id="Supporte2"></span>Supported features    

The Transfer CFT SFTP implementation supports these features:

-   Text/binary file transfer
-   Group of files in heterogeneous mode (mput, mget)
-   Folder monitoring
-   Multi-node
-   SSH compression
-   Bandwidth control in client mode
-   Authentication with the user password
-   Authentication with an SSH key
-   Dual authentication with user password and SSH key
-   Amazon S3

## <span id="Use"></span>Use cases

You can use SFTP with Transfer CFT, other Axway products, and third-party products, to connect file transfer networks.

Use case 1: Connecting networks

Transfer CFT can integrate with non-PeSIT based file transfer networks, as a server as well as a client.

> ![](sftp_arch2.jpg)

Use case 2: Application to application file transfers

Alternatively, you can implement Transfer CFT with SFTP in application to application flow scenarios. Transfer CFT can transfer files between applications using PeSIT or SFTP, as either a client or a server.

> ![](sftp_arch2.jpg)

## <span id="Configur"></span>Configuration template

Transfer CFT provides a basic SFTP configuration template. Click [here](cft-sftp.conf) to view the template.

## Restart a transfer

Transfers are activated by the client, so a restart only works from the client side.

-   Between two Transfer CFTs, interrupted transfers are restarted as on other protocols. There is only one entry in the catalog for the transfer. Use the file name to identify the transfer identifier during the restart.
-   When a send is restarted by the client, it checks that the file is still available on the server. This is possible only when the transfer is configured in Open Mode, because otherwise the server file name is provided by the server and the client does not know what it is.

## <span id="Using"></span>Using Amazon S3

Transfer CFT supports the use of Amazon S3 for SFTP file transfers. Configure as you would for PeSIT, and additionally define the UCONF aws.credentials.\*, workingdir, and storageaccount parameters. Optionally, you can add a sub-folder to the workingdir to restrict access to S3 objects in a specified bucket.

To add a workingdir sub-folder, use the format:

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>WORKINGDIR  = 's3://cft-test-ci.eu-west-3/pub/share',         </td>
      </tr>
   </tbody>
</table>

## <span id="Limitati"></span>Limitations

-   SFTP supports messages and replies (ACK or NACK), but only between Transfer CFTs.
-   SFTP implementation does not support the store-and-forward functionality.
-   You cannot use Copilot to create CFTSSH objects.
-   When using Secure Relay with Transfer CFT for SFTP exchanges, SSH termination is not supported.
-   Transfer CFT supports the RSA digital signature algorithm; however, ECDSA and DSA are not supported.
-   512-bit RSA keys are not supported. Use at least a 1024-bit key for RSA.
-   *Windows* - You cannot modify the files rights (chmod) from the SFTP client when using Transfer CFT Windows as the SFTP server.
-   *z/OS* - Only z/OS UNIX files are processed.
-   *HP NonStop* - Only UNIX files are processed, not native files.

Limitations when using Amazon S3 with SFTP:

-   You cannot restart a transfer in server receive mode.
-   When listing files, only the size and modification time display.
-   You cannot see how much free space is available in the Amazon S3 folder.

## <span id="Transcod"></span>Transcoding concepts

The character conversion in text mode can be done at the requester or server level, either in a send or receive (as with PeSIT).

SFTP version variations

-   SFTP 3 and lower: There is no flag to open a file in text mode, so the text mode is selected through the IDF's FTYPE parameter. The newline conversion can be specified on the client side.
-   SFTP 4 and higher: The client indicates if the transfer is done in binary or text mode. This overrides the IDF's FTYPE parameter. The newline conversion is done on the client side to accommodate the server requirement.

See also, [Configure the SFTP server &gt; Transcoding parameters](sftp_server) and [Configure the SFTP client &gt; Transcoding parameters](sftp_client).

 