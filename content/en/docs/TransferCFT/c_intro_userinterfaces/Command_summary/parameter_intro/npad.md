{
    "title": "npad",
    "linkTitle": "npad",
    "weight": "2240"
}### npad

#### SEND, CFTSEND, RECV and CFTRECV    TYPE = FILE

\[ NPAD = string \]

This parameter defines the padding character at the network level.

-   Fixed format: Pads the record with this character up to the size defined by NLRECL. If NPAD is not set, the padding character depends on the FCODE used. When FCODE=ASCII it is an ASCII space, FCODE=EBCDIC it is an EBCDIC space, and FCODE=BINARY it is a binary zero
-   Variable format: Defines the character used to unpad the record. If NPAD is not set, the record is unchanged.

<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Note</strong></span>         </td>
         <td>In addition to printable characters, you can also enter a non-printable character for NAPD or FPAD using the hexadecimal syntax: 0xHH. For example: <span class="code">0xFC, 0xab, 0x00</span>         </td>
      </tr>
   </tbody>
</table>

For information on [padding](../../../../concepts/transfer_command_overview/padding) at the file level, see [FPAD](../fpad).

[Return to Command index](../../)
