{
    "title": "ftype",
    "linkTitle": "ftype",
    "weight": "1410"
}### <span id="ftype"></span>ftype

#### <span id="ftype_CFTRECV"></span>CFTRECV, CFTSEND

\[ FTYPE = { c } \]  OS-specific

The file type. Some FTYPE parameter values are OS specific. Refer to the Transfer CFT OS-specific documentation for more information.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">When using the SFTP protocol and FTYPE = T, O, X, J or F, the file is considered a text file and there is no specific treatment according to the value. This means that the <b>newline</b> character (EOL character) can be  the CRLF (x0Dx0A)  or LF (x0A) on Windows, or LF (x0A) on UNIX systems.         </td>
      </tr>
</table>

UNIX<span id="UNIX_ftype"></span>

<table border="1" cellspacing="0">
   <col/>
   <col/>
   <col/>
   <thead>
      <tr>
         <th>FTYPE</th>
         <th>FCODE</th>
         <th>Type of sent file </th>
      </tr>
   </thead>
      <tr>
         <td>
            <p>‘ ‘ </p>
         </td>
         <td>
            <p>BINARY </p>
         </td>
         <td>Binary         </td>
      </tr>
      <tr>
         <td>
            <p>B </p>
         </td>
         <td>
            <p>BINARY </p>
         </td>
         <td>Binary         </td>
      </tr>
      <tr>
         <td>
            <p>V </p>
         </td>
         <td>
            <p>BINARY </p>
         </td>
         <td>Binary file emulating locally a variable file format         </td>
      </tr>
      <tr>
         <td>
            <p>T </p>
         </td>
         <td>
            <p>ASCII </p>
         </td>
         <td>Text file with LF or CRLF as end-of-line separator         </td>
      </tr>
      <tr>
         <td>
            <p>O </p>
         </td>
         <td>
            <p>ASCII </p>
         </td>
         <td>Text file with CRLF as end-of-line separator         </td>
      </tr>
      <tr>
         <td>
            <p>X </p>
         </td>
         <td>
            <p>ASCII </p>
         </td>
         <td>Text file with LF as end-of-line separator         </td>
      </tr>
      <tr data-mc-conditions="">
         <td>J          </td>
         <td>ASCII          </td>
         <td>
            <p>Stream text</p>
            <p>Using stream text (J) allows a text type file to be sent that contains records that exceed 32 KB. As opposed to text type (FTYPE=T), stream text does not add an EOL sequence (LF or CRLF) to the received file.</p>
            <p>When using stream text (FTYPE=J), the sender and the receiver must both have the FTYPE set to J. Setting only the sender or receiver to FTYPE=J results in unexpected content for the transferred file.</p>
         </td>
      </tr>
</table>

See also, [UNIX &gt; Transferable files](../../../../cft_intro_install/unix_install_start_here/run_first_time_ux/aix_with_ibm_hacmp_intro/specific_configurations_intro/transferable_files_unix).

Windows

<table cellspacing="0">
   <col/>
   <col/>
   <col/>
   <thead>
      <tr>
         <th>
            <p>FTYPE </p>
</th>
         <th>
            <p>FCODE </p>
</th>
         <th>Type of sent file</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>' '         </td>
         <td>BINARY          </td>
         <td>Binary         </td>
      </tr>
      <tr>
         <td>
            <p>B </p>
         </td>
         <td>
            <p>BINARY </p>
         </td>
         <td>Binary         </td>
      </tr>
      <tr>
         <td>
            <p>V </p>
         </td>
         <td>
            <p>BINARY </p>
         </td>
         <td>Binary file emulating locally a variable file format         </td>
      </tr>
      <tr>
         <td>
            <p>T </p>
         </td>
         <td>
            <p>ASCII </p>
         </td>
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
      <tr data-mc-conditions="">
         <td>J         </td>
         <td>ASCII         </td>
         <td>
            <p>Stream text</p>
            <p>Using stream text (J) allows a text type file to be sent that contains records that exceed 32 KB. As opposed to text type (FTYPE=T), stream text does not add an EOL sequence (LF or CRLF) to the received file.</p>
            <p>When using stream text (FTYPE=J), the sender and the receiver must both have the FTYPE set to J. Setting only the sender or receiver to FTYPE=J results in unexpected content for the transferred file.</p>
         </td>
      </tr>
   </tbody>
</table>

\*Supports ASCII file handling (X'1A') (SEND/RECV FTYPE=F).

See also, [Windows &gt; Transferable files](../../../../cft_intro_install/windows_install_start_here/windows_install_start_here/specific_system_functions/transferable_files_win).

z/OS

Implicit indicates that the FTYPE is automatically detected by the OS.

<table cellspacing="0">
   <col/>
   <col/>
   <col/>
   <thead>
      <tr>
         <th>FTYPE</th>
         <th>FCODE</th>
         <th>Type of sent file </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>Implicit          </td>
         <td>BINARY         </td>
         <td>
            <p>Disk sequential files </p>
         </td>
      </tr>
      <tr>
         <td>Implicit          </td>
         <td>BINARY         </td>
         <td>
            <p>Members of PDS files (1 transfer per member) </p>
         </td>
      </tr>
      <tr>
         <td>Implicit          </td>
         <td>BINARY         </td>
         <td>
            <p>Designated version of a file in GDG </p>
         </td>
      </tr>
      <tr>
         <td>Implicit          </td>
         <td>BINARY         </td>
         <td>
            <p>Multi-volume disk file </p>
         </td>
      </tr>
      <tr>
         <td>Implicit          </td>
         <td>BINARY         </td>
         <td>
            <p>VSAM KSDS or ESDS file </p>
         </td>
      </tr>
      <tr>
         <td>
            <p>A </p>
         </td>
         <td>BINARY         </td>
         <td>
            <p>Print file with ASA jump codes (z/OS to z/OS) </p>
         </td>
      </tr>
      <tr>
         <td>
            <p>M </p>
         </td>
         <td>BINARY         </td>
         <td>
            <p>Print file with machine jump codes (z/OS to z/OS) </p>
         </td>
      </tr>
      <tr>
         <td>
            <p>S </p>
         </td>
         <td>BINARY         </td>
         <td>
            <p>Spanned variable format file (z/OS to z/OS) </p>
         </td>
      </tr>
   </tbody>
</table>

HFS file characteristics

<table cellspacing="0">
   <col/>
   <col/>
   <col/>
   <thead>
      <tr>
         <th>FTYPE</th>
         <th>FCODE</th>
         <th>Type of sent file </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>
            <p>B</p>
         </td>
         <td>BINARY         </td>
         <td>
            <p>Binary file (default)</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>T</p>
         </td>
         <td>EBCDIC         </td>
         <td>
            <p>Text file</p>
         </td>
      </tr>
      <tr>
         <td>J         </td>
         <td>EBCDIC          </td>
         <td>
            <p>Stream text</p>
            <p>Using stream text (J) allows a text type file to be sent that contains records that exceed 32 KB. As opposed to text type (FTYPE=T), stream text does not add an EOL sequence (LF or CRLF) to the received file.</p>
            <p>When using stream text (FTYPE=J), the sender and the receiver must both have the FTYPE set to J. Setting only the sender or receiver to FTYPE=J results in unexpected content for the transferred file.</p>
         </td>
      </tr>
   </tbody>
</table>

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">FTYPE values are OS specific. Refer to the Transfer CFT z/OS documentation for more information.         </td>
      </tr>
</table>

IBM i (OS400)

Native files

The following table lists the different types of files that can be used according to the type of data to transfer.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">Bold  values indicate a recommended combination. For example, <b>FTYPE=D</b> and <b>FRECFM=V</b>, are the recommended settings for PF-DTA files with variable data.         </td>
      </tr>
</table>

<table cellspacing="0">
   <col/>
   <col/>
   <col/>
   <thead>
      <tr>
         <th>
            <p>FTYPE </p>
</th>
         <th>
            <p>FRECFM</p>
</th>
         <th>
            <p>Supported files and data organizations (if applicable).</p>
</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td rowspan="2">‘D’         </td>
         <td>‘F’         </td>
         <td><b>PF-DTA with fixed data</b>, PF-DTA with variable data, PF-SRC, SAVF         </td>
      </tr>
      <tr>
         <td>‘V’         </td>
         <td>PF-DTA with fixed data, <b>PF-DTA with variable data</b>, PF-SRC, SAVF         </td>
      </tr>
      <tr>
         <td>‘S’         </td>
         <td>‘F’         </td>
         <td>
            <p> PF-DTA with fixed data, PF-DTA with variable data, <b>PF-SRC</b></p>
         </td>
      </tr>
      <tr>
         <td>          </td>
         <td>‘V’         </td>
         <td>PF-DTA with fixed data, PF-DTA with variable data, PF-SRC         </td>
      </tr>
      <tr>
         <td>‘E’         </td>
         <td>‘F’         </td>
         <td>	PF-DTA with fixed data, PF-DTA with variable data, <b>PF-SRC</b>         </td>
      </tr>
      <tr>
         <td>          </td>
         <td>‘V’         </td>
         <td>PF-DTA with fixed data, PF-DTA with variable data, PF-SRC         </td>
      </tr>
      <tr>
         <td> ‘Z’         </td>
         <td>‘F’, ‘V’         </td>
         <td><b>SAVF</b>
         </td>
      </tr>
   </tbody>
</table>

Default FTYPE or FRECFM value

The behavior of the values ‘’ and ‘ ’, for FTYPE and FRECFM respectively, are not detailed in the following table. These values correspond to undefined, meaning that the transfer in emission takes the value of both the file type and the member content..

<table cellspacing="0">
   <col/>
   <col/>
   <col/>
   <thead>
      <tr>
         <th>
            <p> </p>
</th>
         <th>
            <p>Default FTYPE </p>
</th>
         <th>
            <p>Default FRECFM</p>
</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>
            <p>PF-DTA<br/>Member containing fixed data</p>
         </td>
         <td>‘D’         </td>
         <td>‘F’         </td>
      </tr>
      <tr>
         <td>
            <p> PF-DTA<br/>Member containing variable data</p>
         </td>
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
         <td> ‘Z’         </td>
         <td>‘F’         </td>
      </tr>
   </tbody>
</table>

IFS files

The following table lists the different types of files that can be used according to the type of data to transfer when using IFS.

<table cellspacing="0">
   <col/>
   <col/>
   <col/>
   <thead>
      <tr>
         <th>FTYPE</th>
         <th>FRECFM </th>
         <th>Type of file</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>             ‘S’	         </td>
         <td>‘V’, ‘F’, ‘ ’	         </td>
         <td>Text           </td>
      </tr>
      <tr>
         <td>            ‘D’ , ‘ ’	         </td>
         <td>‘V’, ‘F’,  ‘ ’	         </td>
         <td>Text          </td>
      </tr>
      <tr>
         <td>             ‘E’	         </td>
         <td>‘V’, ‘F’,  ‘ ’	         </td>
         <td>Text          </td>
      </tr>
      <tr>
         <td>             ‘Z’	         </td>
         <td>‘V’, ‘F’, ‘ ’	         </td>
         <td>Binary         </td>
      </tr>
      <tr>
         <td>             ‘J’         </td>
         <td>	‘V’, ‘F’,  ‘ ’	         </td>
         <td>
            <p>Stream text  is an alternative way to transfer a text file. Every line of a file must end with an LF or CR/LF. However, during a transfer the CR/LF are changed to LFs. This enables a quicker reading, and a faster transfer.
</p>
            <p>When using stream text (FTYPE=J), the sender and the receiver must both have the FTYPE set to J. Setting only the sender or receiver to FTYPE=J results in unexpected content for the transferred file.
</p>
            <p>&amp;&amp;&amp; ïïï ùùù</p>
         </td>
      </tr>
   </tbody>
</table>

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">This transfer mode is not available for native side transfers.
         </td>
      </tr>
</table>

**HP NonStop**

For Unix files, use the values in the Unix [table](#unix_ftype) above. For native HP NonStop files, the values are as follows.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">FTYPE values are OS specific. Refer to the <a href="https://docs.axway.com/bundle/TransferCFT_38_InstallationGuide_os400_en_PDF/resource/TransferCFT_InstallationGuide_os400_en.pdf">Transfer CFT IBM i Installation and Operations Guide</a> for more information.         </td>
      </tr>
</table>

[Return to Command index](../../)