{
    "title": "Request examples",
    "linkTitle": "Request examples",
    "weight": "290"
}This topic presents synchronous transfer request examples using the WSTATES or WPHASES/WPHASESTEPS parameters with the SEND/RECV command, or the SWAITCAT command.

## WPHASES and WPHASESTEPS

The WPHASES and WPHASESTEPS parameters allow for more precision and possibilities than using WSTATES alone.

Example of a transfer request where the wphases is used in conjunction with wphasesteps

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>config type=com,mediacom=tcpip,fname=xhttp://localhost:1765</p>
<p> </p>
<p>send part=loop,idf=t2,wphases=X,wphasesteps=X,wtimeout=40</p>
<p>CFTU00I SEND _ Correct (SWAITCAT_OK: reached phase X, phasestep X, state X)</p>
<p>CFTU00I SEND _ Correct (part=loop,idf=t2,wphases=X,wphasesteps=X,wtimeout=40)</p></td>
</tr>
</tbody>
</table>

Example of a simple transfer request using only wphases

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>config type=com,mediacom=tcpip,fname=xhttp://localhost:1765</p>
<p> </p>
<p>send part=paris,idf=t2,wphases=Z,wtimeout=40,ackstate=require</p>
<p>CFTU00I SEND _ Correct (SWAITCAT_OK: reached phase Z, phasestep H, state Z)</p>
<p>CFTU00I SEND _ Correct (part=paris,idf=t2,wphases=Z,wtimeout=40,ackstate=require)</p></td>
</tr>
</tbody>
</table>

## WSTATES and WTIMEOUT examples

-   Example 1: Transfer request using WSTATES
-   Example 2: Use a SEND with WSTATES and WTIMEOUT

**Example 1: Transfer request using WSTATES**

Trigger a command pending that a transfer has reached a certain defined state. See also [WSTATES](wstates.htm). This task resembles an FTP transfer.

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>config type=com,mediacom=tcpip,fname=xhttp://localhost:1765</p>
<p> </p>
<p>send part=paris,idf=bin,wstates=tx</p>
<p> </p>
<p>PRINT MSG='transfer idtu=%_CAT_IDTU% completed with state=%_CAT_STATE% and diagi=%_CAT_DIAGI%'</p>
<p> </p>
<p>Output</p>
<p>CONFIG _ Correct (type=com,mediacom=tcpip,fname=xhttp://localhost:1765)</p>
<p>CFTU00I SEND _ Correct (SWAITCA,IDTU=A000008B)</p>
<p>CFTU00I SEND _ Correct (part=paris,idf=bin,wstates=tx)</p>
<p>CFTU00I PRINT _ Correct (MSG='')transfer idtu=A000008B completed with state=X and diagi=0</p></td>
</tr>
</tbody>
</table>

**Example 2: Use a SEND with WSTATES and WTIMEOUT**

In this example, the transfer fails because it did not complete prior to the timeout, which leads to an error code of 81.

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>config type=com,mediacom=tcpip,fname=xhttp://localhost:1765</p>
<p> </p>
<p>send part=paris,idf=bin,wstates=tx,wtimeout=2,fname=pub/BIG</p>
<p> </p>
<p>PRINT MSG='ERROR = %_CMDRET%'</p>
<p> </p>
<p>Output</p>
<p>CFTU20I Communication TCPIP:xhttp://localhost:1765</p>
<p>CFTU00I CONFIG _ Correct (type=com,mediacom=tcpip,fname=xhttp://localhost:1765)</p>
<p> </p>
<p>send part=paris,idf=bin,wstates=tx,wtimeout=2,fname=pub/BIG</p>
<p>CFTU25E SEND _ Error (TIMEOUT reached,(IDTU=A0000095,IDT=B1817282))</p>
<p>CFTU00I SEND _ Failed (part=paris,idf=bin,wstates=tx,wtimeout=2,fname=pub/ BIG)</p>
<p> </p>
<p>PRINT MSG='ERROR = %_CMDRET%'</p>
<p>ERROR = 81</p>
<p>CFTU00I PRINT _ Correct (MSG='ERROR = 81')</p></td>
</tr>
</tbody>
</table>

**Example 3: Serialization using WSTATES**

In this example the transfers are executed sequentially depending on the defined WSTATES.

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>config type=com,mediacom=tcpip,fname=xhttp://localhost:1765</p>
<p> </p>
<p>send part=paris,idf=bin,ida=1,wstates=tx</p>
<p>char name=idt1,init=%_CAT_IDT%</p>
<p>send part=paris,idf=bin,ida=2,wstates=tx</p>
<p>char name=idt2,init=%_CAT_IDT%</p>
<p>send part=paris,idf=bin,ida=3,wstates=tx</p>
<p>char name=idt3,init=%_CAT_IDT%</p>
<p>send part=paris,idf=bin,ida=4,wstates=tx</p>
<p>char name=idt4,init=%_CAT_IDT%</p>
<p>PRINT MSG='transfers: idt1=%idt1% - idt2=%idt2% - idt3=%idt3% - idt4=%idt4%'</p>
<p> </p>
<p>Output</p>
<p>CFTU00I SEND _ Correct (SWAITCA,IDTU=A000008F)</p>
<p>CFTU00I SEND _ Correct (part=paris,idf=bin,ida=1,wstates=tx)</p>
<p>CFTU00I CHAR _ Correct (name=IDT1,init=B1817075)</p>
<p>CFTU00I SEND _ Correct (SWAITCA,IDTU=A000008H)</p>
<p>CFTU00I SEND _ Correct (part=paris,idf=bin,ida=2,wstates=tx)</p>
<p>CFTU00I CHAR _ Correct (name=IDT2,init=B1817080)</p>
<p>CFTU00I SEND _ Correct (SWAITCA,IDTU=A000008J)</p>
<p>CFTU00I SEND _ Correct (part=paris,idf=bin,ida=3,wstates=tx)</p>
<p>CFTU00I CHAR _ Correct (name=IDT3,init=B1817081)</p>
<p>CFTU00I SEND _ Correct (SWAITCA,IDTU=A000008L)</p>
<p>CFTU00I SEND _ Correct (part=paris,idf=bin,ida=4,wstates=tx)</p>
<p>CFTU00I CHAR _ Correct (name=IDT4,init=B1817082)</p>
<p> </p>
<p>transfers: idt1=B1817075 - idt2=B1817080 - idt3=B1817081 - idt4=B1817082</p>
<p>CFTU00I PRINT _ Correct (MSG='transfers: idt1=B1817075 - idt2=B1817080 - id</p>
<p>CFTU00I t3=B1817081 - idt4=B1817082')</p>
<p> </p>
<p>Log</p>
<p>00 16/02/18 17:07:27 CFTT57I Requester transfer started &lt;IDTU=A000008F PART=paris IDF=BIN IDT=B181</p>
<p>7075 &gt;...</p>
<p>00 16/02/18 17:07:27 CFTT58I Requester transfer ended &lt;IDTU=A000008F PART=paris IDF=BIN IDT=B181</p>
<p>7075&gt;.....</p>
<p>00 16/02/18 17:07:27 CFTT57I Requester transfer started &lt;IDTU=A000008H PART=paris IDF=BIN IDT=B181</p>
<p>7080 &gt;...</p>
<p>00 16/02/18 17:07:27 CFTT58I Requester transfer ended &lt;IDTU=A000008H PART=paris IDF=BIN IDT=B181</p>
<p>7080&gt;....</p>
<p>00 16/02/18 17:07:27 CFTT57I Requester transfer started &lt;IDTU=A000008J PART=paris IDF=BIN IDT=B181</p>
<p>7081 &gt;...</p>
<p>00 16/02/18 17:07:27 CFTT58I Requester transfer ended &lt;IDTU=A000008J PART=paris IDF=BIN IDT=B181</p>
<p>7081&gt;....</p>
<p>00 16/02/18 17:07:27 CFTT57I Requester transfer started &lt;IDTU=A000008L PART=paris IDF=BIN IDT=B181</p>
<p>7082 &gt;...</p>
<p>00 16/02/18 17:07:27 CFTT58I Requester transfer ended &lt;IDTU=A000008L PART=paris IDF=BIN IDT=B181</p>
<p>7082&gt;...</p></td>
</tr>
</tbody>
</table>

## SWAITCAT example

The examples describe how to use SWAITCAT to perform the following task, wstates is the best way to wait (or wphases).

<span id="SWAITCAT ex 1"></span>**Example: Execute a command once all transfers have completed**

The following example is a way to execute a batch processing task using SWAITCAT, which is a task that you cannot perform using the SEND command with WSTATES.

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>config type=com,mediacom=tcpip,fname=xhttp://localhost:1765</p>
<p> </p>
<p>send part=paris,ida=batch_proccesing,idf=t1</p>
<p>char name=idtu1,init=%_CAT_IDTU%</p>
<p>send part=paris,ida=batch_proccesing,idf=t2</p>
<p>char name=idtu2,init=%_CAT_IDTU%</p>
<p>send part=paris,ida=batch_proccesing,idf=t3</p>
<p>char name=idtu3,init=%_CAT_IDTU%</p>
<p>send part=paris,ida=batch_proccesing,idf=t4</p>
<p>char name=idtu4,init=%_CAT_IDTU%</p>
<p>swaitcat select='IDTU=="%idtu1%"',phases=X,phasesteps=X</p>
<p>swaitcat select='IDTU=="%idtu2%"',phases=X,phasesteps=X</p>
<p>swaitcat select='IDTU=="%idtu3%"',phases=X,phasesteps=X</p>
<p>swaitcat select='IDTU=="%idtu4%"',phases=X,phasesteps=X</p>
<p> </p>
<p>PRINT MSG='batch processing completed with ERROR = %_CMDRET%'</p>
<p> </p>
<p>Output</p>
<p>CFTU00I CONFIG _ Correct (type=com,mediacom=tcpip,fname=xhttp://localhost:1765)</p>
<p>CFTU00I SEND _ Correct (IDT=B1817083 IDTU=A000008N )</p>
<p>CFTU00I SEND _ Correct (part=paris,ida=batch_proccesing,idf=t1)</p>
<p>CFTU00I CHAR _ Correct (name=IDTU1,init=A000008N)</p>
<p>CFTU00I SEND _ Correct (IDT=B1817084 IDTU=A000008P )</p>
<p>CFTU00I SEND _ Correct (part=paris,ida=batch_proccesing,idf=t2)</p>
<p>CFTU00I CHAR _ Correct (name=IDTU2,init=A000008P)</p>
<p>CFTU00I SEND _ Correct (IDT=B1817085 IDTU=A000008R )</p>
<p>CFTU00I SEND _ Correct (part=paris,ida=batch_proccesing,idf=t3)</p>
<p>CFTU00I CHAR _ Correct (name=IDTU3,init=A000008R)</p>
<p>CFTU00I SEND _ Correct (IDT=B1817090 IDTU=A000008T )</p>
<p>CFTU00I SEND _ Correct (part=paris,ida=batch_proccesing,idf=t4)</p>
<p>CFTU00I CHAR _ Correct (name=IDTU4,init=A000008T)</p>
<p>CFTU00I SWAITCAT _ Correct (SWAITCAT_OK: reached phase X, phasestep X, state X)</p>
<p>CFTU00I SWAITCAT _ Correct (select='IDTU=="A000008N"',phases=X,phasesteps=X)</p>
<p>CFTU00I SWAITCAT _ Correct (SWAITCAT_OK: reached phase X, phasestep X, state X)</p>
<p>CFTU00I SWAITCAT _ Correct (select='IDTU=="A000008P"',phases=X,phasesteps=X)</p>
<p>CFTU00I SWAITCAT _ Correct (SWAITCAT_OK: reached phase X, phasestep X, state X)</p>
<p>CFTU00I SWAITCAT _ Correct (select='IDTU=="A000008R"',phases=X,phasesteps=X)</p>
<p>CFTU00I SWAITCAT _ Correct (SWAITCAT_OK: reached phase X, phasestep X, state X)</p>
<p>CFTU00I SWAITCAT _ Correct (select='IDTU=="A000008T"',phases=X,phasesteps=X)</p>
<p> </p>
<p>batch processing completed with ERROR = 0</p></td>
</tr>
</tbody>
</table>
