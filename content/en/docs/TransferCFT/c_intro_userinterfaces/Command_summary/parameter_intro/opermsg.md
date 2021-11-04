{
    "title": "opermsg",
    "linkTitle": "opermsg",
    "weight": "2460"
}<span id="opermsg"></span>

### opermsg

<span id="opermsg_CFTRECV"></span><span id="opermsg_CFTLOG"></span>

#### CFTRECV, CFTSEND, CFTLOG

**\[OPERMSG = {<u>see table</u> | n}\]
 **{0..255}

Defines the categories of messages that are intended for the operator. All
messages are also written in the log file. This is a subset of the <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> log messages
defined by the algebraic sum of the values indicated in the following
table.

<table>
   <th>
      <tr>
<th>Value         </th>
<th>Message category         </th>
<th>Type         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>1 </p>         </td>
         <td><p>Operating information messages </p>         </td>
         <td><p>I </p>         </td>
      </tr>
      <tr>
         <td><p>2 </p>         </td>
         <td><p>System information messages </p>         </td>
         <td><p>I </p>         </td>
      </tr>
      <tr>
         <td><p>4 </p>         </td>
         <td><p>Operating warning messages </p>         </td>
         <td><p>W </p>         </td>
      </tr>
      <tr>
         <td><p>8 </p>         </td>
         <td><p>System warning messages </p>         </td>
         <td><p>W </p>         </td>
      </tr>
      <tr>
         <td><p>16 </p>         </td>
         <td><p>Operating error messages </p>         </td>
         <td><p>E </p>         </td>
      </tr>
      <tr>
         <td><p>32 </p>         </td>
         <td><p>System error messages </p>         </td>
         <td><p>E </p>         </td>
      </tr>
      <tr>
         <td><p>64 </p>         </td>
         <td><p>Operating fatal error messages </p>         </td>
         <td><p>F </p>         </td>
      </tr>
      <tr>
         <td><p>128 </p>         </td>
         <td><p>System fatal error messages </p>         </td>
         <td><p>F </p>         </td>
      </tr>
   </tbody>
</table>

The I, W, E, F types correspond to the type of message indicated in
the log file. Refer to the <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> <a href="../../../../troubleshoot_intro/messages_and_error_codes_start_here" class="MCXref xref">Transfer CFT messages
and error codes</a> section.

The value "0" means that no message is sent to the operator.

The following table indicates, for each system, the default values of
the OPERMSG parameter.

<table>
   <th>
      <tr>
<th><p>OS </p>         </th>
<th><p>Default value for OPERMSG </p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>MVS (z/OS)</p>         </td>
         <td><p>0 </p>         </td>
      </tr>
      <tr>
         <td><p>OS400 </p>         </td>
         <td><p>0 </p>         </td>
      </tr>
      <tr>
         <td><p>UNIX </p>         </td>
         <td><p>0</p>         </td>
      </tr>
      <tr>
         <td><p>Windows</p>         </td>
         <td><p>0</p>         </td>
      </tr>
   </tbody>
</table>

[Return to Command index](../../)
