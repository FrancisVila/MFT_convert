{
    "title": "Communication media - CFTCOM  ",
    "linkTitle": "CFTCOM - Communication media",
    "weight": "300"
}This topic describes the CFTCOM object and parameters. You can use this
command to define the communication media used by Transfer CFT.

****Related
topics****

- Command syntax
    [CFTCOM](../../../command_summary#CFTCOM)
- Object concepts
    [About the
    communication media](../../../../admin_intro/admin_config_commands/communication_media_concepts)

For a description of the object and CFTCOM concepts, go to [CFTCOM
communication media concepts](../../../../admin_intro/admin_config_commands/communication_media_concepts).

As described in the [CFTCOM
concepts: Start here](../../../../admin_intro/admin_config_commands/communication_media_concepts), you can set the communication medium to:

- [File](#TYPE=FILE)
- [TCP/IP](#TYPE=TCPIP)

First define the TYPE, and then define the corresponding communication media parameters.

<span id="TYPE=FILE"></span>

### TYPE=FILE

`NAME = filename`

Designates the communication file name.  

`[ WSCAN = { 60   &#124; n}] {1..3600}`

Communication file scanning time in seconds. Determines the time taken for the Transfer CFT
to process a command. The optimum value is a tradeoff between the desired
response time and the computer’s workload.

<span id="TYPE=TCPIP"></span>

### TYPE=TCPIP

Use CFTCOM TCP/IP for synchronous Transfer CFT communication on the local network.

`[ DISCTS = n ]`

Without a request , the timeout in seconds before
freeing a channel opened by a client.

`HOST = string1..64`

The IP address of the local resource, localhost or 127.0.0.1.

`PROTOCOL = { XHTTP }`

Request/reply protocol implemented on the TCP/IP layer is XHTTP; and HTTP protocol
variant, property of Axway Software.

`PORT = n`

Listening port on the networks defined in the HOST
parameter.

<span id="Defining_CFTCOM_TCPIP"></span>

CFTCOM TCPIP
------------

This table describes the parameters to define the CFTCOM object when the communication
type is TCPIP.


| Parameters  | Description  |
| --- | --- |
| <a href="../../../command_summary/parameter_intro/host">HOST</a> | Networking IP address of the local resource. |
| <a href="../../../command_summary/parameter_intro/id">ID</a>  | Identifier of the CFTCOM object. |
| <a href="../../../command_summary/parameter_intro/mode">MODE</a> | Action to do in the parameter or partner base. This parameter applies to all commands that affect CFT bases. |
| <a href="../../../command_summary/parameter_intro/port">PORT</a> | Listening port of the network. |
| <a href="../../../command_summary/parameter_intro/protocol">PROTOCOL</a> | Defines the remote TCP network resource |
| <a href="../../../command_summary/parameter_intro/type">TYPE</a> | Transfer CFT communication means. |


<span id="Defining_CFTCOM_FILE"></span>

CFTCOM FILE
-----------

This table describes the parameters to define the CFTCOM object when the communication
type is FILE.


| Parameters  | Description  |
| --- | --- |
| <a href="../../../command_summary/parameter_intro/id">ID</a>  | Identifier of the CFTCOM command. |
| <a href="../../../command_summary/parameter_intro/mode">MODE</a> | Action to do in the parameter or partner base. This parameter applies to all commands that affect Transfer CFT bases. |
| <a href="../../../command_summary/parameter_intro/tlvcexec">TLVCEXEC</a>  | Batch to execute when the alert ends.  |
| <a href="../../../command_summary/parameter_intro/tlvclear">TLVCLEAR</a>  | Level below which the alert ceases, as a percentage of filling, where 0% indicates the file is empty and 100% that it is full. |
| <a href="../../../command_summary/parameter_intro/tlvwarn">TLVWARN</a>  | Command file usage limit before issuing an alert, as is a percentage of filling, where 0% indicates the file is empty, and 100% that it is full.<br/> Once this limit is reached, the CFTCOM/TLVWEXEC is executed. |
| <a href="../../../command_summary/parameter_intro/tlvwexec">TLVWEXEC</a>  | Batch to execute when CFTCOM/TLVWARN is reached.  |
| <a href="../../../command_summary/parameter_intro/tlvwrate">TLVWRATE</a>  | The minimum amount of time, in seconds, to wait before resending an alert.  |
| <a href="../../../command_summary/parameter_intro/type">TYPE</a>  | Transfer CFT communication means. |
| <a href="../../../command_summary/parameter_intro/wscan">WSCAN</a> | The frequency, in seconds, with which the Transfer CFT scans the communication file. |


****Example****

TYPE=FILE

```
CFTCOM ID = IDCOM1,
TYPE = FILE
NAME = <filename>,
WSCAN = 120
```
