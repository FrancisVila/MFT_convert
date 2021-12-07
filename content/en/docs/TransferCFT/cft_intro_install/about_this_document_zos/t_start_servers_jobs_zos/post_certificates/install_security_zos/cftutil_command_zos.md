{
    "title": "CFTUTIL commands for z/OS",
    "linkTitle": "CFTUTIL commands for z/OS",
    "weight": "350"
}This section lists the Transfer CFT z/OS CFTUTIL commands, and additional object and class information for:

-   Users with all rights

<!-- -->

-   Users with all rights except for the $CFTOPER class

## User with all rights

```
Command
Object
Class
VARS
UserID
Actions
File/ACC
Notes
ABOUT
 
 
 
 
 
 
No control
PURGE
 
 
 
 
 
COM(UPDATE)
No control
COPYFILE
 
 
 
 
 
 
No control
CFTFILE
 
 
 
 
Cr/De
PART(ALTER)
PARM(ALTER)
CATLG(ALTER)
LOG(ALTER)
COM(ALTER)
No control
CFTPARM
CFTPARM
parmcls
&ID
Cmduser
Cr/De/Mo
PARM(UPDATE)
 
CFTCOM
CFTCOM
parmcls
&ID
Cmduser
Cr/De/Mo
PARM(UPDATE)
 
CFTCAT
CFTCAT
parmcls
&ID
Cmduser
Cr/De/Mo
PARM(UPDATE)
 
CFTLOG
CFTLOG
parmcls
&ID
Cmduser
Cr/De/Mo
PARM(UPDATE)
 
CFTACCNT
CFTACCNT
parmcls
&ID
Cmduser
Cr/De/Mo
PARM(UPDATE)
 
CFTAPPL
CFTAPPL
parmcls
&ID
Cmduser
Cr/De/Mo
PARM(UPDATE)
 
CFTSEND
CFTSEND
parmcls
&ID
Cmduser
Cr/De/Mo
PARM(UPDATE)
 
CFTSEND IMPL=YES
CFTSENDI
parmcls
&ID
Cmduser
Cr/De/Mo
PARM(UPDATE)
 
CFTRECV
CFTRECV
parmcls
&ID
Cmduser
Cr/De/Mo
PARM(UPDATE)
 
CFTEXIT
CFTEXIT
parmcls
&ID
Cmduser
Cr/De/Mo
PARM(UPDATE)
 
CFTAUTH
CFTAUTH
parmcls
&ID
Cmduser
Cr/De/Mo
PARM(UPDATE)
 
CFTIDF
CFTIDF
parmcls
&ID
Cmduser
Cr/De/Mo
PARM(UPDATE)
 
CFTXLATE
CFTXLATE
parmcls
&ID
Cmduser
Cr/De/Mo
PARM(UPDATE)
 
CFTNET
CFTNET
parmcls
&ID
Cmduser
Cr/De/Mo
PARM(UPDATE)
 
CFTPROT
CFTPROT
parmcls
&ID
Cmduser
Cr/De/Mo
PARM(UPDATE)
 
CFTETB
CFTETB
parmcls
&ID
Cmduser
Cr/De/Mo
PARM(UPDATE)
 
CFTPART
CFTPART
parmcls
&ID
Cmduser
Cr/De/Mo
PART(UPDATE)
 
CFTDEST
CFTDEST
parmcls
&ID
Cmduse
Cr/De/Mo
PART(UPDATE)
 
CFTTCP
CFTTCP
parmcls
&ID
Cmduser
Cr/De/Mo
PART(UPDATE)
 
 
 
 
 
 
 
 
 
UCONFGET
UCONF
 
&ID
Cmduser
Read
UCONF(READ)
 
UCONFSUBST
UCONF
 
&ID
Cmduser
Read
UCONF(READ)
 
LISTCUCONF
UCONF
 
&ID
Cmduser
Read
UCONF(UPDATE)
 
UCONFSET
UCONF
 
&ID
Cmduser
Modify
UCONF(UPDATE)
 
UCONFUNSET
UCONF
 
&ID
Cmduser
Delete
UCONF(UPDATE)
 
 
 
 
 
 
 
 
 
CFTEXT
ALL_PARM
opercls
&FNAME
Cmduser
Read
PARM(READ)
 
ALL_PART
opercls
&FNAME
Cmduser
Read
PART(READ)
 
LISTCAT
ALL_CAT
opercls
&FNAME
Cmduser
Read
CATLG(READ)
 
LISTPARM
ALL_PARM
opercls
&FNAME
Cmduser
Read
PARM(READ)
 
LISTPART
ALL_PART
opercls
&FNAME
Cmduser
Read
PART(READ)
 
LISTCOM
ALL_COM
opercls
&FNAME
Cmduser
Read
COM(READ)
 
 
 
 
 
 
 
 
 
ACT
ACT
cmdecls
 
Cmduser
Create
PART(UPDATE)
 
ALL_PART
opercls
&FNAME
Cmduser
Read
CFTPART
parmcls
&ID
Cmduser
Control
INACT
 
INACT
cmdercls
 
Cmduser
Create
PART(UPDATE)
 
ALL_PART
opercls
&FNAME
Cmduser
Read
CFTPART
parmcls
&ID
Cmduser
Control
 
Cmduser = System user (TSO) of the user submitting the command.
```

## User with all rights except the $CFTOPER class

```
Command
Object
Class
VARS
UserID
Actions
File/ACC
Notes
ABOUT
 
 
 
 
 
 
No control
PURGE
 
 
 
 
 
COM(UPDATE)
No control
COPYFILE
 
 
 
 
 
 
No control
CFTFILE
 
 
 
 
Cr/De
 
PART(ALTER)
PARM(ALTER)
CATLG(ALTER)
LOG(ALTER)
COM(ALTER)
No control
CFTPARM
CFTPARM
parmcls
&ID
Cmduser
Cr/De/Mo
PARM(UPDATE)
 
CFTCOM
CFTCOM
parmcls
&ID
Cmduser
Cr/De/Mo
PARM(UPDATE)
 
CFTCAT
CFTCAT
parmcls
&ID
Cmduser
Cr/De/Mo
PARM(UPDATE
 
CFTLOG
CFTLOG
parmcls
&ID
Cmduser
Cr/De/Mo
PARM(UPDATE)
 
CFTACCNT
CFTACCNT
parmcls
&ID
Cmduser
Cr/De/Mo
PARM(UPDATE)
 
CFTAPPL
CFTAPPL
parmcls
&ID
Cmduser
Cr/De/Mo
PARM(UPDATE)
 
CFTSEND
CFTSEND
parmcls
&ID
Cmduser
Cr/De/Mo
PARM(UPDATE)
 
CFTSEND IMPL=YES
CFTSENDI
parmcls
&ID
Cmduser
Cr/De/Mo
PARM(UPDATE)
 
CFTRECV
CFTRECV
parmcls
&ID
Cmduser
Cr/De/Mo
PARM(UPDATE)
 
CFTEXIT
CFTEXIT
parmcls
&ID
Cmduser
Cr/De/Mo
PARM(UPDATE)
 
CFTAUTH
CFTAUTH
parmcls
&ID
Cmduser
Cr/De/Mo
PARM(UPDATE)
 
CFTIDF
CFTIDF
parmcls
&ID
Cmduser
Cr/De/Mo
PARM(UPDATE)
 
CFTXLATE
CFTXLATE
parmcls
&ID
Cmduser
Cr/De/Mo
PARM(UPDATE)
 
CFTNET
CFTNET
parmcls
&ID
Cmduser
Cr/De/Mo
PARM(UPDATE)
 
CFTPROT
CFTPROT
parmcls
&ID
Cmduser
Cr/De/Mo
PARM(UPDATE)
 
CFTETB
CFTETB
parmcls
&ID
Cmduser
Cr/De/Mo
PARM(UPDATE)
 
CFTPART
CFTPART
parmcls
&ID
Cmduser
Cr/De/Mo
PART(UPDATE)
 
CFTDEST
CFTDEST
parmcls
&ID
Cmduser
Cr/De/Mo
PART(UPDATE)
 
CFTTCP
CFTTCP
parmcls
&ID
Cmduser
Cr/De/Mo
PART(UPDATE)
 
CFTEXT
CFTxxx\*
parmcls
&ID
Cmduser
Read
PARM(READ)
CFTyyy\*
parmcls
&ID
Cmduser
Read
PART(READ)
LISTPARM
CFTxxx\*
parmcls
&ID
Cmduser
Read
PARM(READ)
 
LISTPART
CFTyyy\*
parmcls
&ID
Cmduser
Read
PART(READ)
 
LISTCAT
APPL
applcls
&ID
Cmduser
Read
CATLG(READ)
 
LISTCOM
 
 
 
 
 
 
Access denied
ACT
 
ACT
cmdecls
 
Cmduser
Create
PART(UPDATE)
 
CFTPART
parmcls
&ID
Cmduser
Read
CFTPART
parmcls
&ID
Cmduser
Control
INACT
 
INACT
cmdecls
 
Cmduser
Create
PART(UPDATE)
 
CFTPART
parmcls
&ID
Cmduser
Read
CFTPART
parmcls
&ID
Cmduser
Control
 
CFTxxx\* = PARM file configuration commands.
CFTyyy\* = PART file configuration commands.
```
