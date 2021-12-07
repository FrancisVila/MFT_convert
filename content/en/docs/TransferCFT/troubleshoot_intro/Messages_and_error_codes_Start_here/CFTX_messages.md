{
    "title": " Transfer CFT messages:  CFTW and CFTX",
    "linkTitle": "CFTX messages",
    "weight": "390"
}This topic lists the  CFTWxx and CFTXxx  messages and provides the type,  a description, consequence, and corrective actions when applicable.

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
<span id="CFTX01W"></span>CFTX01W Action &action on object &object not authorized for user &user : ID CFTAPPL=&id CFTX01W Action &action on object &object not authorized for user &user : ID CFTAPPL=&id
Explanation
The authorization system does not allow the &user user to
set the &idf IDF, as indicated in the preceding message (either CFTC10I or CFTC11I). You should check with your security administrator to determine
your access rights.
```

 

```
V23 format
V24 format
Warning
<span id="CFTX02W"></span>CFTX02W owner user is &user, owner group is &group
CFTX02W owner user is &user, owner group is &group
Explanation
The user and group names used are displayed. This message is
displayed after the CFTX01W message.
```

 

```
V23 format
V24 format
Warning
<span id="CFTX03W"></span>CFTX03W Action &action on object &object not
authorized for user &user
CFTX03W+Action &action on object &object not authorized for user &user
Explanation
The security system does not allow &user to perform the
specified action (contact your security administrator to set the required
privileges).
```

 

```
V23 format
V24 format
Warning
<span id="CFTX04W"></span>CFTX04W
With value &value
CFTX04W+with value &value
Explanation
Warning message.
```

 

```
V23 format
V24 format
Warning
<span id="CFTX05W"></span>CFTX05W Action &action on object &object not
authorized for user &user: FNAME=&fname
CFTX05W Action &action on object &object not authorized for user &user : FNAME=&fname
Explanation
The security system does not allow &user to specify &fname
as the FNAME value (contact your security administrator to set the required
privileges).
```

 

```
V23 format
V24 format
V23 format
V24 format
V23 format
V24 format
Information
<span id="CFTX10I"></span>CFTX10I Warning : security file commands were modified
CFTX10I Warning : security file commands were modified
<span id="CFTX11I"></span>CFTX11I+ without a generation was done
CFTX11I+ without a generation was done
<span id="CFTX12I"></span>CFTX12I+ Some queer comportements will happenned.
CFTX12I+ Some queer comportements will happenned.
Explanation
Modifications have been made to the authorization system,
but the system has not been regenerated.
Abnormal behavior may arise when {{< TransferCFT/componentshortname >}} is executed.
```
