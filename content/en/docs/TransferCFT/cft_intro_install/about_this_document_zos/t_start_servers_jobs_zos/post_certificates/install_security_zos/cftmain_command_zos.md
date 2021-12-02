{
    "title": "CFTMAIN controlled commands",
    "linkTitle": "CFTMAIN controlled commands",
    "weight": "360"
}This section lists the Transfer CFT z/OS CFTUTIL commands, and additional object and class information for:

-   Users with all rights except for the ALL\_CAT object

<!-- -->

-   Users with all rights to the ALL\_CAT object

<!-- -->

-   Users with all rights

## User with all right except for the ALL\_CAT object

FILE(ACCESS): PARM(READ), PART(READ), COM(UPD), CATLG(UPD), LOG(UPD).

```
Command
Object
Class
Variable
UserID
Action
START
APPL
applcls
&ID
Cmduser
Control
HALT
APPL
applcls
&ID
Cmduser
Control
KEEP
APPL
applcls
&ID
Cmduser
Control
END
APPL
applcls
&ID
Cmduser
Control
SUBMIT
APPL
applcls
&ID
Cmduser
Control
DELETE
APPL
applcls
&ID
Cmduser
Delete
```

## User with all rights to the ALL\_CAT object

FILE(ACCESS): PARM(READ), PART(READ), COM(UPD), CATLG(UPD), LOG(UPD).

```
Command
Object
Class
Variable
UserID
Action
START
ALL\_CAT
opercls
&FNAME
Cmduser
Control
HALT
ALL\_CAT
opercls
&FNAME
Cmduser
Control
KEEP
ALL\_CAT
opercls
&FNAME
Cmduser
Control
END
ALL\_CAT
opercls
&FNAME
Cmduser
Control
SUBMIT
ALL\_CAT
opercls
&FNAME
Cmduser
Control
DELETE
ALL\_CAT
opercls
&FNAME
Cmduser
Delete
```

## User with all rights

FILE(ACCESS):PARM(READ), PART(READ), COM(UPD), CATLG(UPD), LOG(UPD).

```
Command
Object
Class
Variable
UserID
Action
Notes
SHUT
SHUT
cmdecls
 
Cmduser
Create
 
MQUERY
MQUERY
cmdecls
 
Cmduser
Create
 
SWITCH LOG
SWT\_LOG
cmdecls
 
Cmduser
Create
 
SWITCH  ACCOUNT
SWT\_ACNT
cmdecls
 
Cmduser
Create
 
RECV FILE
 
(Requester/ receiver)
 
APPL
applcls
&ID
Cmduser
Create
 
TRANSFER
xfercls
&MODE, &PART, &IDF, &SPART,  &RPART,  &IPART
Appluser
Create
In receive mode, the &FNAME variable is ignored.
File sending
 
(Server/sender)
APPL
applcls
&ID
Cmduser
Create
 
TRANSFER
xfercls
&MODE, &PART, &IDF, &SPART, &RPART, &IPART, &FNAME
Appluser
 
Create
 
Include PDS and GDG cases (\*)
FILE
filecls
&FNAME
Appluser
Read
 
Not applicable
SEND FILE
 
(Requester/ sender)
APPL
applcls
&ID
Cmduser
Create
 
TRANSFER
xfercls
&MODE, &PART, &IDF, &SPART, &RPART, &IPART, &FNAME
Appluser
 
Create
 
Include PDS and GDG cases (\*)
FILE
filecls
&FNAME
Appluser
Read
Not applicable
File reception
(Server/ receiver)
TRANSFER
xfercls
&MODE, &PART, &IDF, &SPART, &RPART, &IPART
Appluser
Create
In receive mode, the &FNAME variable is ignored.
SEND MESSAGE
(Requester/ sender)
APPL
applcls
&ID
Cmduser
Create
 
MESSAGE
messcls
&MODE, &PART, &IDM, &SPART, &RPART
Appluser
Create
 
Message reception
(Server/ receiver)
MESSAGE
messcls
&MODE, &PART, &IDM, &SPART, &RPART
Appluser
 
Create
 
 
SEND REPLY
(Requester/ sender)
APPL
applcls
&ID
Cmduser
 
Create
 
 
Reply reception
(Server/ receiver)
APPL
applcls
&ID
Trfuser
Create
 
(\*)  If GDG &FNAME=CFTV2.GDGHAB(0)
     Or         &FNAME=CFTV2.GDGHAB.G0002V00
     If PDS   &FNAME=CFTV2.INSTALL(D40INIT)
Appluser = System user (TSO) of the user defined by the CFTAPPL command.
Trfuser = System user (TSO) of the original file transfer owner.
```
