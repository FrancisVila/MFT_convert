{
    "title": "Send templates - CFTSEND ",
    "linkTitle": "Send templates - CFTSEND ",
    "weight": "210"
}This topic describes how to define the CFTSEND
template. Use this command to SEND a file or files to a partner.

Related
topics

-   Command syntax
    [CFTSEND](../../../command_summary)
-   Object concepts
    [Default
    send templates](../../../../concepts/cft_configuration_concepts_start_here/default_send_template_concepts)

<table data-cellspacing="0">
<thead>
<tr class="header">
<th>Parameter</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><a href="../../../command_summary/parameter_intro/ackexec">ACKEXEC</a></td>
<td>Name of the file describing the procedure to be executed when receiving an acknowledgement reply for the transfer.</td>
</tr>
<tr class="even">
<td><a href="archivefname.htm">ARCHIVEFNAME</a></td>
<td><p>The archived source file name after transfer completion if FACTION=ARCHIVE.</p>
<table data-cellpadding="0" data-cellspacing="0">
<tbody>
<tr class="odd">
<td data-valign="top"></td>
<td data-valign="top"><span><strong>Note</strong></span></td>
<td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">The <span>fname </span>and <span>archivefname </span>must be on the same volume (all platforms).</td>
</tr>
</tbody>
</table></td>
</tr>
<tr class="odd">
<td><p><a href="../../../command_summary/parameter_intro/comment">COMMENT</a></p></td>
<td><p>Local alphanumeric comment associated with the send transfer.</p></td>
</tr>
<tr class="even">
<td><p><a href="../../../command_summary/parameter_intro/cycdate">CYCDATE</a></p></td>
<td><p>Upper final date for activating the first transfer of a
cycle.</p></td>
</tr>
<tr class="odd">
<td><p><a href="../../../command_summary/parameter_intro/cycle">CYCLE</a></p></td>
<td><p>Number of units defining the transfer cycle period.</p></td>
</tr>
<tr class="even">
<td><p><a href="../../../command_summary/parameter_intro/cyctime">CYCTIME</a></p></td>
<td><p>Upper limit time for activating the first transfer of a
cycle.</p></td>
</tr>
<tr class="odd">
<td><p><a href="../../../command_summary/parameter_intro/delete">DELETE</a> </p></td>
<td><p>Automatic deletion of the catalog entries in the "X"
phase (done) for the corresponding IDF.</p></td>
</tr>
<tr class="even">
<td><p><a href="../../../command_summary/parameter_intro/delete">EXEC</a></p></td>
<td><p>Name of the file describing the procedure to be executed
on completion of the transfer.</p></td>
</tr>
<tr class="odd">
<td><p><a href="../../../command_summary/parameter_intro/execsub">EXECSUB</a></p></td>
<td>Submission policy of the end-of-transfer procedure, when sending a group of files.</td>
</tr>
<tr class="even">
<td><a href="../../../command_summary/parameter_intro/execsuba">EXECSUBA</a></td>
<td>Submission policy of the procedure to launch receiving acknowledgement, when sending a group of files.</td>
</tr>
<tr class="odd">
<td><a href="../../../command_summary/parameter_intro/execsubpre">EXECSUBPRE</a></td>
<td>Submission policy of the preprocessing procedure, when sending a group of files.</td>
</tr>
<tr class="even">
<td><p><a href="../../../command_summary/parameter_intro/exit">EXIT</a></p></td>
<td><p>Identifier of the CFTEXIT command associated with this
transfer.</p>
<p>Used to activate a file EXIT user task. The value of this
parameter may be equal to the symbolic variable &amp;IDF.</p></td>
</tr>
<tr class="odd">
<td><p><a href="../../../command_summary/parameter_intro/faction">FACTION</a></p></td>
<td><p>Action on the file after a send transfer.</p>
<p>If you are using FACTION=DELETE, see the <a href="../../../command_summary/parameter_intro/faction">FACTION</a> parameter specifics.</p></td>
</tr>
<tr class="even">
<td><p><a href="../../../command_summary/parameter_intro/fblksize">FBLKSIZE</a></p></td>
<td><p>Block size of sent file.</p></td>
</tr>
<tr class="odd">
<td><p><a href="../../../command_summary/parameter_intro/fcode">FCODE</a></p></td>
<td><p>Code of the data to be sent.</p></td>
</tr>
<tr class="even">
<td><p><a href="../../../command_summary/parameter_intro/fdisp">FDISP</a></p></td>
<td><p>File sharing option.</p></td>
</tr>
<tr class="odd">
<td><a href="../../../command_summary/parameter_intro/filter">FILTER</a></td>
<td>Defines the filter value to be used when filtering using method defined in filtertype.</td>
</tr>
<tr class="even">
<td><a href="../../../command_summary/parameter_intro/filtertype">FILTERTYPE</a></td>
<td>Defines the type of filter to be applied when sending a generic transfer.</td>
</tr>
<tr class="odd">
<td><p><a href="../../../command_summary/parameter_intro/fkeylen">FKEYLEN</a> </p></td>
<td><p>Key length of an indexed file.</p></td>
</tr>
<tr class="even">
<td><p><a href="../../../command_summary/parameter_intro/fkeypos">FKEYPOS</a></p></td>
<td><p>Key position relative to 0 in the record of an indexed
file.</p></td>
</tr>
<tr class="odd">
<td><a href="../../../command_summary/parameter_intro/flowname">FLOWNAME</a></td>
<td>The local flow descriptor.</td>
</tr>
<tr class="even">
<td><p><a href="../../../command_summary/parameter_intro/flrec">FLRECL</a> </p></td>
<td><p>File record length in bytes.</p></td>
</tr>
<tr class="odd">
<td><p><a href="../../../command_summary/parameter_intro/fname">FNAME</a></p></td>
<td><p>Name of the local file, directory, indirection file, selection
mask or selection directory to be sent.</p>
<p>See also <a href="#additional_filename_information">Additional
filename information</a></p></td>
</tr>
<tr class="even">
<td><p><a href="../../../command_summary/parameter_intro/force">FORCE</a></p></td>
<td><p>Determines the priority with which the parameters
set in CFTSEND are taken into account relative to the parameters set in
an associated SEND command.</p></td>
</tr>
<tr class="odd">
<td><p><a href="../../../command_summary/parameter_intro/forg">FORG</a> </p></td>
<td><p>Organization of the file to be sent:</p>
<ul>
<li>SEQ: sequential</li>
<li>INDEXED: indexed</li>
<li>DIRECT: relative direct access</li>
</ul></td>
</tr>
<tr class="even">
<td><p><a href="../../../command_summary/parameter_intro/frecfm">FRECFM</a></p></td>
<td><p>Record format of the file to be sent:</p>
<ul>
<li>F: fixed</li>
<li>V: variable,</li>
<li>U: undefined</li>
</ul></td>
</tr>
<tr class="odd">
<td><p><a href="../../../command_summary/parameter_intro/fspace">FSPACE</a> </p></td>
<td><p>Size of the file to be sent, in K-bytes (1 K-byte = 1024
bytes).</p></td>
</tr>
<tr class="even">
<td><p><a href="../../../command_summary/parameter_intro/ftype">FTYPE</a></p></td>
<td><p>Type of local file to be sent. Also see the NTYPE parameter.</p></td>
</tr>
<tr class="odd">
<td><p><a href="../../../command_summary/parameter_intro/groupid">GROUPID</a></p></td>
<td><p>Information completing the USERID of the CFTSEND command.</p></td>
</tr>
<tr class="even">
<td><p><a href="../../../command_summary/parameter_intro/id">ID</a> </p></td>
<td><p>Local identifier of the model file (IDF) to be sent.</p></td>
</tr>
<tr class="odd">
<td><a href="../../../command_summary/parameter_intro/ida">IDA</a></td>
<td>Local transfer identifier assigned by the user or user application.</td>
</tr>
<tr class="even">
<td><p><a href="../../../command_summary/parameter_intro/impl">IMPL</a></p></td>
<td><p>Implicit send.</p></td>
</tr>
<tr class="odd">
<td><p><a href="../../../command_summary/parameter_intro/maxdate">MAXDATE</a></p></td>
<td><p>Transfer validity final date.</p></td>
</tr>
<tr class="even">
<td><p><a href="../../../command_summary/parameter_intro/maxtime">MAXTIME</a></p></td>
<td><p>Transfer validity limit time for the final date (MAXDATE).</p></td>
</tr>
<tr class="odd">
<td><p><a href="../../../command_summary/parameter_intro/mindate">MINDATE</a></p></td>
<td><p>Minimum transfer validity date.</p>
<p>Only taken into account in requester
mode</p></td>
</tr>
<tr class="even">
<td><p><a href="../../../command_summary/parameter_intro/nblksize">NBLKSIZE</a></p></td>
<td><p>File block size, in protocol terms.</p></td>
</tr>
<tr class="odd">
<td><p><a href="../../../command_summary/parameter_intro/ncode">NCODE</a> </p></td>
<td><p>Sent data code.</p></td>
</tr>
<tr class="even">
<td><p><a href="../../../command_summary/parameter_intro/ncomp">NCOMP</a></p></td>
<td><p>Compression of on-line data required by the sender.</p></td>
</tr>
<tr class="odd">
<td><p><a href="../../../command_summary/parameter_intro/netband">NETBAND</a></p></td>
<td><p>Select the outgoing port range.</p></td>
</tr>
<tr class="even">
<td><p><a href="../../../command_summary/parameter_intro/nfname">NFNAME</a></p></td>
<td><p>Name of the physical file sent to the receiver partner.</p></td>
</tr>
<tr class="odd">
<td><p><a href="../../../command_summary/parameter_intro/nkeylen">NKEYLEN</a></p></td>
<td><p>Length (in bytes) of the key of an indexed file.</p></td>
</tr>
<tr class="even">
<td><p><a href="../../../command_summary/parameter_intro/nkeypos">NKEYPOS</a></p></td>
<td><p>Location (in bytes) of the key in the records of an indexed
file.</p></td>
</tr>
<tr class="odd">
<td><p><a href="../../../command_summary/parameter_intro/nlrecl">NLRECL</a></p></td>
<td><p>For records of:</p>
<ul>
<li>Fixed
format (FRECFM = F): size in bytes of the records of the receiver file</li>
<li>Variable
format (FRECFM = V): maximum size in bytes of the records</li>
</ul></td>
</tr>
<tr class="even">
<td><p><a href="../../../command_summary/parameter_intro/notify">NOTIFY</a></p></td>
<td><p>Defines the destination of the messages associated with
the send transfer selected from the log file messages, by the value of
the OPERMSG parameter.</p></td>
</tr>
<tr class="odd">
<td><p><a href="../../../command_summary/parameter_intro/nrecfm">NRECFM</a></p></td>
<td><p>Format of the records of the file defined in protocol terms.</p></td>
</tr>
<tr class="even">
<td><p><a href="../../../command_summary/parameter_intro/ntype">NTYPE</a> </p></td>
<td><p>File type, in protocol terms.</p></td>
</tr>
<tr class="odd">
<td><p><a href="../../../command_summary/parameter_intro/opermsg">OPERMSG</a> </p></td>
<td><p>Defines the categories of transfer information messages
intended for the operator, with all the messages also being written in
the log file.</p></td>
</tr>
<tr class="even">
<td><p><a href="../../../command_summary/parameter_intro/parm">PARM</a> </p></td>
<td><p>User parameter sent to the receiver.</p></td>
</tr>
<tr class="odd">
<td><a href="../../../command_summary/parameter_intro/preexec">PREEXEC</a></td>
<td>Name of the file describing the procedure to be executed before the transfer, as per the preprocessing phase.</td>
</tr>
<tr class="even">
<td><p><a href="../../../command_summary/parameter_intro/pri">PRI</a></p></td>
<td><p>Send request selection priority.</p></td>
</tr>
<tr class="odd">
<td><p><a href="../../../command_summary/parameter_intro/ruser">RUSER</a></p></td>
<td><p>Identifier of the file receiver user.</p></td>
</tr>
<tr class="even">
<td><p><a href="../../../command_summary/parameter_intro/selfname">SELFNAME</a> </p></td>
<td><p>Name of the file that contains the list of files selected
for sending.</p>
<table data-cellpadding="0" data-cellspacing="0">
<tbody>
<tr class="odd">
<td data-valign="top"></td>
<td data-valign="top"><span><strong>Note</strong></span></td>
<td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">When using SELFNAME and FACTION=DELETE, the FNAME must be a directory and not a MASK. For example, #dir is deleted, whereas #dir/* is ignored.</td>
</tr>
</tbody>
</table></td>
</tr>
<tr class="odd">
<td><a href="../../../command_summary/parameter_intro/sourceappl">SOURCEAPPL</a></td>
<td>The identifier of the local file sender application.</td>
</tr>
<tr class="even">
<td><p><a href="../../../command_summary/parameter_intro/spart">SPART</a> </p></td>
<td><p>Network designation by which the local Transfer CFT monitor
identifies itself to its partner.</p></td>
</tr>
<tr class="odd">
<td><p><a href="../../../command_summary/parameter_intro/state">STATE</a></p></td>
<td><p>Defines the transfer request state.</p></td>
</tr>
<tr class="even">
<td><p><a href="../../../command_summary/parameter_intro/suser">SUSER</a> </p></td>
<td><p>Identifier of the file sender user.</p></td>
</tr>
<tr class="odd">
<td><a href="../../../command_summary/parameter_intro/targetappl">TARGETAPPL</a></td>
<td>Identifier of the local
file receiver application.</td>
</tr>
<tr class="even">
<td><p><a href="../../../command_summary/parameter_intro/trk">TRK</a></p></td>
<td><p>Specification of how much detail Transfer CFT provides
Sentinel about transfers. Transfer CFT sends detail about the transfers
in the form of tracked instances.</p></td>
</tr>
<tr class="odd">
<td><p><a href="../../../command_summary/parameter_intro/userid">USERID</a></p></td>
<td><p>Identifier of the transfer owner.</p></td>
</tr>
<tr class="even">
<td><p><a href="../../../command_summary/parameter_intro/wfname">WFNAME</a> </p></td>
<td><p>Name of the temporary file used to send a group of files
selected in line with the generic name specified in FNAME.</p></td>
</tr>
<tr class="odd">
<td><p><a href="../../../command_summary/parameter_intro/xlate">XLATE</a> </p></td>
<td><p>Identifier of the translation table used for send transfers
relative to this model file.</p></td>
</tr>
</tbody>
</table>

### <span id="Additional_filename_information"></span>Additional filename information

In the sender server with implicit send operating mode, the use
of the FNAME parameter is mandatory in CFTSEND.

In sender requesteror sender server mode with a hold for sending request, the filename can
be defined in the send transfer request (SEND command or CFTAPI call)
rather than in the CFTSEND object. Click on the links in the following
table for examples and details.

<table data-cellspacing="0">
<thead>
<tr class="header">
<th><p>Format </p></th>
<th><p>Processing </p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="../../../command_summary/filename_conventions">FNAME = filename</a> </p></td>
<td><p>Sends a file or a version of a file </p></td>
</tr>
<tr class="even">
<td><p>FNAME = {mask | dirname} </p></td>
<td><p>Lists a directory </p></td>
</tr>
<tr class="odd">
<td><p><a href="ex_send_group_of_specified_files.htm">FNAME
= #filename</a> </p></td>
<td><p>Sends a group of files, the list of which is located in
the specified file </p></td>
</tr>
<tr class="even">
<td><p>FNAME = {#mask | #dirname} </p></td>
<td><ul>
<li>Sends a group of files selected in line with the generic
name specified (#mask)</li>
<li>Sends all files in the directory specified (#dirname) </li>
</ul></td>
</tr>
</tbody>
</table>

## <span id="Example"></span>Examples

This section provides examples on how to define the CFTSEND template.

### <span id="Implicit_send_example"></span>Implicit send

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>CFTSEND</p>
<p>MODE = REPLACE,</p>
<p>ID = SNDIMPL,     /* IDF implicit send transfers */</p>
<p>IMPL = YES,</p>
<p>FCODE = EBCDIC,      /* EBCDIC data in file */</p>
<p>FNAME = ’JSTATI’     /* called ... */</p></td>
</tr>
</tbody>
</table>

Only used if:

-   The value of the
    transfer IDF is SNDIMPL
-   Transfer CFT responds
    to a send request from the partner, where Transfer CFT is the sender server
-   There is no SEND
    request for this IDF pending in the catalog
-   An implicit send
    mechanism is involved where IMPL = YES

### Default description of the model file

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>CFTSEND</p>
<p>MODE = REPLACE,</p>
<p>ID = IDFDEF,  /* default IDF */</p>
<p>IMPL = NO,</p>
<p>FCODE = ASCII /* EBCDIC data in file */</p></td>
</tr>
</tbody>
</table>

Corresponds to a send transfer when the SEND command specifies an IDF
not described by a CFTSEND object. This is the default description of
the model file to be sent. The CFTPARM object must specify:

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>CFTPARM DEFAULT = IDFDEF, ...</p></td>
</tr>
</tbody>
</table>

The SEND command specifies the name of the file to be sent, the FNAME
parameter.

### Cyclic send

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>CFTSEND</p>
<p>MODE = CREATE,</p>
<p> ID = STAT,                   /* File identifier */</p>
<p>FLRECL = 128, /* of max length 128 bytes */</p>
<p>FACTION = DELETE /* Delete after send */</p>
<p>FCODE = ASCII, /* File coding */</p>
<p>MINDATE = 19920703, /* From 03/07/92 */</p>
<p>MINTIME = 1000, /* at 10:00 (Monday) */</p>
<p>MAXDATE = 19921231, /* Until 31/12/92 */</p>
<p>MAXTIME = 2000, /* at 20:00 */</p>
<p>CYCLE = 7 /* Every week */</p>
<p>TCYCLE = DAY, /* CYCTIME takes the value 1000 */</p>
<p> CYCDATE = 19920705, /* Activate possible */ /* first 3 days of */ /* week, before */ /* Wednesday 10:00 */</p>
<p>PARM = ’Day statistic’ /* Associated parameter.for.*/ /*PeSIT CFT profile */</p></td>
</tr>
</tbody>
</table>

Meets a specific cyclic send requirement.
