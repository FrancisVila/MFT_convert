{
    "title": "Use an internal trace (CFTUTIL command)",
    "linkTitle": "Use an internal trace (CFTUTIL command)",
    "weight": "310"
}Depending on how the trace is started, the file defined is available:

-   When Transfer CFT
    starts up, with the possibility of tracing an initialization sequence
-   During Transfer
    CFT operations

<span id="Trace_commands"></span><span id="Trace_parameter_setting_commands"></span>Trace parameter setting
commands

CFTUTIL parameter setting commands, grouped by function, are presented in the
following table.

<table>
   <th>
      <tr>
<th>Action         </th>
<th>Command         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Update the general parameters before Transfer CFT start-up </p>         </td>
         <td><p>CFTPARM</p>         </td>
      </tr>
      <tr>
         <td><p>Define the trace file or files:</p>
<ul>
<li>Before
Transfer CFT starts </li>
<li>During
Transfer CFT operations </li>
</ul>         </td>
         <td><p>CFTTRACE<br />
</p>         </td>
      </tr>
      <tr>
         <td><p>Start information collection:</p>
<ul>
<li>Transfer
CFT start</li>
<li>During
Transfer CFT operations </li>
</ul>         </td>
         <td><p> </p>
<p>CFTTRACE<br />
</p>         </td>
      </tr>
   </tbody>
</table>

<span id="Trace_command_overview"></span>

### Trace command overview

The following tables are an example of the commands and parameters to
be used for the various trace processes.

#### Defining trace files

<table>
   <th>
      <tr>
<th><p>Trace file definition</p>         </th>
<th>Command         </th>
<th>Parameter         </th>
<th>Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Before starting<br />
Transfer CFT </p>         </td>
         <td><p>CFTPARM </p>         </td>
         <td><p>TRACE=identifier </p>         </td>
         <td><p>CFTTRACE command identifier </p>         </td>
      </tr>
      <tr>
         <td><p> </p>         </td>
         <td><p>CFTTRACE </p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
      </tr>
   </tbody>
</table>

(1): TRCFILE is used in environments
that do not allow dynamic file definition.

#### Start collecting information

<table>
   <th>
      <tr>
<th>Starting information collection         </th>
<th>Command used to define the
file         </th>
<th>Parameter         </th>
<th>Command to enter         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>When starting up Transfer CFT </p>         </td>
         <td><p>CFTTRACE </p>         </td>
         <td><p>START=CFT</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p> </p>         </td>
         <td><p>TRCFILE (1) </p>         </td>
         <td><p>START=CFT </p>         </td>
         <td><p>CFTTRACE </p>         </td>
      </tr>
      <tr>
         <td><p>During Transfer CFT<br />
operations </p>         </td>
         <td><p>CFTTRACE </p>         </td>
         <td><p>START=DELAYED </p>         </td>
         <td><p>STARTTRC </p>         </td>
      </tr>
      <tr>
         <td><p> </p>         </td>
         <td><p>SETTRC </p>         </td>
         <td><p> </p>         </td>
         <td><p>STARTTRC </p>         </td>
      </tr>
   </tbody>
</table>

(1): TRCFILE is used in environments
that do not allow dynamic file definition.

#### Stop collecting - close the file and shutdown the process

<table>
   <th>
      <tr>
<th>Action         </th>
<th>Define the file with         </th>
<th>Enter the command         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Stop information collection </p>         </td>
         <td><p>CFTTRACE </p>         </td>
         <td><p>STOPTRC</p>         </td>
      </tr>
      <tr>
         <td><p>Stop collection, close the files and shutdown the process </p>         </td>
         <td><p>CFTTRACE </p>         </td>
         <td><p>STOPTRC<br />
</p>         </td>
      </tr>
   </tbody>
</table>

## Trace commands with CFTUTIL

### Syntax


    CFTTRACE 
    [XTRACE = {0 | 0..7},]
    ID = identifier,
    [TRCFNAM = " " | filename,]
    [TRCFTYP = {STANDARD | CIRCULAR},]
    [TRCLREC = n,]
    [TRCNREC = n,]
    [MODE = {CREATE | REPLACE | DELETE},]
    START = {CFT | DELAYED}

### Parameters

\[FTRACE = {0
| 0..15}\]

**ID = identifier**

Character string, maximum length: 8; uniquely identifies the trace file
defined by the set of parameters **TRCFNAM, TRCFTYP, TRCLREC, TRCNREC**.

**\[MODE = {CREATE
| REPLACE | DELETE},\]**

Operation to be performed on the ‘‘trace file" entry designated
by the **ID** parameter:

-   CREATE: Create
    an entry
-   REPLACE: Replace
    an entry
-   DELETE: Delete
    an entry

Where **MODE=DELETE**, only the **ID** parameter is useful.

\[MTRACE = {0
| 0..31}\]

\[PTRACE = {0
| 0..31}\]

**START = {<u>CFT</u>
| DELAYED}**

Starting the trace:

-   CFT: at Transfer
    CFT start-up
-   DELAYED: during
    Transfer CFT operations

If **START = CFT**, a trace vector is created with the identifier
defined in the **ID** parameter. This identifier is used in the **STOPTRC**
command to stop collection.

**\[TRCFNAM = {"
" | *filename}*\]**

Name of trace file to be fed by traces.

Character string maximum length: 64 characters.

**\[TRCFTYP = {<u>STANDARD</u>
| CIRCULAR}\]**

Trace file type:

-   STANDARD: sequential
    file written in extend. The new records are written after the old ones.
-   CIRCULAR: direct
    access file, with a set number of fixed-length records. This file is accessed
    through a circular up-date, the new records over-writing the old ones

**\[TRCLREC = n\]**

Trace file physical records (fixed) length.

This parameter is:

-   Mandatory if TRCFTYP
    = CIRCULAR
-   Optional if TRCFTYP
    = STANDARD

**\[TRCNREC = n\]**

Number of trace file records.

This parameter is mandatory if **TRCFTYP = CIRCULAR**.

**\[XTRACE = {<u>0</u>
| 0..7}\]**

Checks the level 1 traces for Transfer CFT EXIT type operations.

This parameter is only relevant if the parameter **START = CFT**.

The chosen value is a mask (logical OR) combination of the desired values.
These values are:

-   1: Trace of the
    request field sent by Transfer CFT to the "EXIT" executive
-   2: Trace of the
    user work field
-   4: Trace of the
    data field

<a href="#" class="selected">Back
to top</a>
