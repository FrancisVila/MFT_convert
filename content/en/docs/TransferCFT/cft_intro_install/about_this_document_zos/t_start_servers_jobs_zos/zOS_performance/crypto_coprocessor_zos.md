{
    "title": "Guidelines for improving CPU efficiency",
    "linkTitle": "Guidelines for improving CPU efficiency",
    "weight": "300"
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

<table cellspacing="0">
   <col/>
   <col/>
   <col/>
   <col/>
   <col/>
   <thead>
      <tr>
         <th>TLS protocol exchange</th>
         <th>Cryptographic function</th>
         <th>Pki.type</th>
         <th>z9 - z10</th>
         <th>z196</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>Handshake phase         </td>
         <td>RSA         </td>
         <td>
            <p>CFT
</p>
            <p>PASSPORT
</p>
            <p>SYSTEM
</p>
         </td>
         <td>
            <p>Software
</p>
            <p>Software
</p>
            <p>CEX2
</p>
         </td>
         <td>
            <p>Software
</p>
            <p>Software
</p>
            <p>CEX3
</p>
         </td>
      </tr>
      <tr>
         <td>Record Level SYM encryption         </td>
         <td>DES, 3DES         </td>
         <td>
            <p>CFT
</p>
            <p>PASSPORT
</p>
            <p>SYSTEM
</p>
         </td>
         <td>
            <p>CPACF </p>
            <p>CPACF </p>
            <p>CPACF </p>
         </td>
         <td>
            <p>CPACF </p>
            <p>CPACF </p>
            <p>CPACF </p>
         </td>
      </tr>
      <tr>
         <td>Record Level SYM encryption         </td>
         <td>AES         </td>
         <td>
            <p>CFT
</p>
            <p>PASSPORT
</p>
            <p>SYSTEM
</p>
         </td>
         <td>
            <p>CPACF </p>
            <p>CPACF </p>
            <p>CPACF </p>
         </td>
         <td>
            <p>CPACF </p>
            <p>CPACF </p>
            <p>CPACF </p>
         </td>
      </tr>
      <tr>
         <td>Record Level SYM encryption         </td>
         <td>RC4         </td>
         <td>
            <p>CFT
</p>
            <p>PASSPORT
</p>
            <p>SYSTEM
</p>
         </td>
         <td>
            <p>Software
</p>
            <p>Software

</p>
            <p>Software
</p>
         </td>
         <td>
            <p>Software
</p>
            <p>Software

</p>
            <p>Software
</p>
         </td>
      </tr>
      <tr>
         <td>Record Level hashing         </td>
         <td>SHA, SHA-256         </td>
         <td>
            <p>CFT
</p>
            <p>PASSPORT
</p>
            <p>SYSTEM
</p>
         </td>
         <td>
            <p>CPACF </p>
            <p>CPACF </p>
            <p>CPACF </p>
         </td>
         <td>
            <p>CPACF </p>
            <p>CPACF </p>
            <p>CPACF </p>
         </td>
      </tr>
      <tr>
         <td>Record Level hashing         </td>
         <td>MD5         </td>
         <td>
            <p>CFT
</p>
            <p>PASSPORT
</p>
            <p>SYSTEM
</p>
         </td>
         <td>
            <p>Software
</p>
            <p>Software

</p>
            <p>Software
</p>
         </td>
         <td>
            <p>Software
</p>
            <p>Software

</p>
            <p>Software
</p>
         </td>
      </tr>
   </tbody>
</table>

### Crypto configuration information

When Transfer CFT is started, depending on the system configuration, the Transfer CFT log contains the following information:

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>CFTI18I+Crypto configuration</p>
            <p>CFTI18I+   CPACF Cryptographic assist is set.</p>
            <p>CFTI18I+   The following CP Assist for Cryptographic Function (CPACF)</p>
            <p>CFTI18I+   operations are supported by OpenSSL s390 engine:</p>
            <p>CFTI18I+     SHA-1:       No</p>
            <p>CFTI18I+     SHA-256:     Yes</p>
            <p>CFTI18I+     SHA-384:     Yes</p>
            <p>CFTI18I+     SHA-512:     Yes</p>
            <p>CFTI18I+     DES CBC:     Yes</p>
            <p>CFTI18I+     TDES CBC:    Yes</p>
            <p>CFTI18I+     AES-128 CBC: Yes</p>
            <p>CFTI18I+     AES-256 CBC: Yes</p>
            <p>CFTI18I+     AES-128 GCM: No</p>
            <p>CFTI18I+     AES-256 GCM: No</p>
         </td>
      </tr>
   </tbody>
</table>
