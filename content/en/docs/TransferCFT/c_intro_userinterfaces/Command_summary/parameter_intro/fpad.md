{
    "title": "fpad",
    "linkTitle": "fpad",
    "weight": "1310"
}### fpad

#### SEND, CFTSEND, RECV and CFTRECV    TYPE = FILE

\[ FPAD = string \]

This parameter defines the padding character at the file level.

-   Fixed format: Specifies the character to use for padding using FPAD at file level. If FPAD is not set, the padding character depends on the FCODE used. When FCODE=ASCII it is an ASCII space, FCODE=EBCDIC it is an EBCDIC space, and FCODE=BINARY it is a binary zero.
-   Variable format: Defines the character to use to unpad the record. If FPAD is not set, the record is unchanged.

<table data-cellpadding="0" data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td data-valign="top">         </td>
         <td data-valign="top"><span><strong>Note</strong></span>         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">In addition to printable characters, you can also enter a non-printable character for NPAD or FPAD using the hexadecimal syntax: 0xHH. For example: <span>0xFC, 0xab, 0x00</span>         </td>
      </tr>
   </tbody>
</table>

For information on [padding](../../../concepts/transfer_command_overview/padding) at the network level see [NPAD](npad).

[Return to Command index](../)
