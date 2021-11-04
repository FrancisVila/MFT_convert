{
    "title": "Use  the CFTTRACE utility for traces",
    "linkTitle": "Use an external trace (CFTTRC utility)",
    "weight": "300"
}<span id="Using_the_start_trace_command"></span>The CFTTRACE utility parameter setting commands, grouped by function, are presented in the
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
         <td><p>Define the trace file or files:</p>
<ul>
<li>Before
Transfer CFT starts </li>
<li>During
Transfer CFT operations </li>
</ul>         </td>
         <td><p> </p>
<ul>
<li>TRCFILE</li>
<li>SETTRC</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Start information collection:</p>
<ul>
<li>Transfer
CFT start</li>
<li>During
Transfer CFT operations </li>
</ul>         </td>
         <td><p>STARTTRC</p>         </td>
      </tr>
      <tr>
         <td><p>Stop information collection </p>         </td>
         <td><p>STOPTRC </p>         </td>
      </tr>
      <tr>
         <td><p>Close files and shut down the process </p>         </td>
         <td><p>SETTRC </p>         </td>
      </tr>
   </tbody>
</table>

<span id="Trace_command_overview"></span>

## Command overview

The following tables are an example of the commands and parameters to
be used for the various trace processes.

### Define trace files

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
      <tr>
         <td><p> </p>         </td>
         <td><p>or TRCFILE (1) </p>         </td>
         <td><p>TYPE=TRACE </p>         </td>
         <td><p>The defined file is a trace file </p>         </td>
      </tr>
      <tr>
         <td><p>During Transfer CFT operations </p>         </td>
         <td><p>SETTRC </p>         </td>
         <td><p>MODE=CREATE or MODIFY </p>         </td>
         <td><p> </p>         </td>
      </tr>
   </tbody>
</table>

(1): TRCFILE is used in environments
that do not allow dynamic file definition.

### Start collecting information

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

### Stop collecting - close the file and shutdown the process

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
         <td><p> </p>         </td>
         <td><p>SETTR </p>         </td>
         <td><p>STOPTRC </p>         </td>
      </tr>
      <tr>
         <td><p>Stop collection, close the files and shutdown the process </p>         </td>
         <td><p>CFTTRACE </p>         </td>
         <td><p>STOPTRC<br />
and<br />
SETTRC MODE=DELETE</p>         </td>
      </tr>
      <tr>
         <td><p> </p>         </td>
         <td><p>SETTRC </p>         </td>
         <td><p>SETTRC MODE=DELETE </p>         </td>
      </tr>
   </tbody>
</table>

<span id="About"></span>

## Using the STARTTRC command

This command, which is associated with a unique identifier, performs
the following tasks:

-   Defines and describes
    the conditions for starting and selecting traced data
-   Associates a file
    identifier, already defined by the SETTRC command, with this trace which
    designated the file in which the traces will be stored

### Syntax

STARTTRC** **ID = *identifier*,  
TID =  *identifier*  

### Parameters

**ID = *identifier***

Identifier which makes the trace vector defined by this parameter set
uniquely identifiable.

This parameter is a character string, maximum length 8.

\[FTRACE = {0
| 0..15}\]

\[MTRACE = {0
| 0..31}\]

\[PTRACE = {0
| 0..31}\]

**TID =  *identifier***

Identifier of the **SETTRC** or **CFTTRACE** command which defines
the collection’s output trace file.

This identifier should exist, in that it should have been initialized
by a **SETTRC** or **CFTTRACE** command**.**

This parameter is a character string, maximum length 8.

**\[XTRACE = {<u>0</u> |
0..7}\]**

Checks the level 1 traces for Transfer CFT "EXIT" type operations.

This parameter is only relevant if the parameter **START = CFT**.

The chosen value is a mask (logical OR) combination of the desired values.
These values are:

-   1: Trace of the
    request field passed by Transfer CFT to the exit executive
-   2: Trace of the
    user work field
-   4: Trace of the
    data field

<span id="Using_the_stop_trace_command"></span><span id="About_the_STOPTRC_command"></span>

## Using the STOPTRC command

This command defines and describes the conditions for stopping a trace.
The trace to be stopped is indicated by the identifier previously created
by the **STARTTRC** command.

### Syntax

STOPTRC  ID =
*identifier*

### Parameters

**ID = *identifier***

Identifier which uniquely identifies the trace vector defined by this
set of parameters.

This parameter is a character string, maximum length: 8.

## Collect a trace

The following example shows how to retrieve a protocol trace. You can use the same steps to perform other types of traces.

1.  Start <span class="mc-variable axway_variables.Component_Long_Name variable">Transfer CFT</span>.

2.  Use the command utility CFTTRACE to set and start the following trace, for example:

    CFTTRACE SETTRC ID=TRC0,TRCFNAM=&lt;trc\_collect\_file\_name>,mode=create

    CFTTRACE STARTTRC ID=T1,TID=TRC0,PTRACE=28

3.  Check that the <span class="code">CFTATMC </span>process is started.

4.  Execute the transfer to trace.

## Extract a trace

To extract information, use the CFTTRACE utility to stop and extract the trace. For example:

CFTTRACE STOPTRC ID=t1

CFTTRACE SETTRC ID=TRC0, MODE=CLOSE

CFTTRACE EXTRACT IFNAME=&lt;trc\_collect\_file\_name>, OFNAME=&lt;trc\_txt\_file\_name>, CONTENT=FULL, PRESENT=intall

<span id="About_the_TRCFILE_command"></span>

## TRCFILE command details

Trace files can be created and pre-formatted in their order of occurrence
or externally with a utility, in particular for environments that cannot
support such operations. The utility is integrated in CFTTRACE, with the
command **TRCFILE** **TYPE = TRACE.**

Use this command to create or destroy a trace file, or to reinitialize
it with empty useable content.

### Syntax

TRCFILE  TYPE** **= TRACE,  
\[MODE = {<u>CREATE</u> | REPLACE | DELETE},\]  
TRCFNAM = *filename,*  
TRCFTYP = {<u>STANDARD</u> | CIRCULAR},  
 

**TRCFTYP = STANDARD**  
\[TRCLREC = {<u>1024</u> | n}\]  
 

**TRCFTYP = CIRCULAR**  
TRCNREC** **= n,  
TRCLREC** **= {<u>0</u> | <u>1024</u> | n}

### Parameters

**\[MODE = {<u>CREATE</u>
| REPLACE | DELETE},\]**

Type of operation to be carried out on the file:

-   CREATE: Create
    and initialize a trace file that does not yet exist.  
    If the file already exists, this operation is refused
-   REPLACE: Reinitialize
    an existing trace file.  
    If the file does not already exist, it is created
-   DELETE: Delete
    a trace file

**TRCFNAM = *filename***

Name of the trace file.

**TRCFTYP = {<u>STANDARD</u>
| CIRCULAR}**

Type of trace file for which an operation is requested:

-   STANDARD: Sequential
    file (fixed record size)
-   CIRCULAR: Direct
    file (fixed record size)

**\[TRCLREC = {<u>0</u>
| <u>1024</u> | n}\]**

Size of records contained in the trace file.

This parameter is:

-   Mandatory when
    TRCFTYP = CIRCULAR, with a default value of 0
-   Optional when TRCFTYP
    = STANDARD with a default value of 1024

**\[TRCNREC = n\]**

Number of useable records contained in the direct file.

This parameter is:

-   Mandatory when
    **TRCFTYP = CIRCULAR**
-   Not applicable
    when **TRCFTYP = STANDARD**

TYPE = TRACE

Operation on a trace file.

## SETTRC command details

The SETTRC command:

-   Defines and describes
    a trace file, which can be available to store captured information
-   Associates an identifier
    with this file and description, which allows it to be identified uniquely,
    if the user wishes to distribute several trace types into several different
    files

### Syntax

SETTRC**  **ID = *identifier*,  
TRCFNAM = {<u>" "</u> | filename},  
\[TRCFTYP = {<u>STANDARD</u> | CIRCULAR},  
\[MODE = {<u>CREATE</u> | REPLACE | CLOSE},\]  
 

**TRCFTYP = STANDARD**  
\[TRCLREC = {<u>0</u> | n}\]

**TRCFTYP = CIRCULAR**  
TRCLREC = {<u>0</u> | n},  
TRCNREC  = n

### Parameters

**\[ID = *identifier*\]**

Character string, maximum length: 8; uniquely identifies the trace file
descriptor defined by this set of parameters.

**\[MODE = {<u>CREATE</u>
| REPLACE | CLOSE}\]**

Operation to be performed on the ‘‘trace file" entry designated
by the ID parameter:

-   CREATE: Create
    an entry, and possibly the file
-   REPLACE: Replace
    the file with another one for the same entry
-   CLOSE: Delete an
    entry, the file will then be closed

Where **MODE = CLOSE**, only the **ID** parameter is useful.

**TRCFNAM = {<u>"
"</u> | *filename*}**

Name of trace file to be fed by traces.

Character string maximum length: 64 characters.

**\[TRCFTYP = <u><span style="text-decoration: none;">{</span>STANDARD</u>
| CIRCULAR}\]**

Trace file type:

-   STANDARD: Sequential
    file written in "extend".  
    The new records are written after the old ones
-   CIRCULAR: Direct
    access file, with a set number of fixed-length records.  
    This file is accessed through a circular up-date, the new records overwriting
    the old ones

**\[TRCLREC = {<u>0</u>
| n}\]**

Length of trace file’s physical records.

This parameter is:

-   Mandatory if TRCFTYP
    = CIRCULAR  
    Concatenation and segmentation algorithms make it possible to manage
    the real - essentially variable - size of data to be written to this file
-   Optional if TRCFTYP
    = STANDARD (sequential file, with fixed-size records)

**\[TRCNREC = n\]**

Number of trace file records.

This parameter is:

-   Mandatory if TRCFTYP
    = CIRCULAR
-   Not applicable
    if TRCFTYP = STANDARD