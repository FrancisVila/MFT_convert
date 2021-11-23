{
    "title": "notify",
    "linkTitle": "notify",
    "weight": "2230"
}<span id="notify"></span>

### notify

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
    {{< TransferCFT/componentshortname >}} "submitter" corresponding to the standard
    output associated with the {{< TransferCFT/componentshortname >}} (the submittal screen,
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

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>OS </p>         </th>
<th class="HeadE-Column1-Header1"><p>Monitor submitter </p>         </th>
<th class="HeadE-Column1-Header1"><p>Operator console </p>         </th>
<th class="HeadD-Column1-Header1"><p>Any user </p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>MVS (z/OS)</p>         </td>
         <td><p>NO </p>         </td>
         <td><p>YES </p>         </td>
         <td><p>YES </p>         </td>
      </tr>
      <tr>
         <td><p>OS400 (IBM i)</p>         </td>
         <td><p>YES </p>         </td>
         <td><p>YES </p>         </td>
         <td><p>YES </p>         </td>
      </tr>
      <tr>
         <td><p>UNIX </p>         </td>
         <td><p>YES </p>         </td>
         <td><p>YES </p>         </td>
         <td><p>YES </p>         </td>
      </tr>
      <tr>
         <td><p>VMS </p>         </td>
         <td><p>NO </p>         </td>
         <td><p>YES </p>         </td>
         <td><p>YES </p>         </td>
      </tr>
      <tr>
         <td><p>Windows</p>         </td>
         <td><p>YES </p>         </td>
         <td><p>NO </p>         </td>
         <td><p>NO </p>         </td>
      </tr>
   </tbody>
</table>

The following table indicates, for each system, the default values of
the NOTIFY parameter supported. The value ‘ ’ corresponds to 7 blank characters.

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>OS </p>         </th>
<th class="HeadD-Column1-Header1"><p>Default values for NOTIFY </p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>MVS (z/OS)</p>         </td>
         <td><p>OP </p>         </td>
      </tr>
      <tr>
         <td><p>OS400 </p>         </td>
         <td><p>‘ ’ </p>         </td>
      </tr>
      <tr>
         <td><p>UNIX </p>         </td>
         <td><p>‘ ’ </p>         </td>
      </tr>
      <tr>
         <td><p>VMS </p>         </td>
         <td><p>OP </p>         </td>
      </tr>
      <tr>
         <td><p>Windows</p>         </td>
         <td><p>‘ ’ </p>         </td>
      </tr>
   </tbody>
</table>

In the operator console, the possible choices are indicated in
the following table. If ‘OP’ is indicated for the interpreted characters,
only these two characters (OP) are interpreted; the following characters
are not significant.

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Operator console
OS</p>         </th>
<th class="HeadE-Column1-Header1"><p>Characters interpreted </p>         </th>
<th class="HeadD-Column1-Header1"><p>Messages sent to...</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>MVS (z/OS)</p>         </td>
         <td><p>OP </p>         </td>
         <td><p>Operator console(s) </p>         </td>
      </tr>
      <tr>
         <td><p>OS400 </p>         </td>
         <td><p>OP </p>         </td>
         <td><p>QSYSOPR "message-queue"  </p>         </td>
      </tr>
      <tr>
         <td><p>UNIX </p>         </td>
         <td><p>OP </p>         </td>
         <td><p>Operator console </p>         </td>
      </tr>
      <tr>
         <td><p>VMS </p>         </td>
         <td><p>Opxxxxxx </p>         </td>
         <td><p>System console and output peripheral system LOG file identified
by the "xxxxxx" link present in the current monitor execution
directory </p>         </td>
      </tr>
      <tr>
         <td><p>Windows</p>         </td>
         <td><p>Not applicable </p>         </td>
         <td><p> </p>         </td>
      </tr>
   </tbody>
</table>

For the user:

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">User OS         </th>
<th class="HeadD-Column1-Header1">Messages are...         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>MVS (z/OS)</p>         </td>
         <td><p>Sent by SEND to the specified
TSO USERID; in this case, the {{< TransferCFT/componentshortname  >}} program
must be authorized (APF).</p>         </td>
      </tr>
      <tr>
         <td><p>VMS</p>         </td>
         <td><p>Sent to the "VMS User " designated
by its VMS name. In this case, the {{< TransferCFT/componentshortname  >}} task
must have the OPER privilege.</p>         </td>
      </tr>
   </tbody>
</table>

[Return to Command index](../../)
