{
    "title": "CFTUTIL commands for z/OS",
    "linkTitle": "CFTUTIL commands for z/OS",
    "weight": "350"
}This section lists the Transfer CFT z/OS CFTUTIL commands, and additional object and class information for:

-   Users with all rights

<!-- -->

-   Users with all rights except for the $CFTOPER class

## User with all rights

<table cellspacing="0">
   <col/>
   <col/>
   <col/>
   <col/>
   <col/>
   <col/>
   <col/>
   <col/>
   <tbody>
      <tr>
         <td>Command         </td>
         <td>Object         </td>
         <td>Class         </td>
         <td>VARS         </td>
         <td>UserID         </td>
         <td>Actions         </td>
         <td>File/ACC         </td>
         <td>Notes         </td>
      </tr>
      <tr>
         <td>
            <p>ABOUT</p>
         </td>
         <td>
            <p> </p>
         </td>
         <td>
            <p> </p>
         </td>
         <td>
            <p> </p>
         </td>
         <td>
            <p> </p>
         </td>
         <td>
            <p> </p>
         </td>
         <td>
            <p> </p>
         </td>
         <td>
            <p>No control</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>PURGE</p>
         </td>
         <td>
            <p> </p>
         </td>
         <td>
            <p> </p>
         </td>
         <td>
            <p> </p>
         </td>
         <td>
            <p> </p>
         </td>
         <td>
            <p> </p>
         </td>
         <td>
            <p>COM(UPDATE)</p>
         </td>
         <td>
            <p>No control</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>COPYFILE</p>
         </td>
         <td>
            <p> </p>
         </td>
         <td>
            <p> </p>
         </td>
         <td>
            <p> </p>
         </td>
         <td>
            <p> </p>
         </td>
         <td>
            <p> </p>
         </td>
         <td>
            <p> </p>
         </td>
         <td>
            <p>No control</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>CFTFILE</p>
         </td>
         <td>
            <p> </p>
         </td>
         <td>
            <p> </p>
         </td>
         <td>
            <p> </p>
         </td>
         <td>
            <p> </p>
            <p>
</p>
         </td>
         <td>
            <p>Cr/De</p>
         </td>
         <td>
            <p>PART(ALTER)</p>
            <p>PARM(ALTER)</p>
            <p>CATLG(ALTER)</p>
            <p>LOG(ALTER)</p>
            <p>COM(ALTER)</p>
         </td>
         <td>
            <p>No control</p>
            <p>
</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>CFTPARM</p>
         </td>
         <td>
            <p>CFTPARM</p>
         </td>
         <td>
            <p>parmcls</p>
         </td>
         <td>
            <p>&amp;ID</p>
         </td>
         <td>
            <p>Cmduser</p>
         </td>
         <td>
            <p>Cr/De/Mo</p>
         </td>
         <td>
            <p>PARM(UPDATE)</p>
         </td>
         <td>
            <p> </p>
         </td>
      </tr>
      <tr>
         <td>
            <p>CFTCOM</p>
         </td>
         <td>
            <p>CFTCOM</p>
         </td>
         <td>
            <p>parmcls</p>
         </td>
         <td>
            <p>&amp;ID</p>
         </td>
         <td>
            <p>Cmduser</p>
         </td>
         <td>
            <p>Cr/De/Mo</p>
         </td>
         <td>
            <p>PARM(UPDATE)</p>
         </td>
         <td>
            <p> </p>
         </td>
      </tr>
      <tr>
         <td>
            <p>CFTCAT</p>
         </td>
         <td>
            <p>CFTCAT</p>
         </td>
         <td>
            <p>parmcls</p>
         </td>
         <td>
            <p>&amp;ID</p>
         </td>
         <td>
            <p>Cmduser</p>
         </td>
         <td>
            <p>Cr/De/Mo</p>
         </td>
         <td>
            <p>PARM(UPDATE)</p>
         </td>
         <td>
            <p> </p>
         </td>
      </tr>
      <tr>
         <td>
            <p>CFTLOG</p>
         </td>
         <td>
            <p>CFTLOG</p>
         </td>
         <td>
            <p>parmcls</p>
         </td>
         <td>
            <p>&amp;ID</p>
         </td>
         <td>
            <p>Cmduser</p>
         </td>
         <td>
            <p>Cr/De/Mo</p>
         </td>
         <td>
            <p>PARM(UPDATE)</p>
         </td>
         <td>
            <p> </p>
         </td>
      </tr>
      <tr>
         <td>
            <p>CFTACCNT</p>
         </td>
         <td>
            <p>CFTACCNT</p>
         </td>
         <td>
            <p>parmcls</p>
         </td>
         <td>
            <p>&amp;ID</p>
         </td>
         <td>
            <p>Cmduser</p>
         </td>
         <td>
            <p>Cr/De/Mo</p>
         </td>
         <td>
            <p>PARM(UPDATE)</p>
         </td>
         <td>
            <p> </p>
         </td>
      </tr>
      <tr>
         <td>
            <p>CFTAPPL</p>
         </td>
         <td>
            <p>CFTAPPL</p>
         </td>
         <td>
            <p>parmcls</p>
         </td>
         <td>
            <p>&amp;ID</p>
         </td>
         <td>
            <p>Cmduser</p>
         </td>
         <td>
            <p>Cr/De/Mo</p>
         </td>
         <td>
            <p>PARM(UPDATE)</p>
         </td>
         <td>
            <p> </p>
         </td>
      </tr>
      <tr>
         <td>
            <p>CFTSEND</p>
         </td>
         <td>
            <p>CFTSEND</p>
         </td>
         <td>
            <p>parmcls</p>
         </td>
         <td>
            <p>&amp;ID</p>
         </td>
         <td>
            <p>Cmduser</p>
         </td>
         <td>
            <p>Cr/De/Mo</p>
         </td>
         <td>
            <p>PARM(UPDATE)</p>
         </td>
         <td>
            <p> </p>
         </td>
      </tr>
      <tr>
         <td>
            <p>CFTSEND IMPL=YES</p>
         </td>
         <td>
            <p>CFTSENDI</p>
         </td>
         <td>
            <p>parmcls</p>
         </td>
         <td>
            <p>&amp;ID</p>
         </td>
         <td>
            <p>Cmduser</p>
         </td>
         <td>
            <p>Cr/De/Mo</p>
         </td>
         <td>
            <p>PARM(UPDATE)</p>
         </td>
         <td>
            <p> </p>
         </td>
      </tr>
      <tr>
         <td>
            <p>CFTRECV</p>
         </td>
         <td>
            <p>CFTRECV</p>
         </td>
         <td>
            <p>parmcls</p>
         </td>
         <td>
            <p>&amp;ID</p>
         </td>
         <td>
            <p>Cmduser</p>
         </td>
         <td>
            <p>Cr/De/Mo</p>
         </td>
         <td>
            <p>PARM(UPDATE)</p>
         </td>
         <td>
            <p> </p>
         </td>
      </tr>
      <tr>
         <td>
            <p>CFTEXIT</p>
         </td>
         <td>
            <p>CFTEXIT</p>
         </td>
         <td>
            <p>parmcls</p>
         </td>
         <td>
            <p>&amp;ID</p>
         </td>
         <td>
            <p>Cmduser</p>
         </td>
         <td>
            <p>Cr/De/Mo</p>
         </td>
         <td>
            <p>PARM(UPDATE)</p>
         </td>
         <td>
            <p> </p>
         </td>
      </tr>
      <tr>
         <td>
            <p>CFTAUTH</p>
         </td>
         <td>
            <p>CFTAUTH</p>
         </td>
         <td>
            <p>parmcls</p>
         </td>
         <td>
            <p>&amp;ID</p>
         </td>
         <td>
            <p>Cmduser</p>
         </td>
         <td>
            <p>Cr/De/Mo</p>
         </td>
         <td>
            <p>PARM(UPDATE)</p>
         </td>
         <td>
            <p> </p>
         </td>
      </tr>
      <tr>
         <td>
            <p>CFTIDF</p>
         </td>
         <td>
            <p>CFTIDF</p>
         </td>
         <td>
            <p>parmcls</p>
         </td>
         <td>
            <p>&amp;ID</p>
         </td>
         <td>
            <p>Cmduser</p>
         </td>
         <td>
            <p>Cr/De/Mo</p>
         </td>
         <td>
            <p>PARM(UPDATE)</p>
         </td>
         <td>
            <p> </p>
         </td>
      </tr>
      <tr>
         <td>
            <p>CFTXLATE</p>
         </td>
         <td>
            <p>CFTXLATE</p>
         </td>
         <td>
            <p>parmcls</p>
         </td>
         <td>
            <p>&amp;ID</p>
         </td>
         <td>
            <p>Cmduser</p>
         </td>
         <td>
            <p>Cr/De/Mo</p>
         </td>
         <td>
            <p>PARM(UPDATE)</p>
         </td>
         <td>
            <p> </p>
         </td>
      </tr>
      <tr>
         <td>
            <p>CFTNET</p>
         </td>
         <td>
            <p>CFTNET</p>
         </td>
         <td>
            <p>parmcls</p>
         </td>
         <td>
            <p>&amp;ID</p>
         </td>
         <td>
            <p>Cmduser</p>
         </td>
         <td>
            <p>Cr/De/Mo</p>
         </td>
         <td>
            <p>PARM(UPDATE)</p>
         </td>
         <td>
            <p> </p>
         </td>
      </tr>
      <tr>
         <td>
            <p>CFTPROT</p>
         </td>
         <td>
            <p>CFTPROT</p>
         </td>
         <td>
            <p>parmcls</p>
         </td>
         <td>
            <p>&amp;ID</p>
         </td>
         <td>
            <p>Cmduser</p>
         </td>
         <td>
            <p>Cr/De/Mo</p>
         </td>
         <td>
            <p>PARM(UPDATE)</p>
         </td>
         <td>
            <p> </p>
         </td>
      </tr>
      <tr>
         <td>
            <p>CFTETB</p>
         </td>
         <td>
            <p>CFTETB</p>
         </td>
         <td>
            <p>parmcls</p>
         </td>
         <td>
            <p>&amp;ID</p>
         </td>
         <td>
            <p>Cmduser</p>
         </td>
         <td>
            <p>Cr/De/Mo</p>
         </td>
         <td>
            <p>PARM(UPDATE)</p>
         </td>
         <td>
            <p> </p>
         </td>
      </tr>
      <tr>
         <td>
            <p>CFTPART</p>
         </td>
         <td>
            <p>CFTPART</p>
         </td>
         <td>
            <p>parmcls</p>
         </td>
         <td>
            <p>&amp;ID</p>
         </td>
         <td>
            <p>Cmduser</p>
         </td>
         <td>
            <p>Cr/De/Mo</p>
         </td>
         <td>
            <p>PART(UPDATE)</p>
         </td>
         <td>
            <p> </p>
         </td>
      </tr>
      <tr>
         <td>
            <p>CFTDEST</p>
         </td>
         <td>
            <p>CFTDEST</p>
         </td>
         <td>
            <p>parmcls</p>
         </td>
         <td>
            <p>&amp;ID</p>
         </td>
         <td>
            <p>Cmduse</p>
         </td>
         <td>
            <p>Cr/De/Mo</p>
         </td>
         <td>
            <p>PART(UPDATE)</p>
         </td>
         <td>
            <p> </p>
         </td>
      </tr>
      <tr>
         <td>
            <p>CFTTCP</p>
         </td>
         <td>
            <p>CFTTCP</p>
         </td>
         <td>
            <p>parmcls</p>
         </td>
         <td>
            <p>&amp;ID</p>
         </td>
         <td>
            <p>Cmduser</p>
         </td>
         <td>
            <p>Cr/De/Mo</p>
         </td>
         <td>
            <p>PART(UPDATE)</p>
         </td>
         <td>
            <p> </p>
         </td>
      </tr>
      <tr>
         <td>
            <p> </p>
         </td>
         <td>
            <p> </p>
         </td>
         <td>
            <p> </p>
         </td>
         <td>
            <p> </p>
         </td>
         <td>
            <p> </p>
         </td>
         <td>
            <p> </p>
         </td>
         <td>
            <p> </p>
         </td>
         <td>
            <p> </p>
         </td>
      </tr>
      <tr>
         <td>
            <p>UCONFGET</p>
         </td>
         <td>
            <p>UCONF</p>
         </td>
         <td>
            <p> </p>
         </td>
         <td>
            <p>&amp;ID</p>
         </td>
         <td>
            <p>Cmduser</p>
         </td>
         <td>
            <p>Read</p>
         </td>
         <td>
            <p>UCONF(READ)</p>
         </td>
         <td>
            <p> </p>
         </td>
      </tr>
      <tr>
         <td>
            <p>UCONFSUBST</p>
         </td>
         <td>
            <p>UCONF</p>
         </td>
         <td>
            <p> </p>
         </td>
         <td>
            <p>&amp;ID</p>
         </td>
         <td>
            <p>Cmduser</p>
         </td>
         <td>
            <p>Read</p>
         </td>
         <td>
            <p>UCONF(READ)</p>
         </td>
         <td>
            <p> </p>
         </td>
      </tr>
      <tr>
         <td>
            <p>LISTCUCONF</p>
         </td>
         <td>
            <p>UCONF</p>
         </td>
         <td>
            <p> </p>
         </td>
         <td>
            <p>&amp;ID</p>
         </td>
         <td>
            <p>Cmduser</p>
         </td>
         <td>
            <p>Read</p>
         </td>
         <td>
            <p>UCONF(UPDATE)</p>
         </td>
         <td>
            <p> </p>
         </td>
      </tr>
      <tr>
         <td>
            <p>UCONFSET</p>
         </td>
         <td>
            <p>UCONF</p>
         </td>
         <td>
            <p> </p>
         </td>
         <td>
            <p>&amp;ID</p>
         </td>
         <td>
            <p>Cmduser</p>
         </td>
         <td>
            <p>Modify</p>
         </td>
         <td>
            <p>UCONF(UPDATE)</p>
         </td>
         <td>
            <p> </p>
         </td>
      </tr>
      <tr>
         <td>
            <p>UCONFUNSET</p>
         </td>
         <td>
            <p>UCONF</p>
         </td>
         <td>
            <p> </p>
         </td>
         <td>
            <p>&amp;ID</p>
         </td>
         <td>
            <p>Cmduser</p>
         </td>
         <td>
            <p>Delete</p>
         </td>
         <td>
            <p>UCONF(UPDATE)</p>
         </td>
         <td>
            <p> </p>
         </td>
      </tr>
      <tr>
         <td>
            <p> </p>
         </td>
         <td>
            <p> </p>
         </td>
         <td>
            <p> </p>
         </td>
         <td>
            <p> </p>
         </td>
         <td>
            <p> </p>
         </td>
         <td>
            <p> </p>
         </td>
         <td>
            <p> </p>
         </td>
         <td>
            <p> </p>
         </td>
      </tr>
      <tr>
         <td rowspan="2">
            <p>CFTEXT</p>
            <p>
</p>
         </td>
         <td>
            <p>ALL_PARM</p>
         </td>
         <td>
            <p>opercls</p>
         </td>
         <td>
            <p>&amp;FNAME</p>
         </td>
         <td>
            <p>Cmduser</p>
         </td>
         <td>
            <p>Read</p>
         </td>
         <td>
            <p>PARM(READ)</p>
         </td>
         <td>
            <p> </p>
         </td>
      </tr>
      <tr>
         <td>
            <p>ALL_PART</p>
         </td>
         <td>
            <p>opercls</p>
         </td>
         <td>
            <p>&amp;FNAME</p>
         </td>
         <td>
            <p>Cmduser</p>
         </td>
         <td>
            <p>Read</p>
         </td>
         <td>
            <p>PART(READ)</p>
         </td>
         <td>
            <p> </p>
         </td>
      </tr>
      <tr>
         <td>
            <p>LISTCAT</p>
         </td>
         <td>
            <p>ALL_CAT</p>
         </td>
         <td>
            <p>opercls</p>
         </td>
         <td>
            <p>&amp;FNAME</p>
         </td>
         <td>
            <p>Cmduser</p>
         </td>
         <td>
            <p>Read</p>
         </td>
         <td>
            <p>CATLG(READ)</p>
         </td>
         <td>
            <p> </p>
         </td>
      </tr>
      <tr>
         <td>
            <p>LISTPARM</p>
         </td>
         <td>
            <p>ALL_PARM</p>
         </td>
         <td>
            <p>opercls</p>
         </td>
         <td>
            <p>&amp;FNAME</p>
         </td>
         <td>
            <p>Cmduser</p>
         </td>
         <td>
            <p>Read</p>
         </td>
         <td>
            <p>PARM(READ)</p>
         </td>
         <td>
            <p> </p>
         </td>
      </tr>
      <tr>
         <td>
            <p>LISTPART</p>
         </td>
         <td>
            <p>ALL_PART</p>
         </td>
         <td>
            <p>opercls</p>
         </td>
         <td>
            <p>&amp;FNAME</p>
         </td>
         <td>
            <p>Cmduser</p>
         </td>
         <td>
            <p>Read</p>
         </td>
         <td>
            <p>PART(READ)</p>
         </td>
         <td>
            <p> </p>
         </td>
      </tr>
      <tr>
         <td>
            <p>LISTCOM</p>
         </td>
         <td>
            <p>ALL_COM</p>
         </td>
         <td>
            <p>opercls</p>
         </td>
         <td>
            <p>&amp;FNAME</p>
         </td>
         <td>
            <p>Cmduser</p>
         </td>
         <td>
            <p>Read</p>
         </td>
         <td>
            <p>COM(READ)</p>
         </td>
         <td>
            <p> </p>
         </td>
      </tr>
      <tr>
         <td>
            <p> </p>
         </td>
         <td>
            <p> </p>
         </td>
         <td>
            <p> </p>
         </td>
         <td>
            <p> </p>
         </td>
         <td>
            <p> </p>
         </td>
         <td>
            <p> </p>
         </td>
         <td>
            <p> </p>
         </td>
         <td>
            <p> </p>
         </td>
      </tr>
      <tr>
         <td rowspan="3">
            <p>ACT</p>
         </td>
         <td>
            <p>ACT</p>
         </td>
         <td>
            <p>cmdecls</p>
         </td>
         <td>
            <p> </p>
         </td>
         <td>
            <p>Cmduser</p>
         </td>
         <td>
            <p>Create</p>
         </td>
         <td rowspan="3">
            <p>PART(UPDATE)</p>
         </td>
         <td rowspan="3">
            <p> </p>
         </td>
      </tr>
      <tr>
         <td>
            <p>ALL_PART</p>
         </td>
         <td>
            <p>opercls</p>
         </td>
         <td>
            <p>&amp;FNAME</p>
         </td>
         <td>
            <p>Cmduser</p>
         </td>
         <td>
            <p>Read</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>CFTPART</p>
         </td>
         <td>
            <p>parmcls</p>
         </td>
         <td>
            <p>&amp;ID</p>
         </td>
         <td>
            <p>Cmduser</p>
         </td>
         <td>
            <p>Control</p>
         </td>
      </tr>
      <tr>
         <td rowspan="3">
            <p>INACT</p>
            <p> </p>
         </td>
         <td>
            <p>INACT</p>
         </td>
         <td>
            <p>cmdercls</p>
         </td>
         <td>
            <p> </p>
         </td>
         <td>
            <p>Cmduser</p>
         </td>
         <td>
            <p>Create</p>
         </td>
         <td rowspan="3">
            <p>PART(UPDATE)</p>
         </td>
         <td rowspan="3">
            <p> </p>
            <p>
</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>ALL_PART</p>
         </td>
         <td>
            <p>opercls</p>
         </td>
         <td>
            <p>&amp;FNAME</p>
         </td>
         <td>
            <p>Cmduser</p>
         </td>
         <td>
            <p>Read</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>CFTPART</p>
         </td>
         <td>
            <p>parmcls</p>
         </td>
         <td>
            <p>&amp;ID</p>
         </td>
         <td>
            <p>Cmduser</p>
         </td>
         <td>
            <p>Control</p>
         </td>
      </tr>
      <tr>
         <td colspan="8">
            <p> </p>
         </td>
      </tr>
      <tr>
         <td colspan="8">
            <p>Cmduser = System user (TSO) of the user submitting the command.</p>
         </td>
      </tr>
   </tbody>
</table>

## User with all rights except the $CFTOPER class

<table cellspacing="0">
   <col/>
   <col/>
   <col/>
   <col/>
   <col/>
   <col/>
   <col/>
   <col/>
   <tbody>
      <tr>
         <td>Command         </td>
         <td>Object         </td>
         <td>Class         </td>
         <td>VARS         </td>
         <td>UserID         </td>
         <td>Actions         </td>
         <td>File/ACC         </td>
         <td>Notes         </td>
      </tr>
      <tr>
         <td>
            <p>ABOUT</p>
         </td>
         <td>
            <p> </p>
         </td>
         <td>
            <p> </p>
         </td>
         <td>
            <p> </p>
         </td>
         <td>
            <p> </p>
         </td>
         <td>
            <p> </p>
         </td>
         <td>
            <p> </p>
         </td>
         <td>
            <p>No control</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>PURGE</p>
         </td>
         <td>
            <p> </p>
         </td>
         <td>
            <p> </p>
         </td>
         <td>
            <p> </p>
         </td>
         <td>
            <p> </p>
         </td>
         <td>
            <p> </p>
         </td>
         <td>
            <p>COM(UPDATE)</p>
         </td>
         <td>
            <p>No control</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>COPYFILE</p>
         </td>
         <td>
            <p> </p>
         </td>
         <td>
            <p> </p>
         </td>
         <td>
            <p> </p>
         </td>
         <td>
            <p> </p>
         </td>
         <td>
            <p> </p>
         </td>
         <td>
            <p> </p>
         </td>
         <td>
            <p>No control</p>
            <p>
</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>CFTFILE</p>
         </td>
         <td>
            <p> </p>
         </td>
         <td>
            <p> </p>
         </td>
         <td>
            <p> </p>
         </td>
         <td>
            <p> </p>
         </td>
         <td>
            <p>Cr/De</p>
            <p> </p>
         </td>
         <td>
            <p>PART(ALTER)</p>
            <p>PARM(ALTER)</p>
            <p>CATLG(ALTER)</p>
            <p>LOG(ALTER)</p>
            <p>COM(ALTER)</p>
         </td>
         <td>
            <p>No control</p>
            <p>
</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>CFTPARM</p>
         </td>
         <td>
            <p>CFTPARM</p>
         </td>
         <td>
            <p>parmcls</p>
         </td>
         <td>
            <p>&amp;ID</p>
         </td>
         <td>
            <p>Cmduser</p>
         </td>
         <td>
            <p>Cr/De/Mo</p>
         </td>
         <td>
            <p>PARM(UPDATE)</p>
         </td>
         <td>
            <p> </p>
         </td>
      </tr>
      <tr>
         <td>
            <p>CFTCOM</p>
         </td>
         <td>
            <p>CFTCOM</p>
         </td>
         <td>
            <p>parmcls</p>
         </td>
         <td>
            <p>&amp;ID</p>
         </td>
         <td>
            <p>Cmduser</p>
         </td>
         <td>
            <p>Cr/De/Mo</p>
         </td>
         <td>
            <p>PARM(UPDATE)</p>
         </td>
         <td>
            <p> </p>
         </td>
      </tr>
      <tr>
         <td>
            <p>CFTCAT</p>
         </td>
         <td>
            <p>CFTCAT</p>
         </td>
         <td>
            <p>parmcls</p>
         </td>
         <td>
            <p>&amp;ID</p>
         </td>
         <td>
            <p>Cmduser</p>
         </td>
         <td>
            <p>Cr/De/Mo</p>
         </td>
         <td>
            <p>PARM(UPDATE</p>
         </td>
         <td>
            <p> </p>
         </td>
      </tr>
      <tr>
         <td>
            <p>CFTLOG</p>
         </td>
         <td>
            <p>CFTLOG</p>
         </td>
         <td>
            <p>parmcls</p>
         </td>
         <td>
            <p>&amp;ID</p>
         </td>
         <td>
            <p>Cmduser</p>
         </td>
         <td>
            <p>Cr/De/Mo</p>
         </td>
         <td>
            <p>PARM(UPDATE)</p>
         </td>
         <td>
            <p> </p>
         </td>
      </tr>
      <tr>
         <td>
            <p>CFTACCNT</p>
         </td>
         <td>
            <p>CFTACCNT</p>
         </td>
         <td>
            <p>parmcls</p>
         </td>
         <td>
            <p>&amp;ID</p>
         </td>
         <td>
            <p>Cmduser</p>
         </td>
         <td>
            <p>Cr/De/Mo</p>
         </td>
         <td>
            <p>PARM(UPDATE)</p>
         </td>
         <td>
            <p> </p>
         </td>
      </tr>
      <tr>
         <td>
            <p>CFTAPPL</p>
         </td>
         <td>
            <p>CFTAPPL</p>
         </td>
         <td>
            <p>parmcls</p>
         </td>
         <td>
            <p>&amp;ID</p>
         </td>
         <td>
            <p>Cmduser</p>
         </td>
         <td>
            <p>Cr/De/Mo</p>
         </td>
         <td>
            <p>PARM(UPDATE)</p>
         </td>
         <td>
            <p> </p>
         </td>
      </tr>
      <tr>
         <td>
            <p>CFTSEND</p>
         </td>
         <td>
            <p>CFTSEND</p>
         </td>
         <td>
            <p>parmcls</p>
         </td>
         <td>
            <p>&amp;ID</p>
         </td>
         <td>
            <p>Cmduser</p>
         </td>
         <td>
            <p>Cr/De/Mo</p>
         </td>
         <td>
            <p>PARM(UPDATE)</p>
         </td>
         <td>
            <p> </p>
         </td>
      </tr>
      <tr>
         <td>
            <p>CFTSEND IMPL=YES</p>
         </td>
         <td>
            <p>CFTSENDI</p>
         </td>
         <td>
            <p>parmcls</p>
         </td>
         <td>
            <p>&amp;ID</p>
         </td>
         <td>
            <p>Cmduser</p>
         </td>
         <td>
            <p>Cr/De/Mo</p>
         </td>
         <td>
            <p>PARM(UPDATE)</p>
         </td>
         <td>
            <p> </p>
         </td>
      </tr>
      <tr>
         <td>
            <p>CFTRECV</p>
         </td>
         <td>
            <p>CFTRECV</p>
         </td>
         <td>
            <p>parmcls</p>
         </td>
         <td>
            <p>&amp;ID</p>
         </td>
         <td>
            <p>Cmduser</p>
         </td>
         <td>
            <p>Cr/De/Mo</p>
         </td>
         <td>
            <p>PARM(UPDATE)</p>
         </td>
         <td>
            <p> </p>
         </td>
      </tr>
      <tr>
         <td>
            <p>CFTEXIT</p>
         </td>
         <td>
            <p>CFTEXIT</p>
         </td>
         <td>
            <p>parmcls</p>
         </td>
         <td>
            <p>&amp;ID</p>
         </td>
         <td>
            <p>Cmduser</p>
         </td>
         <td>
            <p>Cr/De/Mo</p>
         </td>
         <td>
            <p>PARM(UPDATE)</p>
         </td>
         <td>
            <p> </p>
         </td>
      </tr>
      <tr>
         <td>
            <p>CFTAUTH</p>
         </td>
         <td>
            <p>CFTAUTH</p>
         </td>
         <td>
            <p>parmcls</p>
         </td>
         <td>
            <p>&amp;ID</p>
         </td>
         <td>
            <p>Cmduser</p>
         </td>
         <td>
            <p>Cr/De/Mo</p>
         </td>
         <td>
            <p>PARM(UPDATE)</p>
         </td>
         <td>
            <p> </p>
         </td>
      </tr>
      <tr>
         <td>
            <p>CFTIDF</p>
         </td>
         <td>
            <p>CFTIDF</p>
         </td>
         <td>
            <p>parmcls</p>
         </td>
         <td>
            <p>&amp;ID</p>
         </td>
         <td>
            <p>Cmduser</p>
         </td>
         <td>
            <p>Cr/De/Mo</p>
         </td>
         <td>
            <p>PARM(UPDATE)</p>
         </td>
         <td>
            <p> </p>
         </td>
      </tr>
      <tr>
         <td>
            <p>CFTXLATE</p>
         </td>
         <td>
            <p>CFTXLATE</p>
         </td>
         <td>
            <p>parmcls</p>
         </td>
         <td>
            <p>&amp;ID</p>
         </td>
         <td>
            <p>Cmduser</p>
         </td>
         <td>
            <p>Cr/De/Mo</p>
         </td>
         <td>
            <p>PARM(UPDATE)</p>
         </td>
         <td>
            <p> </p>
         </td>
      </tr>
      <tr>
         <td>
            <p>CFTNET</p>
         </td>
         <td>
            <p>CFTNET</p>
         </td>
         <td>
            <p>parmcls</p>
         </td>
         <td>
            <p>&amp;ID</p>
         </td>
         <td>
            <p>Cmduser</p>
         </td>
         <td>
            <p>Cr/De/Mo</p>
         </td>
         <td>
            <p>PARM(UPDATE)</p>
         </td>
         <td>
            <p> </p>
         </td>
      </tr>
      <tr>
         <td>
            <p>CFTPROT</p>
         </td>
         <td>
            <p>CFTPROT</p>
         </td>
         <td>
            <p>parmcls</p>
         </td>
         <td>
            <p>&amp;ID</p>
         </td>
         <td>
            <p>Cmduser</p>
         </td>
         <td>
            <p>Cr/De/Mo</p>
         </td>
         <td>
            <p>PARM(UPDATE)</p>
         </td>
         <td>
            <p> </p>
         </td>
      </tr>
      <tr>
         <td>
            <p>CFTETB</p>
         </td>
         <td>
            <p>CFTETB</p>
         </td>
         <td>
            <p>parmcls</p>
         </td>
         <td>
            <p>&amp;ID</p>
         </td>
         <td>
            <p>Cmduser</p>
         </td>
         <td>
            <p>Cr/De/Mo</p>
         </td>
         <td>
            <p>PARM(UPDATE)</p>
         </td>
         <td>
            <p> </p>
         </td>
      </tr>
      <tr>
         <td>
            <p>CFTPART</p>
         </td>
         <td>
            <p>CFTPART</p>
         </td>
         <td>
            <p>parmcls</p>
         </td>
         <td>
            <p>&amp;ID</p>
         </td>
         <td>
            <p>Cmduser</p>
         </td>
         <td>
            <p>Cr/De/Mo</p>
         </td>
         <td>
            <p>PART(UPDATE)</p>
         </td>
         <td>
            <p> </p>
         </td>
      </tr>
      <tr>
         <td>
            <p>CFTDEST</p>
         </td>
         <td>
            <p>CFTDEST</p>
         </td>
         <td>
            <p>parmcls</p>
         </td>
         <td>
            <p>&amp;ID</p>
         </td>
         <td>
            <p>Cmduser</p>
         </td>
         <td>
            <p>Cr/De/Mo</p>
         </td>
         <td>
            <p>PART(UPDATE)</p>
         </td>
         <td>
            <p> </p>
         </td>
      </tr>
      <tr>
         <td>
            <p>CFTTCP</p>
         </td>
         <td>
            <p>CFTTCP</p>
         </td>
         <td>
            <p>parmcls</p>
         </td>
         <td>
            <p>&amp;ID</p>
         </td>
         <td>
            <p>Cmduser</p>
         </td>
         <td>
            <p>Cr/De/Mo</p>
         </td>
         <td>
            <p>PART(UPDATE)</p>
         </td>
         <td>
            <p> </p>
         </td>
      </tr>
      <tr>
         <td rowspan="2">
            <p>CFTEXT</p>
            <p>
</p>
         </td>
         <td>
            <p>CFTxxx*</p>
         </td>
         <td>
            <p>parmcls</p>
         </td>
         <td>
            <p>&amp;ID</p>
         </td>
         <td>
            <p>Cmduser</p>
         </td>
         <td>
            <p>Read</p>
         </td>
         <td>
            <p>PARM(READ)</p>
         </td>
         <td>
            <p>
</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>CFTyyy*</p>
         </td>
         <td>
            <p>parmcls</p>
         </td>
         <td>
            <p>&amp;ID</p>
         </td>
         <td>
            <p>Cmduser</p>
         </td>
         <td>
            <p>Read</p>
         </td>
         <td>
            <p>PART(READ)</p>
         </td>
         <td>
            <p>
</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>LISTPARM</p>
         </td>
         <td>
            <p>CFTxxx*</p>
         </td>
         <td>
            <p>parmcls</p>
         </td>
         <td>
            <p>&amp;ID</p>
         </td>
         <td>
            <p>Cmduser</p>
         </td>
         <td>
            <p>Read</p>
         </td>
         <td>
            <p>PARM(READ)</p>
         </td>
         <td>
            <p> </p>
         </td>
      </tr>
      <tr>
         <td>
            <p>LISTPART</p>
         </td>
         <td>
            <p>CFTyyy*</p>
         </td>
         <td>
            <p>parmcls</p>
         </td>
         <td>
            <p>&amp;ID</p>
         </td>
         <td>
            <p>Cmduser</p>
         </td>
         <td>
            <p>Read</p>
         </td>
         <td>
            <p>PART(READ)</p>
         </td>
         <td>
            <p> </p>
         </td>
      </tr>
      <tr>
         <td>
            <p>LISTCAT</p>
         </td>
         <td>
            <p>APPL</p>
         </td>
         <td>
            <p>applcls</p>
         </td>
         <td>
            <p>&amp;ID</p>
         </td>
         <td>
            <p>Cmduser</p>
         </td>
         <td>
            <p>Read</p>
         </td>
         <td>
            <p>CATLG(READ)</p>
         </td>
         <td>
            <p> </p>
         </td>
      </tr>
      <tr>
         <td>
            <p>LISTCOM</p>
         </td>
         <td>
            <p> </p>
         </td>
         <td>
            <p> </p>
         </td>
         <td>
            <p> </p>
         </td>
         <td>
            <p> </p>
         </td>
         <td>
            <p> </p>
         </td>
         <td>
            <p> </p>
         </td>
         <td>
            <p>Access denied</p>
         </td>
      </tr>
      <tr>
         <td rowspan="3">
            <p>ACT</p>
            <p> </p>
            <p>
</p>
         </td>
         <td>
            <p>ACT</p>
         </td>
         <td>
            <p>cmdecls</p>
         </td>
         <td>
            <p> </p>
         </td>
         <td>
            <p>Cmduser</p>
         </td>
         <td>
            <p>Create</p>
         </td>
         <td rowspan="3">
            <p>PART(UPDATE)</p>
            <p>
</p>
         </td>
         <td rowspan="3">
            <p> </p>
         </td>
      </tr>
      <tr>
         <td>
            <p>CFTPART</p>
         </td>
         <td>
            <p>parmcls</p>
         </td>
         <td>
            <p>&amp;ID</p>
         </td>
         <td>
            <p>Cmduser</p>
         </td>
         <td>
            <p>Read</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>CFTPART</p>
         </td>
         <td>
            <p>parmcls</p>
         </td>
         <td>
            <p>&amp;ID</p>
         </td>
         <td>
            <p>Cmduser</p>
         </td>
         <td>
            <p>Control</p>
         </td>
      </tr>
      <tr>
         <td rowspan="3">
            <p>INACT</p>
            <p> </p>
            <p>
</p>
         </td>
         <td>
            <p>INACT</p>
         </td>
         <td>
            <p>cmdecls</p>
         </td>
         <td>
            <p> </p>
         </td>
         <td>
            <p>Cmduser</p>
         </td>
         <td>
            <p>Create</p>
         </td>
         <td rowspan="3">
            <p>PART(UPDATE)</p>
            <p>
</p>
         </td>
         <td rowspan="3">
            <p> </p>
            <p>
</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>CFTPART</p>
         </td>
         <td>
            <p>parmcls</p>
         </td>
         <td>
            <p>&amp;ID</p>
         </td>
         <td>
            <p>Cmduser</p>
         </td>
         <td>
            <p>Read</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>CFTPART</p>
         </td>
         <td>
            <p>parmcls</p>
         </td>
         <td>
            <p>&amp;ID</p>
         </td>
         <td>
            <p>Cmduser</p>
         </td>
         <td>
            <p>Control</p>
         </td>
      </tr>
      <tr>
         <td colspan="8">
            <p> </p>
         </td>
      </tr>
      <tr>
         <td colspan="8">
            <p>CFTxxx* = PARM file configuration commands.</p>
         </td>
      </tr>
      <tr>
         <td colspan="8">
            <p>CFTyyy* = PART file configuration commands.</p>
         </td>
      </tr>
   </tbody>
</table>
