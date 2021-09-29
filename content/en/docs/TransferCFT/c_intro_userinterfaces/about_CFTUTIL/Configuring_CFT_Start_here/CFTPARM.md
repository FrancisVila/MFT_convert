{
    "title": "CFTPARM - General parameters",
    "linkTitle": "CFTPARM - General parameters",
    "weight": "410"
}# <span id="kanchor64"></span><span id="Defining_general_parameters__command_line___Start_here"></span>CFTPARM - General parameters

The <span id="Defining_CFTPARM"></span>CFTPARM object is used to specify parameters
that control the operation of Transfer CFT as a whole and to select other
parameter setting commands to be used at run time. The [Symbolic variables](../../../command_summary/symbolic_variables) topic describes
how symbolic variables can be used in the identification and in the body
of these procedures.

Specific SSL, transport security, parameters are described in the topic
[Configuring
Transport Security: Start here](../../../../transport_security_start_here/configuring_transport_security_start_here).

Related
topics

-   Command syntax
    [CFTPARM](../../../command_summary)
-   Object concepts
    [General parameters
    definition](../../../../admin_intro/admin_config_commands/cftparm_general_parameters)

Use this command to:

-   Specify
    the parameters which control overall Transfer CFT operations
-   Select
    the other parameter setting commands which should be taken into account
    during execution

<table data-cellspacing="0">
<thead>
<tr class="header">
<th>Parameter</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="../../../command_summary/parameter_intro/accnt">ACCNT</a></p></td>
<td><p>Identifier of the description command of the statistical
data record of the transfers (<a href="../../../../admin_intro/admin_config_commands/cftaccnt_concepts">CFTACCNT</a>).</p></td>
</tr>
<tr class="even">
<td><p><a href="../../../command_summary/parameter_intro/bufsize">BUFSIZE</a> </p>
<p><a href="../../../command_summary/parameter_intro/bufsize">see table</a>  </p></td>
<td><p>Size of the monitor internal buffer used to exchange data
between monitor tasks, expressed in characters in bytes.</p></td>
</tr>
<tr class="odd">
<td><p><a href="../../../command_summary/parameter_intro/cat">CAT</a></p></td>
<td><p>Identifier of the command describing catalog
file management (<a href="../../../web_copilot_ui/conf_intro/cftcat">Defining the catalog parameters</a>).</p></td>
</tr>
<tr class="even">
<td><p><a href="../../../command_summary/parameter_intro/com">COM</a> </p></td>
<td><p>List of the identifiers of the communication media description
commands (<a href="../../../../admin_intro/admin_config_commands/communication_media_concepts">Defining
the communication media</a>).</p></td>
</tr>
<tr class="odd">
<td><p><a href="../../../command_summary/parameter_intro/comment">COMMENT</a> </p></td>
<td><p>Character comment field.</p></td>
</tr>
<tr class="even">
<td><p>CTLPASSW</p></td>
<td><p>Obsolete.</p></td>
</tr>
<tr class="odd">
<td><p><a href="../../../command_summary/parameter_intro/default">DEFAULT</a></p></td>
<td><p>Default identifier, generically indicated as &lt;defaut&gt;,
of the CFTRECV, CFTSEND, and CFTXLATE commands.</p></td>
</tr>
<tr class="even">
<td><p><a href="../../../command_summary/parameter_intro/execre">EXECRE</a></p></td>
<td><p>Generic name of the file describing the procedures to be
executed, following an incident (Error) occurring during a receive transfer,
the transfer changing to the H or K state.</p></td>
</tr>
<tr class="odd">
<td><p><a href="../../../command_summary/parameter_intro/execrf">EXECRF</a></p></td>
<td><p>Generic name of the file describing the procedures to be
executed on completion of reception of a file.</p></td>
</tr>
<tr class="even">
<td><p><a href="../../../command_summary/parameter_intro/execrm">EXECRM</a></p></td>
<td><p>Generic name of the file describing the procedures to be
executed on completion of reception of a message.</p></td>
</tr>
<tr class="odd">
<td><p><a href="../../../command_summary/parameter_intro/execse">EXECSE</a></p></td>
<td><p>Generic name of the file describing the procedures to be
executed, following an incident (Error) during a send transfer, the transfer
changing to the H or K state.</p></td>
</tr>
<tr class="even">
<td><p><a href="../../../command_summary/parameter_intro/execsf">EXECSF</a></p></td>
<td><p>Generic name of the file describing the procedures to be
executed on completion of the sending of a file.</p></td>
</tr>
<tr class="odd">
<td><p><a href="../../../command_summary/parameter_intro/execsfa">EXECSFA</a> </p></td>
<td><p>Generic name of the file describing the procedures to be
executed on receiving an acknowledgement (REPLY type message), following
the sending of a file.</p></td>
</tr>
<tr class="even">
<td><p><a href="../../../command_summary/parameter_intro/execsm">EXECSM</a> </p></td>
<td><p>Generic name of the file describing the procedures to be
executed on completion of the sending of a message.</p></td>
</tr>
<tr class="odd">
<td><p><a href="../../../command_summary/parameter_intro/execsma">EXECSMA</a> </p></td>
<td><p>Generic name of the file describing the procedures to be
executed on receiving an acknowledgement, REPLY type message, following
the sending of a message.</p></td>
</tr>
<tr class="even">
<td><a href="exitbot.htm">EXITBOT</a></td>
<td><p>EXIT identifier. To activate a beginning-of-transfer EXIT task, this identifier must point to a CFTEXIT command.</p></td>
</tr>
<tr class="odd">
<td><p><a href="../../../command_summary/parameter_intro/exiteot">EXITEOT</a></p></td>
<td><p>EXIT identifier. To activate an end-of-transfer EXIT task, this identifier must point to a CFTEXIT command.</p></td>
</tr>
<tr class="even">
<td><p><a href="../../../command_summary/parameter_intro/id">ID</a> </p></td>
<td><p>Identifier of the CFTPARM command.</p></td>
</tr>
<tr class="odd">
<td><p><a href="../../../command_summary/parameter_intro/key">KEY</a> </p></td>
<td><p>The name of the indirection file preceded by the &lt;file-symb&gt;
character, which is system specific, and containing the set of keys associated
with the Transfer CFT.</p></td>
</tr>
<tr class="even">
<td><p><a href="../../../command_summary/parameter_intro/lenappl">LENAPPL</a></p></td>
<td><p>Length to be taken into account when comparing the file/message
identifier, IDF or IDM, with the identifier of a CFTAPPL command.</p>
<p>See, Security
concepts: Start here.</p></td>
</tr>
<tr class="odd">
<td><p><a href="../../../command_summary/parameter_intro/log">LOG</a></p></td>
<td><p>Identifier of the monitor event log file description command
CFTLOG.</p>
<p>If this parameter is not defined, the Transfer CFT
writes logging messages to the standard output of the monitor.</p></td>
</tr>
<tr class="even">
<td><p><a href="../../../command_summary/parameter_intro/maxtask">MAXTASK</a> </p></td>
<td><p>Number of file access tasks authorized.</p></td>
</tr>
<tr class="odd">
<td><p><a href="../../../command_summary/parameter_intro/maxtrans">MAXTRANS</a></p></td>
<td><p>The maximum authorized number of transfers in parallel. When using multi node, this is the number of transfers per node.</p></td>
</tr>
<tr class="even">
<td><p><a href="../../../command_summary/parameter_intro/net">NET</a></p></td>
<td><p>List of the identifiers of the description commands for
network access methods and monitor network resources CFTNET.</p></td>
</tr>
<tr class="odd">
<td><p><a href="../../../command_summary/parameter_intro/npart">NPART</a> </p></td>
<td><p>Default network identifier of the local site.</p>
<p>Default value of the NSPART parameter of the CFTPART command.</p>
<p>As this name is sent by some file transfer protocols, refer
to the Transfer CFT <a href="../../../../protocols_start_here">Managing</a> Protocols to check its size and format.</p></td>
</tr>
<tr class="even">
<td><p><a href="../../../command_summary/parameter_intro/part">PART</a></p></td>
<td><p>Local identifier, identifying the site on which Transfer
CFT is executed.</p>
<p>This parameter is an item of information appearing in the
transfer catalog.</p></td>
</tr>
<tr class="odd">
<td><p><a href="../../../command_summary/parameter_intro/partfnam">PARTFNAM</a> </p></td>
<td><p>Partner file name (obsolete for Windows/Unix).</p></td>
</tr>
<tr class="even">
<td><p><a href="../../../command_summary/parameter_intro/protocol">PROT</a> </p></td>
<td><p>Identifier of the Transfer CFT protocol description commands
CFTPROT.</p>
<p>Transfer CFT protocol
refers to both file transfer application protocols and network access
methods.</p></td>
</tr>
<tr class="odd">
<td><p><a href="../../../command_summary/parameter_intro/rcvaller">RCVALLER</a> </p></td>
<td><p>Option to be used if an error occurs when receiving
available files FILE=ALL option.</p></td>
</tr>
<tr class="even">
<td><p><a href="../../../command_summary/parameter_intro/secfname">SECFNAME</a></p></td>
<td><p>Name of the CFT internal security file.</p></td>
</tr>
<tr class="odd">
<td><p><a href="../../../command_summary/parameter_intro/trantask">TRANTASK</a></p></td>
<td><p>Number of transfers in parallel performed by a file access
task, above which a new task is created, if possible.</p></td>
</tr>
<tr class="even">
<td><p><a href="../../../command_summary/parameter_intro/trkpart">TRKPART</a></p></td>
<td><p>Specification of how much detail Transfer CFT
provides Sentinel about transfers. Transfer CFT sends detail about the
transfers in the form of tracked instances.</p></td>
</tr>
<tr class="odd">
<td><p><a href="../../../command_summary/parameter_intro/trkrecv">TRKRECV</a></p></td>
<td><p>Specification of how much detail Transfer CFT provides
Sentinel about transfers. Transfer CFT sends detail about the transfers
in the form of tracked instances.</p></td>
</tr>
<tr class="even">
<td><p><a href="../../../command_summary/parameter_intro/trksend">TRKSEND</a></p></td>
<td><p>Specification of how much detail Transfer CFT provides
Sentinel about transfers. Transfer CFT sends detail about the transfers
in the form of tracked instances.</p></td>
</tr>
<tr class="odd">
<td><p><a href="../../../command_summary/parameter_intro/userctrl">USERCTRL</a></p></td>
<td><p>Transferred file access control option.</p></td>
</tr>
<tr class="even">
<td><p><a href="../../../command_summary/parameter_intro/waitresp">WAITRESP</a>
 <a href="../../../command_summary/parameter_intro/waitresp">see
table</a></p></td>
<td><p>Timeout in seconds used during internal communication
between monitor tasks.</p>
<p>This parameter is used during a synchronous exchange of
requests between two monitor tasks. After waitresp
seconds without reply, the timeout is interrupted. A message CFTS09
is written in the log. The task in question is then stopped, CFTTCOM task,
for example.</p>
<p>During the initialization phase, this parameter checks
the time allowed for each of the Transfer CFT monitor tasks to start.
In the event of an insufficient value (case of a highly loaded computer),
the Transfer CFT monitor initialization stops.</p>
<p>The following table indicates the default value for each
system.</p></td>
</tr>
<tr class="odd">
<td><p><a href="../../../command_summary/parameter_intro/waittask">WAITTASK</a> </p></td>
<td><p>Time during which a file access task is inactive
in minutes before being shut down.</p></td>
</tr>
</tbody>
</table>

### <span id="Changing_the_initial_IDPARM_in_CFTUTIL"></span>Changing the initial IDPARM in CFTUTIL

The format that you use to enter commands in CFTUTIL is operating system
dependent. For more information, refer to the *Installation and Operations Gudie*that corresponds
with your operating system.

## <span id="CFTPARM_command_line_examples"></span>CFTPARM command line examples

This topic lists and describes an example of the CFTPARM object using
command line operations to define the CFTPARM object.

Example

The CFTCAT, CFTCOM, CFTLOG, CFTACCNT, CFTNET and CFTPROT
parameter setting objects are not taken into account, during execution,
unless they were selected through the corresponding parameters: CAT, COM,
LOG, ACCNT, NET and PROT.

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>CFTPARM</p>
<p>CAT = CAT1,</p>
<p>COM = COM1,</p>
<p>ID = PARM1,</p>
<p>KEY = ‘XXXXXXXXXXXXXXXXXXXXX’,</p>
<p>NET = (),</p>
<p>PART = identifier,</p>
<p>PROT = (PESITCFT ),</p>
<p>BUFSIZE = 4096</p>
<p>DEFAULT = IDFDEF,</p>
<p>EXECRE = &lt;filename4&gt;,</p>
<p>EXECRF = &lt;filename2&gt;,</p>
<p>EXECSE = &lt;filename3&gt;,</p>
<p>EXECSF = &lt;filename1&gt;,</p>
<p>LOG = LOG1,</p>
<p>MAXTASK = 1,</p>
<p>MAXTRANS = 4,</p>
<p>NPART = MYCFT,</p>
<p>TRANTASK = 1,</p>
<p>WAITRESP = 500</p></td>
</tr>
</tbody>
</table>
