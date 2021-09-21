{
    "title": "Read commands",
    "linkTitle": "Read commands",
    "weight": "320"
}The QUERY, TEST, and WAITCAT commands can locate the first transfer that meets a certain set of criteria. But, if there are other transfers that meet this same criteria, they are overlooked. To overcome this limitation and find these additional transfers, you can use the read commands.

Three read commands are available and described in this section:

-   BEGSELCA: Establishes the selection criteria.
-   GETCAT: Reads a transfer if it meets the BEGSELCA selection criteria.
-   ENDSELCA: Ends the command series.

### BEGSELCA command

#### Syntax

The BEGSELCA command defines the selection criteria for transfers. The FTEMOIN field sets the name of a file to be used as a control to compare the transferred file with the control file. The compared file is opened with the same file attributes as those found in the catalog.

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>BEGSELCA IDA = STR,</p>
            <p>DIRECT = STR,</p>
            <p>IDF = STR,</p>
            <p>PART = STR,</p>
            <p>STATE = STR,</p>
            <p>IDF = STR,</p>
            <p>NIDF = STR,</p>
            <p>MSG = STR,</p>
            <p>SUSER = STR,</p>
            <p>RUSER = STR,</p>
            <p>SAPPL = STR,</p>
            <p>SPART = STR,</p>
            <p>RAPPL = STR,</p>
            <p>RPART</p>
            <p>PARM = STR,</p>
            <p>STATED = STR,</p>
            <p>FRECFM = STR,</p>
            <p>NRECFM = STR,</p>
            <p>FNAME = STR,</p>
            <p>NFNAME = STR,</p>
            <p>DIAGI = STR,</p>
            <p>DIAGP = STR,</p>
            <p>FLRECL = STR,</p>
            <p>NLRECL = STR,</p>
            <p>FBLKSIZE = STR,</p>
            <p>NBLKSIZE = STR,</p>
            <p>USERID = STR,</p>
            <p>JOBNAME = STR,</p>
            <p>PROT = STR</p>
            <p>PRI = STR,</p>
            <p>NCOMP = STR,</p>
            <p>FSPACE = STR,</p>
            <p>NSPACE = STR,</p>
            <p>NCODE = STR,</p>
            <p>FCODE = STR,</p>
            <p>FREC = STR,</p>
            <p>NREC = STR,</p>
            <p>FCAR = STR,</p>
            <p>NCAR = STR,</p>
            <p>ECAR = STR,</p>
            <p>FTIME = STR,</p>
            <p>FDATE = STR,</p>
            <p>FRECFM = STR</p>
            <p>NRECFM = STR</p>
            <p>FTEMOIN = STR</p>
         </td>
      </tr>
   </tbody>
</table>

#### Parameters

-   IDA: Character string specifying the selection criteria IDA field.
-   DIRECT: Character string specifying the selection criteria DIRECT field.
-   IDF: Character string specifying the selection criteria IDF field.
-   PART: Character string specifying the selection criteria SHARE field.
-   STATE: Character string specifying the selection criteria STATE field.
-   IDF: Character string specifying the selection criteria IDF field.
-   NIDF: Character string specifying the selection criteria NIDF field.
-   MSG: Character string specifying the selection criteria MSG field.
-   SUSER: Character string specifying the selection criteria SUSER field.
-   RUSER: Character string specifying the selection criteria RUSER field.
-   SAPPL: Character string specifying the selection criteria Sappl field.
-   SPART: Character string specifying the selection criteria SPART field.
-   RAPPL: Character string specifying the selection criteria RAPPL field.
-   RPART: Character string specifying the selection criteria RPART field.
-   PARM: Character string specifying the criteria for selecting the PARM field.
-   STATED: Character string specifying the selection criteria field STATED field
-   FRECFM: Character string specifying the selection criteria field FRECFM field
-   NRECFM: Character string specifying the selection criteria field NRECFM field
-   FNAME: Character string specifying the selection criteria for the FNAME field
-   NFNAME: Character string specifying the selection criteria field NFNAME field
-   DIAGI: Character string specifying the selection criteria for the DIAGI field
-   DIAGP: Character string specifying the selection criteria for the DIAGP
-   FLRECL: Character string specifying the selection criteria for the FLRECL
-   NLRECL: Character string specifying the selection criteria for the NLRECL
-   FBLKSIZE: Character string specifying the selection criteria for the FBLKSIZE
-   NBLKSIZE: Character string specifying the selection criteria for the NBLKSIZE
-   USERID: Character string specifying the selection criteria for the USERID
-   JOBNAME: Character string specifying the selection criteria for the JOBNAME
-   PROT: Character string specifying the selection criteria for the PROT
-   PRI: Character string specifying the selection criteria for the PRI
-   NCOMP: Character string specifying the selection criteria for the NCOMP
-   FSPACE: Character string specifying the selection criteria for the FSPACE
-   NSPACE: Character string specifying the selection criteria for the NSPACE
-   NCODE: Character string specifying the selection criteria for the NCODE
-   FCODE: Character string specifying the selection criteria for the FCODE
-   FREC: Character string specifying the selection criteria for the FREC
-   NREC: Character string specifying the selection criteria for the NREC
-   FCAR: Character string specifying the selection criteria for the FCAR
-   NCAR: Character string specifying the selection criteria for the NCAR
-   ECAR: Character string specifying the selection criteria for the ECAR
-   FTIME Character string specifying the selection criteria for the FDATE
-   FDATE Character string specifying the selection criteria for the FTIME
-   FRECFM character identifying the value of the parameter F/V/U
-   NRECFM character identifying the value of the parameter F/V/U
-   FTEMOIN: String specifying the name of the comparison file.

### GETCAT

#### Syntax

No parameters are supplied for this command. The GETCAT function searches the catalog record corresponding to the selection criteria indicated by the BEGSELCA command parameters. If a record matches the criteria, predefined variables are initialized and can be exploited.

The predefined variable \_CMDRET is always 0 for OK, and cannot be tested to see if the read was successful or not. In cases where there are additional transfers that meets the criteria, the variables \_CAT\_PART, and \_CAT\_IDT \_CAT\_IDTU have the keyword value of NIL.

This enables you to compare the value of the partner string NIL to see if the read action is complete. See the ENDSELCA example in the following section.

### ENDSELCA

#### Syntax

The ENDSELCA function finishes the selection reading. This command is imperative to close the catalog.

#### Example

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>LONG NAME = VAR, INIT = 0</p>
            <p>LONG NAME = CMP, INIT = 0</p>
            <p>CHAR NAME = STRNIL , SIZE = 10, INIT = NIL</p>
            <p>CHAR NAME = PART , SIZE = 10</p>
            <p>/* set the variable _ECHO to 0 to exclude messages related to  WHILE and IF */</p>
            <p>/* to customize the display. */</p>
            <p>_MOV NAME=_ECHO,VALUE=0</p>
            <p>BEGSELCA DIRECT=SEND,DIAGI=406</p>
            <p>PRINT MSG='Partner DTSA File Transfer Diags Appli. '</p>
            <p>PRINT MSG=' Id. Id. CFT Protocol Id. '</p>
            <p>PRINT MSG='-------- ---- -------- -------- --- -------- --------'</p>
            <p>WHILE NAME = VAR, VALUE = 0, TYPE = EQU</p>
            <p>GETCAT</p>
            <p>Deleted: 1.3.</p>
            <p>Deleted: 1.3.1.</p>
            <p>Deleted: 1.3.</p>
            <p>Deleted: 1.3.1.</p>
            <p>Deleted:</p>
            <p>13</p>
            <p>_STRCPY NAME=PART, STR=%_CAT_PART%</p>
            <p>_STRCMP NAME=PART, STR=STRNIL ,RC=CMP</p>
            <p>IF NAME=CMP, VALUE=0, TYPE=EQU</p>
            <p>BRKWHILE</p>
            <p>ENDIF</p>
            <p>PRINT MSG='%[-8.8]_CAT_PART% %_CAT_DIRECT%%_CAT_TYP%%_CAT_STATE% %[-</p>
            <p>8.8]_CAT_IDF% %_CAT_IDT% %_CAT_DIAGI% %_CAT_DIAGP% %_CAT_IDA%'</p>
            <p>ENDWHILE</p>
            <p>ENDSELCA</p>
            <p>EXIT</p>
         </td>
      </tr>
   </tbody>
</table>

### MQUERY

#### Syntax

The MQUERY command displays the current log content, the catalog and cache for the Transfer CFT.

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>MQUERY OBJECT = STR,</p>
            <p>       CONTENT = STR,</p>
            <p>       NAME = STR,</p>
         </td>
      </tr>
   </tbody>
</table>

#### Parameters

-   OBJECT: Possible values ​​are:
    -   CACHE: Select to list the Transfer CFT catalog or command cache.
    -   SYSTEM: Lists system information.
-   CONTENT: Possible values ​​are FUL / BRIEF.
-   NAME: Possible values ​​are:
    -   CAT: Lists  the catalog cache.
    -   COMMAND: Lists  the command cache.

#### Example

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>MQUERY NAME=CAT,CONTENT=FULL</p>
            <p>CFTI24I  =========================== TRANSFERS ==================================</p>
            <p>CFTI24I  pri    minTime    minDate    reqTime    reqDate    cat_blk part</p>
            <p>CFTI24I  ======================================================================</p>
            <p>CFTI24I  Transfers_Non_Ready    : 3</p>
            <p>CFTI24I  128   11:52:27      TODAY   11:50:27      TODAY 180 LOOP</p>
            <p>CFTI24I  128   12:15:50      TODAY   11:50:50      TODAY 182 LOOP</p>
            <p>CFTI24I  128   12:40:41      TODAY   11:50:41      TODAY 181 LOOP</p>
            <p>CFTI24I  Transfers_Ready        : 0 ( 0 Partners )</p>
            <p>CFTI24I  Transfers_Time__Locked : 0 ( 0 Partners )</p>
            <p>CFTI24I  Transfers_State_Locked : 0 ( 0 Partners )</p>
            <p>CFTI24I  ======================== PARTNERS =====================================</p>
            <p>CFTI24I  name     count state locked diag    diagp    minTime    minDate</p>
            <p>CFTI24I  ======================================================================</p>
            <p>CFTI24I  Partners               : 1</p>
            <p>CFTI24I  LOOP         3  NRDY      0    0</p>
            <p>CFTI24I  Partners_Ready         : 0</p>
            <p>CFTI24I  Partners_Time__Locked  : 0</p>
            <p>CFTI24I  Partners_State_Locked  : 0</p>
            <p>MQUERY  Treated for USER userid</p>
         </td>
      </tr>
   </tbody>
</table>
