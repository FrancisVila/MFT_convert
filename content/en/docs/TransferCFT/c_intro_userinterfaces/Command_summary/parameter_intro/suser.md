{
    "title": "suser",
    "linkTitle": "suser",
    "weight": "3410"
}<span id="suser"></span>

### suser

<span id="suser_CFTSEND"></span>

#### CFTRECV, CFTSEND, SEND, RECV, DISPLAY, LISTCAT

**\[SUSER = *string* 32 \]**

*PeSIT E only*

Identifier for the user who is sending the file.

This parameter value is case sensitive in CFTUTIL commands if you enclose the value in " " quotes.

The server/sender
partner sends and controls this parameter, where:

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p>PeSIT E standard</p>         </td>
         <td><p>In standard PeSIT E, the SUSER parameter is transported
in the PI 03, and its length is limited to 8-characters.
Therefore, the PI 03 contains the concatenated value along with the value of the SAPPL
parameter.</p>         </td>
      </tr>
      <tr>
         <td><p><strong><br />
</strong>PeSIT E CFT/CFT</p>         </td>
         <td><p>In PeSIT E between 2 <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span>s, the SUSER parameter value is transported in the PI 99 if this value is longer than 8 characters.</p>         </td>
      </tr>
   </tbody>
</table>

> **Note:**
>
> You can use the RUSER and SUSER fields when performing a catalog search. Additionally these fields are integrated into the catalog index. See RUSER.

See PeSIT extension PI codes for information on PI codes.

[Return to Command index](../../)
