{
    "title": "Using PKIKEYGEN",
    "linkTitle": "Using PKIKEYGEN",
    "weight": "280"
}The PKIUTIL command PKIKEYGEN can generate a new RSA key pair (PKIKEY) and inserts it in the Transfer CFT PKI database, which you can use when implementing [SFTP](../../../../protocols_start_here/sftp_intro).

<table>
   <th>
      <tr>
<th>Parameter         </th>
<th>Values         </th>
<th>Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>PKIFNAME         </td>
         <td>string         </td>
         <td>Transfer CFT PKI database file name         </td>
      </tr>
      <tr>
         <td>ID         </td>
         <td>string, 32 char         </td>
         <td>PKIKEY identifier         </td>
      </tr>
      <tr>
         <td>COMMENT         </td>
         <td>string         </td>
         <td>A free comment         </td>
      </tr>
      <tr>
         <td>STATE         </td>
         <td><p>ACT, INACT</p>         </td>
         <td><p>State of the key</p>         </td>
      </tr>
      <tr>
         <td>KEYLEN         </td>
         <td>1024, 2048, or 4096         </td>
         <td>Length of the generated key         </td>
      </tr>
      <tr>
         <td>MODE         </td>
         <td>CREATE, REPLACE an existing PKIKEY         </td>
         <td>Action on the database         </td>
      </tr>
   </tbody>
</table>

Procedure

The following example creates both a private and public key. You can then export the public key to a remote Transfer CFT, or to another product that is using SFTP.

1.  Use PKIKEYGEN to generate the key pair.  



        PKIUTIL PKIKEYGEN 
         ID=KEY_2048, 
         PKIFNAME=$CFTPKU, 
         STATE=ACT, 
         KEYLEN=2048, 
         MODE=CREATE, 
         COMMENT="2048-bits RSA key"

2.  Export the SSH key from the Transfer CFT PKI database. See also [PKIEXT](../pkiext).  



        PKIUTIL PKIEXT FOUT=KEY_2048.CFG, ID=KEY_2048, TYPE=KEY

3.  Note the IKNAME value (KPRIVxxxx where xxxx is 4 numeric values) found in the KEY\_2048.CFG file.

4.  Locate the KPUBxxxx file, which is in the same folder as the extracted PKI information (KEY\_2048.CFG).

5.  Use the same four digits as in the IKNAME to locate the KPUB file. For example, if the IKNAME is <span style="color: #b22222;">KPRIV1234 </span>the KPUB that you need is <span style="color: #b22222;">KPUB1234</span>.  
    This public key is in SSH-RSA format and can be used on other SFTP clients.

6.  On the remote <span class="mc-variable axway_variables.Component_Long_Name variable">Transfer CFT</span> import the public key, KPUB1234 in our example, using the PKIKEY command.  



        PKIUTIL PKIKEY ID=KPUB1234, ikname=KPUB1234, ikform=SSH, MODE=REPLACE
