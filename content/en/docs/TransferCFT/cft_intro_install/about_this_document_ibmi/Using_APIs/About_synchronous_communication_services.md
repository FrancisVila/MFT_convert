{
    "title": "Synchronous  communication services",
    "linkTitle": "Synchronous communication services",
    "weight": "260"
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
