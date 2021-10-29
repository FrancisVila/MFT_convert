{
    "title": "suser",
    "linkTitle": "suser",
    "weight": "3440"
}### <span id="suser"></span>suser

#### CFTRECV, <span id="suser_CFTSEND"></span>CFTSEND, SEND, RECV, DISPLAY, LISTCAT

**\[SUSER = *string* 32 \]**

*PeSIT E only*

Identifier for the user who is sending the file.

This parameter value is case sensitive in CFTUTIL commands if you enclose the value in " " quotes.

The server/sender
partner sends and controls this parameter, where:

<table data-cellspacing="0" width="90%">
   <tbody>
      <tr class="odd" data-mc-conditions="">
         <td width="26%">            <p>PeSIT E standard</p>         </td>
         <td width="74%">            <p>In standard PeSIT E, the SUSER parameter is transported
in the PI 03, and its length is limited to 8-characters.
Therefore, the PI 03 contains the concatenated value along with the value of the SAPPL
parameter.</p>         </td>
      </tr>
      <tr class="even">
         <td width="26%">            <p><strong><br />
</strong>PeSIT E CFT/CFT</p>         </td>
         <td width="74%">            <p>In PeSIT E between 2 <span>Transfer CFT</span>s, the SUSER parameter value is transported in the PI 99 if this value is longer than 8 characters.</p>         </td>
      </tr>
   </tbody>
</table>

<table data-cellpadding="0" data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td data-valign="top">         </td>
         <td data-valign="top"><span><strong>Note</strong></span>         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">You can use the RUSER and SUSER fields when performing a catalog search. Additionally these fields are integrated into the catalog index. See <a href="ruser">RUSER</a>.         </td>
      </tr>
   </tbody>
</table>

See PeSIT extension PI codes for information on PI codes.

[Return to Command index](../)
