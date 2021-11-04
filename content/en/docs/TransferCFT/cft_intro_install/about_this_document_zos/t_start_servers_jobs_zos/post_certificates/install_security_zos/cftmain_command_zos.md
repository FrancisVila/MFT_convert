{
    "title": "CFTMAIN controlled commands",
    "linkTitle": "CFTMAIN controlled commands",
    "weight": "360"
}This section lists the Transfer CFT z/OS CFTUTIL commands, and additional object and class information for:

-   Users with all rights except for the ALL\_CAT object

<!-- -->

-   Users with all rights to the ALL\_CAT object

<!-- -->

-   Users with all rights

## User with all right except for the ALL\_CAT object

FILE(ACCESS): PARM(READ), PART(READ), COM(UPD), CATLG(UPD), LOG(UPD).

<table>
   <tbody>
      <tr>
         <td>Command         </td>
         <td>Object         </td>
         <td>Class         </td>
         <td>Variable         </td>
         <td>UserID         </td>
         <td>Action         </td>
      </tr>
      <tr>
         <td><p>START</p>         </td>
         <td><p>APPL</p>         </td>
         <td><p>applcls</p>         </td>
         <td><p>&amp;ID</p>         </td>
         <td><p>Cmduser</p>         </td>
         <td><p>Control</p>         </td>
      </tr>
      <tr>
         <td><p>HALT</p>         </td>
         <td><p>APPL</p>         </td>
         <td><p>applcls</p>         </td>
         <td><p>&amp;ID</p>         </td>
         <td><p>Cmduser</p>         </td>
         <td><p>Control</p>         </td>
      </tr>
      <tr>
         <td><p>KEEP</p>         </td>
         <td><p>APPL</p>         </td>
         <td><p>applcls</p>         </td>
         <td><p>&amp;ID</p>         </td>
         <td><p>Cmduser</p>         </td>
         <td><p>Control</p>         </td>
      </tr>
      <tr>
         <td><p>END</p>         </td>
         <td><p>APPL</p>         </td>
         <td><p>applcls</p>         </td>
         <td><p>&amp;ID</p>         </td>
         <td><p>Cmduser</p>         </td>
         <td><p>Control</p>         </td>
      </tr>
      <tr>
         <td><p>SUBMIT</p>         </td>
         <td><p>APPL</p>         </td>
         <td><p>applcls</p>         </td>
         <td><p>&amp;ID</p>         </td>
         <td><p>Cmduser</p>         </td>
         <td><p>Control</p>         </td>
      </tr>
      <tr>
         <td><p>DELETE</p>         </td>
         <td><p>APPL</p>         </td>
         <td><p>applcls</p>         </td>
         <td><p>&amp;ID</p>         </td>
         <td><p>Cmduser</p>         </td>
         <td><p>Delete</p>         </td>
      </tr>
   </tbody>
</table>

## User with all rights to the ALL\_CAT object

FILE(ACCESS): PARM(READ), PART(READ), COM(UPD), CATLG(UPD), LOG(UPD).

<table>
   <tbody>
      <tr>
         <td>Command         </td>
         <td>Object         </td>
         <td>Class         </td>
         <td>Variable         </td>
         <td>UserID         </td>
         <td>Action         </td>
      </tr>
      <tr>
         <td><p>START</p>         </td>
         <td><p>ALL_CAT</p>         </td>
         <td><p>opercls</p>         </td>
         <td><p>&amp;FNAME</p>         </td>
         <td><p>Cmduser</p>         </td>
         <td><p>Control</p>         </td>
      </tr>
      <tr>
         <td><p>HALT</p>         </td>
         <td><p>ALL_CAT</p>         </td>
         <td><p>opercls</p>         </td>
         <td><p>&amp;FNAME</p>         </td>
         <td><p>Cmduser</p>         </td>
         <td><p>Control</p>         </td>
      </tr>
      <tr>
         <td><p>KEEP</p>         </td>
         <td><p>ALL_CAT</p>         </td>
         <td><p>opercls</p>         </td>
         <td><p>&amp;FNAME</p>         </td>
         <td><p>Cmduser</p>         </td>
         <td><p>Control</p>         </td>
      </tr>
      <tr>
         <td><p>END</p>         </td>
         <td><p>ALL_CAT</p>         </td>
         <td><p>opercls</p>         </td>
         <td><p>&amp;FNAME</p>         </td>
         <td><p>Cmduser</p>         </td>
         <td><p>Control</p>         </td>
      </tr>
      <tr>
         <td><p>SUBMIT</p>         </td>
         <td><p>ALL_CAT</p>         </td>
         <td><p>opercls</p>         </td>
         <td><p>&amp;FNAME</p>         </td>
         <td><p>Cmduser</p>         </td>
         <td><p>Control</p>         </td>
      </tr>
      <tr>
         <td><p>DELETE</p>         </td>
         <td><p>ALL_CAT</p>         </td>
         <td><p>opercls</p>         </td>
         <td><p>&amp;FNAME</p>         </td>
         <td><p>Cmduser</p>         </td>
         <td><p>Delete</p>         </td>
      </tr>
   </tbody>
</table>

## User with all rights

FILE(ACCESS):PARM(READ), PART(READ), COM(UPD), CATLG(UPD), LOG(UPD).

<table>
   <tbody>
      <tr>
         <td>Command         </td>
         <td>Object         </td>
         <td>Class         </td>
         <td>Variable         </td>
         <td>UserID         </td>
         <td>Action         </td>
         <td>Notes         </td>
      </tr>
      <tr>
         <td><p>SHUT</p>         </td>
         <td><p>SHUT</p>         </td>
         <td><p>cmdecls</p>         </td>
         <td><p> </p>         </td>
         <td><p>Cmduser</p>         </td>
         <td><p>Create</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>MQUERY</p>         </td>
         <td><p>MQUERY</p>         </td>
         <td><p>cmdecls</p>         </td>
         <td><p> </p>         </td>
         <td><p>Cmduser</p>         </td>
         <td><p>Create</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>SWITCH LOG</p>         </td>
         <td><p>SWT_LOG</p>         </td>
         <td><p>cmdecls</p>         </td>
         <td><p> </p>         </td>
         <td><p>Cmduser</p>         </td>
         <td><p>Create</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>SWITCH  ACCOUNT</p>         </td>
         <td><p>SWT_ACNT</p>         </td>
         <td><p>cmdecls</p>         </td>
         <td><p> </p>         </td>
         <td><p>Cmduser</p>         </td>
         <td><p>Create</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>RECV FILE</p>
<p> </p>
<p>(Requester/ receiver)</p>
<p> </p>         </td>
         <td><p>APPL</p>         </td>
         <td><p>applcls</p>         </td>
         <td><p>&amp;ID</p>         </td>
         <td><p>Cmduser</p>         </td>
         <td><p>Create</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>TRANSFER</p>         </td>
         <td><p>xfercls</p>         </td>
         <td><p>&amp;MODE, &amp;PART, &amp;IDF, &amp;SPART,  &amp;RPART,  &amp;IPART</p>         </td>
         <td><p>Appluser</p>         </td>
         <td><p>Create</p>         </td>
         <td><p>In receive mode, the &amp;FNAME variable is ignored.</p>         </td>
      </tr>
      <tr>
         <td><p>File sending</p>
<p> </p>
<p>(Server/sender)</p>         </td>
         <td><p>APPL</p>         </td>
         <td><p>applcls</p>         </td>
         <td><p>&amp;ID</p>         </td>
         <td><p>Cmduser</p>         </td>
         <td><p>Create</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>TRANSFER</p>         </td>
         <td><p>xfercls</p>         </td>
         <td><p>&amp;MODE, &amp;PART, &amp;IDF, &amp;SPART, &amp;RPART, &amp;IPART, &amp;FNAME</p>         </td>
         <td><p>Appluser</p>
<p> </p>         </td>
         <td><p>Create</p>
<p> </p>         </td>
         <td><p>Include PDS and GDG cases (*)</p>         </td>
      </tr>
      <tr>
         <td><p>FILE</p>         </td>
         <td><p>filecls</p>         </td>
         <td><p>&amp;FNAME</p>         </td>
         <td><p>Appluser</p>         </td>
         <td><p>Read</p>
<p> </p>         </td>
         <td><p>Not applicable</p>         </td>
      </tr>
      <tr>
         <td><p>SEND FILE</p>
<p> </p>
<p>(Requester/ sender)</p>         </td>
         <td><p>APPL</p>         </td>
         <td><p>applcls</p>         </td>
         <td><p>&amp;ID</p>         </td>
         <td><p>Cmduser</p>         </td>
         <td><p>Create</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>TRANSFER</p>         </td>
         <td><p>xfercls</p>         </td>
         <td><p>&amp;MODE, &amp;PART, &amp;IDF, &amp;SPART, &amp;RPART, &amp;IPART, &amp;FNAME</p>         </td>
         <td><p>Appluser</p>
<p> </p>         </td>
         <td><p>Create</p>
<p> </p>         </td>
         <td><p>Include PDS and GDG cases (*)</p>         </td>
      </tr>
      <tr>
         <td><p>FILE</p>         </td>
         <td><p>filecls</p>         </td>
         <td><p>&amp;FNAME</p>         </td>
         <td><p>Appluser</p>         </td>
         <td><p>Read</p>         </td>
         <td><p>Not applicable</p>         </td>
      </tr>
      <tr>
         <td><p>File reception</p>
<p>(Server/ receiver)</p>         </td>
         <td><p>TRANSFER</p>         </td>
         <td><p>xfercls</p>         </td>
         <td><p>&amp;MODE, &amp;PART, &amp;IDF, &amp;SPART, &amp;RPART, &amp;IPART</p>         </td>
         <td><p>Appluser</p>         </td>
         <td><p>Create</p>         </td>
         <td><p>In receive mode, the &amp;FNAME variable is ignored.</p>         </td>
      </tr>
      <tr>
         <td><p>SEND MESSAGE</p>
<p>(Requester/ sender)</p>         </td>
         <td><p>APPL</p>         </td>
         <td><p>applcls</p>         </td>
         <td><p>&amp;ID</p>         </td>
         <td><p>Cmduser</p>         </td>
         <td><p>Create</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>MESSAGE</p>         </td>
         <td><p>messcls</p>         </td>
         <td><p>&amp;MODE, &amp;PART, &amp;IDM, &amp;SPART, &amp;RPART</p>         </td>
         <td><p>Appluser</p>         </td>
         <td><p>Create</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>Message reception</p>
<p>(Server/ receiver)</p>         </td>
         <td><p>MESSAGE</p>         </td>
         <td><p>messcls</p>         </td>
         <td><p>&amp;MODE, &amp;PART, &amp;IDM, &amp;SPART, &amp;RPART</p>         </td>
         <td><p>Appluser</p>
<p> </p>         </td>
         <td><p>Create</p>
<p> </p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>SEND REPLY</p>
<p>(Requester/ sender)</p>         </td>
         <td><p>APPL</p>         </td>
         <td><p>applcls</p>         </td>
         <td><p>&amp;ID</p>         </td>
         <td><p>Cmduser</p>
<p> </p>         </td>
         <td><p>Create</p>
<p> </p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>Reply reception</p>
<p>(Server/ receiver)</p>         </td>
         <td><p>APPL</p>         </td>
         <td><p>applcls</p>         </td>
         <td><p>&amp;ID</p>         </td>
         <td><p>Trfuser</p>         </td>
         <td><p>Create</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>(*)  If GDG &amp;FNAME=CFTV2.GDGHAB(0)</p>
<p>     Or         &amp;FNAME=CFTV2.GDGHAB.G0002V00</p>
<p>     If PDS   &amp;FNAME=CFTV2.INSTALL(D40INIT)</p>         </td>
      </tr>
      <tr>
         <td><p>Appluser = System user (TSO) of the user defined by the CFTAPPL command.</p>         </td>
      </tr>
      <tr>
         <td><p>Trfuser = System user (TSO) of the original file transfer owner.</p>         </td>
      </tr>
   </tbody>
</table>
