{
    "title": "Using PKIKEYGEN",
    "linkTitle": "Using PKIKEYGEN",
    "weight": "290"
}The PKIUTIL command PKIKEYGEN can generate a new RSA key pair (PKIKEY) and inserts it in the Transfer CFT PKI database, which you can use when implementing [SFTP](../../../protocols_start_here/sftp_intro).

<table data-cellspacing="0">
   <thead>
      <tr class="header">
         <th>Parameter</th>
         <th>Values</th>
         <th>Description</th>
      </tr>
   </thead>
   <tbody>
      <tr class="odd">
         <td>PKIFNAME         </td>
         <td>string         </td>
         <td>Transfer CFT PKI database file name         </td>
      </tr>
      <tr class="even">
         <td>ID         </td>
         <td>string, 32 char         </td>
         <td>PKIKEY identifier         </td>
      </tr>
      <tr class="odd">
         <td>COMMENT         </td>
         <td>string         </td>
         <td>A free comment         </td>
      </tr>
      <tr class="even">
         <td>STATE         </td>
         <td>            <p>ACT, INACT</p>         </td>
         <td>            <p>State of the key</p>         </td>
      </tr>
      <tr class="odd">
         <td>KEYLEN         </td>
         <td>1024, 2048, or 4096         </td>
         <td>Length of the generated key         </td>
      </tr>
      <tr class="even">
         <td>MODE         </td>
         <td>CREATE, REPLACE an existing PKIKEY         </td>
         <td>Action on the database         </td>
      </tr>
   </tbody>
</table>

Procedure

The following example creates both a private and public key. You can then export the public key to a remote Transfer CFT, or to another product that is using SFTP.

1.  Use PKIKEYGEN to generate the key pair.  
    <table data-cellspacing="0">
       <tbody>
          <tr class="odd">
             <td>            <p>PKIUTIL PKIKEYGEN</p>
                <p>ID=KEY_2048,</p>
                <p>PKIFNAME=$CFTPKU,</p>
                <p>STATE=ACT,</p>
                <p>KEYLEN=2048,</p>
                <p>MODE=CREATE,</p>
                <p>COMMENT="2048-bits RSA key"</p>         </td>
          </tr>
       </tbody>
    </table>
2.  Export the SSH key from the Transfer CFT PKI database. See also [PKIEXT](pkiext).  
    <table data-cellspacing="0">
       <tbody>
          <tr class="odd">
             <td>            <p>PKIUTIL PKIEXT FOUT=KEY_2048.CFG, ID=KEY_2048, TYPE=KEY</p>         </td>
          </tr>
       </tbody>
    </table>
3.  Note the IKNAME value (KPRIVxxxx where xxxx is 4 numeric values) found in the KEY\_2048.CFG file.
4.  Locate the KPUBxxxx file, which is in the same folder as the extracted PKI information (KEY\_2048.CFG).
5.  Use the same four digits as in the IKNAME to locate the KPUB file. For example, if the IKNAME is KPRIV1234 the KPUB that you need is KPUB1234.  
    This public key is in SSH-RSA format and can be used on other SFTP clients.
6.  On the remote Transfer CFT import the public key, KPUB1234 in our example, using the PKIKEY command.  
    <table data-cellspacing="0">
       <tbody>
          <tr class="odd">
             <td>            <p>PKIUTIL PKIKEY ID=<span>KPUB1234</span>, ikname=<span>KPUB1234</span>, ikform=SSH, MODE=REPLACE</p>         </td>
          </tr>
       </tbody>
    </table>
