{
    "title": "End-of-transfer exit example",
    "linkTitle": "End-of-transfer exit example",
    "weight": "400"
}# <span id="End_of_transfer_exit_examples"></span>End-of-transfer exit example

This page introduces the following end-of-transfer elements, Parameter
settings, Structure
in C language, User
program in C.

Parameter settings

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>/* CFTPARM Card */<br/><br/>cftparm id = idparm0          ,<br/>        
 exiteot = exe1          ,<br/>.....<br/>.....<br/>         </td>
      </tr>
   </tbody>
</table>

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>/* CFTEXIT Card */<br/><br/>cftexit id = exe1          ,<br/>     language = c          ,<br/>     type = exec          ,<br/>     prog = cftexie         ,<br/>     parm = exe1          ,<br/>     mode = replace</p>
<br/>
         </td>
      </tr>
   </tbody>
</table>

Structure in C

Refer to the exeus.h
delivered with the Transfer CFT product samples.

User program in C

Refer to the exexmp1.c
delivered with the Transfer CFT product samples.
