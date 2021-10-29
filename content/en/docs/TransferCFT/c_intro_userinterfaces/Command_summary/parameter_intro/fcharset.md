{
    "title": "fcharset",
    "linkTitle": "fcharset",
    "weight": "1100"
}### <span id="fcharset"></span>fcharset

#### SEND, RECV, CFTSEND CFTRECV CFTPROT CFTPART

**\[FCHARSET = { None / CFT\_EBCDIC-FR / CFT\_ UTF-8 / UTF-16BE / UTF-16LE / CFT\_ISO8859-1 / ASCII / EBCDIC / UTF-8 / ISO8859-1 / . . . }\]**

Defines the local file encoding.  

-   On the sender side, fcharset is used to read a file. You then use the ncharset to encode this into network data when sending a file.
-   On the receiver side, fcharset is the local file encoding used to write a file that has this type of encoding. The ncharset is used to decode network data when receiving a file.

**Example 1**

To translate a local text file before sending it, for example from UTF-8 to UTF-16, using Transfer CFT mapping:

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>CFTUTIL SEND PART = NEWYORK,</p>
            <p>IDF = TEST_UTF-8,</p>
            <p>FCHARSET = CFT_UTF-8,</p>
            <p>NCHARSET = CFT_UTF-16,</p>
            <p>FTYPE = T</p>         </td>
      </tr>
   </tbody>
</table>

**Example 2**

To translate a local text file before sending it, for example from UTF-8 to UTF-16:

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>CFTUTIL SEND PART = NEWYORK,</p>
            <p>IDF = TEST_UTF-8_2,</p>
            <p>FCHARSET = UTF-8,</p>
            <p>NCHARSET = UTF-16,</p>
            <p>FTYPE = T</p>         </td>
      </tr>
   </tbody>
</table>

See also [ncharset](ncharset) and *[Using character sets for transcoding](../../../concepts/transfer_command_overview/use_extended_character_sets).*

[Return to Command index](../)
