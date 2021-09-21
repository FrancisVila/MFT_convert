{
    "title": "Messages and error codes",
    "linkTitle": "Messages and error codes",
    "weight": "260"
}# Transfer CFT messages and error codes

This section lists the different types of messages that Transfer CFT generates, and corrective actions when applicable. It begins with this section, which describes message formats, severity, and additional conventions used in this documentation.

## Message format

### Format in the documentation

Transfer CFT messages provide information on the status of the Transfer CFT. Messages have the general format and supporting information:

<table border="1" cellspacing="0">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>
            <p>The message severity is displayed</p>
</th>
         <th>
            <p>CFTxxx: the actual message that is displayed on <span>Transfer CFT</span></p>
</th>
      </tr>
   </thead>
   <tbody>
      <tr valign="top">
         <td width="20%">
            <p>Explanation</p>
         </td>
         <td width="80%">
            <p>The elements, such as variables, in the above message are detailed.</p>
         </td>
      </tr>
      <tr valign="top">
         <td width="20%">
            <p>Consequence</p>
         </td>
         <td width="80%">
            <p>Description of what happens to the <span>Transfer CFT</span>, or  lists corrective actions.</p>
         </td>
      </tr>
      <tr valign="top">
         <td width="20%">Action         </td>
         <td width="80%">If applicable, add corrective action here.          </td>
      </tr>
   </tbody>
</table>

### <span id="Message_format"></span>Format in the product

Earlier versions of Transfer CFT used a different message format
than the version 3.1.3 and higher. The error messages displayed in this document use the former, or earlier version, format. If your system uses
the CFTLOG parameter Format = V24,
the log display is as shown below:

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>CFTXXX: fixed text message &lt;variables&gt;         </td>
      </tr>
   </tbody>
</table>

**Example**

CFTLOG FORMAT=\[V23,V24\]

-   For V23: CFTT57I
    PART=&part IDF=&idf IDT=&idt &str transfer started
-   For V24: CFTT57I
    &str transfer started   &lt;IDTU=&idtu
    PART=&part IDF=&idf IDT=&idt>

### Auto documented messages

Certain messages that are auto-documented, for example CFTA01I, CFTA02W, CFTA03E, CFTA04F, may not appear in this documentation. These messages are considered self-explanatory.

## Writing conventions

Messages are written according to the following conventions.

### Message description

The Transfer CFT messages use the format CFTxnns, for example CFTC01E. The elements that make up the message format are described in the following sections.

Where:

-   x: message source
-   nn: sequence number
-   s: message severity

### Message source

<table border="1" cellspacing="0">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Code </th>
         <th>Description</th>
      </tr>
   </thead>
   <tbody>
      <tr valign="top">
         <td>C         </td>
         <td width="80%">Catalog:
Access to the catalog         </td>
      </tr>
      <tr valign="top">
         <td>E         </td>
         <td width="80%">End: <span>Transfer CFT</span> shutdown phase         </td>
      </tr>
      <tr valign="top">
         <td>F         </td>
         <td width="80%">File:
Access to files         </td>
      </tr>
      <tr valign="top">
         <td>H         </td>
         <td width="80%">External PeSIT:
PeSIT protocol, non-SIT profile and CFT profile         </td>
      </tr>
      <tr valign="top">
         <td>I         </td>
         <td width="80%">Init:
<span>Transfer CFT</span> initialization phase         </td>
      </tr>
      <tr valign="top">
         <td>N         </td>
         <td width="80%">Network          </td>
      </tr>
      <tr valign="top">
         <td>P         </td>
         <td width="80%">
<p width="80%">Parameter:
Access to parameter files</p>
         </td>
      </tr>
      <tr valign="top">
         <td>R         </td>
         <td width="80%">Request:
Requests that <span>Transfer CFT</span> received  from CFTUTIL, applications, or interactive
functions         </td>
      </tr>
      <tr valign="top">
         <td>S         </td>
         <td width="80%">System:
System interface operations by the <span>Transfer CFT</span>         </td>
      </tr>
      <tr valign="top">
         <td>T         </td>
         <td width="80%">Transfers:
Actions relating to transfers         </td>
      </tr>
      <tr valign="top">
         <td>U         </td>
         <td width="80%">CFTUTIL: Messages from the CFTUTIL utility         </td>
      </tr>
      <tr valign="top">
         <td>X         </td>
         <td width="80%">Security:
Security system (only in the log)         </td>
      </tr>
      <tr valign="top">
         <td>Y         </td>
         <td width="80%">SSL:
SSL protocol         </td>
      </tr>
   </tbody>
</table>

### Sequence number

The sequence number is an index characterizing the message within a given class.

### Severity

The severity code is described in the following table.

<table cellspacing="0">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Code </th>
         <th>Indicates</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>I         </td>
         <td>Informational message only         </td>
      </tr>
      <tr>
         <td>W         </td>
         <td>An anomaly which may be an error         </td>
      </tr>
      <tr>
         <td>E         </td>
         <td>An error requiring correction (parameter setting or environment error)         </td>
      </tr>
      <tr>
         <td>F         </td>
         <td>A serious system error requiring the intervention of Product Support         </td>
      </tr>
   </tbody>
</table>

### Symbolic variables used in message text

The table below lists the symbolic variables used in message text.

<table cellspacing="0">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>
            <p>Code</p>
</th>
         <th>
            <p>Description</p>
</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>
            <p>char</p>
         </td>
         <td>
            <p>Alphanumeric character</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>cr</p>
         </td>
         <td>
            <p>Function return code</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>cmd</p>
         </td>
         <td>
            <p>Parameter setting or operator command name<br/>Example: CFTPARM, SEND</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>cpu_id</p>
         </td>
         <td>
            <p>Host computer's CPU number</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>ctx</p>
         </td>
         <td>
            <p>Internal context</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>diagn</p>
         </td>
         <td>
            <p>Diagnostic code of a network error<br/>Specific to the access method and, in some cases, to the system<br/>Expressed in hexadecimal form</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>diagi</p>
         </td>
         <td>
            <p>Internal CFT diagnostic code (DIAGI) of the catalog</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>diagp</p>
         </td>
         <td>
            <p>CFT protocol diagnostic code (DIAGP) of the catalog</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>dest</p>
         </td>
         <td>
            <p>Partner list identifier (CFTDEST command)</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>direct</p>
         </td>
         <td>
            <p>Transmission direction</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>fname</p>
         </td>
         <td>
            <p>File name</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>host</p>
         </td>
         <td>
            <p>Physical address of the remote partner</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>id</p>
         </td>
         <td>
            <p>Command identifier (value of the ID parameter)</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>idf</p>
         </td>
         <td>
            <p>Model file identifier (CFTSEND/CFTRECV command)</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>idt</p>
         </td>
         <td>
            <p>Transfer identifier</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>keyw</p>
         </td>
         <td>
            <p>Keyword in a parameter setting command or an operator request<br/>Example: PART, DIRECT</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>local</p>
         </td>
         <td>
            <p>Location of a network error:<br/>     1: local<br/>     0: remote</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>label</p>
         </td>
         <td>
            <p>Freeform name relating to the software protection key</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>maxtrans</p>
         </td>
         <td>
            <p>Number of transfers authorized at any one time</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>mode</p>
         </td>
         <td>
            <p>Action requested</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>n</p>
         </td>
         <td>
            <p>Numeric character</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>nb</p>
         </td>
         <td>
            <p>Numeric code</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>ncr</p>
         </td>
         <td>
            <p>General network error code</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>ncs</p>
         </td>
         <td>
            <p>Network error code specific to the access method and system </p>
         </td>
      </tr>
      <tr>
         <td>
            <p>net</p>
         </td>
         <td>
            <p>Network resource identifier (CFTNET command)</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>part</p>
         </td>
         <td>
            <p>Local partner identifier (CFTPART command)</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>prot</p>
         </td>
         <td>
            <p><span>Transfer CFT</span> protocol identifier (CFTPROT command)</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>pevent</p>
         </td>
         <td>
            <p>Protocol event</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>pid</p>
         </td>
         <td>
            <p>Process identifier</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>pstate</p>
         </td>
         <td>
            <p>Protocol status</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>recov</p>
         </td>
         <td>
            <p>General error recovery code (in the case of a network error), independent of the system or access method</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>reason</p>
         </td>
         <td>
            <p>Reason code for a network error<br/>Specific to the access method and, in some cases, to the system<br/>Expressed in hexadecimal form</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>sappl</p>
         </td>
         <td>
            <p>SAPPL parameter value (name of the sending application)</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>scs</p>
         </td>
         <td>
            <p>System return code describing a system interface access error</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>state</p>
         </td>
         <td>
            <p>Transfer status</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>str</p>
         </td>
         <td>
            <p>Character string forming the message label</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>vfm</p>
         </td>
         <td>
            <p>VFM base name</p>
         </td>
      </tr>
   </tbody>
</table>
