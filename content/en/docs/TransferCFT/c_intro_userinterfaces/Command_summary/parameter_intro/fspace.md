{
    "title": "fspace",
    "linkTitle": "fspace",
    "weight": "1350"
}<span id="fspace"></span>

### fspace

<span id="fspace_CFTRECV"></span>

#### CFTRECV, RECV

**\[FSPACE = {** **0**
**| n } \]**

Size of the receiver file, in Kbytes
(1 Kbyte = 1024 bytes).

This size usually corresponds to the primary allocation.

<table>
   <tbody>
      <tr>
         <td><p>UNIX</p>         </td>
         <td><p>Parameter not applicable</p>         </td>
      </tr>
   </tbody>
</table>

<span id="fspace_CFTSEND"></span>

#### CFTSEND, SEND

**\[FSPACE = { <span style="text-decoration: underline;">0</span>
| n } \]**

Size of the file to be sent, in Kbytes (1 Kbyte = 1024 bytes).

This parameter does not usually need to be defined, since at each transfer
CFT automatically retrieves the size of the file it is going to send (if
necessary, check in the *Operations Guide* that this facility is
supported by the system in question).

<span id="fspace_CFTFILE"></span>

#### CFTFILE

\[FSPACE
= {see [table](#FSPACE_Table) | n}\]

{0..65536}

According to TYPE/**OS**

Primary allocation of the file to be created, expressed in Kbytes (1024).

For TYPE = COM and TYPE = CAT, this parameter should not be defined
for any system. The primary allocation of the file to be created is deduced
from the value of the RECNB parameter (number of records in the file).

The table below indicates, for each system, the default value supported
according to the type of file to be created. In this table, the FSPACE
parameter does not need to be defined when the default value of the primary
allocation of the file to be created is "no".

<table>
   <thead>
      <tr>
<th colspan="7" class="HeadD-Column1-Header1"><span id="FSPACE_Table"></span>FSPACE         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>OS </p>         </td>
         <td><p>PARM </p>         </td>
         <td><p>PART </p>         </td>
         <td><p>CAT </p>         </td>
         <td><p>COM </p>         </td>
         <td><p>LOG </p>         </td>
         <td><p>ACCNT </p>         </td>
      </tr>
      <tr>
         <td><p>MVS (z/OS)</p>         </td>
         <td><p>50 </p>         </td>
         <td><p>100 </p>         </td>
         <td><p>no </p>         </td>
         <td><p>no </p>         </td>
         <td><p>200 </p>         </td>
         <td><p>200 </p>         </td>
      </tr>
      <tr>
         <td><p>IBM i (OS400) </p>         </td>
         <td><p>512 </p>         </td>
         <td><p>512 </p>         </td>
         <td><p>no </p>         </td>
         <td><p>no </p>         </td>
         <td><p>512 </p>         </td>
         <td><p>512 </p>         </td>
      </tr>
      <tr>
         <td><p>UNIX </p>         </td>
         <td><p>no </p>         </td>
         <td><p>no </p>         </td>
         <td><p>no </p>         </td>
         <td><p>no </p>         </td>
         <td><p>no </p>         </td>
         <td><p>no </p>         </td>
      </tr>
      <tr>
         <td><p>Windows</p>         </td>
         <td><p>no </p>         </td>
         <td><p>no </p>         </td>
         <td><p>no </p>         </td>
         <td><p>no </p>         </td>
         <td><p>no </p>         </td>
         <td><p>no </p>         </td>
      </tr>
   </tbody>
</table>

[Return to Command index](../../)
