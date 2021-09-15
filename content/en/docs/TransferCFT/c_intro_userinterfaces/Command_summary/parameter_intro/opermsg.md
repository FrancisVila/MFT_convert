{
    "title": "opermsg",
    "linkTitle": "opermsg",
    "weight": "2490"
}### <span id="opermsg"></span>opermsg

#### <span id="opermsg_CFTRECV"></span>CFTRECV, CFTSEND, <span id="opermsg_CFTLOG"></span>CFTLOG

**\[OPERMSG = {<u>see table</u> | n}\]
 **{0..255}

Defines the categories of messages that are intended for the operator. All
messages are also written in the log file. This is a subset of the Transfer CFT log messages
defined by the algebraic sum of the values indicated in the following
table.

<table cellspacing="0" width="90%">
   <col/>
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Value</th>
         <th>Message category</th>
         <th>Type</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td valign="top" width="11%">
            <p>1 </p>
         </td>
         <td valign="top" width="43%">
            <p>Operating information messages </p>
         </td>
         <td valign="top" width="45%">
            <p>I </p>
         </td>
      </tr>
      <tr>
         <td valign="top" width="11%">
            <p>2 </p>
         </td>
         <td valign="top" width="43%">
            <p>System information messages </p>
         </td>
         <td valign="top" width="45%">
            <p>I </p>
         </td>
      </tr>
      <tr>
         <td valign="top" width="11%">
            <p>4 </p>
         </td>
         <td valign="top" width="43%">
            <p>Operating warning messages </p>
         </td>
         <td valign="top" width="45%">
            <p>W </p>
         </td>
      </tr>
      <tr>
         <td valign="top" width="11%">
            <p>8 </p>
         </td>
         <td valign="top" width="43%">
            <p>System warning messages </p>
         </td>
         <td valign="top" width="45%">
            <p>W </p>
         </td>
      </tr>
      <tr>
         <td valign="top" width="11%">
            <p>16 </p>
         </td>
         <td valign="top" width="43%">
            <p>Operating error messages </p>
         </td>
         <td valign="top" width="45%">
            <p>E </p>
         </td>
      </tr>
      <tr>
         <td valign="top" width="11%">
            <p>32 </p>
         </td>
         <td valign="top" width="43%">
            <p>System error messages </p>
         </td>
         <td valign="top" width="45%">
            <p>E </p>
         </td>
      </tr>
      <tr>
         <td valign="top" width="11%">
            <p>64 </p>
         </td>
         <td valign="top" width="43%">
            <p>Operating fatal error messages </p>
         </td>
         <td valign="top" width="45%">
            <p>F </p>
         </td>
      </tr>
      <tr>
         <td valign="top" width="11%">
            <p>128 </p>
         </td>
         <td valign="top" width="43%">
            <p>System fatal error messages </p>
         </td>
         <td valign="top" width="45%">
            <p>F </p>
         </td>
      </tr>
   </tbody>
</table>

The I, W, E, F types correspond to the type of message indicated in
the log file. Refer to the Transfer CFT [Transfer CFT messages
and error codes](../../../../troubleshoot_intro/messages_and_error_codes_start_here) section.

The value "0" means that no message is sent to the operator.

The following table indicates, for each system, the default values of
the OPERMSG parameter.

<table cellspacing="0" width="90%">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>
            <p>OS </p>
</th>
         <th>
            <p>Default value for OPERMSG </p>
</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td valign="top" width="22%">
            <p>MVS (z/OS)</p>
         </td>
         <td valign="top" width="78%">
            <p>0 </p>
         </td>
      </tr>
      <tr>
         <td valign="top" width="22%">
            <p>OS400 </p>
         </td>
         <td valign="top" width="78%">
            <p>0 </p>
         </td>
      </tr>
      <tr>
         <td valign="top" width="22%">
            <p>UNIX </p>
         </td>
         <td valign="top" width="78%">
            <p>0</p>
         </td>
      </tr>
      <tr>
         <td valign="top" width="22%">
            <p>Windows</p>
         </td>
         <td valign="top" width="78%">
            <p>0</p>
         </td>
      </tr>
   </tbody>
</table>

[Return to Command index](../../)
