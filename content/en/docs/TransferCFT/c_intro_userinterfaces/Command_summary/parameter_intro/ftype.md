{
    "title": "ftype",
    "linkTitle": "ftype",
    "weight": "1380"
}<span id="ftype"></span>

### ftype

<span id="ftype_CFTRECV"></span>

#### CFTRECV, CFTSEND

\[ FTYPE = { c } \]  OS-specific

The file type. Some FTYPE parameter values are OS specific. Refer to the Transfer CFT OS-specific documentation for more information.

> **Note:**
>
> When using the SFTP protocol and FTYPE = T, O, X, J or F, the file is considered a text file and there is no specific treatment according to the value. This means that the newline character (EOL character) can be the CRLF (x0Dx0A) or LF (x0A) on Windows, or LF (x0A) on UNIX systems.

UNIX<span id="UNIX_ftype"></span>

<table>
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">FTYPE         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">FCODE         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1">Type of sent file         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>‘ ‘ </p>         </td>
         <td><p>BINARY </p>         </td>
         <td>Binary         </td>
      </tr>
      <tr>
         <td><p>B </p>         </td>
         <td><p>BINARY </p>         </td>
         <td>Binary         </td>
      </tr>
      <tr>
         <td><p>V </p>         </td>
         <td><p>BINARY </p>         </td>
         <td>Binary file emulating locally a variable file format         </td>
      </tr>
      <tr>
         <td><p>T </p>         </td>
         <td><p>ASCII </p>         </td>
         <td>Text file with LF or CRLF as end-of-line separator         </td>
      </tr>
      <tr>
         <td><p>O </p>         </td>
         <td><p>ASCII </p>         </td>
         <td>Text file with CRLF as end-of-line separator         </td>
      </tr>
      <tr>
         <td><p>X </p>         </td>
         <td><p>ASCII </p>         </td>
         <td>Text file with LF as end-of-line separator         </td>
      </tr>
      <tr>
         <td>J         </td>
         <td>ASCII          </td>
         <td><p>Stream text</p>
<p>Using stream text (J) allows a text type file to be sent that contains records that exceed 32 KB. As opposed to text type (FTYPE=T), stream text does not add an EOL sequence (LF or CRLF) to the received file.</p>
<p>When using stream text (FTYPE=J), the sender and the receiver must both have the FTYPE set to J. Setting only the sender or receiver to FTYPE=J results in unexpected content for the transferred file.</p>         </td>
      </tr>
   </tbody>
</table>

See also, [UNIX &gt; Transferable files](../../../../cft_intro_install/unix_install_start_here/run_first_time_ux/aix_with_ibm_hacmp_intro/specific_configurations_intro/transferable_files_unix).

Windows

<table>
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1"><p>FTYPE </p>         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1"><p>FCODE </p>         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1">Type of sent file         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>' '         </td>
         <td>BINARY          </td>
         <td>Binary         </td>
      </tr>
      <tr>
         <td><p>B </p>         </td>
         <td><p>BINARY </p>         </td>
         <td>Binary         </td>
      </tr>
      <tr>
         <td><p>V </p>         </td>
         <td><p>BINARY </p>         </td>
         <td>Binary file emulating locally a variable file format         </td>
      </tr>
      <tr>
         <td><p>T </p>         </td>
         <td><p>ASCII </p>         </td>
         <td>Text file with LF or CRLF as end-of-line separator         </td>
      </tr>
      <tr>
         <td>F         </td>
         <td>ASCII         </td>
         <td>Text file where the last character '1A' is transmitted (is not
considered an EOF character)         </td>
      </tr>
      <tr>
         <td>O         </td>
         <td>ASCII         </td>
         <td>Text file with CRLF as end-of-line separator         </td>
      </tr>
      <tr>
         <td>X         </td>
         <td>ASCII         </td>
         <td>Text file with LF as end-of-line separator         </td>
      </tr>
      <tr>
         <td>J         </td>
         <td>ASCII         </td>
         <td><p>Stream text</p>
<p>Using stream text (J) allows a text type file to be sent that contains records that exceed 32 KB. As opposed to text type (FTYPE=T), stream text does not add an EOL sequence (LF or CRLF) to the received file.</p>
<p>When using stream text (FTYPE=J), the sender and the receiver must both have the FTYPE set to J. Setting only the sender or receiver to FTYPE=J results in unexpected content for the transferred file.</p>         </td>
      </tr>
   </tbody>
</table>

\*Supports ASCII file handling (X'1A') (SEND/RECV FTYPE=F).

See also, [Windows &gt; Transferable files]().

z/OS

Implicit indicates that the FTYPE is automatically detected by the OS.

<table>
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">FTYPE         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">FCODE         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1">Type of sent file         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>Implicit         </td>
         <td>BINARY         </td>
         <td><p>Disk sequential files</p>         </td>
      </tr>
      <tr>
         <td>Implicit         </td>
         <td>BINARY         </td>
         <td><p>Members of PDS files (1 transfer per member)</p>         </td>
      </tr>
      <tr>
         <td>Implicit         </td>
         <td>BINARY         </td>
         <td><p>Designated version of a file in GDG</p>         </td>
      </tr>
      <tr>
         <td>Implicit         </td>
         <td>BINARY         </td>
         <td><p>Multi-volume disk file</p>         </td>
      </tr>
      <tr>
         <td>Implicit         </td>
         <td>BINARY         </td>
         <td><p>VSAM KSDS or ESDS file</p>         </td>
      </tr>
      <tr>
         <td><p>A</p>         </td>
         <td>BINARY         </td>
         <td><p>Print file with ASA jump codes (z/OS to z/OS)</p>         </td>
      </tr>
      <tr>
         <td><p>M</p>         </td>
         <td>BINARY         </td>
         <td><p>Print file with machine jump codes (z/OS to z/OS)</p>         </td>
      </tr>
      <tr>
         <td><p>S</p>         </td>
         <td>BINARY         </td>
         <td><p>Spanned variable format file (z/OS to z/OS)</p>         </td>
      </tr>
   </tbody>
</table>

HFS file characteristics

<table>
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">FTYPE         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">FCODE         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1">Type of sent file         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>B</p>         </td>
         <td>BINARY         </td>
         <td><p>Binary file (default)</p>         </td>
      </tr>
      <tr>
         <td><p>T</p>         </td>
         <td>EBCDIC         </td>
         <td><p>Text file</p>         </td>
      </tr>
      <tr>
         <td>J         </td>
         <td>EBCDIC         </td>
         <td><p>Stream text</p>
<p>Using stream text (J) allows a text type file to be sent that contains records that exceed 32 KB. As opposed to text type (FTYPE=T), stream text does not add an EOL sequence (LF or CRLF) to the received file.</p>
<p>When using stream text (FTYPE=J), the sender and the receiver must both have the FTYPE set to J. Setting only the sender or receiver to FTYPE=J results in unexpected content for the transferred file.</p>         </td>
      </tr>
   </tbody>
</table>

> **Note:**
>
> FTYPE values are OS specific. Refer to the Transfer CFT z/OS documentation for more information.

IBM i (OS400)

Native files

The following table lists the different types of files that can be used according to the type of data to transfer.

> **Note:**
>
> Bold values indicate a recommended combination. For example, FTYPE=D and FRECFM=V, are the recommended settings for PF-DTA files with variable data.

<table>
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1"><p>FTYPE</p>         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1"><p>FRECFM</p>         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1"><p>Supported files and data organizations (if applicable).</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>‘D’         </td>
         <td>‘F’         </td>
         <td><strong>PF-DTA with fixed data</strong>, PF-DTA with variable data, PF-SRC, SAVF         </td>
      </tr>
      <tr>
         <td>‘V’         </td>
         <td>PF-DTA with fixed data, <strong>PF-DTA with variable data</strong>, PF-SRC, SAVF         </td>
      </tr>
      <tr>
         <td>‘S’         </td>
         <td>‘F’         </td>
         <td><p>PF-DTA with fixed data, PF-DTA with variable data, <strong>PF-SRC</strong></p>         </td>
      </tr>
      <tr>
         <td>          </td>
         <td>‘V’         </td>
         <td>PF-DTA with fixed data, PF-DTA with variable data, PF-SRC         </td>
      </tr>
      <tr>
         <td>‘E’         </td>
         <td>‘F’         </td>
         <td>PF-DTA with fixed data, PF-DTA with variable data, <strong>PF-SRC</strong>         </td>
      </tr>
      <tr>
         <td>          </td>
         <td>‘V’         </td>
         <td>PF-DTA with fixed data, PF-DTA with variable data, PF-SRC         </td>
      </tr>
      <tr>
         <td>‘Z’         </td>
         <td>‘F’, ‘V’         </td>
         <td><strong>SAVF</strong>         </td>
      </tr>
   </tbody>
</table>

Default FTYPE or FRECFM value

The behavior of the values ‘’ and ‘ ’, for FTYPE and FRECFM respectively, are not detailed in the following table. These values correspond to `undefined`, meaning that the transfer in emission takes the value of both the file type and the member content..

<table>
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1"><p> </p>         </th>
<th style="text-align: center;" class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1"><p>Default FTYPE</p>         </th>
<th style="text-align: center;" class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1"><p>Default FRECFM</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>PF-DTA<br />
Member containing fixed data</p>         </td>
         <td>‘D’         </td>
         <td>‘F’         </td>
      </tr>
      <tr>
         <td><p>PF-DTA<br />
Member containing variable data</p>         </td>
         <td>‘D’         </td>
         <td>‘V’         </td>
      </tr>
      <tr>
         <td>PF-SRC         </td>
         <td>‘D’         </td>
         <td>‘F’         </td>
      </tr>
      <tr>
         <td>SAVF         </td>
         <td>‘Z’         </td>
         <td>‘F’         </td>
      </tr>
   </tbody>
</table>

IFS files

The following table lists the different types of files that can be used according to the type of data to transfer when using IFS.

<table>
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">FTYPE         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">FRECFM         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1">Type of file         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>‘S’         </td>
         <td>‘V’, ‘F’, ‘ ’         </td>
         <td>Text         </td>
      </tr>
      <tr>
         <td>‘D’ , ‘ ’         </td>
         <td>‘V’, ‘F’, ‘ ’         </td>
         <td>Text         </td>
      </tr>
      <tr>
         <td>‘E’         </td>
         <td>‘V’, ‘F’, ‘ ’         </td>
         <td>Text         </td>
      </tr>
      <tr>
         <td>‘Z’         </td>
         <td>‘V’, ‘F’, ‘ ’         </td>
         <td>Binary         </td>
      </tr>
      <tr>
         <td>‘J’         </td>
         <td>‘V’, ‘F’, ‘ ’         </td>
         <td><p>Stream text is an alternative way to transfer a text file. Every line of a file must end with an LF or CR/LF. However, during a transfer the CR/LF are changed to LFs. This enables a quicker reading, and a faster transfer.</p>
<p>When using stream text (FTYPE=J), the sender and the receiver must both have the FTYPE set to J. Setting only the sender or receiver to FTYPE=J results in unexpected content for the transferred file.</p>
<blockquote>
<p><strong>Note:</strong></p>
<p>This transfer mode is not available for native side transfers.</p>
</blockquote>         </td>
      </tr>
   </tbody>
</table>

> **Note:**
>
> FTYPE values are OS specific. Refer to the Transfer CFT IBM i Installation and Operations Guide for more information.

**HP NonStop**

For Unix files, use the values in the Unix [table](#UNIX_ftype) above. For native HP NonStop files, the values are as follows.

<table>
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">FTYPE         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">FCODE         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1">Type of sent file         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>‘ ‘ </p>         </td>
         <td><p>BINARY </p>         </td>
         <td>Binary         </td>
      </tr>
      <tr>
         <td><p>B </p>         </td>
         <td><p>BINARY </p>         </td>
         <td>Binary         </td>
      </tr>
      <tr>
         <td><p>V </p>         </td>
         <td><p>BINARY </p>         </td>
         <td>Binary file emulating locally a variable file format         </td>
      </tr>
      <tr>
         <td><p>T </p>         </td>
         <td><p>ASCII </p>         </td>
         <td>Text file with LF or CRLF as end-of-line separator         </td>
      </tr>
      <tr>
         <td><p>O </p>         </td>
         <td><p>ASCII </p>         </td>
         <td>Text file with CRLF as end-of-line separator         </td>
      </tr>
      <tr>
         <td><p>X </p>         </td>
         <td><p>ASCII </p>         </td>
         <td>Text file with LF as end-of-line separator         </td>
      </tr>
      <tr>
         <td>J         </td>
         <td>ASCII          </td>
         <td><p>Text file with LF or CRLF as end-of-line separator</p>
<p>FTYPE = J refers to stream text. The stream text type allows sending a text file that contains records that are larger than 32 KB. Unlike classical text types (T, O, X) the stream text type does not add an EOL sequence (LF or CRLF) at the end of the received file.</p>         </td>
      </tr>
      <tr>
         <td>E         </td>
         <td>ASCII         </td>
         <td>Edit native files.         </td>
      </tr>
      <tr>
         <td>N         </td>
         <td>BINARY          </td>
         <td>Non-edit native file (force the detection of native files rather than OSS ones).         </td>
      </tr>
   </tbody>
</table>

[Return to Command index](../../)
