{
    "title": "Communication media - CFTCOM  ",
    "linkTitle": "Communication media - CFTCOM ",
    "weight": "210"
}This topic describes the CFTCOM object and parameters. You can use this
command to define the communication media used by Transfer CFT.

Related
topics

-   Command syntax
    [CFTCOM](../../../command_summary#CFTCOM)
-   Object concepts
    [About the
    communication media](../../../../admin_intro/admin_config_commands/communication_media_concepts)

For a description of the object and CFTCOM concepts, go to [CFTCOM
communication media concepts](../../../../admin_intro/admin_config_commands/communication_media_concepts).

As described in the [CFTCOM
concepts: Start here](../../../../admin_intro/admin_config_commands/communication_media_concepts), you can set the communication medium to:

-   [File](#TYPE=FILE)
-   [TCP/IP](#TYPE=TCPIP)

First define the TYPE, and then define the corresponding communication media parameters.

<span id="TYPE=FILE"></span>

### TYPE=FILE

NAME = filename

Designates the communication file name.  

\[WSCAN = {60
| n}\] {1..3600}

Communication file scanning time (in seconds).

Determines the time taken for the Transfer CFT
to process a command.

The optimum value is a tradeoff between the desired
response time and the computer’s workload.

<span id="TYPE=TCPIP"></span>

### TYPE=TCPIP

Use CFTCOM TCP/IP for synchronous Transfer CFT communication on the local network.

\[ADDRLIST = (string1..64,string1..64…)\]

The <span class="code">ADDRLIST </span>parameter is non-functional in that you can only use TCPIP in local networks for synchronous communication.

\[DISCTS = n\]

Without a request , the timeout (in seconds) before
freeing a channel opened by a client.

HOST = string1..64

IP address of the local resource.

This address (expressed in string format) can be completed
with one of the following:

-   The real IP address
    in notation point (ex: 192.9.200.10)

<!-- -->

-   The logical name,
    HOSTNAME, associated with the real IP address
-   The value, ALL,
    specifying all the local network addresses.

PROTOCOL = { XHTTP }

Request/reply protocol implemented on the TCP/IP layer:

-   XHTTP: HTTP protocol
    variant, property of Axway Software

PORT = n

Listening port on the networks defined in the HOST
parameter.

<span id="Defining_CFTCOM_TCPIP"></span>

## CFTCOM TCPIP

This table describes the parameters to define the CFTCOM object when the communication
type is TCPIP.

<table>
   <th>
      <tr>
<th>Parameters         </th>
<th>Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p><a href="../../../command_summary/parameter_intro/addrlist">ADDRLIST</a></p>         </td>
         <td><p>This field defines a list of authorized addresses that you can use to
connect to the communication media.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="../../../command_summary/parameter_intro/host">HOST</a></p>         </td>
         <td><p>Networking IP address of the local resource.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="../../../command_summary/parameter_intro/id">ID</a> </p>         </td>
         <td><p>Identifier of the CFTCOM object.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="../../../command_summary/parameter_intro/mode">MODE</a></p>         </td>
         <td><p>Action to do in the parameter or partner base. This parameter
applies to all commands that affect CFT bases.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="../../../command_summary/parameter_intro/port">PORT</a></p>         </td>
         <td><p>Listening port of the network.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="../../../command_summary/parameter_intro/protocol">PROTOCOL</a></p>         </td>
         <td><p>Defines the remote TCP network resource</p>         </td>
      </tr>
      <tr>
         <td><p><a href="../../../command_summary/parameter_intro/type">TYPE</a></p>         </td>
         <td><p>Transfer CFT communication means.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="Defining_CFTCOM_FILE"></span>

## CFTCOM FILE

This table describes the parameters to define the CFTCOM object when the communication
type is FILE.

<table>
   <th>
      <tr>
<th>Parameters         </th>
<th>Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p><a href="../../../command_summary/parameter_intro/id">ID</a> </p>         </td>
         <td><p>Identifier of the CFTCOM command.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="../../../command_summary/parameter_intro/mode">MODE</a></p>         </td>
         <td><p>Action to do in the parameter or partner base. This parameter
applies to all commands that affect Transfer CFT bases.</p>         </td>
      </tr>
      <tr>
         <td><a href="../../../command_summary/parameter_intro/tlvcexec">TLVCEXEC</a>         </td>
         <td>Batch to execute when the alert ends.         </td>
      </tr>
      <tr>
         <td><a href="../../../command_summary/parameter_intro/tlvclear">TLVCLEAR</a>         </td>
         <td><p>Level below which the alert ceases, as a percentage of filling, where 0% indicates the file is empty and 100% that it is full.</p>         </td>
      </tr>
      <tr>
         <td><a href="../../../command_summary/parameter_intro/tlvwarn">TLVWARN</a>         </td>
         <td><p>Command file usage limit before issuing an alert, as is a percentage of filling, where 0% indicates the file is empty, and 100% that it is full.</p>
<p>Once this limit is reached, the CFTCOM/TLVWEXEC is executed.</p>         </td>
      </tr>
      <tr>
         <td><a href="../../../command_summary/parameter_intro/tlvwexec">TLVWEXEC</a>         </td>
         <td>Batch to execute when CFTCOM/TLVWARN is reached.         </td>
      </tr>
      <tr>
         <td><a href="../../../command_summary/parameter_intro/tlvwrate">TLVWRATE</a>         </td>
         <td>The minimum amount of time, in seconds, to wait before resending an alert.         </td>
      </tr>
      <tr>
         <td><p><a href="../../../command_summary/parameter_intro/type">TYPE</a> </p>         </td>
         <td><p>Transfer CFT communication means.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="../../../command_summary/parameter_intro/wscan">WSCAN</a></p>         </td>
         <td><p>The frequency, in seconds, with which the Transfer CFT scans
the communication file.</p>         </td>
      </tr>
   </tbody>
</table>

<span class="bold_in_para">Example</span>

TYPE=FILE


    CFTCOM ID = IDCOM,
    TYPE = FILE
    NAME = <filename>,
    WSCAN = 120

### Communication media characteristics

-   For file communication:

<!-- -->

-   The <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> can be inactive at the time
    the commands assigned to it are issued, to the limit of the file size.
    Commands are taken into account at the time the <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> is activated,
    if a CFTCOM command relative to this communication file has been defined.
    A communication file can be created by the CFTFILE command.

<!-- -->

-   For TCP synchronous
    mediums:
    -   Communication is only possible if the Transfer
        CFT is present.
        To retrieve the IDT and the IDTU values of the transfer, you can use the
        variables %\_CAT\_IDT% and %\_CAT\_IDTU%.

**Example**



    SEND 
    PART = PART1
    IDF = TEST1 
     
    Then...
    LISTCAT 
    IDT = %_CAT_IDT%