{
    "title": "Guidelines for improving CPU efficiency",
    "linkTitle": "Guidelines for improving CPU efficiency",
    "weight": "290"
}Use the following guidelines to help reduce your CPU load and enhance performance.

-   The data compression/decompression functions are CPU-time consuming.
-   The SGTRACE option activation is very CPU-time consuming.
-   Transfer CFT can multi-task, using multiple processors concurrently.
-   Transfer CFT z/OS accepts CFTPROT xRUSIZE values that are less than or equal to 32750 bytes.
    -   A high RUSIZE value significantly reduces the CPU load. Since CFTPROT values are negotiated with the remote side and the smallest value is used, specifying large values for CFTPROT RRUSIZE and RPACING is a good performance choice.
    -   Do not set RCHKW to 0, which would indicate no flow control.
-   Transfer CFT can detect and use available CPACF features (hardware assist). CPACF is a free IBM feature for the z/Series.
-   The SSL handshake may use a lot of CPU cycles depending on the length of the asymmetric (RSA) key. Using an IBM Crypto Express coprocessor, along with a supporting PKI exit, may improve performance.

## Using zIIP

This section describes how Transfer CFT z/OS uses zIIP capability for Transfer CFT compression. The System z Integrated Information Processor, zIIP, is a special purpose engine available on IBM z9 and z10 mainframes that enables you to significantly reduce the cost of computing by reducing CPU consumption.

To use the zIIP feature:

-   Your System z must have one or more online zIIP processors.
-   You require a minimum z/OS version of 1.10.
-   Set ziipsup to 1 to activate. You can modify this in the member of target.UPARM(CNFENV), which by default is set to 0.

## Cryptographic devices and supported algorithms

### Available SSL cryptographic devices

The following SSL crypto devices and related crypto algorithms are available for the z9, z10, and z196 models.

-   CPACF (CP Assist for Cryptographic Functions): DES, 3DES, AES128, AES256, SHA256, SHA512
-   CEX2 (Crypto Express2): RSA
-   CEX3 (Crypto Express3): RSA

### Transfer CFT 3.x z/OS crypto device usage

This table lists, for each possible SSL-protocol cryptographic function and Pki.type used, whether a crypto device used.


| TLS protocol exchange  | Cryptographic function  | Pki.type  | z9 - z10  | z196  |
| --- | --- | --- | --- | --- |
| Handshake phase  | RSA  |  CFT<br/>PASSPORT<br/>SYSTEM  |  Software<br/>Software<br/>CEX2  |  Software<br/>Software<br/>CEX3  |
| Record Level SYM encryption  | DES, 3DES  |  CFT<br/>PASSPORT<br/>SYSTEM  |  CPACF<br/>CPACF<br/>CPACF  |  CPACF<br/>CPACF<br/>CPACF  |
| Record Level SYM encryption  | AES  |  CFT<br/>PASSPORT<br/>SYSTEM  |  CPACF<br/>CPACF<br/>CPACF  |  CPACF CPACF CPACF  |
| Record Level SYM encryption  | RC4  |  CFT PASSPORT SYSTEM  |  Software Software Software  |  Software Software Software  |
| Record Level hashing  | SHA, SHA-256  |  CFT PASSPORT SYSTEM  |  CPACF CPACF CPACF  |  CPACF CPACF CPACF  |
| Record Level hashing  | MD5  |  CFT PASSPORT SYSTEM  |  Software Software Software  |  Software Software Software  |


### Crypto configuration information

When {{< TransferCFT/transfercftname  >}} is started, depending on the system configuration, the Transfer CFT log contains the following information:
