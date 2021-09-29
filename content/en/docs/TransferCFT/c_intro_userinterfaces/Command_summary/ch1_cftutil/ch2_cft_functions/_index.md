{
    "title": "Transfer CFT batch commands",
    "linkTitle": "Transfer CFT batch commands",
    "weight": "290"
}This section describes the following Transfer CFT commands:

-   QUERY
-   WAITCAT
-   TEST

### QUERY

The QUERY command checks the catalog for the first record that matches the indicated criteria in the defined order. Once a record that matches is found, the catalog variables are filled with the predefined values. See the section [Predefined Variables](ch2_predefined_varaibles).

#### Syntax

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>QUERY IDA = STR,</p>
<p>      DIRECT = STR,</p>
<p>      IDF = STR,</p>
<p>      IDT = STR,</p>
<p>      PART = STR,</p>
<p>      STATE = STR,</p>
<p>      NIDF = STR,</p>
<p>      NAME = VAR,</p>
<p>      FIELD = CHAMP</p>
<p>      TYPE = STR,</p></td>
</tr>
</tbody>
</table>

#### Parameters

-   IDA: Character string specifying the criteria for the IDA field .
-   DIRECT: Character string specifying the criteria for the DIRECT field.
-   IDF: Character string specifying the criteria for the IDF field.
-   IDT: Character string specifying the criteria for the IDT field.
-   PART: Character string specifying the criteria for the SHARE field.
-   STATE: Character string specifying the criteria for the STATE field.
-   NIDF: Character string specifying the criteria for the NIDF field.
-   NAME: The name of the variable that will be filled by the catalog field value specified in FIELD.
-   FIELD: Character string for the catalog field to read information for the NAME variable. Field names include IDT, STATE, and TIMES.
-   TYPE: String with a possible value of \*, FILE, MSG, REPLY, or NACK.

#### Example

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>CHAR NAME = IDT, SIZE=12</p>
<p>QUERY PART = PSITC001, DIRECT = RECV,</p>
<p>NAME=IDT,FIELD=IDT</p></td>
</tr>
</tbody>
</table>

### WAITCAT

The WAITCAT command scans the catalog searching for a record that corresponds to the criteria specified in the command parameters. If a record matches the selected criteria, the result is a return code of 0. If there are no matches, the result is a non-zero return code. The return code is stored in the predefined variable \_CMDRET.

You can specify a maximum wait time as well as a scanning range for the catalog.

#### Syntax

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>WAITCAT IDA = STR,</p>
<p>        DIRECT = STR,</p>
<p>        IDF = STR,</p>
<p>        IDT = STR,</p>
<p>        PART = STR,</p>
<p>        STATE = STR,</p>
<p>        NIDF = STR,</p>
<p>        TYPE = STR,</p>
<p>        MAXTIME = STR,</p>
<p>        SCANTIME = NNN,</p>
<p>        DURING = NNN,</p>
<p>        NBCHKPT = NNN,</p>
<p>        DIAGP = STR,</p>
<p>        DIAGI = STR</p>
<p>       IDTU = STR</p>
<p>       PHASE = STR</p>
<p>       PHASESTEP = STR</p></td>
</tr>
</tbody>
</table>

#### Parameters

-   IDA: Character string specifying the criteria for the IDA field.
-   DIRECT: Character string specifying the criteria for the DIRECT field.
-   IDF: Character string specifying the criteria for the IDF field.
-   IDT: Character string specifying the criteria for the IDT field.
-   PART: Character string specifying the criteria for the SHARE field.
-   STATE: Character string specifying the selection criteria for the STATE field.
-   NIDF : Character string specifying the selection criteria for the NIDF field.
-   TYPE: Character string specifying the selection criteria for the TYPE field.
-   MAXTIME: Character string specifying maximum waiting time as HHMMSSCC.
-   SCANTIME: The catalog scan interval in seconds.
-   DURING: The maximum delay to wait in seconds.
-   NBCHKPT: The criteria to indicate the number of synchronization points in the catalog.
-   DIAGP: Character string specifying the criteria for the DIAGP.
-   DIAGI: Character string specifying the criteria for the DIAGI.
-   IDTU: Character string.
-   PHASE: Character string.
-   PHASESTEP: Character string.

#### Example

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>WAITCAT PART = PSITC001, DIRECT = RECV, DURING = 30,</p>
<p>SCANTIME = 1</p>
<p>PRINT MSG='The return code for WAIT is : %_CMDRET%'</p></td>
</tr>
</tbody>
</table>

### TEST

#### Syntax

The TEST command searches in the catalog records for criteria that matches the command parameters. If a record matches the criteria, the TEST command has a return code of 0, otherwise it results in a non-zero value return code.

The return code is stored in the predefined variable \_CMDRET.FTEMOIN field sets the name of a file to be used as a control to compare the transferred file. The control file is opened with the same file attributes that were defined in the catalog for the transferred file.

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>TEST IDA = STR,</p>
<p>    DIRECT = STR,</p>
<p>     IDF = STR,</p>
<p>     PART = STR,</p>
<p>     STATE = STR,</p>
<p>     IDF = STR,</p>
<p>     NIDF = STR,</p>
<p>     MSG = STR,</p>
<p>     SUSER = STR,</p>
<p>     RUSER = STR,</p>
<p>     SAPPL = STR,</p>
<p>     SPART = STR,</p>
<p>     RAPPL = STR,</p>
<p>     RPART = STR,</p>
<p>     PARM = STR,</p>
<p>     STATED = STR,</p>
<p>     FRECFM = STR,</p>
<p>     NRECFM = STR,</p>
<p>     FNAME = STR,</p>
<p>     NFNAME = STR,</p>
<p>     DIAGI = STR,</p>
<p>     DIAGP = STR,</p>
<p>     FLRECL = STR,</p>
<p>     NLRECL = STR,</p>
<p>    FBLKSIZE = STR,</p>
<p>    NBLKSIZE = STR,</p>
<p>    USERID = STR,</p>
<p>            JOBNAME = STR,</p>
<p>            PROT = STR,</p>
<p>  PRI = STR,</p>
<p>            NCOMP = STR,</p>
<p>           FSPACE = STR,</p>
<p>   NSPACE = STR,</p>
<p>   NCODE = STR,</p>
<p>          FCODE = STR,</p>
<p>          FREC = STR,</p>
<p>   NREC = STR,</p>
<p>   FCAR = STR,</p>
<p>          NCAR = STR,</p>
<p>          ECAR = STR,</p>
<p>   FTIME = STR,</p>
<p>   FDATE = STR,</p>
<p>          FRECFM = STR,</p>
<p>   FRECFM = STR,</p>
<p>          FTEMOIN = STR</p>
<p>   FTIME = STR</p>
<p>   FDATE = STR</p>
<p>   APPSTATE = STR</p>
<p>   PHASE = STR</p>
<p>   PHASESTEP = STR</p>
<p>   PIDTU = STR</p></td>
</tr>
</tbody>
</table>

#### Parameters

-   IDA: Character string specifying the selection criteria for the IDA field.
-   DIRECT: Character string specifying the selection criteria for the DIRECT field.
-   IDF: Character string specifying the selection criteria for the IDF field.
-   PART: Character string specifying the selection criteria for the PART field.
-   STATE: Character string specifying the selection criteria for the STATE field.
-   IDF: Character string specifying the selection criteria for the IDF field.
-   NIDF: Character string specifying the selection criteria for the NIDF field.
-   MSG: Character string specifying the selection criteria for the MSG field.
-   SUSER: Character string specifying the selection criteria for the SUSER field.
-   RUSER: Character string specifying the selection criteria for the RUSER field.
-   SAPPL: Character string specifying the selection criteria for the SAPPL field.
-   SPART: Character string specifying the selection criteria for the SPART field.
-   RAPPL: Character string specifying the selection criteria for the RAPPL field.
-   RPART: Character string specifying the selection criteria for the RPART field.
-   PARM: Character string specifying the selection criteria for the PARM field.
-   STATED: Character string specifying the selection criteria for the STATED field.
-   FRECFM: Character string specifying the selection criteria for the FRECFM field.
-   NRECFM: Character string specifying the selection criteria for the NRECFM field.
-   FNAME: Character string specifying the selection criteria for the FNAME field.
-   NFNAME: Character string specifying the selection criteria for the NFNAME field.
-   DIAGI: Character string specifying the selection criteria for the DIAGI field.
-   DIAGP: Character string specifying the selection criteria for the DIAGP field.
-   FLRECL: Character string specifying the selection criteria for the FLRECL field.
-   NLRECL: Character string specifying the selection criteria for the NLRECL field.
-   FBLKSIZE: Character string specifying the selection criteria for the FBLKSIZE field.
-   NBLKSIZE: Character string specifying the selection criteria for the NBLKSIZE field.
-   USERID: Character string specifying the selection criteria for the USERID field.
-   JOBNAME: Character string specifying the selection criteria for the JOBNAME field.
-   PROT: Character string specifying the selection criteria for the PROT field.
-   PRI: Character string specifying the selection criteria for the PRI field.
-   NCOMP: Character string specifying the selection criteria for the NCOMP field.
-   FSPACE: Character string specifying the selection criteria for the FSPACE field.
-   NSPACE: Character string specifying the selection criteria for the NSPACE field.
-   NCODE: Character string specifying the selection criteria for the NCODE field.
-   FCODE: Character string specifying the selection criteria for theFCODE field.
-   FREC: Character string specifying the selection criteria for theFREC field.
-   NREC: Character string specifying the selection criteria for theNREC field.
-   FCAR: Character string specifying the selection criteria for theFCAR field.
-   NCAR: Character string specifying the selection criteria for theNCAR field.
-   ECAR: Character string specifying the selection criteria for theECAR field.
-   FTIME: Character string specifying the selection criteria for the FDATE field.
-   FDATE: Character string specifying the selection criteria for the FTIME field.
-   FRECFM: character representing the F/V/U parameter value.
-   NRECFM: character representing the F/V/U parameter value.
-   FTEMOIN: String specifying the name of the comparison file.
-   APPSTATE: Character string specifying the selection criteria for the APPSTATE field.
-   PHASE: Character string specifying the selection criteria for the PHASE field.
-   PHASESTEP: Character string specifying the selection criteria for the PHASESTEP field.
-   PIDTU: Character string specifying the selection criteria for the PIDTU field.

#### Example

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>TEST PART = PSITC001, DIRECT = RECV,</p>
<p>PRINT MSG='The test return code is: %_CMDRET%'</p></td>
</tr>
</tbody>
</table>
