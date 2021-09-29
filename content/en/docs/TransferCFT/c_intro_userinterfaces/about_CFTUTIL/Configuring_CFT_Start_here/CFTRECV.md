{
    "title": "CFTRECV - Default receive templates",
    "linkTitle": "CFTRECV - Default receive templates",
    "weight": "440"
}# <span id="kanchor17"></span><span id="Default_RECV_examples"></span>CFTRECV - Receive templates

This topic describes the Transfer CFT
receive template. You can use the CFTRECV object to:

-   Give the default
    name and local physical characteristics of the file to receive
-   Define the default
    actions to perform locally during and after the transfer (translation,
    compression, call to a user EXIT, an end-of-transfer procedure...)
-   Authorize the default
    time slot and default user associated with the transfers

Related
topics

-   Command syntax
    [CFTRECV](../../../command_summary)

<table data-cellspacing="0">
<thead>
<tr class="header">
<th>Parameter</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd" data-valign="top">
<td width="19.982%"><p><a href="../../../command_summary/parameter_intro/comment">COMMENT</a></p></td>
<td width="80.018%"><p>Local alphanumeric comment associated
with receive transfers.</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="19.982%"><p><a href="../../../command_summary/parameter_intro/cycdate">CYCDATE</a></p></td>
<td width="80.018%"><p>Upper final date for activating the first
transfer of a cycle.</p></td>
</tr>
<tr class="odd" data-valign="top">
<td width="19.982%"><p><a href="../../../command_summary/parameter_intro/cyctime">CYCTIME</a></p></td>
<td width="80.018%"><p>Upper limit time for activating the first
transfer of a cycle.</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="19.982%"><p><a href="../../../command_summary/parameter_intro/delete">DELETE</a> </p></td>
<td width="80.018%"><p>Automatic deletion of the catalog entries
in the "X" phase (done) for the corresponding IDF.</p></td>
</tr>
<tr class="odd" data-valign="top">
<td width="19.982%"><p><a href="../../../command_summary/parameter_intro/exit">EXIT</a></p></td>
<td width="80.018%"><p>Identifier of the CFTEXIT command associated
with this transfer.</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="19.982%"><p><a href="../../../command_summary/parameter_intro/faction">FACTION</a></p></td>
<td width="80.018%"><p>Action on the file for a receive transfer.</p></td>
</tr>
<tr class="odd" data-valign="top">
<td width="19.982%"><p><a href="../../../command_summary/parameter_intro/fblksize">FBLKSIZE</a></p></td>
<td width="80.018%"><p>This parameter (in bytes) controls the
"blocking factor" of the receiver file records: according to
the system, it defines the disk block size and/or the file input/output
buffer size.</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="19.982%"><a href="../../../command_summary/parameter_intro/fcharset">FCHARSET</a></td>
<td width="80.018%">Defines the local file encoding.</td>
</tr>
<tr class="odd" data-valign="top">
<td width="19.982%"><p><a href="../../../command_summary/parameter_intro/fcheck">FCHECK</a></p></td>
<td width="80.018%"><p>Checks record length attributes.</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="19.982%"><p><a href="../../../command_summary/parameter_intro/fcode">FCODE</a></p></td>
<td width="80.018%"><p>Code of the receiver file data (local
data code).</p></td>
</tr>
<tr class="odd" data-valign="top">
<td width="19.982%"><p><a href="../../../command_summary/parameter_intro/fdisp">FDISP</a></p></td>
<td width="80.018%"><p>Presence check indicator of the receiver
file used to determine the action of the Transfer CFT monitor.</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="19.982%"><p><a href="../../../command_summary/parameter_intro/fkeylen">FKEYLEN</a> </p></td>
<td width="80.018%"><p>Key length of an indexed file.</p></td>
</tr>
<tr class="odd" data-valign="top">
<td width="19.982%"><p><a href="../../../command_summary/parameter_intro/fkeypos">FKEYPOS</a></p></td>
<td width="80.018%"><p>Key position relative to 0 in the record
of an indexed file.</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="19.982%"><a href="../../../command_summary/parameter_intro/flowname">FLOWNAME</a></td>
<td width="80.018%">The local flow descriptor.</td>
</tr>
<tr class="odd" data-valign="top">
<td width="19.982%"><p><a href="../../../command_summary/parameter_intro/flrec">FLRECL</a> </p></td>
<td width="80.018%"><p>File record length in bytes.</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="19.982%"><p><a href="../../../command_summary/parameter_intro/fname">FNAME</a></p></td>
<td width="80.018%"><p>Name of the physical receiver file (filename
or complete pathname) of the directory.</p></td>
</tr>
<tr class="odd" data-valign="top">
<td width="19.982%"><p><a href="../../../command_summary/parameter_intro/force">FORCE</a> </p></td>
<td width="80.018%"><p>Determines the priority with which the
parameters set in CFTRECV are taken into account relative to the parameters
set in an associated RECV command.</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="19.982%"><p><a href="../../../command_summary/parameter_intro/forg">FORG</a> </p></td>
<td width="80.018%"><p>Organization of the file to be sent.</p></td>
</tr>
<tr class="odd" data-valign="top">
<td width="19.982%"><p><a href="../../../command_summary/parameter_intro/frecfm">FRECFM</a> </p></td>
<td width="80.018%"><p>Record format of the receiver file.</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="19.982%"><p><a href="../../../command_summary/parameter_intro/fspace">FSPACE</a> </p></td>
<td width="80.018%"><p>Size of the receiver file, in K-bytes
(1 K-byte = 1024 bytes).</p></td>
</tr>
<tr class="odd" data-valign="top">
<td width="19.982%"><p><a href="../../../command_summary/parameter_intro/ftype">FTYPE</a></p></td>
<td width="80.018%"><p>Type of the receiver file.</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="19.982%"><p><a href="../../../command_summary/parameter_intro/groupid">GROUPID</a></p></td>
<td width="80.018%"><p>Information completing the USERID of the
CFTRECV command.</p></td>
</tr>
<tr class="odd" data-valign="top">
<td width="19.982%"><p><a href="../../../command_summary/parameter_intro/id">ID</a> </p></td>
<td width="80.018%"><p>Local model file identifier (IDF).</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="19.982%"><p><a href="../../../command_summary/parameter_intro/maction">MACTION</a> </p></td>
<td width="80.018%"><p>Action on the files transferred by COPY
at the time of creation.</p></td>
</tr>
<tr class="odd" data-valign="top">
<td width="19.982%"><p><a href="../../../command_summary/parameter_intro/maxdate">MAXDATE</a></p></td>
<td width="80.018%"><p>Transfer validity final date.</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="19.982%"><p><a href="../../../command_summary/parameter_intro/maxtime">MAXTIME</a></p></td>
<td width="80.018%"><p>Transfer validity limit time for the final
date (MAXDATE).</p></td>
</tr>
<tr class="odd" data-valign="top">
<td width="19.982%"><p><a href="../../../command_summary/parameter_intro/mindate">MINDATE</a></p></td>
<td width="80.018%"><p>Minimum transfer validity date.</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="19.982%"><p><a href="../../../command_summary/parameter_intro/mintime">MINTIME</a></p></td>
<td width="80.018%"><p>Transfer initial validity time, from the
first day (MINDATE).</p></td>
</tr>
<tr class="odd" data-valign="top">
<td width="19.982%"><a href="../../../command_summary/parameter_intro/ncharset">NCHARSET</a></td>
<td width="80.018%">Defines the destination file encoding that is used on a file
to encode or decode network data.</td>
</tr>
<tr class="even" data-valign="top">
<td width="19.982%"><a href="../../../command_summary/parameter_intro/ncode">NCODE</a></td>
<td width="80.018%">The network data code when receiving transfers. <em>Available only when using SFTP.</em></td>
</tr>
<tr class="odd" data-valign="top">
<td width="19.982%"><p><a href="../../../command_summary/parameter_intro/ncomp">NCOMP</a></p></td>
<td width="80.018%"><p>Compression of on-line data requested
by the receiver.</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="19.982%"><p><a href="../../../command_summary/parameter_intro/netband">NETBAND</a></p></td>
<td width="80.018%"><p>Select the outgoing port range.</p></td>
</tr>
<tr class="odd" data-valign="top">
<td width="19.982%"><p><a href="../../../command_summary/parameter_intro/notify">NOTIFY</a></p></td>
<td width="80.018%"><p>Defines the destination of the messages
associated with the send transfer selected from the log file messages,
by the value of the OPERMSG parameter.</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="19.982%"><p><a href="../../../command_summary/parameter_intro/opermsg">OPERMSG</a> </p></td>
<td width="80.018%"><p>Defines the categories of transfer information
messages intended for the operator (all the messages also being written
in the log file).</p></td>
</tr>
<tr class="odd" data-valign="top">
<td width="19.982%"><p><a href="../../../command_summary/parameter_intro/pri">PRI</a></p></td>
<td width="80.018%"><p>Receive request selection priority.</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="19.982%"><p><a href="../../../command_summary/parameter_intro/ruser">RUSER</a></p></td>
<td width="80.018%"><p>Identifier of the file receiver user.</p></td>
</tr>
<tr class="odd" data-valign="top">
<td width="19.982%"><a href="../../../command_summary/parameter_intro/sourceappl">SOURCEAPPL</a></td>
<td width="80.018%">The identifier of the local file sender application.</td>
</tr>
<tr class="even" data-valign="top">
<td width="19.982%"><p><a href="../../../command_summary/parameter_intro/state">STATE</a> </p></td>
<td width="80.018%"><p>Defines the transfer request state.</p></td>
</tr>
<tr class="odd" data-valign="top">
<td width="19.982%"><p><a href="../../../command_summary/parameter_intro/suser">SUSER</a> </p></td>
<td width="80.018%"><p>Identifier of the file sender user.</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="19.982%"><a href="../../../command_summary/parameter_intro/targetappl">TARGETAPPL</a></td>
<td width="80.018%">Identifier of the local
file receiver application.</td>
</tr>
<tr class="odd" data-valign="top">
<td width="19.982%"><p><a href="../../../command_summary/parameter_intro/tcycle">TCYCLE</a> </p></td>
<td width="80.018%"><p>Transfer cycle period unit.</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="19.982%"><p><a href="../../../command_summary/parameter_intro/trk">TRK</a> </p></td>
<td width="80.018%"><p>Specification of how much detail Transfer
CFT provides Sentinel about transfers. Transfer CFT sends detail about
the transfers in the form of tracked instances.</p></td>
</tr>
<tr class="odd" data-valign="top">
<td width="19.982%"><p><a href="../../../command_summary/parameter_intro/userid">USERID</a></p></td>
<td width="80.018%"><p>Identifier of the transfer owner.</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="19.982%"><p><a href="../../../command_summary/parameter_intro/wfname">WFNAME</a> </p></td>
<td width="80.018%"><p>Name of the temporary file used during
the transfer.</p></td>
</tr>
<tr class="odd" data-valign="top">
<td width="19.982%"><p><a href="../../../command_summary/parameter_intro/xlate">XLATE</a> </p></td>
<td width="80.018%"><p>Identifier of the translation table used
for the receive transfers.</p></td>
</tr>
</tbody>
</table>

#### Examples

This section displays examples for a default receive template.

Example 1

CFTRECV

<table data-cellspacing="0" height="318">
<tbody>
<tr class="odd">
<td width="40.792%"><p>MODE = REPLACE,</p></td>
<td width="59.208%"><p> </p></td>
</tr>
<tr class="even">
<td width="40.792%"><p>ID = SRCFILES,</p></td>
<td width="59.208%"><p>/* IDF for source files */</p></td>
</tr>
<tr class="odd">
<td width="40.792%"><p>FDISP = BOTH</p></td>
<td width="59.208%"><p>/* already exists or not */</p></td>
</tr>
<tr class="even">
<td width="40.792%"><p>FACTION = ERASE,</p></td>
<td width="59.208%"><p>/* if exists erase */</p></td>
</tr>
<tr class="odd">
<td width="40.792%"><p>XLATE = ETOA</p></td>
<td width="59.208%"><p>/* with this table  */</p></td>
</tr>
</tbody>
</table>

The set of parameters corresponding to this command is used, during
a data receive transfer, if the explicit value of the transfer IDF is
"SRCFILES".  
The monitor thereby has default values for receiver file management. The
FNAME parameter is not defined. The monitor can consequently only operate
if a RECV command specifying FNAME has been entered (Transfer CFT is requester),
or if the partner (Transfer CFT is server) has specified the receiver
file name (open mode for receive transfers).

Example 2

CFTRECV

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td width="38.168%"><p>MODE = REPLACE,</p>
<p>ID = IDFDEF, /* default IDF */</p>
<p>FDISP = BOTH, /* already exists or not */</p>
<p>FACTION = DELETE, /* if exists - delete */</p>
<p>FNAME = &amp;IDT /* file as per IDT value */</p></td>
</tr>
</tbody>
</table>

This command corresponds to the data receive transfer case where the
identifier (IDF) has no explicit description (CFTRECV object). This is
the default receiver model file. The CFTPARM object must specify: CFTPARM
DEFAULT = IDFDEF, ... Transfer CFT then creates a file whose name contains
the unique transfer identifier.

**IBM i:** This command corresponds
to the general database file receive transfer case.
