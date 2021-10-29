{
    "title": "KSTATE - Suspend a transfer when offline",
    "linkTitle": "Suspend a transfer when offline",
    "weight": "400"
}The KSTATE
command is used to suspend a transfer in the catalog when the Transfer CFT is offline. Transfer CFT must
be shut down before the command is run and then restarted. The transfer
must exist in the catalog and be in one of the following phasesteps: in process
C, available D,
or hold H. After execution of
the command, the phasestep is set to K.

The command generates a WLOG command which reports the event in the
LOG file.

<table data-cellspacing="0" width="90%">
   <thead>
      <tr class="header">
         <th>Parameter</th>
         <th>Description</th>
      </tr>
   </thead>
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="20.241%">            <p><a href="../../../c_intro_userinterfaces/command_summary/parameter_intro/idf">IDF</a></p>         </td>
         <td width="59.777%">            <p>Model file identifier.</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20.241%">            <p><a href="../../../c_intro_userinterfaces/command_summary/parameter_intro/idtu">IDTU</a></p>         </td>
         <td width="59.777%">            <p>Local transfer counter identifier.</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="20.241%">            <p><a href="../../../c_intro_userinterfaces/command_summary/parameter_intro/part">PART</a></p>
            <p>(Mandatory)</p>         </td>
         <td width="59.777%">            <p>Identifier of the partner.</p>         </td>
      </tr>
   </tbody>
</table>
