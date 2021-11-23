{
    "title": "CFTRECV  - Receive templates",
    "linkTitle": "Receive templates - CFTRECV ",
    "weight": "220"
}This topic describes the {{< TransferCFT/transfercftname  >}}
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
    [CFTRECV](../../../command_summary#CFTRECV)

<table>
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Parameter         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p><a href="../../../command_summary/parameter_intro/comment">COMMENT</a></p>         </td>
         <td><p>Local alphanumeric comment associated
with receive transfers.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="../../../command_summary/parameter_intro/cycdate">CYCDATE</a></p>         </td>
         <td><p>Upper final date for activating the first
transfer of a cycle.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="../../../command_summary/parameter_intro/cyctime">CYCTIME</a></p>         </td>
         <td><p>Upper limit time for activating the first
transfer of a cycle.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="../../../command_summary/parameter_intro/delete">DELETE</a> </p>         </td>
         <td><p>Automatic deletion of the catalog entries
in the "X" phase (done) for the corresponding IDF.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="../../../command_summary/parameter_intro/exit">EXIT</a></p>         </td>
         <td><p>Identifier of the CFTEXIT command associated
with this transfer.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="../../../command_summary/parameter_intro/faction">FACTION</a></p>         </td>
         <td><p>Action on the file for a receive transfer.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="../../../command_summary/parameter_intro/fblksize">FBLKSIZE</a></p>         </td>
         <td><p>This parameter (in bytes) controls the
"blocking factor" of the receiver file records: according to
the system, it defines the disk block size and/or the file input/output
buffer size.</p>         </td>
      </tr>
      <tr>
         <td><a href="../../../command_summary/parameter_intro/fcharset">FCHARSET</a>         </td>
         <td>Defines the local file encoding.         </td>
      </tr>
      <tr>
         <td><p><a href="../../../command_summary/parameter_intro/fcheck">FCHECK</a></p>         </td>
         <td><p>Checks record length attributes.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="../../../command_summary/parameter_intro/fcode#fcode_CFTSEND">FCODE</a></p>         </td>
         <td><p>Code of the receiver file data (local
data code).</p>         </td>
      </tr>
      <tr>
         <td><p><a href="../../../command_summary/parameter_intro/fdisp#fdisp_CFTRECV">FDISP</a></p>         </td>
         <td><p>Presence check indicator of the receiver
file used to determine the action of the Transfer CFT monitor.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="../../../command_summary/parameter_intro/fkeylen">FKEYLEN</a> </p>         </td>
         <td><p>Key length of an indexed file.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="../../../command_summary/parameter_intro/fkeypos#fkeypos">FKEYPOS</a></p>         </td>
         <td><p>Key position relative to 0 in the record
of an indexed file.</p>         </td>
      </tr>
      <tr>
         <td><a href="../../../command_summary/parameter_intro/flowname">FLOWNAME</a>         </td>
         <td>The local flow descriptor.         </td>
      </tr>
      <tr>
         <td><p><a href="../../../command_summary/parameter_intro/flrec#flrecl">FLRECL</a> </p>         </td>
         <td><p>File record length in bytes.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="../../../command_summary/parameter_intro/fname#fname%20CFTSEND__CFTRECV__CFTISEND">FNAME</a></p>         </td>
         <td><p>Name of the physical receiver file (filename
or complete pathname) of the directory.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="../../../command_summary/parameter_intro/force">FORCE</a> </p>         </td>
         <td><p>Determines the priority with which the
parameters set in CFTRECV are taken into account relative to the parameters
set in an associated RECV command.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="../../../command_summary/parameter_intro/forg">FORG</a> </p>         </td>
         <td><p>Organization of the file to be sent.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="../../../command_summary/parameter_intro/frecfm">FRECFM</a> </p>         </td>
         <td><p>Record format of the receiver file.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="../../../command_summary/parameter_intro/fspace">FSPACE</a> </p>         </td>
         <td><p>Size of the receiver file, in K-bytes
(1 K-byte = 1024 bytes).</p>         </td>
      </tr>
      <tr>
         <td><p><a href="../../../command_summary/parameter_intro/ftype#ftype">FTYPE</a></p>         </td>
         <td><p>Type of the receiver file.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="../../../command_summary/parameter_intro/groupid">GROUPID</a></p>         </td>
         <td><p>Information completing the USERID of the
CFTRECV command.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="../../../command_summary/parameter_intro/id#id_CFTSEND">ID</a> </p>         </td>
         <td><p>Local model file identifier (IDF).</p>         </td>
      </tr>
      <tr>
         <td><p><a href="../../../command_summary/parameter_intro/maction">MACTION</a> </p>         </td>
         <td><p>Action on the files transferred by COPY
at the time of creation.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="../../../command_summary/parameter_intro/maxdate">MAXDATE</a></p>         </td>
         <td><p>Transfer validity final date.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="../../../command_summary/parameter_intro/maxtime">MAXTIME</a></p>         </td>
         <td><p>Transfer validity limit time for the final
date (MAXDATE).</p>         </td>
      </tr>
      <tr>
         <td><p><a href="../../../command_summary/parameter_intro/mindate">MINDATE</a></p>         </td>
         <td><p>Minimum transfer validity date.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="../../../command_summary/parameter_intro/mintime">MINTIME</a></p>         </td>
         <td><p>Transfer initial validity time, from the
first day (MINDATE).</p>         </td>
      </tr>
      <tr>
         <td><a href="../../../command_summary/parameter_intro/ncharset">NCHARSET</a>         </td>
         <td>Defines the destination file encoding that is used on a file
to encode or decode network data.         </td>
      </tr>
      <tr>
         <td><a href="../../../command_summary/parameter_intro/ncode">NCODE</a>         </td>
         <td>The network data code when receiving transfers. <em>Available only when using SFTP.</em>         </td>
      </tr>
      <tr>
         <td><p><a href="../../../command_summary/parameter_intro/ncomp">NCOMP</a></p>         </td>
         <td><p>Compression of on-line data requested
by the receiver.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="../../../command_summary/parameter_intro/netband">NETBAND</a></p>         </td>
         <td><p>Select the outgoing port range.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="../../../command_summary/parameter_intro/notify">NOTIFY</a></p>         </td>
         <td><p>Defines the destination of the messages
associated with the send transfer selected from the log file messages,
by the value of the OPERMSG parameter.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="../../../command_summary/parameter_intro/opermsg">OPERMSG</a> </p>         </td>
         <td><p>Defines the categories of transfer information
messages intended for the operator (all the messages also being written
in the log file).</p>         </td>
      </tr>
      <tr>
         <td><p><a href="../../../command_summary/parameter_intro/pri">PRI</a></p>         </td>
         <td><p>Receive request selection priority.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="../../../command_summary/parameter_intro/ruser">RUSER</a></p>         </td>
         <td><p>Identifier of the file receiver user.</p>         </td>
      </tr>
      <tr>
         <td><a href="../../../command_summary/parameter_intro/sourceappl">SOURCEAPPL</a>         </td>
         <td>The identifier of the local file sender application.         </td>
      </tr>
      <tr>
         <td><p><a href="../../../command_summary/parameter_intro/state">STATE</a> </p>         </td>
         <td><p>Defines the transfer request state.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="../../../command_summary/parameter_intro/suser">SUSER</a> </p>         </td>
         <td><p>Identifier of the file sender user.</p>         </td>
      </tr>
      <tr>
         <td><a href="../../../command_summary/parameter_intro/targetappl">TARGETAPPL</a>         </td>
         <td>Identifier of the local
file receiver application.         </td>
      </tr>
      <tr>
         <td><p><a href="../../../command_summary/parameter_intro/tcycle">TCYCLE</a> </p>         </td>
         <td><p>Transfer cycle period unit.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="../../../command_summary/parameter_intro/trk">TRK</a> </p>         </td>
         <td><p>Specification of how much detail Transfer
CFT provides Sentinel about transfers. Transfer CFT sends detail about
the transfers in the form of tracked instances.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="../../../command_summary/parameter_intro/userid#userid_CFTRECV">USERID</a></p>         </td>
         <td><p>Identifier of the transfer owner.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="../../../command_summary/parameter_intro/wfname">WFNAME</a> </p>         </td>
         <td><p>Name of the temporary file used during
the transfer.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="../../../command_summary/parameter_intro/xlate">XLATE</a> </p>         </td>
         <td><p>Identifier of the translation table used
for the receive transfers.</p>         </td>
      </tr>
   </tbody>
</table>

#### Examples

This section displays examples for a default receive template.

Example 1

CFTRECV



    MODE = REPLACE,

     


    ID = SRCFILES,

    /* IDF for source files */


    FDISP = BOTH

    /* already exists or not */


    FACTION = ERASE,

    /* if exists erase */


    XLATE = ETOA

    /* with this table  */

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


    MODE = REPLACE,
    ID = IDFDEF, /* default IDF */
    FDISP = BOTH, /* already exists or not */
    FACTION = DELETE, /* if exists - delete */
    FNAME = &IDT /* file as per IDT value */

This command corresponds to the data receive transfer case where the
identifier (IDF) has no explicit description (CFTRECV object). This is
the default receiver model file. The CFTPARM object must specify: CFTPARM
DEFAULT = IDFDEF, ... Transfer CFT then creates a file whose name contains
the unique transfer identifier.

**IBM i:** This command corresponds
to the general database file receive transfer case.
