{
    "title": "Security elements",
    "linkTitle": "Transport security",
    "weight": "250"
}This section describes how to implement transfer security with {{< TransferCFT/axwayvariablesComponentShortName  >}} {{< TransferCFT/axwayvariablesComponentVersion  >}} and higher.

Delivered components
--------------------

To implement the transfer security measures using SSL protocol, you must have access to certificates. Standard certificates are supplied as sequential files that are restored during the product installation.

The following table describes the certificates.


| Certificate name  | Function  |
| --- | --- |
| AXWAY_MFT_DEMONSTRATION_ROOT_CERTIFICAT.DER  | Local authority certificate. |
| MFT_DEMONSTRATION_USER_CERTIFICATE.DER  | Client certificate signed by the local authority. |
| MFT_DEMONSTRATION_USER_CERTIFICATEK.DER  | Private key associated with the preceding certificate. |
| CFTPKI.INX | Indexed certificate internal datafile that is generated by PKIUTIL. |
| MFT_DEMONSTRATION_USER_CERTIFICATE.P12  | Certificate in pkcs12 format.  |


Logical names and symbols
-------------------------

The following table lists the logical name and the role of the logical name.


| Logical name  | Role  |
| --- | --- |
| CFTPKU  | Logical name specifying the certificate database  |


.PKIUTIL is the symbol that launches PKIUTIL.EXE program execution.

Modifying parameters
--------------------

You must define specific elements in setting the product parameters in order to implement the transfer security measures as described in the {{< TransferCFT/axwayvariablesComponentShortName  >}} Transport Security sub-book in the {{< TransferCFT/axwayvariablesComponentShortName  >}} online documentation.

For the CFTPARM card, you must define the number of CFTTSSL tasks to use (sslmtask) and the location of the configuration file (CFTPKU).

```
cftparmid = IDPARM0,
. . .
sslmtask
= 1,   
pkifname
= CFTPKU,
pkipassw
= ‘XXX’,
        . . .
```

For the CFTPROT card, you must define a new protocol that uses the CFTSSL type card.

```
cftprot id       = PANYRT,
        type     = PESIT,
        . . .
        ssl      = SSLPESIT
```

 The addition of two CFTSSL-type cards, associated with this protocol, define a server mode (direct = server) and a client mode (direct = client). These cards are designed to work according to version 3 of the SSL protocol.

****Server configuration****

```
cftssl id = SSLPESIT,
direct = SERVER,
rootcid = (AXWMFTCA),
usercid = AXWMFTUSER,
passw = 'AXWMFTUSER',
ciphlist = (61,60,59,53,47,10,9,5,4,1,2),
verify = NONE,
parm = 'SERVER ONLY AUTH'
```

****Client configuration****

```
cftssl id = SSL_LOOP0,
direct = CLIENT,
rootcid = (AXWMFTCA),
passw = 'AXWMFTCA',
ciphlist = (53,47,10,9,5,4,1,2),
verify = REQUIRED,
parm = 'SERVER ONLY AUTH',
mode = replace
```

Create a LOOPAT partner that dialogs in TCP and uses a new protocol to secure its exchanges (ssl = PANYRT):

```
cftpart id = LOOPSSL0,
prot = PESITSSL,
sap = %uconf:samples.pesitssl_sap.value%,
nspart = LOOPSSL0,
nrpart = LOOPSSL0,
ssl = SSL_LOOP0,
mode = replace
cfttcp id = LOOPSSL0,
host = XXXXXXXX,
cnxout = 8,
cnxin = 8,
cnxinout = 8,
mode = replace
```