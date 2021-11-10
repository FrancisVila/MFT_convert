{
    "title": "CFTUTIL predefined variables",
    "linkTitle": "CFTUTIL predefined variables",
    "weight": "280"
}A number of variables are predefined in CFTUTIL for the catalog fields. These variables can be used in all of the batch programming commands.

Each variable begins with the underscore character \_. For example, to display the IDTU value of a transfer, specify:


    PRINT MSG='Transfer IDTU value: %_CAT_IDTU%'

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Variable         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>_CAT_CFTV         </td>
         <td>Catalog version.         </td>
      </tr>
      <tr>
         <td>_CAT_COMMENT         </td>
         <td>Comment associated with the IDF.         </td>
      </tr>
      <tr>
         <td>_CAT_DATEB         </td>
         <td>Transfer start date.         </td>
      </tr>
      <tr>
         <td>_CAT_DATEC         </td>
         <td>IDF cycledate value.         </td>
      </tr>
      <tr>
         <td>_CAT_DATED         </td>
         <td>Transfer filing date.         </td>
      </tr>
      <tr>
         <td>_CAT_DATED         </td>
         <td>End of transfer date.         </td>
      </tr>
      <tr>
         <td>_CAT_DATEK         </td>
         <td>Date of last writing.         </td>
      </tr>
      <tr>
         <td>_CAT_DATEM         </td>
         <td>Value of the IDF MINDATE parameter.         </td>
      </tr>
      <tr>
         <td>_CAT_DATEMAX         </td>
         <td>Value of the IDF MAXDATE parameter.         </td>
      </tr>
      <tr>
         <td>_CAT_DEST         </td>
         <td>CFTDEST command identifier.         </td>
      </tr>
      <tr>
         <td>_CAT_DIAGC         </td>
         <td>Additional diagnostic value.         </td>
      </tr>
      <tr>
         <td>_CAT_DIAGI         </td>
         <td>Internal diagnostic value.         </td>
      </tr>
      <tr>
         <td>_CAT_DIAGP         </td>
         <td><p>Diagnostic protocol value.</p>         </td>
      </tr>
      <tr>
         <td>_CAT_DIFTYP         </td>
         <td><p>Broadcast type:</p>
<ul>
<li>L for broadcasting to
multiple partners.</li>
<li>N for sending to a single partner.</li>
</ul>         </td>
      </tr>
      <tr>
         <td>_CAT_DIRECT         </td>
         <td>Transfer direction.         </td>
      </tr>
      <tr>
         <td>_CAT_EXEC         </td>
         <td>IDF procedure name.         </td>
      </tr>
      <tr>
         <td>_CAT_FACTION         </td>
         <td>FACTION parameter value.         </td>
      </tr>
      <tr>
         <td>_CAT_FCOMP         </td>
         <td>FCOMP parameter value.         </td>
      </tr>
      <tr>
         <td>_CAT_FDISP         </td>
         <td>FDISP parameter value.         </td>
      </tr>
      <tr>
         <td>_CAT_FILTYP         </td>
         <td><p>File type:</p>
<ul>
<li>L for file list.</li>
<li>N for normal file.</li>
</ul>         </td>
      </tr>
      <tr>
         <td>_CAT_FLAG         </td>
         <td>Indicates if the transfer mode is REQUESTER or SERVER.         </td>
      </tr>
      <tr>
         <td>_CAT_FNAME         </td>
         <td>Name of file to be transferred.         </td>
      </tr>
      <tr>
         <td>_CAT_FTNAME         </td>
         <td>Temporary file name.         </td>
      </tr>
      <tr>
         <td>_CAT_GROUP         </td>
         <td>Name of the group initiating the request.         </td>
      </tr>
      <tr>
         <td>_CAT_GROUPID         </td>
         <td>Name of the group that the transfer owner belongs to.         </td>
      </tr>
      <tr>
         <td>_CAT_IDA         </td>
         <td>Application identifier.         </td>
      </tr>
      <tr>
         <td>_CAT_IDEXIT         </td>
         <td>CFTEXIT command file type identifier.         </td>
      </tr>
      <tr>
         <td>_CAT_IDEXITA         </td>
         <td>CFTEXIT command directory type identifier.         </td>
      </tr>
      <tr>
         <td>_CAT_IDEXITE         </td>
         <td>CFTEXIT command ETEBAC3 type identifier.         </td>
      </tr>
      <tr>
         <td>_CAT_IDF         </td>
         <td>Identifier associated with the IDF.         </td>
      </tr>
      <tr>
         <td>_CAT_IDR         </td>
         <td>IDR value.         </td>
      </tr>
      <tr>
         <td>_CAT_IDT         </td>
         <td>PROTC value.         </td>
      </tr>
      <tr>
         <td>_CAT_IDTD         </td>
         <td>IDT value.         </td>
      </tr>
      <tr>
         <td>_CAT_IDTU         </td>
         <td>IDTU value.         </td>
      </tr>
      <tr>
         <td>_CAT_IPART         </td>
         <td>Channel partner value.         </td>
      </tr>
      <tr>
         <td>_CAT_JOBNAME         </td>
         <td>Name of the task for which the transfer was created.         </td>
      </tr>
      <tr>
         <td>_CAT_NCOMP         </td>
         <td>Network compression value.         </td>
      </tr>
      <tr>
         <td>_CAT_NFNAME         </td>
         <td>Network filename.         </td>
      </tr>
      <tr>
         <td>_CAT_NIDF         </td>
         <td>Network IDF value.         </td>
      </tr>
      <tr>
         <td>_CAT_NPART         </td>
         <td>Connection partner value.         </td>
      </tr>
      <tr>
         <td>_CAT_ORIGIN         </td>
         <td>Origin of owner of the transfer.         </td>
      </tr>
      <tr>
         <td>_CAT_PARM         </td>
         <td>PARM parameter value.         </td>
      </tr>
      <tr>
         <td>_CAT_PART         </td>
         <td>PART value.         </td>
      </tr>
      <tr>
         <td>_CAT_PIDF         </td>
         <td>The previous value of the file ID.         </td>
      </tr>
      <tr>
         <td>_CAT_PRI         </td>
         <td>Transfer priority.         </td>
      </tr>
      <tr>
         <td>_CAT_PROT         </td>
         <td>Associated CFTPROT identifier.         </td>
      </tr>
      <tr>
         <td>_CAT_PROTC         </td>
         <td>PROTC value.         </td>
      </tr>
      <tr>
         <td>_CAT_RAPPL         </td>
         <td>RAPPL parameter value.         </td>
      </tr>
      <tr>
         <td>_CAT_RELANCE         </td>
         <td>Indicates if there was a restart or not.         </td>
      </tr>
      <tr>
         <td>_CAT_REQGROUP         </td>
         <td>Value of the initiator group for the command.         </td>
      </tr>
      <tr>
         <td>_CAT_REQUSER         </td>
         <td>Value of the user initiating the command.         </td>
      </tr>
      <tr>
         <td>_CAT_RPART         </td>
         <td>File receiving partner.         </td>
      </tr>
      <tr>
         <td>_CAT_RUSER         </td>
         <td>RUSER parameter value.         </td>
      </tr>
      <tr>
         <td>_CAT_SAPPL         </td>
         <td>SAPPL parameter value.         </td>
      </tr>
      <tr>
         <td>_CAT_SGD         </td>
         <td>Date         </td>
      </tr>
      <tr>
         <td>_CAT_SGT         </td>
         <td>Time         </td>
      </tr>
      <tr>
         <td>_CAT_SPART         </td>
         <td>SPART parameter value.         </td>
      </tr>
      <tr>
         <td>_CAT_STATE         </td>
         <td>State of the local transfer.         </td>
      </tr>
      <tr>
         <td>_CAT_STATED         </td>
         <td>State of the remote transfer.         </td>
      </tr>
      <tr>
         <td>_CAT_SUSER         </td>
         <td>SUSER parameter value.         </td>
      </tr>
      <tr>
         <td>_CAT_TCYCLE         </td>
         <td>TCYCLE parameter value.         </td>
      </tr>
      <tr>
         <td>_CAT_TIMEB         </td>
         <td>Transfer start time.         </td>
      </tr>
      <tr>
         <td>_CAT_TIMEC         </td>
         <td>TCYCLE parameter value.<span style="color: #ff0000;"> </span>         </td>
      </tr>
      <tr>
         <td>_CAT_TIMED         </td>
         <td>Creation time of the transfer.         </td>
      </tr>
      <tr>
         <td>_CAT_TIMEE         </td>
         <td>Transfer end time.         </td>
      </tr>
      <tr>
         <td>_CAT_TIMEK         </td>
         <td>Time of last writing.         </td>
      </tr>
      <tr>
         <td>_CAT_TIMEM         </td>
         <td>MINTIME parameter value.         </td>
      </tr>
      <tr>
         <td>_CAT_TIMEMAX         </td>
         <td>MAXTIME parameter value.         </td>
      </tr>
      <tr>
         <td>_CAT_TIMMAXC         </td>
         <td>Maximum time for a call.         </td>
      </tr>
      <tr>
         <td>_CAT_TIMMC         </td>
         <td>Minimum time for a call.         </td>
      </tr>
      <tr>
         <td>_CAT_TYP         </td>
         <td>Transfer type.         </td>
      </tr>
      <tr>
         <td>_CAT_USERID         </td>
         <td>Transfer owner.         </td>
      </tr>
      <tr>
         <td>_CAT_XLATE         </td>
         <td>Associated CFTXLATE identifier card.         </td>
      </tr>
      <tr>
         <td>_CAT_FDBNAME         </td>
         <td>VFM name used for transfer.         </td>
      </tr>
   </tbody>
</table>
