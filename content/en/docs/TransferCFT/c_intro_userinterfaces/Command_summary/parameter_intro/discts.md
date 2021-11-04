{
    "title": "discts",
    "linkTitle": "discts",
    "weight": "740"
}<span id="discts"></span>

### discts

#### CFTPROT

\[DISCTS =
{ <u>see the table</u> | n} \] {0..3600}  

The synchronous connection time as managed by <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span>. If <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> does not receive requests to communicate in discts (the number of seconds), <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> closes the session.

The session established for a transfer remains active for DISCTS seconds
after the completion of this transfer. If at the end of this timeout,
no new transfer has been received, the connection is freed by the ABORT
FPDU.

If the value is 0, the wait time-out is infinite.

The default value (in seconds) depends on the protocol and is indicated
in the following table.

Default values are:

<table>
   <th>
      <tr>
<th>Protocol          </th>
<th>Default value         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>PeSIT ANY profile</p>         </td>
         <td><p>60</p>         </td>
      </tr>
      <tr>
         <td><p>ODETTE </p>         </td>
         <td><p>65 </p>         </td>
      </tr>
   </tbody>
</table>

[Return to Command index](../../)
