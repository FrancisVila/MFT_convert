{
    "title": "Transfer CFT messages: CFTP",
    "linkTitle": "CFTP messages",
    "weight": "340"
}This topic lists the CFTPxx  (CFT xnnx) messages and provides the type,  a description, consequence, and corrective actions when applicable.

**Message format**

Earlier versions of Transfer CFT used a different message format than version 3.1.3 and higher. This document displays both formats when applicable and available, otherwise only the v23 is used. Using the CFTLOG Format = V24 setting, the log displays as shown:

CFTXXX: fixed text message &lt;variables>

**Example**

CFTLOG FORMAT=\[V23,V24\]

For V23: `CFTT57I PART=&part IDF=&idf IDT=&idt &str transfer started`

For V24: `CFTT57I &str transfer started   <IDTU=&idtu PART=&part IDF=&idf IDT=&idt>`


|  V23 format<br/>V24 format<br/>Error  |  <span id="CFTP01F"></span>CFTP01F CFTPARM &amp;id _ Not found<br/>CFTP01F CFTPARM &amp;id _ Not found  |
| --- | --- |
|  Explanation  |  The &amp;id identifier of the {{< TransferCFT/componentshortname  >}} parameter file (see the CFTPARM parameter) is not defined.  |
|  Consequence  |  The Transfer CFT initialization phase is stopped.  |
|  Action  |  Check the CFTPARM parameter settings (see the CFTPARM parameter), correct and restart {{< TransferCFT/componentshortname  >}}.  |


 


|  V23 format<br/>V24 format<br/>Error  |  <span id="CFTP02F"></span>CFTP02F CFTTRACE &amp;id for CFTPARM &amp;id _ Not found<br/>CFTP02F CFTSYST &amp;id for CFTPARM &amp;id _ Not found  |
| --- | --- |
|  Explanation  |  When initializing {{< TransferCFT/componentshortname  >}}, the CFTTRACE &amp;id identifier was not found in the Transfer CFT parameter file.  |
|  Consequence  |  The Transfer CFT initialization phase is stopped.  |
|  Action  |  Check the CFTSYST parameter settings (see the CFTPARM parameter), correct and restart {{< TransferCFT/componentshortname  >}}.  |


 


|  V23 format<br/>V24 format<br/>Error  |  CFTP03F CFTLOG &amp;id for CFTPARM &amp;id _ Not found<br/>CFTP03F CFTLOG &amp;id for CFTPARM &amp;id _ Not found  |
| --- | --- |
|  Explanation  |  During Transfer CFT initialization the CFTLOG &amp;id identifier was not found in the {{< TransferCFT/componentshortname  >}} parameter file.  |
|  Consequence  |  The Transfer CFT initialization phase is stopped.  |
|  Action  |  Check the CFTLOG parameter settings (see the CFTPARM parameter), correct and restart {{< TransferCFT/componentshortname  >}}.  |


 


|  V23 format<br/>V24 format<br/>Error  |  <span id="CFTP04F"></span>CFTP04F CFTNET &amp;id for CFTPARM &amp;id _ Not found<br/>CFTP04F CFTNET &amp;id for CFTPARM &amp;id _ Not found  |
| --- | --- |
|  Explanation  |  During Transfer CFT initialization the CFTNET &amp;id identifier was not found in the {{< TransferCFT/componentshortname  >}} parameter file.  |
|  Consequence  |  The Transfer CFT initialization phase is stopped.  |
|  Action  |  Check the CFTNET parameter settings (see the CFTPARM parameter), correct and restart {{< TransferCFT/componentshortname  >}}.  |


 


|  V23 format<br/>V24 format<br/>Error  |  <span id="CFTP05F"></span>CFTP05F CFTPROT &amp;id for CFTPARM &amp;id_ Not found<br/>CFTP05F CFTPROT &amp;id for CFTPARM &amp;id _ Not found  |
| --- | --- |
|  Explanation  |  During Transfer CFT initialization the CFTPROT &amp;id identifier was not found in the {{< TransferCFT/componentshortname  >}} parameter file.  |
|  Consequence  |  The Transfer CFT initialization phase is stopped.  |
|  Action  |  Check the CFTPROT parameter settings (see CFTPROT), correct and restart Transfer CFT.  |


 


|  V23 format<br/>V24 format<br/>Error  |  <span id="CFTP06F"></span>CFTP06F CFTCAT &amp;id for CFTPARM &amp;id _ Not found<br/>CFTP06F CFTCAT &amp;id for CFTPARM &amp;id _ Not found  |
| --- | --- |
|  Explanation  |  During Transfer CFT initialization the CFTCAT &amp;id identifier was not found in the {{< TransferCFT/componentshortname  >}} parameter file.  |
|  Consequence  |  The Transfer CFT initialization phase is stopped.  |
|  Action  |  Check the CFTCAT parameter settings (see CFTCAT), correct and restart {{< TransferCFT/componentshortname  >}}.  |


 


|  V23 format<br/>V24 format<br/>Error  |  <span id="CFTP07F"></span>CFTP07F CFTCOM &amp;id for CFTPARM &amp;id _ Not found<br/>CFTP07F CFTCOM &amp;id for CFTPARM &amp;id _ Not found  |
| --- | --- |
|  Explanation  |  During Transfer CFT initialization the CFTCOM &amp;id identifier was not found in the {{< TransferCFT/componentshortname  >}} parameter file.  |
|  Consequence  |  The Transfer CFT initialization phase is stopped.  |
|  Action  |  Check the CFTCOM parameter settings (see CFTCOM), correct and restart {{< TransferCFT/componentshortname  >}}.  |


 


|  V23 format<br/>V24 format<br/>Fatal  |  <span id="CFTP08F"></span>CFTP08F CFTNET &amp;id for CFTPROT &amp;id _ Not found<br/>CFTP08F CFTNET &amp;id for CFTPROT &amp;id _ Not found  |
| --- | --- |
|  Explanation  |  During Transfer CFT initialization the CFTNET &amp;id identifier for a given CFTPROT &amp;id protocol was not found in the {{< TransferCFT/componentshortname  >}} parameter file.  |
|  Consequence  |  The Transfer CFT initialization phase is stopped.  |
|  Action  |  Check:<br/> • the CFTNET and CFTPROT parameter settings (see the CFT CFTNET and CFTPROT topics)<br/> • the CFTPARM parameter settings<br/> • the list of authorized protocols and network identifiers (NET=(.,.), PROT=(.,.) ) that the number of items in this list does not exceed the maximum authorized quota<br/>Correct and restart {{< TransferCFT/componentshortname  >}}.  |


 


|  V23 format<br/>V24 format<br/>Error  |  <span id="CFTP09F"></span>CFTP09F CFTSEND &amp;id for CFTPARM &amp;id _ No default record found<br/>CFTP09F CFTSEND &amp;id for CFTPARM &amp;id _ No default record found  |
| --- | --- |
|  Explanation  |  During Transfer CFT initialization the identifier describing the default file characteristics used for send transfers (CFTSEND parameter) is unknown.  |
|  Consequence  |  The Transfer CFT initialization phase cannot continue correctly and {{< TransferCFT/componentshortname  >}} is aborted.  |
|  Action  |  Check the CFTPARM (DEFAULT=.) and CFTSEND parameter settings, correct and restart {{< TransferCFT/componentshortname  >}}.  |


 


|  V23 format<br/>V24 format<br/>Error  |  <span id="CFTP10F"></span>CFTP10F CFTRECV &amp;id for CFTPARM &amp;id _ No Default record found<br/>CFTP10F CFTRECV &amp;id for CFTPARM &amp;id _ No Default record found  |
| --- | --- |
|  Explanation  |  During Transfer CFT initialization the identifier describing the default file characteristics used for receive transfers (CFTRECV parameter) is unknown.  |
|  Consequence  |  The Transfer CFT initialization phase cannot continue correctly and {{< TransferCFT/componentshortname  >}} is aborted.  |
|  Action  |  Check CFTPARM (DEFAULT=.) and CFTRECV parameter settings, correct and restart Transfer CFT.  |


 


|  V23 format<br/>V24 format<br/>Error  |  CFTP13F CFTXLATE &amp;id _ Not found<br/>CFTP13F CFTXLATE &amp;id not found (DIRECT=&amp;direct FCODE=&amp;fcode NCODE=&amp;ncode  |
| --- | --- |
|  Explanation  |  There is no CFTXLATE command, the identifier of which is &amp;id.  |
|  Consequence  |  The transfer requiring this translation table definition cannot be executed.  |
|  Action  |  Specify a CFTXLATE command for this transfer direction and the source and target alphabets.  |


 


|  V23 format<br/>V24 format<br/>Error  |  <span id="CFTP14F"></span>CFTP14F CFTACCNT &amp;id for CFTPARM &amp;id _ Not found<br/>CFTP14F CFTACCNT &amp;id for CFTPARM &amp;id _ Not found  |
| --- | --- |
|  Explanation  |  During Transfer CFT initialization the command describing the accounting characteristics (CFTACCNT command), the ID parameter of which corresponds to the ACCNT parameter in the CFTPARM command, was not found.  |
|  Consequence  |  The Transfer CFT initialization phase cannot continue correctly and {{< TransferCFT/componentshortname  >}} is aborted.  |
|  Action  |  Check the CFTACCNT parameter settings, correct and restart {{< TransferCFT/componentshortname  >}}.  |


 


|  V23 format<br/>V24 format<br/>Error  |  <span id="CFTP15F"></span>CFTP15F CFTPROT &amp;idprot for CFTPARM &amp;idparm _ Not loading in memory<br/>CFTP15F CFTPROT &amp;id for CFTPARM &amp;id _ Not loading in memory  |
| --- | --- |
|  Explanation  |  During Transfer CFT initialization the CFTPROT &amp;idprot card could not be loaded in memory (insufficient space).  |
|  Consequence  |  This card cannot be used for transfers.  |
|  Action  |  Reduce the number of CFTPROT card identifiers in the CFTPARM &amp;idparm command (see the {{< TransferCFT/componentshortname  >}} topics that correspond to your OS to find out the parameter setting limits). After correcting your parameter settings, restart {{< TransferCFT/componentshortname  >}}.  |


 


|  V23 format<br/>V24 format<br/>Error  |  <span id="CFTP16F"></span>CFTP16F CFTNET &amp;idnet for CFTPARM &amp;idparm _ Not loading in memory<br/>CFTP16F CFTNET &amp;id for CFTPARM &amp;id _ Not loading in memory  |
| --- | --- |
|  Explanation  |  During Transfer CFT initialization the CFTNET &amp;idnet card could not be loaded in memory (insufficient space).  |
|  Consequence  |  This card cannot be used for transfers.  |
|  Action  |  Reduce the number of CFTNET card identifiers in the CFTPARM &amp;idparm command (see the {{< TransferCFT/componentshortname  >}} topics that correspond to your OS to find out the parameter setting limits).<br/>After correcting your parameter settings, restart {{< TransferCFT/componentshortname  >}}.  |


 


|  V23 format<br/>V24 format<br/>Error  |  <span id="CFTP17F"></span>CFTP17F CFTCOM &amp;idcom for CFTPARM &amp;idparm _ Not loading in memory<br/>CFTP17F CFTCOM &amp;id for CFTPARM &amp;id _ Not loading in memory  |
| --- | --- |
|  Explanation  |  During Transfer CFT initialization the CFTCOM &amp;idcom card could not be loaded in memory (insufficient space).  |
|  Consequence  |  This card cannot be used for transfers.  |
|  Action  |  Reduce the number of CFTCOM card identifiers in the CFTPARM &amp;idparm command (see the {{< TransferCFT/componentshortname  >}} topics that correspond to your OS to find out the parameter setting limits).<br/>After correcting your parameter settings, restart {{< TransferCFT/componentshortname  >}}.  |


 


|  V23 format<br/>V24 format<br/>Error  |  <span id="CFTP18F"></span>CFTP18F Error of integrity<br/>CFTP18F Error of integrity  |
| --- | --- |
|  Explanation  |  An integrity violation has been detected on the parameter or partner file when the file is sealed. The previous message of the CFTIxxx (partner file) or CFTPxxx (parameter file) type gives more information about the operation requested on the file(s).  |
|  Consequence  |  The Transfer CFT initialization phase is aborted.  |


 


|  V23 format<br/>V24 format<br/>Error  |  <span id="CFTP19E"></span>CFTP19E PART=&amp;part IDF=&amp;idf CFTAPPL=&amp;id DIRECT=&amp;direct not found<br/>CFTP19E PART=&amp;part IDF=&amp;idf CFTAPPL=&amp;id DIRECT=&amp;direct not found  |
| --- | --- |
|  Explanation  |  The security system is running but the CFTAPPL &amp;id card used to assign an owner to a transfer and corresponding to IDF=&amp;idf was not found.  |
|  Consequence  |  The transfer is rejected and no entry is created in the catalog.  |


 

```
V23 format
V24 format
Error
<span id="CFTP20E"></span>CFTP20E The client CFTSSH &ssh cannot be found for partner &part
CFTP20E The client CFTSSH &id cannot be found for partner &id
Explanation
A client CFTSSH referenced in a CFTPART cannot be found.
Action
Add the CFTSSH.
```

 


|  V23 format<br/>V24 format<br/>Error  |  <span id="CFTP20F"></span>CFTP20F direct=server &amp;id for CFTPROT &amp;prot _ Not found<br/>CFTP20F CFTSSL direct=server &amp;id for CFTPROT &amp;id _ Not found  |
| --- | --- |
|  Explanation  |  The security (SSL) being activated, the CFTSSL &amp;id direct=server card whose ID parameter corresponds to the value of the SSL parameter, CFTPROT command was not found.  |
|  Consequence  |  The Transfer CFT initialization phase has shut down.  |


 

```
V23 format
V24 format
Error
<span id="CFTP21E"></span>CFTP21E The client private key &key cannot be loaded from &origin
CFTP21E The client private key &key cannot be loaded from &origin
Explanation
Could not load the private key defined in the CLIPRIVKEY  parameter from file (&origin = file) or PKI database (&origin = PKI database).
Action
Check if the key has been inserted in the PKI database and that the key name is correct. For a file, check the file name and file format (should be RSA).
```

 

```
V23 format
V24 format
Error
<span id="CFTP22E"></span>CFTP22E The client public key &key cannot be loaded from &origin
CFTP22E The client public key &key cannot be loaded from &origin
Explanation
Could not load the public key defined in the CLIPRIVKEY  parameter from file (&origin = file) or PKI database (&origin = PKI database).
Action
Check if the key has been inserted in the PKI database and that the key name is correct. For a file, check the file name and file format (should be RSA).
```

 

```
V23 format
V24 format
Warning
<span id="CFTP23W"></span>CFTP23W CFTNET &id for CFTPARM &id uses &net network _ Disabled
CFTP23W CFTNET &id for CFTPARM &id uses &net network _ Disabled
Explanation
Only CFTNET  TCP type protocols are loaded when starting {{< TransferCFT/componentlongname >}}.
Action
Remove the unsupported protocols if you no longer want this message to display.
```

 

```
V23 format
V24 format
Warning
CFTP24W CFTPROT &id uses CFTNET &id _ Disabled
CFTP24W CFTPROT &id uses CFTNET &id _ Disabled
Explanation
Only CFTNET  TCP type protocols are loaded when starting {{< TransferCFT/componentlongname >}}.
Action
Remove the unsupported protocols if you no longer want this message to display.
```


|  V23 format<br/>V24 format Warning  |  <span id="CFTP24W"></span>CFTP25W CFTCOM &amp;id uses TYPE 'MBX' Disabled<br/>CFTP25W CFTCOM &amp;id uses TYPE 'MBX' Disabled  |
| --- | --- |
| Explanation  | The CFTCOM mailbox is no longer supported on z/OS, Windows platforms.  |
| Action  | Remove the unsupported TYPE.  |


 

```
V23 format
V24 format
Error
<span id="CFTP30F"></span>CFTP30F CFTSSH &ssh for CFTPROT &prot cannot be found
CFTP30F CFTSSH &id for CFTPROT &id cannot be found
Explanation
Cannot find the server CFTSSH referenced in a CFTPROT.
Action
Add the CFTSSH.
```

 

```
V23 format
V24 format
Error
<span id="CFTP30F"></span>
<span id="CFTP31F"></span>CFTP31F CFTNET &id for CFTPROT &id cannot be found
CFTP31F CFTNET &id for CFTPROT &id cannot be found
Explanation
Cannot find the CFTNET referenced in this CFTPROT.
Action
Check the CFTNET referenced in CFTPROT and add the CFTNET if necessary.
```
