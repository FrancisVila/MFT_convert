{
    "title": "Using base64",
    "linkTitle": "Using base64",
    "weight": "320"
}The Transfer CFT PKICER command can use Base64 or PEM data instead of a file in order to, for example, send a certificate and key by REST API.

## Importing

The IDATA and INAME parameters and the IKDATA and IKNAME parameters are mutually exclusive.

## Exporting

When exporting data from the PKI database, you can extract the data in Base64 instead of files. By doing this, no files are created other than the command file.

For instance, with the following base:

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>Certificates:

</p>
            <p>Id.            Root          iNum  T S C K E          Exp.Date     Delivered to     Delivered by
</p>
            <p>------------ ------------ ---- - - - - - ---------- ------------- ------------</p>
            <p>INTER         ROOT                  I A x                                    22/07/2029   2k_l1_ca           2k_root
</p>
            <p>ROOT            ROOT                 R A x                     22/07/2029   2k_root              2k_root
</p>
            <p>USER         ROOT                     U A x x                               22/07/2029   2k_l1_user1      2k_root


</p>
            <p>Keys:

</p>
            <p>Id.                                                          S K Bits
</p>
            <p>-------------------------------- - - ----
</p>
            <p>PRIV                                                       A x 2048</p>
         </td>
      </tr>
   </tbody>
</table>

By default, PKIEXT uses INAME/IKNAME to create the PKICER/PKIKEY objects:

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>PKIUTIL PKIEXT FOUT=FOO.cmd</p>
         </td>
      </tr>
   </tbody>
</table>

This exports a `FOO.cmd` file, where additional files are created containing the following data:

-   ROOT0001: the ROOT DER certificate
-   USER0002: the INTER DER certificate
-   USER0003: the USER DER certificate
-   USERK003: the USER private key in KPRIV format
-   KPRIV004: the PRIV private key in KPRIV format
-   KPUB0004: the PRIV public key in ssh-rsa format

By contrast, the Base64 option uses the IDATA/IKDATA parameters to extract a single `BAR.cmd` file instead of files.

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>PKIUTIL PKIEXT FOUT=BAR.cmd, BASE64=YES</p>
         </td>
      </tr>
   </tbody>
</table>