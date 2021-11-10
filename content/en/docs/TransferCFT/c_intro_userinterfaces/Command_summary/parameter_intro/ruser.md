{
    "title": "ruser",
    "linkTitle": "ruser",
    "weight": "3010"
}<span id="ruser"></span>

### ruser

<span id="ruser_CFTRECV"></span><span id="ruser_CFTSEND"></span>

#### CFTRECV, CFTSEND, RECV, SEND, DISPLAY, LISTCAT

**\[RUSER = *string* 32 \]** 

*PeSIT E only*

Identifier of the user who is receiving the file.

This parameter value is case sensitive in CFTUTIL commands if you enclose the value in " " quotes.

The server/sender
partner sends and controls this parameter, where:

<table>
   <tbody>
      <tr>
         <td><p>PeSIT E standard</p>         </td>
         <td><p>In standard PeSIT E, the RUSER parameter value is transported
in the PI 04, but its length is limited to 8-characters.
Therefore, the PI 04 contains the concatenated value along with the value of the RAPPL
parameter.</p>         </td>
      </tr>
      <tr>
         <td><p><strong><br />
</strong>PeSIT E CFT/CFT</p>         </td>
         <td><p>In PeSIT E between 2 <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span>s, the RUSER parameter value is transported in the PI 99 if this value exceeds 8 characters.</p>         </td>
      </tr>
   </tbody>
</table>

> **Note:**
>
> You can use the RUSER and SUSER fields when performing a catalog search. Additionally these fields are integrated into the catalog index. See SUSER.

See PeSIT extension PI codes for information on PI codes.

[Return to Command index](../../)
