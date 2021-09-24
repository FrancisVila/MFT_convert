{
    "title": "npad",
    "linkTitle": "npad",
    "weight": "2270"
}### npad

#### SEND, CFTSEND, RECV and CFTRECV    TYPE = FILE

\[ NPAD = string \]

This parameter defines the padding character at the network level.

-   Fixed format: Pads the record with this character up to the size defined by NLRECL. If NPAD is not set, the padding character depends on the FCODE used. When FCODE=ASCII it is an ASCII space, FCODE=EBCDIC it is an EBCDIC space, and FCODE=BINARY it is a binary zero
-   Variable format: Defines the character used to unpad the record. If NPAD is not set, the record is unchanged.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">In addition to printable characters, you can also enter a non-printable character for NAPD or FPAD using the hexadecimal syntax: 0xHH. For example: <span>0xFC, 0xab, 0x00</span>         </td>
      </tr>
</table>

For information on [padding](../../../../concepts/transfer_command_overview/padding) at the file level, see [FPAD](../fpad).

[Return to Command index](../../)
