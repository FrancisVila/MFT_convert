{
    "title": "Extended character set mapping",
    "linkTitle": "Transcoding character set mapping",
    "weight": "230"
}Character transcoding defines how data are encoded during the transfer process. This is important when transferring files that do not have the same coding requirements on the sending and receiving systems. See the section **Character set transcoding** in the *Transfer CFT User Guide* for more information.

## NCHARSET and FCHARSET parameter mapping

The following table shows the mapping for the IBM i (OS/400) platform when using the NCHARSET and FCHARSET parameters.

<table data-cellspacing="0">
   <thead>
      <tr class="header">
         <th>CFT_ charset</th>
         <th>IBM i</th>
      </tr>
   </thead>
   <tbody>
      <tr class="odd">
         <td>CFT_UTF-8         </td>
         <td>01208         </td>
      </tr>
      <tr class="even">
         <td>CFT_UTF-16         </td>
         <td>01204         </td>
      </tr>
      <tr class="odd">
         <td>CFT_UTF-16LE         </td>
         <td>01202         </td>
      </tr>
      <tr class="even">
         <td>CFT_UTF-16BE         </td>
         <td>01200         </td>
      </tr>
      <tr class="odd">
         <td>CFT_UTF-32         </td>
         <td>01236         </td>
      </tr>
      <tr class="even">
         <td>CFT_UTF-32BE         </td>
         <td>01232         </td>
      </tr>
      <tr class="odd">
         <td>CFT_UCS-2         </td>
         <td>N/A         </td>
      </tr>
      <tr class="even">
         <td>CFT_CP850         </td>
         <td>00850         </td>
      </tr>
      <tr class="odd">
         <td>CFT_BIG5         </td>
         <td>00947         </td>
      </tr>
      <tr class="even">
         <td>CFT_ISO8859-1         </td>
         <td>00819         </td>
      </tr>
      <tr class="odd">
         <td>CFT_ISO8859-15         </td>
         <td>00923         </td>
      </tr>
      <tr class="even">
         <td>CFT_EBCDIC-FR         </td>
         <td>00297         </td>
      </tr>
   </tbody>
</table>
