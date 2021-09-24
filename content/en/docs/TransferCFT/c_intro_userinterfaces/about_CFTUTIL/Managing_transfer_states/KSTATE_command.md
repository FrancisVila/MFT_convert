{
    "title": "KSTATE - Suspending a catalog transfer",
    "linkTitle": "KSTATE - Suspending a catalog transfer",
    "weight": "350"
}The KSTATE
command is used to suspend a transfer in the catalog when the Transfer CFT is offline. Transfer CFT must
be shut down before the command is run and then restarted. The transfer
must exist in the catalog and be in one of the following phasesteps: in process
C, available D,
or hold H. After execution of
the command, the phasestep is set to K.

The command generates a WLOG command which reports the event in the
LOG file.

<table cellspacing="0" width="90%">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Parameter</th>
         <th>Description</th>
      </tr>
   </thead>
   <tbody>
      <tr valign="top">
         <td width="20.241%">
            <p><a href="../../../command_summary/parameter_intro/idf">IDF</a>
</p>
         </td>
         <td width="59.777%">
            <p>Model file identifier.</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1" width="20.241%">
            <p><a href="../../../command_summary/parameter_intro/idtu">IDTU</a>
</p>
         </td>
         <td colspan="1" rowspan="1" width="59.777%">
            <p>Local transfer counter identifier.</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1" width="20.241%">
            <p><a href="../../../command_summary/parameter_intro/part">PART</a>
</p>
            <p>(Mandatory)</p>
         </td>
         <td colspan="1" rowspan="1" width="59.777%">
            <p>Identifier of the partner.</p>
         </td>
      </tr>
   </tbody>
</table>
