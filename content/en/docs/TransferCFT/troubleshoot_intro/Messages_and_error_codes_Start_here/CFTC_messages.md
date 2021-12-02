{
    "title": "Transfer CFT messages: CFTC",
    "linkTitle": "CFTC messages",
    "weight": "280"
}This topic lists the CFTC (CFT xnnx) messages and provides the type, a description, consequence, and corrective actions when applicable.

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
<span id="CFTC01W"></span>CFTC01W CFT catalog storage is short n record(s) free 
CFTC01W CFT catalog storage is short n record(s) free 
Explanation
Catalog storage is short n record(s) free.
Consequence
The catalog is nearly full - there are only n records free. Consider modifications to free up space.
```

 

```
V23 format
V24 format
Error
<span id="CFTC01E"></span>CFTC01E CFT catalog storage is full  
CFTC01E CFT catalog storage is full
Explanation
The catalog storage is full. A command SHUT FAST=KILL is executed.
Consequence
The stored commands can only be retrieved by restarting {{< TransferCFT/componentshortname >}}. First purge the {{< TransferCFT/componentshortname >}} catalog (and modify the retention dates, for example).
```

 

```
V23 format
V24 format
Warning
<span id="CFTC03W"></span>CFTC03W PART=&part IDF=&idf IDT=&idt \_
Running out of time (HHMMSSCC)
CFTC03W Transfer Running out of time <IDTU=&idtu PART=&part IDF=&idf IDT=&idt \[sgt=HHMMSSCC\]
Explanation
The transfer start time is outside the interval authorized by
the &part partner.
Consequence
The next transfer retry will take place at the specified time
\[HHMMSSCC\].
```

 

```
V23 format
V24 format
Warning
<span id="CFTC04W"></span>CFTC04W PART=&part  IDF=&idf IDT=&idt
\_ State C delete forbidden
CFTC04W \_ State C delete forbidden <IDTU=&idtu PART=&part IDF=&idf IDT=&idt
Explanation
A DELETE command was executed on a catalog request (in the C
state), but this operation is not allowed.
Consequence
The catalog entry could not be deleted.
```

 

```
V23 format
V24 format
Warning
<span id="CFTC05W"></span>CFTC05W PART=&part \[IDF=&idf | IDM=&idm\] IDT=&idt \_ Delete
failed
CFTC05W \_ Delete failed <IDTU=&idtu PART=&part \[IDF=&idf | IDM=&idm\] IDT=&idt
Explanation
A DELETE command was executed on a catalog request (in a state
other than C or D), but it failed as a result of a catalog access error.
Consequence
The catalog entry could not be deleted.
The
CFTT21E message may be displayed before this message.
```

 

```
V23 format
V24 format
Error
<span id="CFTC06E"></span>CFTC06E PART=&part IDF=&idf IDT=&idt \_
Update failed
CFTC06E \_ Update failed <IDTU=&idtu PART=&part IDF=&idf IDT=&idt>
Explanation
A Transfer
CFT catalog access error was detected when executing commands, such as
END, START, ACT and INACT.
Consequence
The catalog entry was not updated and the command was ignored.
The CFTT21E message is displayed prior to this message.
```

 

```
V23 format
V24 format
Information
<span id="CFTC07I"></span>CFTC07I PART=&part \[IDF=&idf | IDM=&idm\]IDT=&idt
STATE=&state - Deleted
CFTC07I Transfer Deleted <IDTU=&idtu PART=&part \[IDF=&idf | IDM=&idm\] IDT=&idt STATE=&state DIRECT=&direct
Explanation
A Transfer
CFT catalog entry for partner &part, with identifier &idf, idt
&idt and state &state, has been deleted.
```

 


|  V23 format<br/>V24 format Information  |  <span id="CFTC08I"></span>CFTC08I &amp;str<br/>CFTC08I &amp;str  |
| --- | --- |
| Explanation  |  Possible values for &amp;str are described here. The following messages are displayed when the catalog is purged on {{< TransferCFT/componentshortname  >}} startup, or at the time set for the daily purge. For example:<br/>When there are no transfers to delete: <div class="indentTableNested"> Purge Started<br /> Purge catalog-size=1000 in-use=0 pre-filtered=0(0%)<br /> Purge Treated: catalog empty<br /> Purge deleted= n treated=n(d%) match=d%.<br /> Purge Treated<br /> Purge Treated: no record found to delete </div> When there are transfers to delete: <div class="indentTableNested"> Catalog: Loading...<br /> Catalog: Load Done<br /> Catalog: Size=100, Used=8(8%)<br /> Purge Started.<br /> Purge catalog-size=100 in-use=8 pre-filtered=8(100)<br /> Purge deleted=1 treated=1(12) match=100<br /> Purge deleted=2 treated=2(25) match=100<br /> ….<br /> Purge deleted=8 treated=8(100) match=100<br /> Purge Treated. </div> When {{< TransferCFT/componentshortname  >}} starts: <div class="indentTableNested"> If there are no transfers to delete: <div class="indentTableNested"> Catalog: Loading...<br /> Catalog: Load Done<br /> Catalog: Size= &amp;00, Used=0(0%)<br /> </div> If there are transfers to delete: <div class="indentTableNested"> Catalog: Loading...<br /> Catalog: Load Done<br /> Catalog: Size=100, Used=8(8%) </div> </div> If there is a problem with the catalog INIT: <div class="indentTableNested"> Catalog: Recovering<br /> Catalog: Recovery Done: n errors<br /> Catalog Recovery: n transfers from C to D state </div>  |


 

```
V23 format
V24 format
Information
<span id="CFTC09I"></span>CFTC09I PART=&part IDF=&idf IDT=&idt STATE=&state
DIRECT=&direct : &cmd not executed
CFTC09I Command not executed <IDTU=&idtu PART=&part IDF=&idf IDT=&idt STATE=&state DIRECT=&direct : Cmd=&cmd
Explanation
The security system does not allow the user to execute this
command on the catalog.
Consequence
The command is ignored.
This
message is followed by the CFTX02W and CFTX04W messages.
```

 

```
V23 format
V24 format
Information
<span id="CFTC10I"></span>CFTC10I PART=&part IDF or IDM=&idf STATE=&state
MODE=&mode : &cmd not executed
CFTC10I PART=&part \[IDF=&idf | IDM=&idm\] STATE=&state MODE=&mode : &cmd not executed
Explanation
The security system does not allow this user to execute this
command on the catalog.
Consequence
The command is ignored. One of the following messages displays after CFTC10I to provide additional information: CFTX01W , CFTX03W , or CFTX04W.
```

 

```
V23 format
V24 format
Information
<span id="CFTC11I"></span>CFTC11I PART=&part IDM=&idf IDT=&idt :
SEND REPLY not executed
CFTC11I Command not executed <IDTU=&idtu PART=&part \[IDF=&idf | IDM=&idm\] IDT=&idt : Cmd=&cmd
Explanation
The security system does not allow the user to execute this
command on the catalog.
Consequence
The command is ignored.

> **Note:**
> This message
> is followed by the CFTX01W message.

```

 

```
V23 format
V24 format
Information
<span id="CFTC12I"></span>CFTC12I PART=&part STATE=&state DIRECT=&direct TYPE=&type SENTINEL\_STATE=&trkstate Deleted
CFTC12I IDTU=&idtu PART=&part STATE=&state PHASE=&phase PHASESTEP=&phasestep DIRECT=&direct TYPE=&type SENTINEL\_STATE=&trkstate Deleted
Explanation
This {{< TransferCFT/componentshortname >}} message is displayed for each transfer that is deleted when the catalog is purged. Where:

-   &state = transfer status (C/D/H/K/T/X)
-   &direct = S (send) / R (recv)
-   &type = F (file) / M (message)
-   &trkstate = Sentinel state

Possible values are:

-   TO\_EXECUTE
-   SUSPENDED
-   RECEIVING
-   SENDING
-   CANCELED
-   RECEIVED
-   SENT
-   CREATED
-   INTERRUPTED
-   ACKED
-   NACKED

Consequence
The command is ignored.
```

 

```
V23 format
V24 format
Information
<span id="CFTC13I"></span>CFTC13I Catalog resize (xxxx --> yyyy) done
CFTC13I Catalog resize (xxxx --> yyyy) done
Explanation
A dynamic command to resize the catalog was executed. The first message displays the new size, and the second message indicates that the resizing (from the original size xxxx to the new size yyyy) is complete.
Consequence
The catalog automatically expands to the new size (the <yyyy> value) when possible, up to the maximum defined limit.
```

 

```
V23 format
V24 format
Error
<span id="CFTC13E"></span>CFTC13E {{< TransferCFT/componentshortname >}} catalog resize (xxxx --> yyyy) reached max before expansion
CFTC13I Catalog resize (xxxx --> yyyy) done
Explanation
A dynamic command to automatically expand the catalog failed, as the maximum number of records has already been reached. The catalog size remains unchanged (the <xxxx> value).
Consequence
Normal functioning with existing catalog size, and no catalog expansion occurs.
```

 

```
V23 format
V24 format
Information
<span id="CFTC13E"></span><span id="CFTC15I"></span>CFTC15I Deprecated command not executed BLKNUM=&blknum PART=&part IDT=&idt : Cmd=&cmd>
CFTC15I Deprecated command not executed BLKNUM=&blknum PART=&part IDT=&idt : Cmd=&cmd
Explanation
Set the uconf parameter `cft.cftcat.enable_deprecated_blknum=Yes` to enable BLKNUM.

> **Note:**
> Regardless of the cft.cftcat.enable\_deprecated\_blknum parameter setting, BLKNUM is disabled in a multi-node configuration (uconf:cft.multi\_node.enable=Yes), and this message is displayed.

Consequence
The command is ignored.
```

 

```
V23 format
V24 format
Warning
<span id="CFTC29W"></span>CFTC29W
Catalog Alert fill threshold reached: level=&level , id=CAT0
CFTC29W Catalog Alert fill threshold reached: level=&level ID=&id
Explanation
&level of the catalog space has been used. &level is the amount
set by the CFTCAT TLVWARN parameter.
When the critical fill threshold is reached, a message
is recorded in the {{< TransferCFT/componentshortname >}} log.
A batch in response to the alert, the CFTCAT TLVWEXEC parameter,
is submitted.
```

 

```
V23 format
V24 format
Warning
<span id="CFTC30W"></span>CFTC30W Catalog
Alert cleared: level=&level, id=CAT0
CFTC30W Catalog Alert cleared : level=&level ID=&id
Explanation
This alert stops when the fill level drops below the TLVCLEAR
level.
When the alert stops, the message is recorded in the Transfer
CFT log, and a batch, the CFTCAT TLVCEXEC parameter, is submitted.
```
