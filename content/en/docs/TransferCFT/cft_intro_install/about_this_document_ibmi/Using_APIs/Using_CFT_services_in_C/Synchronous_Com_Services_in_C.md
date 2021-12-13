{
    "title": "Synchronous  communication services",
    "linkTitle": "Synchronous communication services in C",
    "weight": "330"
}This topic describes  {{< TransferCFT/componentshortname  >}} synchronous communication services.

## Description of functions

```

Function

Use

COM
Set the communication medium
GETXINFO
Retrieve information concerning the last transfer made
from a synchronous request after a request of the following types: SEND,
RECV, HALT, KEEP, START, RESUME, DELETE, END, SUBMIT, SWITCH, PURGE.
The information is stored in a cftApiInf-type structure:

-   Transfer
    state
-   Diagnostic
-   Diagnostic
    protocol
-   Value
    of the PART field of CFTPARM
-   Transfer
    identifier (IDT)
-   Local
    transfer identifier (IDTU)
-   Transfer
    type (single, cyclical, diffusion list, collection, file group)
-   Public
    reference of the transfer (only for a single transfer in Send)

The GETXINFO action returns an error if the communication
medium is not synchronous.

> **Note**
> The public
> reference of the transfer is a character string of variable length. In
> the PESIT protocol, it contains 'pi13.pi3.pi4.pi11.pi12.pi61.pi62'.

```
<span id="Call Syntax"></span>

## Call syntax

rc =      cftau (verb,param)

rc =      cftac (verb,param)

Where:

-   cftau indicates
    that syntax analysis is requested  
    cftac indicates that syntax analysis is not requested
-   &lt;verb> is
    the command that you want to process
-   &lt;param> is
    a character string of variable length that contains the command parameters.
    The end of the field is defined by a character initially set to low-value
-   &lt;rc> is the
    return code

The available &lt;verbs> are listed in the following table.

```

<verb>

Service

COM
Communication mode
GETXINFO
Retrieving information about a transfer made from a synchronous
request
```

The available &lt;param> are listed in the following table.

```

<verb>

<param>

Description

com
 
param
 
The COM command parameter structure is as follows: <medium
type> = <Medium name>
The medium type consists in an uppercase letter:

-   'F' for
    file
-   'T' for the TCP/IP synchronous medium
-   'C' for
    the configuration file (ConfigFileName)

The medium name is the:

-   Filename,
    if the medium type is 'F'
-   Name
    of the communication channel, if the medium type is 'T'
-   Name
    of the configuration file containing the medium of communication characteristics,
    if the medium type is C.

getxinfo
xinf
Information about a transfer in the format described in
the cftapi.h file.
```

## Step procedure

Use the COM command to define the synchronous medium.

1.  Open the synchronous communication.
2.  Write the command. This is not specific to synchronous mediums.
3.  Retrieve information using the GETXINFO service.

To view the synchronous communication template containing details and an example, see tcftsyn.

## Return codes

```

Mnemonic

Description

CAPI_NOERR
No error.
CAPI_FUNC_UNDEF
Command not valid.
CAPI_COM_OPEN
Communication medium opening error.
CAPI_COM_WRITE
Communication medium write error.
CAPI_COM_CLOSE
Communication medium closing problem.
CAPI_COM_ALLOC
Communication medium allocation problem.
CAPI_COM_ERR
Communication medium not available on this system.
```
