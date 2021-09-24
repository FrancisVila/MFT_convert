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

<table cellspacing="0" width="90%">
   <col/>
   <col/>
      <tr data-mc-conditions="">
         <td width="26%">
            <p>PeSIT E standard</p>
         </td>
         <td width="74%">
            <p>In standard PeSIT E, the SUSER parameter is transported 
 in the PI 03, and its length is limited to 8-characters. 
 Therefore, the PI 03 contains the concatenated value along with the value of the SAPPL 
 parameter.</p>
         </td>
      </tr>
      <tr>
         <td width="26%">
            <p><b><br/></b>PeSIT E CFT/CFT</p>
         </td>
         <td width="74%">
            <p>In PeSIT E between 2  <span>Transfer CFT</span>s,  the SUSER parameter value is  transported in the PI 99 if this value is longer than 8 characters.</p>
         </td>
      </tr>
</table>

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">You can use the RUSER and SUSER  fields when performing a catalog search. Additionally these fields are integrated into the catalog index. See <a href="../ruser">RUSER</a>.         </td>
      </tr>
</table>

See [PeSIT extension PI codes](specific_pi_codes.htm) for information on PI codes.

[Return to Command index](../../)
