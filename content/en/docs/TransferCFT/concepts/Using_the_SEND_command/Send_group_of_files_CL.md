{
    "title": "Sending  a group of files ",
    "linkTitle": "Sending a group of files",
    "weight": "210"
}You can use the FNAME parameter in a SEND command, when prefixed with the &lt;file\_symb>
indirection character, to trigger SEND operations that correspond to:

-   A list of file names in an indirection file (SEND FNAME = #LIST for example) in heterogeneous mode only
-   A series of files indicated by a generic name (SEND
    FNAME = #FIL\* for example) or a directory name (SEND FNAME = #DIRECTORY\\\*)
    -   In homogeneous mode
    -   In heterogeneous mode
    -   Using a file name filter

<table data-cellpadding="0" data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td data-valign="top">         </td>
         <td data-valign="top"><span><strong>Note</strong></span>         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">If FNAME designates a generic name and the &lt;file_symb&gt;
indirection character is omitted, SEND FNAME = FIL* for example, the SEND
command triggers a single transfer, in which pseudo-records each of which corresponds
to a file name are sent.         </td>
      </tr>
   </tbody>
</table>

## <span id="Sending_files_designated_by_an_indirection_file"></span>Use an indirection file

You can use a list of file names to send a group of files using the indirection file structure as follows:

-   A record can contain
    only one file name
-   A file name must
    begin in the first column
-   The file can contain
    empty records
-   The file name cannot contain an asterisk (\*)

#### Example

For a file called REPORTS containing the following list:

-   file1
-   file2
-   file3

Windows

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>CFTUTIL SEND part=tokyo, idf=myfiles, fname=#REPORTS         </td>
      </tr>
   </tbody>
</table>

UNIX

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>CFTUTIL SEND part=tokyo, idf=myfiles, fname=@REPORTS         </td>
      </tr>
   </tbody>
</table>

The files file1, file2 and file3 will be sent.

<table data-cellpadding="0" data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td data-valign="top">         </td>
         <td data-valign="top"><span><strong>Note</strong></span>         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">You cannot use a file name with an asterisk, for example fil*, as that denotes the beginning of a file not a directory.         </td>
      </tr>
   </tbody>
</table>

If there are N files to be sent, a SEND IDF = ID\_EM, FNAME = #GROUP (or @GROUP)
... command generates N+1 transfer entries in the catalog, as follows:

-   One entry for each
    file transfer (that is N entries)
-   A generic (virtual)
    entry, which never triggers an actual transfer but is used locally to
    manage the group of files to be sent
    -   This virtual transfer is identified by a DIAGP code set to LIST\_FI,
        when the catalog is queried. Its state is immediately set to K
        in the catalog.
    -   The generic entry is set to the T
        or **X** state when all transfers have been set to **T** state (or **X** depending on the mode).
    -   The post-processing procedure is activated when all files in
        the group have been transferred (LIST\_FI entry set to the T
        or **X** state, depending on the mode).
    -   If the group file does not exist or cannot be opened, the generic entry
        remains set to the K state and
        error message CFTT34E is returned.
    -   If one of the files in the group cannot be sent (for example an unknown file), the other transfers are not affected,
        but the generic entry for the group is not set to the **T** state (or **X** depending on the mode).

<table data-cellpadding="0" data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td data-valign="top">         </td>
         <td data-valign="top"><span><strong>Note</strong></span>         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">See also <a href="../phase_and_phasestep/processing_compatability">COMPAT</a> mode, if using backward compatibility.         </td>
      </tr>
   </tbody>
</table>

For the receiver:

-   A catalog entry is created for each file received
-   The name of each file can be specified using the
    &FPATH, &FROOT and &FSUF symbolic variables

<table data-cellpadding="0" data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td data-valign="top">         </td>
         <td data-valign="top"><span><strong>Note</strong></span>         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">You can specify a list of directories to be sent in the indirection
file.
However, do not mix files and directories in the same indirection file.         </td>
      </tr>
   </tbody>
</table>

IBM i (OS/400)

If your file contains the list of files to be sent, you must first create a REPORTS file in \*DATA format (\*SRC files contain a header and Transfer CFT cannot use these).

For example:

1.  CRTLIB MYSEND
2.  CRTPF FILE(MYSEND/REPORTS) RCDLEN(92) FILETYPE(\*DATA)
3.  EDTF FILE(MYSEND/REPORTS)
    -   Add the list of files to transfer:
        -   MYSEND/FILE1
        -   MYSEND/FILE2
        -   MYSEND/FILE3
4.  CALL PGM(CFTUTIL) PARM(SEND 'part=paris, idf=LISTFI,fname=#MYSEND/REPORTS')

## <span id="Sending_generic_name_files"></span>Use generic name files

To send a group of generic files, use the command:

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>SEND FNAME=#<em>mask</em> or SEND FNAME=#<em>dirname</em>         </td>
      </tr>
   </tbody>
</table>

Where the FNAME parameter is set to one of the following values:

-   A directory name,
    *dirname*, in which
    case all files accessible in the directory are to be sent
-   A generic name,
    *mask,* including wildcard characters,
    in which case only the selected files are to be sent
-   A directory name
    and a generic file name, in which case only the files selected in the
    directory are to be sent

The processing performed is of two types, depending on the operating
system of the remote site. The type of remote site is characterized by
the SYST parameter in the CFTPART command. Sites are said to be mono-platform
when the same operating system is used by both partners.

### Types of group file transfers

There are two types of send procedures for groups of files: homogeneous and heterogeneous.
These procedure types are described in detail further on in this topic.

#### Homogeneous send for a group of files

A homogeneous send occurs between two Transfer CFT that run on the same operating
system. This transfer procedure concatenates at the site sending the group of files and de-concatenates upon reception.

Mandatory parameters for homogeneous sends include:

-   WFNAME: Determines transmission and reception in homogeneous sends, because
    the file resulting from the concatenation is the file that is sent.
-   SYST: Defined for a remote partner, where the default value is the local operating system. Homogeneous transfers are only possible when CFTPART command's SYST value is the same as the local operating system.

<table data-cellspacing="0">
   <thead>
      <tr class="header">
         <th>Platform</th>
         <th>UNIX-like environment</th>
         <th>Native</th>
      </tr>
   </thead>
   <tbody>
      <tr class="odd">
         <td>UNIX         </td>
         <td>Available         </td>
         <td>Available         </td>
      </tr>
      <tr class="even">
         <td>Windows         </td>
         <td>Not supported         </td>
         <td>Available         </td>
      </tr>
      <tr class="odd">
         <td>z/OS         </td>
         <td>Not supported         </td>
         <td>Available         </td>
      </tr>
      <tr class="even">
         <td>IBM i         </td>
         <td>Not supported         </td>
         <td>Not supported         </td>
      </tr>
      <tr class="odd" data-mc-conditions="">
         <td>HP Nonstop         </td>
         <td>Available         </td>
         <td>Not supported         </td>
      </tr>
   </tbody>
</table>

Example

An example of a homogeneous send in a Windows environment:

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>cftsend id = copie,<br />
fname = #c:\e\cft320\tmp\a*,<br />
wfname = c:\e\cft320\&amp;idtu.snd,<br />
frecfm = v,
ftype = b,<br />
mode = create<br />
cftrecv id = copie,<br />
fname = c:\cft320\bin\recv,<br />
faction = delete,<br />
wfname = &amp;idtu.rcv,<br />
ftype = b</p>         </td>
      </tr>
   </tbody>
</table>

#### Heterogeneous send for a group of files

A heterogeneous send occurs between two Transfer CFT that run on dissimilar operating
systems. This type of group file transfer triggers the transfer
of all files belonging to the group.

General syntax

Windows: fname =#directory\\\*

Unix: fname =@directory/\*

#### Force heterogeneous mode for a group of files

In Transfer CFT both homogeneous and heterogeneous mode are enabled by default. However, you may want to ensure that groups of files are transferred using only the heterogeneous mode. The UCONF configuration parameter cft.server.force\_heterogeneous\_mode allows you to do this, effectively disabling homogeneous mode even if the partner is configured for homogeneous exchanges.

For more information on sending groups of files and heterogeneous mode exchanges, see [Sending a group of files](#).

To force heterogeneous mode:

1.  Access the unified configuration utility using either [command line](../../uconf/uconf_w_cftutil.htm) or the UI.
2.  Set the following parameter to enable forced heterogeneous exchanges for group file transfers.

Unix/Windows

<table data-cellspacing="0">
   <thead>
      <tr class="header">
         <th>Parameter</th>
         <th>Default</th>
         <th>Description</th>
      </tr>
   </thead>
   <tbody>
      <tr class="odd">
         <td>cft.server.force_heterogeneous_mode         </td>
         <td>No         </td>
         <td>            <p>Force heterogeneous mode for group file transfers. This parameter replaces the deprecated environment variable: CFTSFMCPY.</p>
            <p>Possible values:</p>
            <ul>
               <li>Yes: Force heterogeneous mode exchanges (override homogeneous mode)               </li>
               <li>No: Standard heterogeneous and homogeneous functioning               </li>
            </ul>         </td>
      </tr>
   </tbody>
</table>

#### Sending to a remote site in homogeneous mode

<table data-cellpadding="0" data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td data-valign="top">         </td>
         <td data-valign="top"><span><strong>Note</strong></span>         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">The following is valid when using the same system type <em>and</em> heterogeneous mode is not forced. When using <span>Central Governance</span> remember that heterogeneous mode is the default setting.         </td>
      </tr>
   </tbody>
</table>

The files to be transferred are copied and concatenated in a work file
that must be specified in the WFNAME parameter of the send command.

On the sender side, two entries are
created in the catalog:

-   A generic entry
    (LIST\_FI) with the following attributes:
    -   FNAME =
        {dirname | mask}
    -   and WFNAME
        = temp-filename

Its state is immediately set to K, once it has been created in the catalog.
This entry is set to the T (or X) state when all transfers have been set to T (or X depending on the compatibility mode).

-   A transfer entry
    with the following attributes:
    -   FNAME =
        temp-filename
    -   WFNAME
        = {dirname | mask}

On the receiver side, a single transfer
entry is created. The data is received in the work file that must be specified
in the WFNAME parameter and de-concatenated in the directory specified
in the FNAME parameter of the receive command.

Once the transfer has been completed, the work file is deleted by each
of the relevant partners. If the transfer is interrupted however, the
associated WFNAME work file is not deleted. It will only be removed when
the transfer has been restarted and successfully completed or the associated
catalog entry has been deleted.

The file attributes defined for the transfer (CFTRECV or RECV command)
apply to the copied/concatenated WFNAME file.

**Sending to a remote site**

![](/Images/TransferCFT/send_to_remote_site.png)

#### <span id="Heterogeneous send"></span>Sending to a remote site with a different operating system in heterogeneous mode

The copy/concatenation operation is not performed for a remote site
with a different operating system, i.e. a heterogeneous send. If the WFNAME parameter is set in the
send command, it is ignored.

The sender creates the following entries:

-   One transfer entry
    for each file selected after analyzing the generic request
-   A generic entry
    identified by the DIAGP code set to LIST\_FI. Once it has been created
    in the catalog, its state is immediately set to K. The state is changed
    to T (or X) when all related transfers are set to T (or X, depending on the compatibility mode).

The EXECSF end of transfer procedure is activated when all selected
files have been transferred. If one of the files concerned by the generic
transfer cannot be sent, the other transfers are in no way affected, but
the generic entry is not set to the T state (or X, depending on the compatibility mode).

On
the receiver side, one transfer entry is created for each file
received.

For operating reasons, the receiving Transfer CFT may wish to archive each
file received using a name derived from that of the sender site. The following
paragraphs explain how the sending Transfer CFT can send the name of each file
transferred to the partner via a generic request.

A receiving Transfer CFT can specify the name of each file received via the
&FROOT, &FPATH and &FSUF symbolic variables.

Sending to a remote site with a different
operating system

![](/Images/TransferCFT/new_group_files.png)

Example

In Windows, an example of a heterogeneous receive:

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>cftsend id = copie,<br />
fname = #c:\e\cft320\tmp\a*,<br />
wfname = c:\e\cft320\&amp;idtu.snd,<br />
frecfm = v,
ftype = b,<br />
mode = create<br />
cftrecv id = copie,<br />
fname = c:\cft320\bin\recv,<br />
faction = delete,<br />
wfname = &amp;idtu.rcv,<br />
ftype = b</p>         </td>
      </tr>
   </tbody>
</table>

### <span id="Create"></span>Create filters using CFTSEND

You  can use the CFTSEND [FILTER](../../CFTUTIL/Parameter_index/filter.htm) and [FILTERTYPE](../../CFTUTIL/Parameter_index/filtertype.htm) parameters to apply file filtering based on the FNAME.

For example, create a filter that includes all .jpg files that are:

-   A word (at least one other word character)
-   Followed by four-digit number

#### Heterogeneous mode

For example, a transfer from a Unix platform to Windows, the following filter would include all of the files in "myfolder" that match the pattern described above such as the file IMGP0122.jpg.

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p> CFTSEND ID = 'findfile',</p>
            <p> FILTERTYPE = 'EREGEX',</p>
            <p> FILTER = '^[0-9a-zA-Z]+[0-9]{4}.jpg'</p>
            <p>...</p>
            <p> </p>
            <p>SEND PART = PARIS,</p>
            <p> IDF = 'findfile',</p>
            <p> FNAME = '@myfolder/*'</p>
            <p>...</p>         </td>
      </tr>
   </tbody>
</table>

For example on a z/OS platform, the following filter would include the files AXDSYN.TOOLS.GRPFIL. or GRPFIM. followed by A4 or A5:

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>CFTSEND ID = 'TREGEX03',</p>
            <p>FILTERTYPE = 'EREGEX',</p>
            <p>FILTER = '^-[\.]+*\.-[^\.]+*\.GRPFI(L|M).A(4|5)\.'</p>
            <p>...</p>
            <p> </p>
            <p>SEND PART = PARIS,</p>
            <p>IDF = 'TREGEX03',</p>
            <p>FNAME = '#AXDSYN.TOOLS.*'</p>         </td>
      </tr>
   </tbody>
</table>

The FILTERTYPE can be either STRJCMP or EREGEX, used as described further on in this topic.

#### Homogeneous mode

For example, a transfer between Unix platforms, the following filter would include all of the files in "myfolder" that match the pattern described above such as the file IMGP0122.jpg.

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p> CFTSEND ID = 'findfile',</p>
            <p> FILTERTYPE = 'EREGEX',</p>
            <p> FILTER = '^[0-9a-zA-Z]+[0-9]{4}.jpg'</p>
            <p>...</p>
            <p> </p>
            <p>SEND PART = PARIS,</p>
            <p> IDF = 'findfile',</p>
            <p> FNAME = '@myfolder/*'</p>
            <p>WFNAME = '&amp;idtu.tmp'</p>
            <p>...</p>         </td>
      </tr>
   </tbody>
</table>

## STRJCMP filter

A STRJCMP pattern-matching filter can contain the asterisk (\*) and/or the question mark (?) characters. The STRJCMP filter characters are interpreted as follows:

<table data-cellspacing="0">
   <thead>
      <tr class="header">
         <th>Character</th>
         <th>Description</th>
         <th>Example</th>
      </tr>
   </thead>
   <tbody>
      <tr class="odd">
         <td>*         </td>
         <td>Indicates any sequence of zero or more characters.         </td>
         <td>The filter "*.dat" selects any file name that has the extension ".dat".         </td>
      </tr>
      <tr class="even">
         <td>?         </td>
         <td>Indicates any single character.         </td>
         <td>The filter "T*.???" selects any file name starting with a 'T' and having an extension of exactly three characters.         </td>
      </tr>
   </tbody>
</table>

## EREGEX filter

EREGEX (extended regular expressions) is the use of special characters and strings to define a search pattern. In Transfer CFT, you can use these search patterns to create filters.

In POSIX-Extended regular expressions, all characters match themselves meaning they match a sub-string anywhere inside the string to be searched. For example *abc*, matches abc123, 123abc, and 123abcxyz. Some symbols are exceptions though; commonly used symbols and example usages are listed in the following table.

<table data-cellspacing="0">
   <thead>
      <tr class="header">
         <th>Symbol</th>
         <th>Indicates</th>
         <th>Example</th>
      </tr>
   </thead>
   <tbody>
      <tr class="odd">
         <td>.         </td>
         <td>Any character except newline (line break)         </td>
         <td><em>a.c</em> matches abc         </td>
      </tr>
      <tr class="even">
         <td>[ ]         </td>
         <td>Or         </td>
         <td><em>[def]</em> means d or e or f         </td>
      </tr>
      <tr class="odd">
         <td>{}         </td>
         <td>Exactly         </td>
         <td><em>{3}</em> means exactly three         </td>
      </tr>
      <tr class="even">
         <td>()         </td>
         <td>Capture group         </td>
         <td><em>pand(ora|467)</em> matches pandora OR pand467         </td>
      </tr>
      <tr class="odd">
         <td>*         </td>
         <td>0 or more occurrences of the preceding element         </td>
         <td>            <p><em>ab*c</em> matches ac, abc, abbc, abbbc, and so on</p>         </td>
      </tr>
      <tr class="even">
         <td>+         </td>
         <td>1 or more occurrences of the preceding element         </td>
         <td><em>ab+c</em> matches abc, abbc, abbbc, and so on, but not ac         </td>
      </tr>
      <tr class="odd">
         <td>?         </td>
         <td>Zero or one occurrence of the preceding element         </td>
         <td><em>plurals?</em> matches plural         </td>
      </tr>
      <tr class="even">
         <td>|         </td>
         <td>Alternation (matches either the right side or the left) / OR operand         </td>
         <td><em>ab|cd|ef</em> matches ab or cd or ef         </td>
      </tr>
      <tr class="odd">
         <td>^         </td>
         <td>Start of a string         </td>
         <td><em>^a</em> matches any file that starts with an a         </td>
      </tr>
      <tr class="even">
         <td>[^ ...]         </td>
         <td>Any single character that is <strong>not</strong> in the class         </td>
         <td><em>[^/]*</em> matches zero or more occurrences of any character that is not a forward-slash, such as http://         </td>
      </tr>
      <tr class="odd">
         <td>$         </td>
         <td>End of string         </td>
         <td><em>.*? the end$</em> matches this is the end         </td>
      </tr>
   </tbody>
</table>

<table data-cellpadding="0" data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td data-valign="top">         </td>
         <td data-valign="top"><span><strong>Note</strong></span>         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">EREGEX refers to POSIX Extended Regular Expression. There are multiple tutorials available online to aid in creating search patterns; for additional information on expression syntax please refer to <a href="http://pubs.opengroup.org/onlinepubs/009696899/basedefs/xbd_chap09.html">Regular expressions</a>.         </td>
      </tr>
   </tbody>
</table>

## <span id="SNDINDFILEERR"></span>Define the catalog details policy for group-of-files transfers

If you execute a SEND transfer request for a group of files that uses a sequential file as input, it creates as many transfer requests as there are lines in the input file, possibly causing the catalog to overfill.

To avoid this you can use the CFTPARM parameter SNDINDFILEERR to define the policy for a group of files type of transfer to address this issue if there is an error.

Parameter values:

-   CONTINUE (default): Keep the existing behavior, which creates as many transfer requests as there are lines in the input file.
-   ABORT: If the input file line is not a file, this gives the current transfer the status K diagi 132 diagp SNDINDFI, the generic transfer status is K diagi 200, and no other child requests are created.

Catalog details

Simplified catalog view when set to CONTINUE

<table data-cellspacing="0">
   <thead>
      <tr class="header">
         <th>Transfer type</th>
         <th>IDTU</th>
         <th>PIDTU</th>
         <th>Phasestep</th>
         <th>Diagi</th>
      </tr>
   </thead>
   <tbody>
      <tr class="odd">
         <td>Parent         </td>
         <td>1         </td>
         <td>          </td>
         <td>H         </td>
         <td>0         </td>
      </tr>
      <tr class="even">
         <td>Child         </td>
         <td>2         </td>
         <td>1         </td>
         <td>K         </td>
         <td>110         </td>
      </tr>
      <tr class="odd">
         <td>Child         </td>
         <td>3         </td>
         <td>1         </td>
         <td>C         </td>
         <td>0         </td>
      </tr>
      <tr class="even">
         <td>Child         </td>
         <td>N         </td>
         <td>1         </td>
         <td>C         </td>
         <td>0         </td>
      </tr>
   </tbody>
</table>

Simplified catalog view when set to ABORT

<table data-cellspacing="0">
   <thead>
      <tr class="header">
         <th>Transfer type</th>
         <th>IDTU</th>
         <th>PIDTU</th>
         <th>Phasestep</th>
         <th>Diagi</th>
      </tr>
   </thead>
   <tbody>
      <tr class="odd">
         <td>Parent         </td>
         <td>1         </td>
         <td>          </td>
         <td>H         </td>
         <td>200         </td>
      </tr>
      <tr class="even">
         <td>Child         </td>
         <td>2         </td>
         <td>1         </td>
         <td>K         </td>
         <td>132         </td>
      </tr>
   </tbody>
</table>
