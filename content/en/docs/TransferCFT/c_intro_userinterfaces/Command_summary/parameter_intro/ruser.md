{
    "title": "ruser",
    "linkTitle": "ruser",
    "weight": "3040"
}### <span id="ruser"></span>ruser

#### <span id="ruser_CFTRECV"></span>CFTRECV, <span id="ruser_CFTSEND"></span>CFTSEND, RECV, SEND, DISPLAY, LISTCAT

**\[RUSER = *string* 32 \]** 

*PeSIT E only*

Identifier of the user who is receiving the file.

This parameter value is case sensitive in CFTUTIL commands if you enclose the value in " " quotes.

The server/sender
partner sends and controls this parameter, where:

<table cellspacing="0">
   <col/>
   <col/>
   <tbody>
      <tr>
         <td>
            <p>PeSIT E standard</p>
         </td>
         <td>
            <p>In standard PeSIT E, the  RUSER parameter value is transported 
 in the PI 04, but its length is limited to 8-characters. 
 Therefore, the PI 04 contains the concatenated value along with the value of the RAPPL 
 parameter.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p><b><br/></b>PeSIT E CFT/CFT</p>
         </td>
         <td>
            <p>In PeSIT E between 2  <span>Transfer CFT</span>s,  the RUSER parameter value is  transported in the PI 99 if this value exceeds 8 characters.</p>
         </td>
      </tr>
   </tbody>
</table>

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">You can use the RUSER and SUSER  fields when performing a catalog search. Additionally these fields are integrated into the catalog index. See <a href="../suser">SUSER</a>.         </td>
      </tr>
</table>

See [PeSIT extension PI codes](specific_pi_codes.htm) for information on PI codes.

[Return to Command index](../../)
