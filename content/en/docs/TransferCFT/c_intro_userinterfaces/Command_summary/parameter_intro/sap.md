{
    "title": "sap",
    "linkTitle": "sap",
    "weight": "3030"
}<span id="sap"></span>

### sap

#### CFTPROT

\[SAP = string32 \]

Name of the local SAP, Service Access Point, associated with this protocol.
It is used to identify the access point at which incoming connection requests
for this communication protocol are placed.

The SAP supplied by a requester partner when making its connection request
is retrieved by the local  {{< TransferCFT/componentshortname  >}}, which uses it to deduce the protocol
to be used. Each CFTPROT command in a given resource class must include
its specific SAP.

If the SAP parameter is not set to a value for a given protocol, that
protocol is only available in requester mode.

#### CFTPROT SAP - Parameter values

<table>
   <thead>
      <tr>
<th >Access method         </th>
<th colspan="2" ><p>Size in characters </p>         </th>
<th >Details         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td   data-valign="top" width="14%"><p>TCP/IP </p>         </td>
         <td colspan="2"   data-valign="top"><p>1 to 15<br />
 </p>         </td>
         <td   data-valign="top"><p>Number of the local monitoring port on which the Transfer CFT
can be called, expressed in the form of the:</p>
<ul>
<li>real number used
by TCP/IP:</li>
<li>authorized
numbers: between 1025 and 65535</li>
<li>recommended
numbers: 1761, 1762, 1763, 1764, 1765, 1766, 1767, 1768 <strong>(1)</strong></li>
<li>logical name
associated with the number used by TCP/IP and configured in the SERVICES
file (if this file exists)<br />
<br />
recommended logical names: cft-0, cft-1, cft-2, cft-3, cft-4, cft-5,
cft-6, cft-7 <strong>(1)</strong></li>
</ul>         </td>
      </tr>
   </tbody>
</table>

**(1):** these logical port numbers and
names have been officially reserved by Sopra from the IANA (Internet Assigned
Numbers Authority).

**<span id="CFTPART_SAP___Parameter_values"></span>CFTPART**

\[SAP
= (string, string, string, ...) \]

Values of the remote SAPs (service
access points) associated with each of the protocols defined by the PROT
parameter.

-   For transfers to a  {{< TransferCFT/componentshortname >}} other than
    the  {{< TransferCFT/componentshortname >}}, the use of this additional information should
    be looked into on a case by case basis.
-   For transfers to a  {{< TransferCFT/componentshortname >}},
    this parameter is used to designate the protocol applied to the partner
      {{< TransferCFT/componentshortname >}}. In other words, the "sap" is an additional
    item of information used to reach a remote application subset (a protocol
    in the  {{< TransferCFT/componentshortname >}} case) and not only a  {{< TransferCFT/componentshortname >}}.
-   Each of the values of the parameter represents the "sap" associated
    with the communication protocol, the identifier of which matches in the
    PROT parameter.
-   The maximum number of SAPs equals the maximum number of protocols (see
    the table for the PROT parameter).

The value
of this parameter is specific to each data exchange protocol, and to each
system, as applicable, as specified in the table below.

CFTPART SAP - Parameter values

```

Access method 

Size in characters
(alphanumeric)

Definition and comments 

TCP/IP 
1 to 15
 
Number of the port on which the monitor partner is listening.
The value of this number can be:

-   a number
    in clear corresponding to the real number used by the remote partner at
    the protocol level of the TCP/IP protocol
    Authorized numbers: between 1025 and 65535 (not including limit values)
    Recommended numbers: between: 1761, 1762, 1763, 1764, 1765, 1766, 1767,
    1768 (1)
-   the logical
    name associated with the number used by TCP/IP and configured in the SERVICES
    file, if this file exists
    Recommend logical names: cft-0, cft-1, cft-2, cft-3, cft-4,
    cft-5, cft-6, cft-7 (1)

If the local and remote partner parameter setting commands (CFTPART
and CFTPROT respectively) use the logical name of the port defined in
the "SERVICES" database, the consistency of the two bases must
be ensured 
```

**(1)** These logical port numbers and
names have been officially reserved by SOPRA from the IANA (Internet Assigned
Numbers Authority).

 

[Return to Command index](../../)
