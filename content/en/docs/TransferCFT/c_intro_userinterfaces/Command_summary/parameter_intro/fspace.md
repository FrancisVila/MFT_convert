{
    "title": "fspace",
    "linkTitle": "fspace",
    "weight": "1350"
}<span id="fspace"></span>

### fspace

<span id="fspace_CFTRECV"></span>

#### CFTRECV, RECV

**\[FSPACE = {** **0**
**| n } \]**

Size of the receiver file, in Kbytes
(1 Kbyte = 1024 bytes).

This size usually corresponds to the primary allocation.

<span id="fspace_CFTSEND"></span>

#### CFTSEND, SEND

**\[FSPACE = {
| n } \]**

Size of the file to be sent, in Kbytes (1 Kbyte = 1024 bytes).

This parameter does not usually need to be defined, since at each transfer
CFT automatically retrieves the size of the file it is going to send (if
necessary, check in the *Operations Guide* that this facility is
supported by the system in question).

<span id="fspace_CFTFILE"></span>

#### CFTFILE

\[FSPACE
= {see [table](#FSPACE_Table) | n}\]

{0..65536}

According to TYPE/**OS**

Primary allocation of the file to be created, expressed in Kbytes (1024).

For TYPE = COM and TYPE = CAT, this parameter should not be defined
for any system. The primary allocation of the file to be created is deduced
from the value of the RECNB parameter (number of records in the file).

The table below indicates, for each system, the default value supported
according to the type of file to be created. In this table, the FSPACE
parameter does not need to be defined when the default value of the primary
allocation of the file to be created is "no".

[Return to Command index](../../)
