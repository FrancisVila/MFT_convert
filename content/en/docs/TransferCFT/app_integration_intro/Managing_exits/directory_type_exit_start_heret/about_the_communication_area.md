{
    "title": "About  the communication area",
    "linkTitle": "About the communication area",
    "weight": "320"
}This topic describes the communication area structure. The communication
area contains:

-   [General
    information fields](#General_information_fields)
-   [Return
    codes](#Return_codes___directory_exit)
-   [Partner
    information](#Partner_information___directory_exit)
-   [Partner
    network information](#Partner_network_information___directory_exit)
-   [Information
    per network type](#Partner_network_information___directory_exit) (not supported by all networks)

The next topic describes the communication area structure between the
interface and the user program.

The following tables list all the fields of the communication structure.

<span id="General_information_fields"></span>

### General information fields

```
Field
Explanation
version 
Interface
version number
The current version
number is "0130".
idexit 
EXIT task
identifier
exname
User name
The user name is equal to the value of the exaref parameter
of the exaini function.
parm
User parameter
The user parameter
is equal to the value of the PARM parameter of the CFTEXIT object.
exver
Exit version V24 or higher
language
Language
of the user program:

-   C: C
    language
-   O: COBOL

etype
EXIT task
type
A: directory Exit
etrace
Inoperative
parameter
mode
Call mode:

-   R: Requester
    mode
-   S: Server
    mode

commutfl
Switching
flag (intermediate partner):

-   0: no
    switching in process
-   1: switching
    in process

curtime
Current
time (HHMMSSCC)
curdate
Current date (YYYYMMDD)
curreqc
Current number of transfers in requester
mode for the given network partner
cursrvc
Current number of transfers in server
mode for the given network partner
maxrty
Requester mode only
Maximum number of network connection attempts
currty
Requester
mode only
Current number of network connection attempts
maxrtyp 
Requester
mode only
Maximum
number of protocol connection attempts
currtyp
Requester
mode only
Current
number of protocol connection attempts
protl 
Information about the protocols of the CFTPARM object:

-   protocol
    identifier
-   protocol
    type
-   profile,
    in the case of the PESIT protocol
-   associated
    network type

idf 
Partner-related
file identifier
```
<span id="Return_codes___directory_exit"></span>

### Return codes

```

Field

Explanation

ret1
Return
code

-   0: Processing
    ok
-   1: Transfer
    CFT must take charge of the call
-   2: Connection
    refusal
-   9: Processing
    error

ret2 
Cause
of connection refusal if the return code value is 2

-   1: Partner
    not known
-   2: Password
    not valid
-   3: Address
    not known
-   4: Call
    time not valid
-   5: Communication
    protocol not valid
-   6: Maximum
    number of virtual circuits reached
-   7: Maximum
    number of transfers reached
-   8: Maximum
    number of partners reached
-   9: Caller
    taxation refusal
-   10: Network
    problem
-   255:
    Other cause of connection refusal

These refusal codes are converted by {{< TransferCFT/componentshortname >}} into
internal diagnostic codes.
In
server mode, the internal diagnostic codes are converted into
protocol diagnostic codes and sent to the calling partner.
In
requester mode, the internal diagnostic codes are saved in
the catalog.
diag
Diagnostic
code if the return code is not 0 and 1
The contents of this field are used in the EXIT related
error.
msg 
User message
If this field is defined, the content is sent to the Transfer
CFT standard output.
```
<span id="Partner_information___directory_exit"></span>

### Partner information

```

Field

Explanation

ptype
Partner
type:

-   C: normal
    {{< TransferCFT/componentshortname >}} partner
-   D: dynamic
    {{< TransferCFT/componentshortname >}} partner
-   E: non
    {{< TransferCFT/componentshortname >}} partner

part
Partner
local identifie
ipart
Intermediate partner local identifier
cpart
Associated store and forward partner identifier
idnet
Network resource identifier
idprot
Protocol identifier
prot
Protocol type:

-   P: PeSIT
    protocol
-   0: ODETTE
    protocol

prof
PeSIT
only
Profile:

-   C : PeSIT
    D, Cft
-   S: PeSIT
    D, Sit
-   A: PeSIT
    E
-   D: PeSIT
    E (DMZ)

syst
Operating
system:

-   4: OS400
-   7: GCOS7
-   8: GCOS8
-   M: MVS
-   S: UNIX
-   V: VMS
-   G: GUARD
-   B: BS2000
-   W: WINDOWS

code 
Code:

-   A:  ASCII
-   E:  EBCDIC

open
No longer supported
commut
Store
and forward indicator:

-   N:  No
    store and forward
-   Y: Immediate
    store and forward
-   S: Deferred
    store and forward
-   P: Forced
    commutation

sap
Remote
SAP (Service Access Point)
imaxtime
Maximum incoming call time (HHMMSSCC)
imintime
Minimum incoming call time (HHMMSSCC)
omaxtime
Maximum outgoing call time (HHMMSSCC)
omintime
Minimum outgoing call time (HHMMSSCC)
nrpart
Remote partner name
nrpassw
Remote partner password
newnrpw
PeSIT E only
Remote partner new password
nspart
Local name
nspassw
Local password
newnspw
PeSIT E only
New local password
group
Group identifier
sauth
File send authorization list identifier
rauth
File receive authorization list identifier
xlate
Transcoding table identifier
```
<span id="Partner_network_information___directory_exit"></span>

### Partner network information

```

Field

Explanation

ntype
Network
type:

-   T: TCP

addr
Remote
partner address
imaxt
Maximum incoming call time on the network
resource
imint
Minimum incoming call time on the network
resource
omaxt 
Maximum outgoing call time on the network
resource
omint
Minimum outgoing call time on the network
resource
retryw
Spacing of connection attempts (in minutes)
retryn
Number of connection attempts spaced by
retryw
retrym
Maximum number of connection attempts
cnxin
Maximum number of simultaneous incoming
calls for the given network partner
cnxout
Maximum number of simultaneous outgoing
calls, for the given network partner
cnxinout
Maximum number of simultaneous communications,
for the given network partner
```
<span id="Network_dependent_information___directory_exit"></span>

### Network dependent information

```

Field

Explanation

udata
User data
odata
Other data.
speedin
Virtual
circuit input speed (in bits/second)
speedout
Virtual circuit output speed (in bits/second)
pcvin
Incoming reverse charge call:

-   1: Yes
-   0: No

pcvout
Outgoing
reverse charge call:

-   1: Yes
-   0: No

gfa
Closed
subscriber group number
verify
Number of characters (between 0 and 64)
to be checked in the caing partner address
parity
Obsolete parameter
databit
Obsolete parameter
stopbit
Obsolete parameter
modout
Obsolete parameter
config
Obsolete parameter
padno
Obsolete parameter
padset
Obsolete parameter
```

### Additional information

```

Field

Explanation

cMode
SSL mode Client/Server
cAuthPolicy
SSL auth Anonymous/Simple/Double
bCipher
SSL cipher suite
sParm
SSL command free parameters
sRemoteUserDn
Remote User certificate Dn
sRemoteIssuerDn
Remote Issuer Dn
sRemoteCaId
Remote CA Alias
sUserCId
User Certificate Alias
sCertFname
File including Remote certificate
sProf
SSL profile ID
sRemoteSerial
Serial Number
ExitFree
Free Area between all EXITs
XferCycleId
CycleId for tracking occurrences
XferObjectcId
Name of the transfer tracking class
```
