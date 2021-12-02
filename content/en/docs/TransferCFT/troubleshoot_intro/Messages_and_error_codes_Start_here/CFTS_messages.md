{
    "title": "Transfer CFT messages: CFTS",
    "linkTitle": "CFTS messages",
    "weight": "360"
}This topic lists the CFTSxx (CFT xnnx) messages and provides the type, a description, consequence, and corrective actions when applicable.

**Message format**

Earlier versions of Transfer CFT used a different message format than version 3.1.3 and higher. This document displays both formats when applicable and available, otherwise only the v23 is used. Using the CFTLOG Format = V24 setting, the log displays as shown:

CFTXXX: fixed text message &lt;variables>

**Example**

CFTLOG FORMAT=\[V23,V24\]

For V23: `CFTT57I PART=&part IDF=&idf IDT=&idt &str transfer started`

For V24: `CFTT57I &str transfer started   <IDTU=&idtu PART=&part IDF=&idf IDT=&idt>`

```
V23 format
V24 format
Warning
<span id="CFTS01W"></span>CFTS01W Synch. response time-out \_ Waitresp increased to &ns (&str)
CFTS01W Synch. response time-out \_ Waitresp increased to &ns (&str)
Explanation
The message placed in a synchronous queue has received no response
(time limit has expired).
Where:

-   &n is the value in seconds of the new WAITRESP
-   &str is either CFTTCOM or CFTTFIL, the process who wrote the message

Consequence
Another attempt will be made.
```

 

```
V23 format
V24 format
Error
<span id="CFTS02E"></span>CFTS02E PART=&part \[IDF=&idf | IDM=&idm\]
IDT=&idt DIRECT=&direct  &fname not found
CFTS02E \_ &fname not found <IDTU=&idtu PART=&part \[IDF=&idf | IDM=&idm\] IDT=&idt DIRECT=&direct>
Explanation
The &fname
procedure was not found for a given transfer (&idt).
This procedure
was requested after a file or message transfer or subsequent to an error
(see the {{< TransferCFT/componentshortname >}} Online documentation, EXEC parameters).
```

 

```
V23 format
V24 format
Information
<span id="CFTS03I"></span>CFTS03I PART=&part \[IDF=&idf | IDM=&idm\]IDT=&idt
\_ &fname submitted
CFTS03I \_ &fname submitted<IDTU=&idtu PART=&part \[IDF=&idf | IDM=&idm\] IDT=&idt> (&n sec)
Explanation
The procedure
(&fname) was submitted for a given transfer (&idt).
This procedure
was requested at the end of a file or message transfer, or in the event
of an error (see the
EXECxxx parameters).
```

 

```
V23 format
V24 format
Warning
<span id="CFTS04W"></span>CFTS04W Action file &fname is empty
CFTS04W Action file &fname is empty
Explanation
An action
is envisaged at the end of a transfer or in the event of an error (see
the {{< TransferCFT/componentshortname >}} Online documentation, EXECxxx
parameters); the file to be submitted is empty.
```

 

```
V23 format
V24 format
Error
<span id="CFTS05E"></span>CFTS05E Error code &scs \_ Trying to
access &str
CFTS05E Error code &scs \_ Trying to access &str
Explanation
An access error was detected on a file.
This file (&fname) corresponds to an action requested
at the end of a transfer or in the event of an error (see the Transfer
CFT Online
documentation EXECxxx parameters).
The &str variable can
have the following values:
&fname
Consequence
The procedure will not be executed. If the action was requested
at the end of a transfer, the transfer ends normally.
Action
Check that the characteristics of the file to be submitted are
correct (attributes and length) and inform Product Support if necessary.
```

 

```
V23 format
V24 format
Error
<span id="CFTS06E"></span>CFTS06E Error code &scs \_ Trying to access temporary
file
CFTS06E Error code &scs \_ Trying to access temporary file
Explanation
An action
was requested at the end of a transfer or in the event of an error. This
action is submitted (see the
EXECxxx parameters) through a buffer file (&fname).
An access
error was detected on this buffer file.
Consequence
The procedure will not be executed. If the action was requested
at the end of the transfer, the transfer ends normally.
Action

-   Check
    that the characteristics of the buffer file are correct (attributes and
    length).
-   Check that it
    exists (created or defined logically in the {{< TransferCFT/componentshortname >}} startup procedure).
-   Contact Product Support.

```

 

```
V23 format
V24 format
Error
<span id="CFTS07E"></span>CFTS07E Insufficient space for temporary file
CFTS07E Insufficient space for temporary file
Explanation
An action
was requested at the end of a transfer or in the event of an error. This
action is submitted (see the {{< TransferCFT/componentshortname >}} Online documentation,
EXECxxx parameters) through a buffer file (&fname). The space reserved
for this file proves insufficient.
Consequence
The procedure will not be executed. If the action was requested
at the end of the transfer, the transfer ends normally.
Action
Increase the file size, inform Product Support.
```

 

```
V23 format
V24 format
Error
<span id="CFTS08E"></span>CFTS08E Error code &scs \_ Executing temporary file
CFTS08E Error code &scs \_ Executing temporary file
Explanation
The procedure
(&fname) could not be executed for a given transfer (&idt).
This procedure
was requested at the end of a file or message transfer or in the event
of an error (see the {{< TransferCFT/componentshortname >}} Online documentation
EXECxxx parameters).
Consequence
The procedure will not be executed. If the action was requested
at the end of the transfer, the transfer ends normally.
Action
Analyze the &scs code and inform Product Support if necessary.
```

 

```
V23 format
V24 format
Error
<span id="CFTS10E"></span>CFTS10E File communication task error (&str1) \_
&str2
CFTS10E File communication task error (&str1) \_ &str2
Explanation
Following a synchronous message queue time-out, the communication
task aborted.
The str1 and str2 values are:
str1
Associated str2 value
define sem
terminating
open
terminating
memory
terminating
post
terminating
invalid sem
terminating
catalog full
terminating
<cs code>
terminating
read
continue
delete shut
continue
Action
Contact
Axway Support.
```

 

```
V23 format
V24 format
Error
<span id="CFTS11E"></span>CFTS11E Allocation error \_ Trying to access temporary
file
CFTS11E Allocation error \_ Trying to access temporary file
Explanation
An action
was requested at the end of a transfer or in the event of an error.
This action
is submitted (see the {{< TransferCFT/componentshortname >}} Online documentation,
EXECxxx parameters) through a buffer file (&fname). An allocation
error was detected on this buffer file.
Consequence
The procedure will not be executed. If the action was requested
at the end of the transfer, the transfer ends normally.
Action

-   Check that the
    characteristics of the buffer file are correct (attributes and length).
-   Check that it
    exists (created or defined logically in the {{< TransferCFT/componentshortname >}} startup procedure).
-   Contact
    Product Support.

```

 

```
V23 format
V24 format
Warning
<span id="CFTS12W"></span>CFTS12W Error code &scs \_ CFT write messages to
output stream
CFTS12W Error code &scs \_ CFT write messages to output stream
Explanation
The Transfer
CFT logging process can no longer write messages in the log file(s) (problem
adding to the file, system incident).
Consequence
Transfer
CFT messages will be written to the standard output (screen for example).
Action
Analyze the &scs code and inform Product Support if necessary.
```

 

```
V23 format
V24 format
Error
<span id="CFTS13E"></span>CFTS13E Semaphore failure &cs\_CFTTPRO aborted
CFTS13E Semaphore failure &cs\_CFTTPRO aborted
Explanation
Problem
receiving an internal {{< TransferCFT/componentshortname >}} message by the PROTOCOL task.
Consequence
A message has perhaps been lost; the reactions are unpredictable.
Action
Analyze the &scs code and inform Product Support if necessary.
```

 

```
V23 format
V24 format
Error
<span id="CFTS14E"></span>CFTS14E ID=&id error initializing process
CFTS14E Unknown synchronization message CLASS=&class TYPE=&type
Explanation
Cannot run the end of transfer exit task. This message follows the {{< TransferCFT/componentshortname >}} message CFTI01.
Consequence
No effect on the actual transfer (catalog not updated). The exit
is not executed. If an end of transfer procedure was defined, it is run.
Action
Inform Product Support.
```

 

```
Information
<span id="CFTS15I"></span>CFTS15I PART = &part Kill Session Reference &ctx:&ctx
CFTS15I PART = &part Kill Session Reference &ctx:&ctx
Explanation
Internal message to {{< TransferCFT/componentshortname >}} giving information on the transfer
context killed. The &ctx values specify the context concerned.
```

 

```
V23 format
V24 format
Error
<span id="CFTS16E"></span>CFTS16E Synch. response time-out\_End transfer exit
CFTS16E Synch. response time-out \_ End of transfer exit
Explanation
The exit
task is run but does not respond to the {{< TransferCFT/componentshortname >}}. This corresponds
to the initial phase establishing communications between the {{< TransferCFT/componentshortname >}} and
the exit task.
Consequence
None on the actual transfer (catalog not updated). The exit
is not executed. If an end of transfer procedure has been defined, it
is run.
Action
Inform Product Support.
```

 

```
V23 format
V24 format
Error
<span id="CFTS17E"></span>CFTS17E Error code &scs \_ Trying to access End transfer
exit
CFTS17E Error code &scs \_ Trying to access End of transfer exit
Explanation
Error posting a {{< TransferCFT/componentshortname >}} message to the exit task during inter-task
communications.
Consequence
None on the actual transfer (catalog not updated). The exit
is does not receive any directives from the {{< TransferCFT/componentshortname >}}.
Action
Inform Product Support.
```

 

```
V23 format
V24 format
Error
<span id="CFTS18W"></span><span id="CFTS18E"></span>CFTS18E PART=&part \[IDF=&idf | IDM=&idm\] IDT=&idt \_ Catalog record Update Error: &scs
CFTS18E \_ Catalog Update Error: &scs <IDTU=&idtu PART=&part \[IDF=&idf | IDM=&idm\] IDT=&idt>
Explanation
Transfer CFT catalog update issue with error code = &scs.
Consequence
The transfer record is not updated.
```

 

```
V23 format
V24 format
Warning
<span id="CFTS18W"></span>CFTS18W PART=&part \[IDF=&idf | IDM=&idm\]
IDT=&idt \_ Catalog record label
CFTS18W \_ Catalog record &label <IDTU=&idtu PART=&part \[IDF=&idf | IDM=&idm\] IDT=&idt>
Explanation
Label
equals "State not updated x -> y" (x = current state,
y = requested state) or "not deleted".
Transfer
CFT catalog update issue.
Consequence
The catalog entry corresponding to the transfer is not updated.
Action
Inform Product Support.
```

 

```
V23 format
V24 format
Information
<span id="CFTS19I"></span>CFTS19I PART=&part \[IDF=&idf | IDM=&idm\]IDT=&idt
\_ Catalog record label
CFTS19I \_ Catalog record &str <IDTU=&idtu PART=&part \[IDF=&idf | IDM=&idm\] IDT=&idt>
Explanation
Information
message label equals "updated x to y"  (x = current
state, y = requested state) or "deleted". The Transfer
CFT catalog is updated.
```

 

```
V23 format
V24 format
Information
<span id="CFTS20I"></span>CFTS20I Communication file row number deleted: nnnnnnnn (&str)
CFTS20I &str", &str = Communication file row number deleted: nnnnnnnn
or File communication task INIT (&n,WSCAN=&wscan,RET=&ret)
Explanation
Communication file related message where the 8 digits (n) represent the record number.
If the jobname is set in the catalog, then the information <JOBNAME=PID> (all platforms except z/OS) or <JOBNAME=jobname jobid> (z/OS platforms) displays in the message in place of (&str).
```

 

```
V23 format
V24 format
Information
<span id="CFTS21I"></span>CFTS21I PART=&part \[IDF=&idf | IDM=&idm\]IDT=&idt
Exit request ID=&id
CFTS21I Exit request ID=&id <IDTU=&idtu PART=&part \[IDF=&idf | IDM=&idm\] IDT=&idt>
Explanation
Information message prior to sending information to the end
of transfer exit.
Consequence
None.
```

 

```
V23 format
V24 format
Information
<span id="CFTS22I"></span>CFTS22I Task time out End of transfer exit
CFTS22I Task time out End of transfer exit
Explanation
Exit task re-entry time-out. The task is stopped automatically.
Consequence
The exit task will be rerun by the next call.
Action
If necessary, increase the value of the WAITTASK parameter in
the CFTEXIT card.
```

 

```
V23 format
V24 format
Error
<span id="CFTS23E"></span>CFTS23E Bad user return code <details>
CFTS23E &str PART=&part \[IDF=&idf | IDM=&idm\] IDT=&idt ", &str = Bad End transfer exit version : &ver / &ver
or
CFTS23E &str <IDTU=&idtu PART=&part \[IDF=&idf | IDM=&idm\] IDT=&idt >") Invalid state transit '&state'->'&state' or Unknown state &state
or
Unknown action &action or Bad User return code : &scs
Explanation
Error message specific to the end-of-transfer user exit. The details that display in the message depend on the CFTLOG format (v23 or v24).
**Example**
V24 format:
`CFTS23E Bad User return code: 4 <IDTU=idtu PART=part1 IDF=idf1  IDT=idt >`
V23 format:
CFTS23E Bad User return code : 4 PART=part1 IDF=idf1 IDT=idt
Consequence
None.
```

 

```
V23 format
V24 format
Error
<span id="CFTS26E"></span>CFTS26E XTRK task error &str 
CFTS26E XTRK task error &str
Explanation
Error initializing the Sentinel monitoring task.
Action
Take note of the complete text of the message (&str) and
contact Axway Product Support. 
```

 

```
V23 format
V24 format
Error
<span id="CFTS27E"></span>CFTS27E Synchronous communication task error CR=&cr
&str
CFTS27E Synchronous communication task error CR= &cr &str
Explanation
Synchronous communication task error.
CR=&cr &str CFT

-   Internal synchronization error.
-   Password authentication error due to invalid user or password.

Consequence
Depending on the severity of the problem, the
synchronous communication task can be stopped or continued (and either Terminating or Continue is displayed in the accompanying message
&str).
Action
Notify Technical Support, if necessary. Furnish the complete
message as well as the synchronous
communication media parameters.
```

 

```
V23 format
V24 format
Information
<span id="CFTS29I"></span>CFTS29I Cannot acces XTRK task \_ &str
CFTS29I Cannot acces XTRK task \_ &str
Explanation
Problem in communication with the Sentinel monitoring task.
Action
Take note of the complete text of the message and contact Axway
Product Support. 
```

 

```
V23 format
V24 format
Information
<span id="CFTS30I"></span>CFTS30I XTRK Information &str
CFTS30I XTRK Information &str
Explanation
Elements of information concerning the Sentinel monitoring task.
The field "&str" is an explicit string:
“Buffer File Info : Current = nn , Max=mm”
where:

-   number
    of current records = nn
-   maximum
    number of records = mm

```

 

```
V23 format
V24 format
Warning
<span id="CFTS31W"></span>CFTS31W XTRK Warning &str Error Code = &cr
CFTS31W XTRK Warning &str Error Code = &cr
Explanation
The user is warned of a problem in communication with the Sentinel
Server or the Sentinel Agent. The message is stored in the overflow
file for the Sentinel monitoring task.
The text of the &str message specifies the possible
type of warning:
sendMessage : send of a message to Sentinel
```

 

```
V23 format
V24 format
Warning
<span id="CFTS32W"></span>CFTS32W TCOMS Connection
refused (address=nnn.nnn.nnn.nnn, name=userid)
CFTS32W TCOMS Connection
refused
Explanation
An incoming connection from name=userid and address=nnn.nnn.nnn.nnn
was rejected because this address is not authorized for Synchronous Communication.
See the CFTCOM object  ADDRLIST
parameter.
```

 

```
V23 format
V24 format
Information
<span id="CFTS33I"></span>CFTS33I CFTLOG current
file before switch
CFTS33I CFTLOG current file before switch :&fname
Explanation
For SWITCH LOG or SWITCH ACCNT:

-   Transfer
    CFT start-up
-   SWITCH
    operator
-   SWITCH
    cache command
-   SWITCH
    if file is full during a write
-   If no
    switch procedure is defined

```

 

```
V23 format
V24 format
Information
<span id="CFTS34I"></span>CFTS34I CFTLOG executed
switch proc
CFTS34I CFTLOG execute switch procedure : &fname
Explanation
For SWITCH LOG or SWITCH ACCNT:

-   Transfer
    CFT start-up
-   SWITCH
    operator
-   SWITCH
    cache command
-   SWITCH
    if file is full during a write
-   If no
    switch procedure is defined

```

 

```
V23 format
V24 format
Information
<span id="CFTS35I"></span>CFTS35I CFTLOG current
file after switch
CFTS35I CFTLOG current file after switch :&fname
Explanation
For SWITCH LOG or SWITCH ACCNT:

-   Transfer
    CFT start-up
-   SWITCH
    operator
-   SWITCH
    cache command
-   SWITCH
    if file is full during a write
-   If no
    switch procedure is defined

```

 

```
V23 format
V24 format
Information
<span id="CFTS36I"></span>CFTS36I CFTACCNT current
file (no switch executed)
CFTS36I CFTACCNT current file (no switch executed): &fname
Explanation
For SWITCH LOG or SWITCH ACCNT:

-   Transfer
    CFT start-up
-   SWITCH
    operator
-   SWITCH
    cache command
-   SWITCH
    if file is full during a write

<!-- -->

-   If the two CFTLOG
    files are full and are not performing the switch:

<!-- -->

-   CFTS36I CFTLOG
    current file (no switch executed): CFTOUT
-   If the two CFTACCNT
    files are full and are not performing the switch:
-   CFTS36I CFTACCNT
    current file (no switch executed): Files full

```

```
V23 format
V24 format
Information
 
<span id="CFTS37I"></span>CFTS37I CRONJOB ID=&idcron, CRONTAB=&cronname &exec executed, NEXT=&date
CFTS37I CRONJOB: ID=&idcron, CRONTAB=&cronname ACT DONE
CFTS37I CRONJOB: RECONFIG type=CRON DONE
Explanation
Job defined by &exec is executed correctly; the next submit is indicated in NEXT=date time.
```

[ ](../cfti_messages)

```
V23 format
V24 format
Warning  
<span id="CFTS39E"></span>CFTS38W CRONJOB NEXT TIME CALCUL FAILED, RETURN &ret
CFTS38W CRONJOB NEXT TIME CALCUL IS AFTER 2035, ABORTING, RETURN &ret
Explanation
Cronjob next time calcul failed. No time corresponding to filter was found. Cronjob is not executed.
or
Cronjob next time calculated is after 2035. Cronjob is not executed.
```

 

```
V23 format
V24 format
Error
 
<span id="CFTS39E"></span>
CFTS39E CRONJOB ID=&id, CRONTAB=&cronname exec &fname failed
CFTS39E CRONJOB: ID=&id INACT FAILED: CRONJOB Not Found
CFTS39E CRONJOB: ID=&id ACT FAILED: CRONJOB Not Found
Explanation
 Job failed. Could not file the file to submit. Check file properties.
```

 

```
V23 format
V24 format
Error
 
<span id="CFTS39E"></span>
CFTI40E OMVS SEGMENT NOT DEFINED for user=xxxxxx
CFTI40E OMVS SEGMENT NOT DEFINED for user=xxxxxx
Explanation
Reserved for z/OS systems.
```

 

```
V23 format
V24 format
Fatal
<span id="CFTS40F"></span>CFTS40F CFTACCNT FORMAT=(V23/V24) not available for &fname
CFTS40F CFTACCNT FORMAT=(V23|V24) not available for &fname
Explanation
An error occurred in the FORMAT=V23/V24 (V23 default) parameter of CFTFILE TYPE=ACCNT. When using the V23 format, the saved description (for ACCOUNT files) is the same as in previous versions. However when using the V24 format, the length for saving is 2048, and  the saved description takes into account the new longer field lengths.

> **Note:**
> The FORMAT parameter for the CFTACCNT command must be the same setting as for CFTFILE TYPE=ACCNT. If not, a message displays in the LOG and Transfer CFT doesnot start.

The message is either:
   CFTS40F CFTACCNT FORMAT=V24 not available for CFT.ACCNT    
   CFTS40F CFTACCNT FORMAT=V23 not available for CFT.ACCNT
Followed by the message: CFTI17F Init error \_ Account file .CFT.ACCNT

```

 

```
V23 format
V24 format
Information
<span id="CFTS41I"></span>CFTS41I Catalog Alert
exec &fname executed
CFTS41I Catalog Alert exec &fname executed
Explanation
The procedure &FNAME for a catalog alert was executed.

-   When the critical
    fill threshold is reached, a message CFTC29W is recorded in the Transfer
    CFT log.

A batch, which is defined by the CFTCAT TLVWEXEC parameter,
is submitted.

-   When
    the alert ceases, a message CFTC30W is recorded in the {{< TransferCFT/componentshortname >}} log.

A batch, which is defined by the CFTCAT TLVCEXEC parameter,
is submitted.
```

 

```
V23 format
V24 format
Error
<span id="CFTS42E"></span>CFTS42E Catalog Alert exec &fname &str" where &str= "not found" or "failed"
CFTS42E Catalog Alert exec &fname &str
Explanation
The procedure &FNAME for a catalog alert was not found
or failed on access producing this error.

-   When
    the critical fill threshold is reached, a message CFTC29W is recorded
    in the {{< TransferCFT/componentshortname >}} log.
    -   The batch, which is defined by the CFTCAT TLVWEXEC
        parameter, is not executed
-   When
    the alert ceases, a message CFTC30W is recorded in the {{< TransferCFT/componentshortname >}} log
    -   The batch, which is defined by the CFTCAT TLVCEXEC
        parameter, is not executed.

```

 

```
V23 format
 
V24 format
Information
<span id="CFTS43I"></span>CFTS43I &str", &str = RECONFIG PARM CACHE CFTMAIN or RECONFIG &task : Keep &key : &value or Parameter &task &value --> &value or RECONFIG &task 
CFTS43I &str
Explanation
Displays information about CFTUTIL RECONFIG TYPE=UCONF.
Wwhere &str = "RECONFIG PARM CACHE CFTMAIN "

-   &str = "RECONFIG &task : Keep &key : &value"
-   &str = "Parameter &task &value --> &value or RECONFIG &task"

```

 

```
V23 format
V24 format
Warning
<span id="CFTS44W"></span>CFTS44W Unexpected message Class &n <TASK=&str>
CFTS44W Unexpected Message Class &n <TASK=&task>
Explanation
An internal message received by the &str task has an unexpected class value (&n).
Consequence
The message is ignored.
```

 

```
V23 format
V24 format
Warning
<span id="CFTS45W"></span>CFTS45W Unexpected Message Class &n <TASK=&task>
CFTS45W Unexpected Message Type &n <TASK=&task CLASS=&n>
Explanation
An internal message received by the &str task with CLASS=&str has an unexpected type value (&n).
Consequence
The message is ignored.
```

 

```
V23 format
V24 format
Fatal
<span id="CFTS46F"></span>CFTS46F CFTPRX error \_ &str
CFTS46F CFTPRX error \_ &str
Explanation
A fatal error occurred in the proxy task (CFTPRX). The error details are in &str.
Consequence
{{< TransferCFT/componentshortname >}} stops.
Action
If necessary, contact Axway support.
```

 

```
V23 format
V24 format
Error
<span id="CFTS47E"></span>CFTS47E CFTPRX error \_ &str
CFTS47E CFTPRX error \_ &str
Explanation
A significant error occurred in the proxy task (CFTPRX). The error is detailed in &str.
Consequence
The concerned transfer goes into error.
Action
If necessary, contact Axway support.
```

 

```
V23 format
V24 format
Warning
<span id="CFTS48W"></span>CFTS48W CFTPRX \_ &str
CFTS48W CFTPRX \_ &str
Explanation
An anomaly occurred in the proxy task (CFTPRX). The anomaly details are in &str.
```

 

```
V23 format
V24 format
Information
<span id="CFTS49I"></span>CFTS49I CFTPRX \_ &str
CFTS49I CFTPRX \_ &str
Explanation
Information message from the Proxy task (CFTPRX). The &str value gives additional details.
```

 

```
V23 format
V24 format
Fatal
<span id="CFTS50F"></span>CFTS50F CFTJRE error \_ &str
CFTS50F CFTJRE error \_ &str
Explanation
A fatal error occurred when starting the CFT Java task (CFTJRE). The error is detailed in &str.
Consequence
{{< TransferCFT/componentshortname >}} is stopping.
Action
If necessary, contact {{< TransferCFT/platformorsuiteshortname >}} support.
```

 

```
V23 format
V24 format
Error
<span id="CFTS51E"></span>CFTS51E CFTJRE error \_ &str
CFTS51E CFTJRE error \_ &str
Explanation
A significant error occurred in the {{< TransferCFT/componentshortname >}} Java task (CFTJRE). The error is detailed in &str.
Consequence
The concerned transfer goes in error.
Action
If necessary, contact {{< TransferCFT/platformorsuiteshortname >}} support.
```

 

```
V23 format
V24 format
Warning
<span id="CFTS52W"></span>CFTS52W CFTJRE \_ &str
CFTS52W CFTJRE \_ &str
Explanation
An anomaly occurred in the {{< TransferCFT/componentshortname >}} Java task (CFTJRE). The anomaly is detailed in &str.
```

 

```
V23 format
V24 format
Error
<span id="CFTS53I"></span>CFTS53I CFTJRE \_ &str
CFTS53I CFTJRE \_ &str
Explanation
Information message from the {{< TransferCFT/componentshortname >}} Java task (CFTJRE). The &str value gives additional details.
```

 

```
V23 format
V24 format
Error
<span id="CFTS54F"></span>CFTS54F CFTACC task fatal CR=&cr &str
CFTS54F CFTACC task fatal CR= &cr &str
Explanation
A fatal error occurred in the accelerator task (CFTACC). The error is detailed in &str.
Consequence
{{< TransferCFT/componentshortname >}} is stopping.
Action
If necessary, contact Axway support.
```

 

```
V23 format
V24 format
Information
<span id="CFTS55I"></span>CFTS55I Acceleration &str
CFTS55I Acceleration &str
Explanation
Information message from the Accelerator task (CFTACC). the &str value gives more detail.
```

 

```
V23 format
V24 format
Error
<span id="CFTS56E"></span>CFTS56E Central Governance error (<error\_code>) <error\_msg>
CFTS56E Central Governance &str", &str = &type error (send): (&code) &message
CFTS56E Central Governance &str", &str = &type error (recv): (&code) &message
Explanation
An error occurred when executing a <request> on Central Governance.
Consequence
The {{< TransferCFT/componentshortname >}} instance does not display the correct status.
```

 

```
V23 format
 
V24 format
Warning
<span id="CFTS57W"></span>CFTS57W Synchronous communication \_ Authentication ignored - authentication\_enable=yes but authentication\_method=&auth\_method
CFTS57W Synchronous communication \_ Authentication ignored - authentication\_enable=yes but authentication\_method=&auth\_method
Explanation
Possible scenarios include:

-   Authentication\_enable=yes but authentication\_method=noneIn the unified configuration authentication is enabled, but no mode is defined: uconf: cft.server.cftcoms.authentication\_enable=yes
    uconf: cft.server.authentication\_method=none
-   User=user01 Group=group01 provided a password but authentication\_enable=noIn the CONFIG command the PASSWORD parameter is set, but in the unified configuration it is disabled: uconf:cft.server.cftcoms.authentication\_enable=no

```

 

```
V23 format
V24 format
Error
<span id="CFTS59E"></span>CFTS59E Multi-node error \_ &str
CFTS58F Multi-node error \_ &str
Explanation
An important error occurred during the transfer recovery. The error is detailed in &str.
Consequence
The transfer in question is not recovered.
Action
Contact the support team if necessary.
```

```
V23 format
V24 format
Warning
<span id="CFTS60W"></span>CFTS60W Multi-node \_ &str
CFTS60W Multi-node \_ &str
Explanation
An anomaly occurred during the transfer recovery. The anomaly is detailed in &str.
```

 

```
V23 format
V24 format
Information
<span id="CFTS61I"></span>CFTS61I Multi-node \_ &str
CFTS61I Multi-node \_ &str
Explanation
Displays information about the multi-node transfer recovery phase. The &str value provides additional details.
```

 

```
V23 format
V24 format
Information
<span id="CFTS62I"></span>CFTS62I &str
CFTS62I &str
Explanation
Displays information about UCONF scheduling.
Where:

-   &str = "SCHEDULE : Id &id is not a valid uconf entry", or
-   &str = " SCHEDULE &id : Parameter &parm '&value' --> '&value'", or
-   &str = "RECONFIG AM &task or SCHEDULED CONFIG &task"

```

 

```
V23 format
V24 format
Fatal
<span id="CFTS63F"></span>CFTS63F Secure Relay fatal error \_ &str
CFTS63F Secure Relay fatal error \_ &str
Explanation
Fatal error detected. &str indicates the reason
Secure Relay Master agent is stopped.
Secure Relay is not available.
Action
Check the configuration depending on the reason and restart Transfer CFT.
```

 

```
V23 format
V24 format
Information
<span id="CFTS64I"></span>CFTS64I Secure Relay \_ &str
CFTS64I Secure Relay \_ &str
Explanation
Secure relay information message : &str= Router agent &n is enabled but has no host or ports.
```

```
V23 format
V24 format
Warning
<span id="CFTS64I"></span><span id="CFTS65W"></span>CFTS65W Unable to launch another script for 60s due to the cft.server.max\_processing\_scripts limit
CFTS65W Unable to launch another script for 60s due to the cft.server.max\_processing\_scripts limit
Explanation
The total number of transfers in the AC, YC and ZC state has reached the `cft.server.max_scripts` limit and has not decreased for 60s.
Consequence
A script has been waiting to be launched for at least 60s.
Action
Check that there is an END command in the EXEC scripts.
```

 

```
V23 format
V24 format
Error
<span id="CFTS64I"></span><span id="CFTS66E"></span>CFTS66E TFIL error \_ &str", &str = Regular expression &mask parsing error or List generation error &scs
CFTS66E TFIL error \_ &str
Explanation
The regular expression (REGEX) &mask configured in fname (SEND or CFTSEND) can not be parsed with error &scs
Consequence.
Where;

-   &str = "Regular expression &mask parsing error", or
-   &str = " List generation error &scs"

Consequence
Transfer is not executed.
Action
Check and modify the REGEX &mask value.
```

 

```
V23 format
V24 format
Error
<span id="CFTS67E"></span>CFTS67E Error replacing variable &var &message
CFTS67E Error replacing variable &var &message
Explanation
The **<var>** variable contains blacklisted characters.
```

 

```
V23 format
V24 format
Error
<span id="CFTS68E"></span>CFTS68E PART=&part \[IDF=&idf | IDM=&idm\]IDT=&idt \_ &fname not executed
CFTS68E \_ &fname not executed <IDTU=&idtu PART=&part \[IDF=&idf | IDM=&idm\] IDT=&idt DIRECT=&direct>
Explanation
The **&fname** script was not executed because a variable contained blacklisted characters. The file was nonetheless created, and may contain some data.
```

 

```
V23 format
V24 format
Warning
<span id="CFTS71W"></span>CFTS71W Command file Alert fill threshold reached: level=&level ID=&id
CFTS71W Command file Alert fill threshold reached: level=&level ID=&id
Explanation
&level of the COM file space has been used. &level is the amount set by the CFTCOM TLVWARN parameter.
When the critical fill threshold is reached, a message is recorded in the Transfer CFT log.
A batch in response to the alert, the CFTCOM TLVWEXEC parameter, is submitted.
```

 

```
V23 format
V24 format
Warning
<span id="CFTS72W"></span>CFTS72W Command file Alert cleared : level=&level ID=&id
CFTS72W Command file Alert cleared : level=&level ID=&id
Explanation
This alert stops when the fill level drops below the TLVCLEAR level.
When the alert stops, the message is recorded in the Transfer CFT log and a batch, the CFTCOM TLVCEXEC parameter, is submitted.
```

 

```
V23 format
V24 format
Information
<span id="CFTS73I"></span>CFTS73I Command file Alert exec &fname executed
CFTS73I Command file Alert exec &fname executed
Explanation
The &FNAME procedure for a catalog alert was executed.

-   If the critical fill threshold is reached, the CFTS71W message is recorded in the Transfer CFT log.
-   If the alert ceases, the CFTS72W message is recorded in the Transfer CFT log.

Either way a batch is submitted, as by the CFTCOM TLVCEXEC parameter.
```

 

```
V23 format
V24 format
Error
<span id="CFTS74E"></span>CFTS74E Command file Alert exec &fname &str"
CFTS74E Command file Alert exec &fname &str"
Explanation
The &FNAME procedure for a command file alert was not found or failed on access, producing this error.

-   If the critical fill threshold is reached, the CFTS71W message is recorded in the Transfer CFT log.

<!-- -->

-   If the alert ceases, the CFTS72W message is recorded in the Transfer CFT log.

In either case, the batch defined by the CFTCOM TLVCEXEC parameter is not executed.
Where:

-   &str = "not found", or
-   &str = "failed"

```
