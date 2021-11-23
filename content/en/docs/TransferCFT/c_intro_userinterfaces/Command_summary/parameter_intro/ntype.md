{
    "title": "ntype",
    "linkTitle": "ntype",
    "weight": "2350"
}<span id="ntype"></span>

### ntype

#### CFTSEND, SEND

**\[NTYPE = {<u>see comment</u> | c}\]
       ODETTE,
PeSIT D CFT profile, PeSIT E CFT/CFT,  OS**

File type, in protocol terms.

This parameter is used to designate the partner receiver file type.

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>PeSIT D CFT profile<br />
PeSIT E CFT/CFT</strong></p>         </td>
         <td><p><em></em></p>
<p>If this parameter is not defined, Transfer
CFT assigns a default value, as a function of the:</p>
<ul>
<li>local
file type (FTYPE parameter),</li>
<li>operating
system of the transfer recipient (SYST parameter of CFTPART).</li>
</ul>
<p>The default values are indicated in <em>NTYPE sent by default</em>.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>ODETTE</strong></p>         </td>
         <td><p>The specific value NTYPE = T may be used to request the
sending of a file in ODETTE text format. Refer to Managing Protocols.</p>         </td>
      </tr>
   </tbody>
</table>

 

[Return to Command index](../../)
