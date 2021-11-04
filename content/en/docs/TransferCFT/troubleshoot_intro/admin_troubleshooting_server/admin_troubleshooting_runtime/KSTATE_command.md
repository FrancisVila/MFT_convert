{
    "title": "KSTATE - Suspend a transfer when offline",
    "linkTitle": "Suspend a transfer when offline",
    "weight": "320"
}The KSTATE
command is used to suspend a transfer in the catalog when the Transfer CFT is offline. <span class="mc-variable axway_variables.Component_Long_Name variable">Transfer CFT</span> must
be shut down before the command is run and then restarted. The transfer
must exist in the catalog and be in one of the following phasesteps: in process
<span style="font-weight: bold;">C</span>, available <span style="font-weight: bold;">D</span>,
or hold <span style="font-weight: bold;">H</span>. After execution of
the command, the phasestep is set to <span style="font-weight: bold;">K</span>.

The command generates a WLOG command which reports the event in the
LOG file.

<table>
         
         
         
   
   <th>
      <tr>
<th>Parameter         </th>
<th>Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p><a href="../../../../c_intro_userinterfaces/command_summary/parameter_intro/idf">IDF</a></p>         </td>
         <td><p>Model file identifier.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="../../../../c_intro_userinterfaces/command_summary/parameter_intro/idtu">IDTU</a></p>         </td>
         <td><p>Local transfer counter identifier.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="../../../../c_intro_userinterfaces/command_summary/parameter_intro/part">PART</a></p>
<p>(Mandatory)</p>         </td>
         <td><p>Identifier of the partner.</p>         </td>
      </tr>
   </tbody>
</table>
