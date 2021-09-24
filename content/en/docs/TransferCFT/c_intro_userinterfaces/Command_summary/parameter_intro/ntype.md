{
    "title": "ntype",
    "linkTitle": "ntype",
    "weight": "2380"
}### <span id="ntype"></span>ntype

#### CFTSEND, SEND

**\[NTYPE = {<u>see comment</u> | c}\]
       ODETTE,
PeSIT D CFT profile, PeSIT E CFT/CFT,  OS**

File type, in protocol terms.

This parameter is used to designate the partner receiver file type.

<table cellspacing="0" width="90%">
   <col/>
   <col/>
      <tr>
         <td width="26%">
            <p><b>PeSIT D CFT profile<br/>PeSIT E CFT/CFT</b>
</p>
         </td>
         <td width="74%">
            <p><i><span>Default 
 value</span></i>
</p>
            <p>If this parameter is not defined, Transfer 
 CFT assigns a default value, as a function of the:</p>
            <ul>
               <li>local 
 file type (FTYPE parameter),               </li>
               <li>operating 
 system of the transfer recipient (SYST parameter of CFTPART).               </li>
            </ul>
            <p>The default values are indicated in <i>NTYPE sent by default</i>.</p>
         </td>
      </tr>
      <tr>
         <td width="26%">
            <p><b>ODETTE</b>
</p>
         </td>
         <td width="74%">
            <p>The specific value NTYPE = T may be used to request the 
 sending of a file in ODETTE text format. Refer to Managing Protocols.</p>
         </td>
      </tr>
</table>

 

[Return to Command index](../../)
