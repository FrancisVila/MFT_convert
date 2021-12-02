{
    "title": "Troubleshoot SFTP",
    "linkTitle": "Troubleshoot SFTP",
    "weight": "200"
}T

## Start Transfer CFT issues

### Error when starting {{< TransferCFT/transfercftname  >}}

If the following error displays:

CFTN05E SFTP bind() failed: ECDSA, DSA, or RSA host key file must be set.

Check the SRVPRIVKEY ID (CFTSSH direct=server) parameter. Presently, only the RSA algorithm is supported; even if ECDSA and DSA are mentioned in the error message, these algorithms are not supported.

## Authentication issues

### Server authentication issues

Client does not accept the server's public key

The following is an example of a public key authentication issue where the client does not accept the server's public key.

### Client authentication issues

Invalid users or password issues

Transfer CFT client authentication mismatches can lead to the following errors:

You may require a [trace](#Perform) on the Transfer CFT server for additional information (to see if the issue is user or password).

SFTP client case sensitivity

Remember that NSPART and NRPART are case sensitive when they are enclosed in quotes " ". For example, if the user name is `login`, then the CFTPART ID=PART,NSPART="login" and NRPART=login.

### Transfer fails

#### Enable implicit mode

You must define CFTSEND IDF=&lt;idf>,IMPL=YES when in server mode. Failing to do so leads to the following type of message:

#### Working directory

Here the connection is interrupted because of a `workingdir `issue when connecting to the Transfer CFT SFTP via an SFTP client:

#### SAUTH/RAUTH

These parameters check the authorized IDF for the user. For example, in the following messages an error occurred because when performing a RECV (`get`) command, the IDF was not included in the remote authorization list.

Server

No catalog record, and in the log:

Client

Catalog record:

Log:

#### Open mode not allowed

When open mode is not enabled on a non-Transfer CFT client, a generic message displays:

On the server side, additional information can be found in the log:

Catalog:

#### Client key does not correspond to server key

When using {{< TransferCFT/transfercftname  >}} as a client, the server's public key referenced by SRVPUBKEY (CFTSSH direct=Client) does not correspond to the server key.

Check that the public key stored in the PKI database corresponds with the server's (SRVPUBKEY value). This issue may occur due to a Transfer CFT limitation where when an SFTP server refers to multiple hostkeys (located in `etc/ssh/sshd_config`), the Transfer CFT related hostkey must be placed in the first position.

As shown in the following example, the Transfer CFT public key references the `ssh_host_rsa_key`, an error occurs:

### Resources

[Diagi:Diagnostic codes](../../../troubleshoot_intro/messages_and_error_codes_start_here/diagi_diagnostic_codes). Codes with a value between 001 and 499 indicate a local issue; values between 501 and 999 correspond to a fault reported by the partner. Therefore when troubleshooting if the code is greater than 500 it refers to a remote issue.

## Check updates to the configuration (delay)

The parameters used by SFTP in CFTPARM and CFTPART files are loaded in memory when {{< TransferCFT/transfercftname  >}} starts and updated every 10 seconds if there is a change in the file.

<span id="Perform"></span>

## Perform a trace

If you were not able to remedy the issue as described in the previous sections, you may want to perform an SFTP trace. After performing the following commands, you must restart {{< TransferCFT/transfercftname  >}}.
