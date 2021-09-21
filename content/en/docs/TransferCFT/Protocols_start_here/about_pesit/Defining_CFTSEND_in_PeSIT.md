{
    "title": "Defining CFTSEND in PeSIT",
    "linkTitle": "Defining CFTSEND in PeSIT",
    "weight": "200"
}# <span id="Defining_CFTSEND_in_PeSIT"></span>Defining CFTSEND in PeSIT 

The CFTSEND object contains the parameters controlling the access to
the data to be sent and the execution of the send process.

When the transfer is initiated by a local SEND object explicitly containing
one or more parameters also contained in the CFTSEND object, the parameters
of the SEND command take precedence over the others, unless the CFTSEND
FORCE parameter is set to YES. For the other parameters common to both
objects, CFTSEND only provides the SEND default values.

This topic presents the CFTSEND
object parameters that are affected by the PeSIT protocol. These parameters
are:

-   The partner [identification parameters](#identification_parameters)
-   The [data
    processing parameters](#data_processing_parameters)
-   The [file
    network characteristics](#file_network_characteristics)
-   A free parameter
    for the [Transfer CFT user](#user_parameter)
-   [An
    execution control parameter](#execution_control_parameter)
-   [Parameter
    values for negotiated functional levels](#parameter_values_for_negotiated_functional_levels)

### <span id="Identification_parameters"></span>Identification parameters

#### **PeSIT E**

The **RAPPL** and **SAPPL** parameters identify the file receiver
and sender users respectively. The **RUSER** and **SUSER** parameters
identify the file receiver and sender applications respectively.

#### **PeSIT E CFT/CFT**

In PeSIT E, the protocol standard only allocates 8 characters for transporting
these parameters. However, with a Transfer CFT monitor, the maximum size
authorized for **RAPPL** and **SAPPL** is 48 characters. The size
authorized for **RUSER** and **SUSER** is 28 characters.

For some PeSIT profiles, the RAPPL, SAPPL, RUSER and SUSER parameters
can be sent to the partner during the selection phase.

If the partner is a Transfer CFT server/sender,
it checks these parameters against any values set in its CFTSEND or SEND
parameters. It processes the receive request first based on a send operation
on hold, SEND TYPE = HOLD, and then by default based on an implicit send,
CFTSEND IMPL = YES. The request is however ignored if the parameters set
in the command are different from those sent by the receiver partner.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top"> If the requester/receiver does 
 not set any parameters, it uses the corresponding value sent by the server/sender.         </td>
      </tr>
</table>

If the partner is a server/receiver,
the parameters sent override those set in the associated receive command.

### <span id="Data_processing_parameters"></span>Data processing parameters

The on-line compression of data requested by the user is given by the
**NCOMP** parameter. The authorized values and the default values are
the same as for the SCOMP parameter of the CFTPROT object. During transmission,
the combination of the values taken by NCOMP and SCOMP is used as a basis
for the protocol data compression negotiation.

The list of the authorized values is given in the description of the
SCOMP parameter of the CFTPROT object.

### <span id="File_network_characteristics"></span>File network characteristics

These parameters relate to the file characteristics for the partner.
The corresponding information is sent in the data units of the PeSIT protocol
(FPDU) and are used by the receiving monitor according to its specific
capabilities. The values sent must be valid for the receiving partner.

#### PeSIT E

The following characteristics can be sent by the PeSIT protocol:

-   FDATE/FTIME:
    date and time attached to the file,
-   NCODE:
    code of data sent
-   NFNAME:
    filename on receiver site (transmission in open mode)
-   NIDF:
    file network identifier
-   NLRECL:
    size of receiver file records
-   NORG:
    file organization
-   NRECFM:
    file record format (fixed, variable)
-   NSPACE:
    file size

#### PeSIT E

The E version of the PeSIT protocol introduced the following characteristics:

-   NKEYLEN:
    length of the access key to an indexed file
-   NKEYPOS:
    location, relative to the start of the article, of the file access key

The NKEYLEN and NKEYPOS parameters are sent but not used by Transfer
CFT. The indexed file is transferred in the form of sequential records.
The client can develop a file type EXIT as required for the purpose of
making use of this information or an end of transfer procedure, symbolic
variables which can be used: &FKEYLEN and &FKEYPOS.

#### PeSIT E CFT/CFT, PeSIT ANY profile CFT/CFT

Transfer CFT specific extensions must be implemented to send the following
characteristics to the partner. The partner must hence be a Transfer CFT:

-   NBLKSIZE:
    file block size
-   NIDF:
    extended to 32 characters for PeSIT E CFT/CFT
-   NRECFM:
    file record format, either fixed, variable, or indefinite
-   NTYPE:
    file type

### <span id="User_parameter"></span>User parameter

PeSIT E CFT/CFT

The PARM parameter, which is not used, can be sent to the receiver
for the purpose of implementing Transfer CFT specific extensions.

### <span id="Execution_control_parameter"></span>Execution control parameter

The PRI parameter designates the priority with which the local
Transfer CFT selects the transmission request. This parameter is also sent
from a protocol standpoint to the remote partner. Given that PeSIT only
recognizes three priority levels, the value sent to the partner will be
converted as follows:

-   PRI > 128: high
    priority
-   PRI = 128: average
    priority
-   PRI &lt; 128: low
    priority

### <span id="Parameter_values_for_negotiated_functional_levels"></span>Parameter values for negotiated functional levels

The table below summarizes the parameter values authorized according
to the functional levels negotiated for the protocol.

<table cellspacing="0">
   <col/>
   <col/>
   <col/>
   <thead>
      <tr>
         <th>
            <p>CFTSEND or SEND parameter </p>
</th>
         <th>
            <p>PeSIT E  </p>
</th>
         <th>
            <p>PeSIT E</p>
            <p>+</p>
            <p>Transfer CFT extensions </p>
</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>
            <p>FDATE/FTIME </p>
         </td>
         <td>
            <p>X </p>
         </td>
         <td colspan="1">
            <p>X </p>
         </td>
      </tr>
      <tr>
         <td>
            <p>NBLKSIZE </p>
         </td>
         <td>
            <p>- </p>
         </td>
         <td colspan="1">
            <p>X </p>
         </td>
      </tr>
      <tr>
         <td>
            <p>NCODE </p>
         </td>
         <td>
            <p>X </p>
         </td>
         <td colspan="1">
            <p>X </p>
         </td>
      </tr>
      <tr>
         <td>
            <p>NCOMP </p>
         </td>
         <td>
            <p>0, 2, 8, 10<br/>(dft: 10) </p>
         </td>
         <td colspan="1">
            <p>0..15<br/>(dft: 15) </p>
         </td>
      </tr>
      <tr>
         <td>
            <p>NFNAME (transmission in open mode) </p>
         </td>
         <td>
            <p>X (3) </p>
         </td>
         <td colspan="1">
            <p>X </p>
         </td>
      </tr>
      <tr>
         <td>
            <p>NIDF</p>
         </td>
         <td>
            <p>string14 </p>
         </td>
         <td colspan="1">
            <p>string28 </p>
         </td>
      </tr>
      <tr>
         <td>
            <p>NLRECL </p>
         </td>
         <td>
            <p>X </p>
         </td>
         <td colspan="1">
            <p>X </p>
         </td>
      </tr>
      <tr>
         <td>
            <p>NKEYLEN </p>
         </td>
         <td>
            <p>X </p>
         </td>
         <td colspan="1">
            <p>X </p>
         </td>
      </tr>
      <tr>
         <td>
            <p>NKEYPOS </p>
         </td>
         <td>
            <p>X </p>
         </td>
         <td colspan="1">
            <p>X </p>
         </td>
      </tr>
      <tr>
         <td>
            <p>NORG</p>
         </td>
         <td>
            <p>X  </p>
         </td>
         <td colspan="1">
            <p>X </p>
         </td>
      </tr>
      <tr>
         <td>
            <p>NRECFM </p>
         </td>
         <td>
            <p>F, V </p>
         </td>
         <td colspan="1">
            <p>F, V, U </p>
         </td>
      </tr>
      <tr>
         <td>
            <p>NSPACE </p>
         </td>
         <td>
            <p>X </p>
         </td>
         <td colspan="1">
            <p>X </p>
         </td>
      </tr>
      <tr>
         <td>
            <p>NTYPE </p>
         </td>
         <td>
            <p>- </p>
         </td>
         <td colspan="1">
            <p>X </p>
         </td>
      </tr>
      <tr>
         <td>
            <p>PARM</p>
         </td>
         <td>
            <p>- </p>
         </td>
         <td colspan="1">
            <p>X </p>
         </td>
      </tr>
      <tr>
         <td>
            <p>PRI  </p>
         </td>
         <td>
            <p>low &lt; 128<br/>average = 128<br/>high &gt; 128 </p>
         </td>
         <td colspan="1">
            <p>low &lt; 128<br/>average = 128<br/>high &gt; 128 </p>
         </td>
      </tr>
      <tr>
         <td>
            <p>RAPPL </p>
         </td>
         <td>
            <p>string8 </p>
         </td>
         <td colspan="1">
            <p>string48 </p>
         </td>
      </tr>
      <tr>
         <td>
            <p>RUSER </p>
         </td>
         <td>
            <p>string8 </p>
         </td>
         <td colspan="1">
            <p>string32</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>SAPPL</p>
         </td>
         <td>
            <p>string8 </p>
         </td>
         <td colspan="1">
            <p>string48 </p>
         </td>
      </tr>
      <tr>
         <td>
            <p>SUSER </p>
         </td>
         <td>
            <p>string8 </p>
         </td>
         <td colspan="1">
            <p>string32</p>
         </td>
      </tr>
   </tbody>
</table>

-   X:  parameter
    used without restriction for protocol exchanges.
-   "-":  parameter
    not used by the protocol.
-   (3): this parameter is conveyed
    by the protocol but the associated semantics (not specified by PeSIT)
    of the open mode is specific to Transfer CFT.