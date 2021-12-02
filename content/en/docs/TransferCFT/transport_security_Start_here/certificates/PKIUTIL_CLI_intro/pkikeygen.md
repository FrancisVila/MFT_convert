{
    "title": "Using PKIKEYGEN",
    "linkTitle": "Using PKIKEYGEN",
    "weight": "280"
}The PKIUTIL command PKIKEYGEN can generate a new RSA key pair (PKIKEY) and inserts it in the Transfer CFT PKI database, which you can use when implementing [SFTP](../../../../protocols_start_here/sftp_intro).

Procedure

The following example creates both a private and public key. You can then export the public key to a remote Transfer CFT, or to another product that is using SFTP.

1.  Use PKIKEYGEN to generate the key pair.  
2.  Export the SSH key from the Transfer CFT PKI database. See also [PKIEXT](../pkiext).  
3.  Note the IKNAME value (KPRIVxxxx where xxxx is 4 numeric values) found in the KEY\_2048.CFG file.
4.  Locate the KPUBxxxx file, which is in the same folder as the extracted PKI information (KEY\_2048.CFG).
5.  Use the same four digits as in the IKNAME to locate the KPUB file. For example, if the IKNAME is the KPUB that you need is .  
    This public key is in SSH-RSA format and can be used on other SFTP clients.
6.  On the remote {{< TransferCFT/componentlongname >}} import the public key, KPUB1234 in our example, using the PKIKEY command.  
