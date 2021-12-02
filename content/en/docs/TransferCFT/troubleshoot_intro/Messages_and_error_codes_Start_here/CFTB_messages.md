{
    "title": "Transfer CFT messages: CFTB",
    "linkTitle": "CFTAB messages",
    "weight": "270"
}This topic lists the CFTBxx messages and provides a type, a description, and when applicable a consequence and corrective action.

**Message format**

Earlier versions of Transfer CFT used a different message format than version 3.1.3 and higher. This document displays both formats when applicable and available, otherwise only the v23 is used. Using the CFTLOG Format = V24 setting, the log displays as shown:

CFTXXX: fixed text message &lt;variables>

**Example**

CFTLOG FORMAT=\[V23,V24\]

For V23: `CFTT57I PART=&part IDF=&idf IDT=&idt &str transfer started`

For V24: `CFTT57I &str transfer started   <IDTU=&idtu PART=&part IDF=&idf IDT=&idt>`

### Auto documented messages

Certain auto-documented messages, for example CFTA01I, CFTA02W, CFTA03E, CFTA04F, are not fully detailed as they are considered self-explanatory. The CFTAnnx messages refer to the acceleration feature on all platforms that support acceleration.

-   CFTA01, CFTLOG\_SYS\_INFOR "CFTA01I &str"
-   CFTA02, CFTLOG\_SYS\_WARNI "CFTA02W &str"
-   CFTA03, CFTLOG\_SYS\_ERROR "CFTA03E &str"
-   CFTA04, CFTLOG\_SYS\_FATAL "CFTA04F &str"

 

```
V23 format
V24 format
Error
<span id="CFTB01E"></span>CFTB01E PART=&part Context area allocation failure
CS=&scs
CFTB01E PART=&part Context area allocation failure CS=&cs
Explanation
Cannot allocate the working area necessary for the transfer.
Consequence
In REQUESTER mode, the transfer is refused with a {{< TransferCFT/componentshortname >}}
122 diagnostic code and a MALLOC protocol diagnostic message.
In SERVER mode, the incoming call is rejected.
In this case, as the partner's name is not known, the value
UNKNOWN is displayed.
```

 

```
V23 format
V24 format
Error
<span id="CFTB02E"></span>CFTB02E PART=&part
TFIL Exchange buffer allocation failure CS=&scs
CFTB02E PART=&part TFIL Exchange buffer allocation failure CS=&cs
Explanation
Cannot allocate the working area required to exchange information
between the PROTOCOL task and the FILE task.
Consequence
In REQUESTER mode, the transfer is refused with a Transfer
CFT 122 code and a MALLOC protocol diagnostic message.
In SERVER mode, the incoming call is rejected. In this
case, as the partner's name is not known, the value UNKNOWN is displayed.
```

 

```
V23 format
V24 format
Error
<span id="CFTB03E"></span>CFTB03E PART=&part Error sending data on network
NCR=&ncr NCS=&ncs NET=&net
CFTB03E PART=&part Error sending data on network NCR=&ncr NCS=&cs NET=&net
Explanation
Cannot send a message on the network.
Consequence
The transfer
is interrupted with a {{< TransferCFT/componentshortname >}} 302 code and a protocol diagnostic
message indicating the specific error code of the error occurring during
the send request. This code is expressed in hexadecimal form.
```

 

```
V23 format
V24 format
Error
<span id="CFTB06E"></span>CFTB06E Flow control error NCR=&ncr NCS=&ncs
NET=&net
CFTB06E PART=&part Flow control error NCR=&ncr NCS=&cs NET=&net
Explanation
Network flow control error.
```

 

```
V23 format
V24 format
Error
<span id="CFTB07E"></span>CFTB07E PART=&part TFIL task Synchronization error
CR=&cr CS=&cs
CFTB07E PART=&part TFIL task Synchronization error CR= &cr CS=&cs
Explanation
Problem encountered when sending an internal {{< TransferCFT/componentshortname >}}
message to the FILE task.
Consequence
The transfer is aborted by the protocol task (network disconnection).
However, as the FILE task is not protected by a time-out, the request
remains in the C status in the catalog
```

 

```
V23 format
V24 format
Error
<span id="CFTB08E"></span>CFTB08E PART=&part Network release resp err NCR=&ncr
NCS=&ncs NET=&net
CFTB08E PART=&part Network release resp err NCR=&ncr NCS=&cs NET=&net
Explanation
Cannot respond to a network disconnection indication.
Consequence
This incident has no effect on the previous transfer (whether
completed or interrupted).
```

 

```
V23 format
V24 format
Error
<span id="CFTB09E"></span>CFTB09E PART=&part Network connect req local err
NCR=&ncr NCS=&ncs NET=&net
CFTB09E PART=&part Network connect req local err NCR=&ncr NCS=&cs NET=&net
Explanation
Cannot make an outgoing connection request on the network.
Consequence
For a general
-6 code (maximum number of connections reached on the resource), the transfer
is refused with a {{< TransferCFT/componentshortname >}} 416 diagnostic code and a MAXCNX protocol
diagnostic message. The transfer will be retried (minimum time-out equal
to the WSCAN parameter of the CFTCAT command), without incrementing the
retry counter.
```

 

```
V23 format
V24 format
Error
<span id="CFTB10E"></span>CFTB10E PART=&part RECOV=&recov L=&local
R=&reason D=&diag NET=&net
CFTB10E PART=&part RECOV=&recov L=&local R=&reason ld D=&diag ld NET=&net
Explanation
Physical connection refused.
Consequence
Depending on the source of the refusal and the RECOV code, the
transfer is set to the K status (diagnostic code 303) or remains
in the D status (diagnostic code 302) and will be retried.
```

 

```
V23 format
V24 format
Error
<span id="CFTB18E"></span>CFTB18E Incoming call reject error NCR=&ncr NCS=&ncs
NET=&net
CFTB18E Incoming call reject error NCR=&ncr NCS=&cs NET=&net
Explanation
Cannot refuse an incoming call.
```

 

```
V23 format
V24 format
Error
<span id="CFTB19E"></span>CFTB19E Incoming call accept error NCR=&ncr NCS=&ncs
NET=&net
CFTB19E Incoming call accept error NCR=&ncr NCS=&cs NET=&net
Explanation
Cannot accept an incoming call.
```

 

```
V23 format
V24 format
Error
<span id="CFTB19E"></span>CFTB20E Invalid ETEBAC3 Card &id NET=&net
CFTB20E Invalid ETEBAC3 Card &id NET=&net
Explanation
 
```

 

```
V23 format
V24 format
Error
<span id="CFTB21E"></span>CFTB21E PART=&part MAIN task Synchronization error
CR=&cr CS=&scs
CFTB21E PART=&part MAIN task Synchronization error CR= &cr CS=&cs
Explanation
Transfer
CFT internal synchronization error.
```
