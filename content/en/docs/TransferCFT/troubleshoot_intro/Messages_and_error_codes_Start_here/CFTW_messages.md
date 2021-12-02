{
    "title": " Transfer CFT messages: CFTW",
    "linkTitle": "CFTW messages",
    "weight": "380"
}This topic lists the CFTWxx and CFTXxx messages and provides the type, a description, consequence, and corrective actions when applicable.

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
<span id="CFTW01W"></span>CFTW01W PART=&part
IDF=&idf IDT=&idt Temporary
file &file deleted
CFTW01W File &fname deleted <IDTU=&idtu PART=&part IDF=&idf IDT=&idt >
Explanation
The &file temporary file was deleted at the end of
the transfer. The name of this file is declared in the WFNAME parameter
of the CFTSEND and CFTRECV commands.
```

 

```
V23 format
V24 format
Warning
<span id="CFTW02W"></span>CFTW02W CFTSEND &idsend override SEND parameters
CFTW02W CFTSEND &id override SEND parameters
Explanation
The parameters of the SEND command are overridden by the parameters
in the associated CFTSEND command.
```

 

```
V23 format
V24 format
Warning
<span id="CFTW03W"></span>CFTW03W \_ Send command: Unauthorized usage of IDF =
&idf
CFTW03W \_ Send Command : Unauthorized usage on IDF = &id
Explanation
The &idf IDF is not authorized for the SEND command. Check your software key restrictions.
```

 

```
V23 format
V24 format
Warning
<span id="CFTW04W"></span>CFTW04W \_ Recv command: Unauthorized usage on IDF =
&idf
CFTW04W \_ Recv Command : Unauthorized usage on IDF = &id
Explanation
The &idf IDF is not authorized for the RECV command. See
the restrictions concerning the value of your software key.
```

 

```
V23 format
V24 format
Warning
<span id="CFTW05W"></span>CFTW05W PART=&part IDF = &idf Temporary file
unknown, WFNAME not defined in SEND
CFTW05W PART=&part IDF=&idf Temporary file unknown, WFNAME not defined in SEND
Explanation
The WFNAME was not set in the CFTSEND command when preparing
a transfer requiring additional processing
and sending a group of files.
Action
Modify the parameter settings using a different IDF for this
type of transfer.
```

 

```
V23 format
V24 format
Warning
<span id="CFTW07W"></span>CFTW07W PART=&part IDF = &idf \_ SELFNAME not
authorized for COPY
CFTW07W PART=&par IDF=&idf \_ SELFNAME not authorized for COPY\\n
Explanation
You cannot use a selection file when implementing additional
processing prior to a transfer (IEBCOPY with MVS for example).
Consequence
The transfer is not triggered.
Action
Do not use a selection file; you can, however, specify a generic
file name (FNAME= #FIL1\*, FNAME= #TFILM\*).
```

 

```
V23 format
V24 format
Warning
<span id="CFTW08W"></span>CFTW08W CFTRECV &idrecv override RECV parameters
CFTW08W CFTRECV &id override RECV parameters
Explanation
The RECV command parameters are overridden by the parameters
set in the associated CFTRECV command.
```

 

```
V23 format
 
V24 format
 
Information
<span id="CFTW09I"></span>CFTW09I PART=&part IDF=&idf IDT=&idt CFTSEND &idf NIDF=&nidf XLATE=&xlate
CFTW09I PART=&part IDF=&idf IDT=&idt CFTRECV &idf NIDF=&nidf XLATE=&xlate
CFTW09I CFTSEND &idf <IDTU=&idtu PART=&part IDF=&idf IDT=&idt NIDF=&nidf XLATE=&xlate>
CFTW09I CFTRECV &idf <IDTU=&idtu PART=&part IDF=&idf IDT=&idt NIDF=&nidf XLATE=&xlate>
Explanation
Indicates the ID of the CFTSEND or CFTRECV that was actually
used.
**Example**
CFTW09I CFTSEND TRTR <IDTU=A0000024 PART=SERVER IDF=TRTR IDT=I0714504 NIDF=TRTR XLATE=CONV1>
```
