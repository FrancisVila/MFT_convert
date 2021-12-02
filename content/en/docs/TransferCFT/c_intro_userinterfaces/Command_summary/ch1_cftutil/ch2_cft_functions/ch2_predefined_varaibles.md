{
    "title": "CFTUTIL predefined variables",
    "linkTitle": "CFTUTIL predefined variables",
    "weight": "280"
}A number of variables are predefined in CFTUTIL for the catalog fields. These variables can be used in all of the batch programming commands.

Each variable begins with the underscore character \_. For example, to display the IDTU value of a transfer, specify:

```
PRINT MSG='Transfer IDTU value: %\_CAT\_IDTU%'
```

```

Variable

Description

\_CAT\_CFTV
Catalog version.
\_CAT\_COMMENT
Comment associated with the IDF.
\_CAT\_DATEB
Transfer start date.
\_CAT\_DATEC
IDF cycledate value.
\_CAT\_DATED
Transfer filing date.
\_CAT\_DATED
End of transfer date.
\_CAT\_DATEK
Date of last writing.
\_CAT\_DATEM
Value of the IDF MINDATE parameter.
\_CAT\_DATEMAX
Value of the IDF MAXDATE parameter.
\_CAT\_DEST
CFTDEST command identifier.
\_CAT\_DIAGC
Additional diagnostic value.
\_CAT\_DIAGI
Internal diagnostic value.
\_CAT\_DIAGP
Diagnostic protocol value.
\_CAT\_DIFTYP
Broadcast type:

-   L for broadcasting to
    multiple partners.
-   N for sending to a single partner.

\_CAT\_DIRECT
Transfer direction.
\_CAT\_EXEC
IDF procedure name.
\_CAT\_FACTION
FACTION parameter value.
\_CAT\_FCOMP
FCOMP parameter value.
\_CAT\_FDISP
FDISP parameter value.
\_CAT\_FILTYP
File type:

-   L for file list.
-   N for normal file.

\_CAT\_FLAG
Indicates if the transfer mode is REQUESTER or SERVER.
\_CAT\_FNAME
Name of file to be transferred.
\_CAT\_FTNAME
Temporary file name.
\_CAT\_GROUP
Name of the group initiating the request.
\_CAT\_GROUPID
Name of the group that the transfer owner belongs to.
\_CAT\_IDA
Application identifier.
\_CAT\_IDEXIT
CFTEXIT command file type identifier.
\_CAT\_IDEXITA
CFTEXIT command directory type identifier.
\_CAT\_IDEXITE
CFTEXIT command ETEBAC3 type identifier.
\_CAT\_IDF
Identifier associated with the IDF.
\_CAT\_IDR
IDR value.
\_CAT\_IDT
PROTC value.
\_CAT\_IDTD
IDT value.
\_CAT\_IDTU
IDTU value.
\_CAT\_IPART
Channel partner value.
\_CAT\_JOBNAME
Name of the task for which the transfer was created.
\_CAT\_NCOMP
Network compression value.
\_CAT\_NFNAME
Network filename.
\_CAT\_NIDF
Network IDF value.
\_CAT\_NPART
Connection partner value.
\_CAT\_ORIGIN
Origin of owner of the transfer.
\_CAT\_PARM
PARM parameter value.
\_CAT\_PART
PART value.
\_CAT\_PIDF
The previous value of the file ID.
\_CAT\_PRI
Transfer priority.
\_CAT\_PROT
Associated CFTPROT identifier.
\_CAT\_PROTC
PROTC value.
\_CAT\_RAPPL
RAPPL parameter value.
\_CAT\_RELANCE
Indicates if there was a restart or not.
\_CAT\_REQGROUP
Value of the initiator group for the command.
\_CAT\_REQUSER
Value of the user initiating the command.
\_CAT\_RPART
File receiving partner.
\_CAT\_RUSER
RUSER parameter value.
\_CAT\_SAPPL
SAPPL parameter value.
\_CAT\_SGD
Date
\_CAT\_SGT
Time
\_CAT\_SPART
SPART parameter value.
\_CAT\_STATE
State of the local transfer.
\_CAT\_STATED
State of the remote transfer.
\_CAT\_SUSER
SUSER parameter value.
\_CAT\_TCYCLE
TCYCLE parameter value.
\_CAT\_TIMEB
Transfer start time.
\_CAT\_TIMEC
TCYCLE parameter value.
\_CAT\_TIMED
Creation time of the transfer.
\_CAT\_TIMEE
Transfer end time.
\_CAT\_TIMEK
Time of last writing.
\_CAT\_TIMEM
MINTIME parameter value.
\_CAT\_TIMEMAX
MAXTIME parameter value.
\_CAT\_TIMMAXC
Maximum time for a call.
\_CAT\_TIMMC
Minimum time for a call.
\_CAT\_TYP
Transfer type.
\_CAT\_USERID
Transfer owner.
\_CAT\_XLATE
Associated CFTXLATE identifier card.
\_CAT\_FDBNAME
VFM name used for transfer.
```
