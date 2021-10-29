{
    "title": "notify",
    "linkTitle": "notify",
    "weight": "2260"
}### <span id="notify"></span>notify

#### CFTLOG, CFTSEND, **<span id="notify_CFTRECV"></span>**CFTRECV, SEND, RECV

NOTIFY = {string see
below}

Defines the destination of the operator
messages selected according to the value of the OPERMSG parameter as follows:

-   All
    log file messages if defined in the CFTLOG object
-   For
    all transfer messages with the IDF if defined in CFTSEND or CFTRECV
-   For
    all messages from a transfer that was requested with the command if used
    in SEND or RECV

The value of this parameter is a left aligned 8-character string.

The destination of these messages may be, according to the system:

-   the
    Transfer CFT "submitter" corresponding to the standard
    output associated with the Transfer CFT (the submittal screen,
    for example)  
    The value of the NOTIFY parameter must be then be set to ‘ ’ (8 blank
    characters)
-   an
    operator console  
    The NOTIFY parameter value must begin by the 2 characters OP

<!-- -->

-   a computer
    user  
    The value of the NOTIFY parameter indicates the user system identifier
    according to the format "xxxxxxxx"

The following table indicates the possible recipients for each system
involved:

-   YES indicates that the corresponding
    recipient type exists
-   NO indicates the corresponding recipient
    type does not exist

<table data-cellspacing="0" width="90%">
   <thead>
      <tr class="header">
         <th>            <p>OS </p></th>
         <th>            <p>Monitor submitter </p></th>
         <th>            <p>Operator console </p></th>
         <th>            <p>Any user </p></th>
      </tr>
   </thead>
   <tbody>
      <tr class="odd">
         <td data-valign="top" width="19%">            <p>MVS (z/OS)</p>         </td>
         <td data-valign="top" width="24%">            <p>NO </p>         </td>
         <td data-valign="top" width="22%">            <p>YES </p>         </td>
         <td data-valign="top" width="35%">            <p>YES </p>         </td>
      </tr>
      <tr class="even">
         <td data-valign="top" width="19%">            <p>OS400 (IBM i)</p>         </td>
         <td data-valign="top" width="24%">            <p>YES </p>         </td>
         <td data-valign="top" width="22%">            <p>YES </p>         </td>
         <td data-valign="top" width="35%">            <p>YES </p>         </td>
      </tr>
      <tr class="odd">
         <td data-valign="top" width="19%">            <p>UNIX </p>         </td>
         <td data-valign="top" width="24%">            <p>YES </p>         </td>
         <td data-valign="top" width="22%">            <p>YES </p>         </td>
         <td data-valign="top" width="35%">            <p>YES </p>         </td>
      </tr>
      <tr class="even">
         <td data-valign="top" width="19%">            <p>VMS </p>         </td>
         <td data-valign="top" width="24%">            <p>NO </p>         </td>
         <td data-valign="top" width="22%">            <p>YES </p>         </td>
         <td data-valign="top" width="35%">            <p>YES </p>         </td>
      </tr>
      <tr class="odd">
         <td data-valign="top" width="19%">            <p>Windows</p>         </td>
         <td data-valign="top" width="24%">            <p>YES </p>         </td>
         <td data-valign="top" width="22%">            <p>NO </p>         </td>
         <td data-valign="top" width="35%">            <p>NO </p>         </td>
      </tr>
   </tbody>
</table>

The following table indicates, for each system, the default values of
the NOTIFY parameter supported. The value ‘ ’ corresponds to 7 blank characters.

<table data-cellspacing="0" width="90%">
   <thead>
      <tr class="header">
         <th>            <p>OS </p></th>
         <th>            <p>Default values for NOTIFY </p></th>
      </tr>
   </thead>
   <tbody>
      <tr class="odd">
         <td data-valign="top" width="17%">            <p>MVS (z/OS)</p>         </td>
         <td data-valign="top" width="83%">            <p>OP </p>         </td>
      </tr>
      <tr class="even">
         <td data-valign="top" width="17%">            <p>OS400 </p>         </td>
         <td data-valign="top" width="83%">            <p>‘ ’ </p>         </td>
      </tr>
      <tr class="odd">
         <td data-valign="top" width="17%">            <p>UNIX </p>         </td>
         <td data-valign="top" width="83%">            <p>‘ ’ </p>         </td>
      </tr>
      <tr class="even">
         <td data-valign="top" width="17%">            <p>VMS </p>         </td>
         <td data-valign="top" width="83%">            <p>OP </p>         </td>
      </tr>
      <tr class="odd">
         <td data-valign="top" width="17%">            <p>Windows</p>         </td>
         <td data-valign="top" width="83%">            <p>‘ ’ </p>         </td>
      </tr>
   </tbody>
</table>

In the operator console, the possible choices are indicated in
the following table. If ‘OP’ is indicated for the interpreted characters,
only these two characters (OP) are interpreted; the following characters
are not significant.

<table data-cellspacing="0">
   <thead>
      <tr class="header">
         <th>            <p>Operator console
OS</p></th>
         <th>            <p>Characters interpreted </p></th>
         <th>            <p>Messages sent to...</p></th>
      </tr>
   </thead>
   <tbody>
      <tr class="odd">
         <td data-valign="top" width="21%">            <p>MVS (z/OS)</p>         </td>
         <td data-valign="top" width="21%">            <p>OP </p>         </td>
         <td data-valign="top" width="58%">            <p>Operator console(s) </p>         </td>
      </tr>
      <tr class="even">
         <td data-valign="top" width="21%">            <p>OS400 </p>         </td>
         <td data-valign="top" width="21%">            <p>OP </p>         </td>
         <td data-valign="top" width="58%">            <p>QSYSOPR "message-queue"  </p>         </td>
      </tr>
      <tr class="odd">
         <td data-valign="top" width="21%">            <p>UNIX </p>         </td>
         <td data-valign="top" width="21%">            <p>OP </p>         </td>
         <td data-valign="top" width="58%">            <p>Operator console </p>         </td>
      </tr>
      <tr class="even">
         <td data-valign="top" width="21%">            <p>VMS </p>         </td>
         <td data-valign="top" width="21%">            <p>Opxxxxxx </p>         </td>
         <td data-valign="top" width="58%">            <p>System console and output peripheral system LOG file identified
by the "xxxxxx" link present in the current monitor execution
directory </p>         </td>
      </tr>
      <tr class="odd">
         <td data-valign="top" width="21%">            <p>Windows</p>         </td>
         <td data-valign="top" width="21%">            <p>Not applicable </p>         </td>
         <td data-valign="top" width="58%">            <p> </p>         </td>
      </tr>
   </tbody>
</table>

For the user:

<table data-cellspacing="0">
   <thead>
      <tr class="header">
         <th>User OS</th>
         <th>Messages are...</th>
      </tr>
   </thead>
   <tbody>
      <tr class="odd">
         <td width="26%">            <p>MVS (z/OS)</p>         </td>
         <td width="74%">            <p>Sent by SEND to the specified
TSO USERID; in this case, the <span>Transfer CFT</span> program
must be authorized (APF).</p>         </td>
      </tr>
      <tr class="even">
         <td width="26%">            <p>VMS</p>         </td>
         <td width="74%">            <p>Sent to the "VMS User " designated
by its VMS name. In this case, the <span>Transfer CFT</span> task
must have the OPER privilege.</p>         </td>
      </tr>
   </tbody>
</table>

[Return to Command index](../)
