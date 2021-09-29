{
    "title": "CFTF messages",
    "linkTitle": "CFTF messages",
    "weight": "320"
}# Transfer CFT messages: CFTF

This topic lists the CFTFxx (CFT xnnx) messages and provides the type, a description, consequence, and corrective actions when applicable.

**Message format**

Earlier versions of Transfer CFT used a different message format than version 3.1.3 and higher. This document displays both formats when applicable and available, otherwise only the v23 is used. Using the CFTLOG Format = V24 setting, the log displays as shown:

CFTXXX: fixed text message &lt;variables>

**Example**

CFTLOG FORMAT=\[V23,V24\]

For V23: CFTT57I PART=&part IDF=&idf IDT=&idt &str transfer started

For V24: `CFTT57I &str transfer started   <IDTU=&idtu PART=&part IDF=&idf IDT=&idt>`

<table data-border="1" data-cellspacing="0">
<tbody>
<tr class="odd" data-valign="top">
<td width="20%"><p>V23 format</p>
<p>V24 format</p>
<p>Error</p></td>
<td width="80%"><p><span id="CFTF01E"></span>CFTF01E PART=&amp;part IDF=&amp;idf IDT=&amp;idt local
file [&amp;fname] creation error &amp;diagi</p>
<p>CFTF01E local file [&amp;fname] creation error &amp;scs &lt;IDTU=&amp;idtu PART=&amp;part IDF=&amp;idf IDT=&amp;idt</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="20%"><p>Explanation</p></td>
<td width="80%"><p>During a transfer request a local error was detected when creating
a file.</p></td>
</tr>
<tr class="odd" data-valign="top">
<td width="20%"><p>Consequence</p></td>
<td width="80%"><p>The transfer is not executed. The corresponding entry in the
catalog is set to the K state if RKERROR=KEEP and the catalog entry is
deleted by the <span>Transfer CFT</span> if RKERROR=DELETE.</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="21.734%"><p>Action</p></td>
<td width="78.266%"><p>Analyze the file access system code, correct the error and try
again.</p></td>
</tr>
</tbody>
</table>

 

<table data-border="1" data-cellspacing="0">
<tbody>
<tr class="odd" data-valign="top">
<td width="20%"><p>V23 format</p>
<p>V24 format</p>
<p>Error</p></td>
<td width="80%"><p><span id="CFTF02E"></span>CFTF02E PART=&amp;part IDF=&amp;idf IDT=&amp;idt local
file selection error &amp;scs</p>
<p>CFTF02E local file selection error &amp;scs &lt;IDTU=&amp;idtu PART=&amp;part IDF=&amp;idf IDT=&amp;idt</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="20%"><p>Explanation</p></td>
<td width="80%"><p>During a transfer request a local error was detected when selecting
a file.</p></td>
</tr>
<tr class="odd" data-valign="top">
<td width="20%"><p>Consequence</p></td>
<td width="80%"><p>The transfer is not executed. The corresponding catalog entry
is put on HOLD.</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="21.734%"><p>Action</p></td>
<td width="78.266%"><p>Analyze the file access system code, correct the error and try
again.</p></td>
</tr>
</tbody>
</table>

 

<table data-border="1" data-cellspacing="0">
<tbody>
<tr class="odd" data-valign="top">
<td width="20%"><p>V23 format</p>
<p>V24 format</p>
<p>Warning</p></td>
<td width="80%"><p>CFTF02W PART=&amp;part IDF=&amp;idf IDT=&amp;idt local file selection error (file not found ignored) &amp;scs</p>
<p>CFTF02W local file selection error (file not found ignored) &amp;scs &lt;IDTU=&amp;idtu PART=&amp;part IDF=&amp;idf IDT=&amp;idt</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="20%"><p>Explanation</p></td>
<td width="80%">During a transfer request, a local error was detected when selecting a file.</td>
</tr>
<tr class="odd" data-valign="top">
<td width="20%"><p>Consequence</p></td>
<td width="80%">When you set <span>filenotfound</span> to <span>ignore</span> in the transfer request, the transfer is executed, the file is ignored, and the corresponding catalog entry is terminated (completed).</td>
</tr>
<tr class="even" data-valign="top">
<td width="21.734%"><p>Action</p></td>
<td width="78.266%">You can ignore the message.</td>
</tr>
</tbody>
</table>

 

<table data-border="1" data-cellspacing="0">
<tbody>
<tr class="odd" data-valign="top">
<td width="20%"><p>V23 format</p>
<p>V24 format</p>
<p>Error</p></td>
<td width="80%"><p><span id="CFTF03E"></span>CFTF03E PART=&amp;part IDF=&amp;idf IDT=&amp;idt local
file deselect error &amp;scs</p>
<p>CFTF03E local file deselect error &amp;scs &lt;IDTU=&amp;idtu PART=&amp;part IDF=&amp;idf IDT=&amp;idt</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="20%"><p>Explanation</p></td>
<td width="80%"><p>During a transfer a local error was detected when releasing
the transferred file.</p></td>
</tr>
<tr class="odd" data-valign="top">
<td width="20%"><p>Consequence</p></td>
<td width="80%"><p>The transfer is interrupted. The corresponding catalog entry
is put on HOLD.</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="21.734%"><p>Action</p></td>
<td width="78.266%"><p>Analyze the file access system code, correct the error and try
again.</p></td>
</tr>
</tbody>
</table>

 

<table data-border="1" data-cellspacing="0">
<tbody>
<tr class="odd" data-valign="top">
<td width="20%"><p>V23 format</p>
<p>V24 format</p>
<p>Error</p></td>
<td width="80%"><p><span id="CFTF04E"></span>CFTF04E PART=&amp;part IDF=&amp;idf IDT=&amp;idt local
file open error &amp;scs</p>
<p>CFTF04E local file open error &amp;scs &lt;IDTU=&amp;idtu PART=&amp;part IDF=&amp;idf IDT=&amp;idt</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="20%"><p>Explanation</p></td>
<td width="80%"><p>During a transfer request a local error was detected when opening
a file.</p></td>
</tr>
<tr class="odd" data-valign="top">
<td width="20%"><p>Consequence</p></td>
<td width="80%"><p>The transfer is not executed. The corresponding catalog entry
is put on HOLD.</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="21.734%"><p>Action</p></td>
<td width="78.266%"><p>Analyze the file access system code, correct the error and try
again.</p></td>
</tr>
</tbody>
</table>

 

<table data-border="1" data-cellspacing="0">
<tbody>
<tr class="odd" data-valign="top">
<td width="20%"><p>V23 format</p>
<p>V24 format</p>
<p>Error</p></td>
<td width="80%"><p><span id="CFTF05E"></span>CFTF05E PART=&amp;part IDF=&amp;idf IDT=&amp;idt local
file close error &amp;scs</p>
<p>CFTF05E local file deselect error &amp;scs &lt;IDTU=&amp;idtu PART=&amp;part IDF=&amp;idf IDT=&amp;idt</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="20%"><p>Explanation</p></td>
<td width="80%"><p>During a transfer a local error was detected when closing the
file.</p></td>
</tr>
<tr class="odd" data-valign="top">
<td width="20%"><p>Consequence</p></td>
<td width="80%"><p>The transfer is interrupted. The corresponding catalog entry
is put on HOLD.</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="21.734%"><p>Action</p></td>
<td width="78.266%"><p>Analyze the file access system code, correct the error and try
again.</p></td>
</tr>
</tbody>
</table>

 

<table data-border="1" data-cellspacing="0">
<tbody>
<tr class="odd" data-valign="top">
<td width="20%"><p>V23 format</p>
<p>V24 format</p>
<p>Error</p></td>
<td width="80%"><p><span id="CFTF06E"></span>CFTF06E PART=&amp;part IDF=&amp;idf IDT=&amp;idt local
file note error &amp;scs</p>
<p>CFTF06E local file note error &amp;scs &lt;IDTU=&amp;idtu PART=&amp;part IDF=&amp;idf IDT=&amp;idt</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="20%"><p>Explanation</p></td>
<td width="80%"><p>During a transfer a local error was detected when recording
the current position in the file.</p></td>
</tr>
<tr class="odd" data-valign="top">
<td width="20%"><p>Consequence</p></td>
<td width="80%"><p>The transfer is interrupted and the corresponding catalog entry
is put on HOLD.</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="21.734%"><p>Action</p></td>
<td width="78.266%"><p>Analyze the file access system code, correct the error and try
again.</p></td>
</tr>
</tbody>
</table>

 

<table data-border="1" data-cellspacing="0">
<tbody>
<tr class="odd" data-valign="top">
<td width="20%"><p>V23 format</p>
<p>V24 format</p>
<p>Error</p></td>
<td width="80%"><p><span id="CFTF07E"></span>CFTF07E PART=&amp;part IDF=&amp;idf IDT=&amp;idt local
file point error &amp;scs</p>
<p>CFTF07E local file point error &amp;scs &lt;IDTU=&amp;idtu PART=&amp;part IDF=&amp;idf IDT=&amp;idt</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="20%"><p>Explanation</p></td>
<td width="80%"><p>During a transfer restart a local error was detected when repositioning
the pointer in the file.</p></td>
</tr>
<tr class="odd" data-valign="top">
<td width="20%"><p>Consequence</p></td>
<td width="80%"><p>The transfer is not restarted and the corresponding catalog
entry remains on HOLD.</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="21.734%"><p>Action</p></td>
<td width="78.266%"><p>Analyze the file access system code, correct the error and restart
the transfer.</p></td>
</tr>
</tbody>
</table>

 

<table data-border="1" data-cellspacing="0">
<tbody>
<tr class="odd" data-valign="top">
<td width="20%"><p>V23 format</p>
<p>V24 format</p>
<p>Error</p></td>
<td width="80%"><p><span id="CFTF08E"></span>CFTF08E PART=&amp;part IDF=&amp;idf IDT=&amp;idt local
file read error &amp;scs</p>
<p>CFTF08E local file read error &amp;scs &lt;IDTU=&amp;idtu PART=&amp;part IDF=&amp;idf IDT=&amp;idt</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="20%"><p>Explanation</p></td>
<td width="80%"><p>During a transfer a local error was detected when reading the
file.</p></td>
</tr>
<tr class="odd" data-valign="top">
<td width="20%"><p>Consequence</p></td>
<td width="80%"><p>The transfer is interrupted. The corresponding catalog entry
is put on HOLD.</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="21.734%"><p>Action</p></td>
<td width="78.266%"><p>Analyze the file access system code, correct the error and try
again.</p></td>
</tr>
</tbody>
</table>

 

<table data-border="1" data-cellspacing="0">
<tbody>
<tr class="odd" data-valign="top">
<td width="20%"><p>V23 format</p>
<p>V24 format</p>
<p>Error</p></td>
<td width="80%"><p><span id="CFTF09E"></span>CFTF09E PART=&amp;part IDF=&amp;idf IDT=&amp;idt local
file write error &amp;scs</p>
<p>CFTF09E local file write error &amp;scs &lt;IDTU=&amp;idtu PART=&amp;part IDF=&amp;idf IDT=&amp;idt</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="20%"><p>Explanation</p></td>
<td width="80%"><p>During a transfer a local error was detected when writing the
file.</p></td>
</tr>
<tr class="odd" data-valign="top">
<td width="20%"><p>Consequence</p></td>
<td width="80%"><p>The transfer is interrupted. The corresponding catalog entry
is put on HOLD.</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="21.734%"><p>Action</p></td>
<td width="78.266%"><p>Analyze the file access system code, correct the error and try
again.</p></td>
</tr>
</tbody>
</table>

 

<table data-border="1" data-cellspacing="0">
<tbody>
<tr class="odd" data-valign="top">
<td width="20%"><p>V23 format</p>
<p>V24 format</p>
<p>Error</p></td>
<td width="80%"><p><span id="CFTF13E"></span>CFTF13E PART=&amp;part IDF=&amp;idf IDT=&amp;idt remote
file deselect error &amp;diagp</p>
<p>CFTF13E remote file deselect error &amp;scs &lt;IDTU=&amp;idtu PART=&amp;part IDF=&amp;idf IDT=&amp;idt</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="20%"><p>Explanation</p></td>
<td width="80%"><p>The file deselect operation was refused by the partner.</p></td>
</tr>
<tr class="odd" data-valign="top">
<td width="20%"><p>Consequence</p></td>
<td width="80%"><p>The transfer is not executed. The corresponding catalog entry
is put on HOLD.</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="21.734%"><p>Action</p></td>
<td width="78.266%"><p>Correct the error and try again.</p></td>
</tr>
</tbody>
</table>

 

<table data-border="1" data-cellspacing="0">
<tbody>
<tr class="odd" data-valign="top">
<td width="20%"><p>V23 format</p>
<p>V24 format</p>
<p>Error</p></td>
<td width="80%"><p><span id="CFTF21E"></span>CFTF21E PART=&amp;part IDF=&amp;idf IDT=&amp;idt storage
allocation error &amp;scs</p>
<p>CFTF21E storage allocation error &amp;scs &lt;IDTU=&amp;idtu PART=&amp;part IDF=&amp;idf IDT=&amp;idt</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="20%"><p>Explanation</p></td>
<td width="80%"><p>During a transfer a local error was detected when allocating
memory.</p></td>
</tr>
<tr class="odd" data-valign="top">
<td width="20%"><p>Consequence</p></td>
<td width="80%"><p>The transfer is interrupted. The corresponding catalog entry
is put on HOLD.</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="21.734%"><p>Action</p></td>
<td width="78.266%"><p>Analyze the memory access system code, correct the error and
try again.</p></td>
</tr>
</tbody>
</table>

 

<table data-border="1" data-cellspacing="0">
<tbody>
<tr class="odd" data-valign="top">
<td width="20%"><p>V23 format</p>
<p>V24 format</p>
<p>Error</p></td>
<td width="80%"><p><span id="CFTF22E"></span>CFTF22E PART=&amp;part IDF=&amp;idf IDT=&amp;idt duplicate
file &amp;diagp</p>
<p>CFTF22E duplicate file &amp;scs &lt;IDTU=&amp;idtu PART=&amp;part IDF=&amp;idf IDT=&amp;idt</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="20%"><p>Explanation</p></td>
<td width="80%"><p>A transfer requests the creation of a file but the file already
exists - the FDISP parameter prevents the existing file from being erased.</p></td>
</tr>
<tr class="odd" data-valign="top">
<td width="20%"><p>Consequence</p></td>
<td width="80%"><p>The transfer is not executed and the corresponding catalog entry
is set to the KEEP status.</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="21.734%"><p>Action</p></td>
<td width="78.266%"><p>Delete the existing file, revise the parameter settings, or
receive the data in another file.</p></td>
</tr>
</tbody>
</table>

 

<table data-border="1" data-cellspacing="0">
<tbody>
<tr class="odd" data-valign="top">
<td><p>V23 format</p>
<p>V24 format</p>
<p>Error</p></td>
<td width="80%"><p><span id="CFTF23E"></span>CFTF23E PART=&amp;part IDF=&amp;idf IDT=&amp;idt file
space allocation exhausted &amp;scs</p>
<p>CFTF23E file space allocation exhausted &amp;scs &lt;IDTU=&amp;idtu PART=&amp;part IDF=&amp;idf IDT=&amp;idt</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>Explanation</p></td>
<td width="80%"><p>During a transfer a local error was detected when writing the
file (insufficient space reserved for the file).</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>Consequence</p></td>
<td width="80%"><p>The transfer is interrupted and the corresponding catalog entry
is set to the KEEP status.</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>Action</p></td>
<td width="78.266%"><p>Allocate more available space for this file.</p></td>
</tr>
</tbody>
</table>

 

<table data-border="1" data-cellspacing="0">
<tbody>
<tr class="odd" data-valign="top">
<td><p>V23 format</p>
<p>V24 format</p>
<p>Error</p></td>
<td width="80%"><p><span id="CFTF24E"></span>CFTF24E PART=&amp;part IDF=&amp;idf IDT=&amp;idt duplicate
working file</p>
<p>CFTF24E duplicate working file &lt;IDTU=&amp;idtu PART=&amp;part IDF=&amp;idf IDT=&amp;idt&gt;</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>Explanation</p></td>
<td width="80%"><p>During a transfer using an intermediate file (CFTRECV FNAME
=) an error was detected: the intermediate file already exists and consequently
cannot be created.</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>Consequence</p></td>
<td width="80%"><p>The transfer is interrupted.</p></td>
</tr>
</tbody>
</table>

 

<table data-border="1" data-cellspacing="0">
<tbody>
<tr class="odd" data-valign="top">
<td><p>V23 format</p>
<p>V24 format</p>
<p>Error</p></td>
<td width="80%"><p><span id="CFTF25E"></span>CFTF25E PART=&amp;part IDF=&amp;idf IDT=&amp;idt working
file rename error &amp;scs</p>
<p>CFTF25E working file rename error &amp;scs &lt;IDTU=&amp;idtu PART=&amp;part IDF=&amp;idf IDT=&amp;idt &gt;</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>Explanation</p></td>
<td width="80%"><p>At the end of a transfer using an intermediate file (CFTRECV
WFNAME =) an error was detected: the intermediate file could not be renamed.</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>Consequence</p></td>
<td width="80%"><p>The file
is correctly transferred but an error is reported to the <span>Transfer CFT</span>
user.</p></td>
</tr>
</tbody>
</table>

 

<table data-border="1" data-cellspacing="0">
<tbody>
<tr class="odd" data-valign="top">
<td><p>V23 format</p>
<p>V24 format</p>
<p>Error</p></td>
<td width="80%"><p><span id="CFTF26E"></span>CFTF26E PART=&amp;part IDF=&amp;idf IDT=&amp;idt will
be unable to rename working file</p>
<p>CFTF26E will be unable to rename working file &lt;IDTU=&amp;idtu PART=&amp;part IDF=&amp;idf IDT=&amp;idt&gt;</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>Explanation</p></td>
<td width="80%"><p>During a transfer using an intermediate file (CFTRECV FNAME
= ) an error was detected: the intermediate file could not be renamed
at the end of the transfer (as the real file already exists).</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>Consequence</p></td>
<td width="80%"><p>The transfer is interrupted.</p></td>
</tr>
</tbody>
</table>

 

<table data-border="1" data-cellspacing="0">
<tbody>
<tr class="odd" data-valign="top">
<td><p>V23 format</p>
<p>V24 format</p>
<p>Error</p></td>
<td width="80%"><p><span id="CFTF27E"></span>CFTF27E PART=part IDF=idf
IDT=idt local /virtual file attribute mismatch</p>
<p>CFTF27E local/virtual file attribute mismatch &lt;IDTU=&amp;idtu PART=&amp;part IDF=&amp;idf IDT=&amp;idt&gt;</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>Explanation</p></td>
<td width="80%"><p>There are invalid file attributes in CFTRECV command. The
local file attributes, FLRECL or FRECFM, do not match with virtual file
attributes.</p>
<p>(This is only applicable if FCHECK parameter is set to
YES in the CFTRECV command.)</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>Consequence</p></td>
<td width="80%"><p>The transfer is cancelled with DIAGP 139. DIAGP = ERR LRECL
or ERR RECFM.</p></td>
</tr>
</tbody>
</table>

 

<table data-border="1" data-cellspacing="0">
<tbody>
<tr class="odd" data-valign="top">
<td><p>V23 format</p>
<p>V24 format</p>
<p>V23 format</p>
<p>V24 format</p>
<p>Warning</p></td>
<td width="80%"><p><span id="CFTF30W"></span>CFTF30W PART=&amp;part IDF=&amp;idf IDT=&amp;idt &amp;diagc</p>
<p>CFTF30W +PART=&amp;part IDF=&amp;idf IDT=&amp;idt &amp;str</p>
<p>CFTF30W &amp;diagc &lt;IDTU=&amp;idtu PART=&amp;part IDF=&amp;idf IDT=&amp;idt &gt;</p>
<p>CFTF30W+&amp;str &lt;IDTU=&amp;idtu PART=&amp;part IDF=&amp;idf IDT=&amp;idt &gt;</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>Explanation</p></td>
<td width="80%"><p>After an error, an additional message or two containing
the DIAGC zones are displayed:</p>
<ul>
<li>CFTF02E
PART=&amp;part IDF=&amp;idf
 IDT=&amp;idt
local file selection error xxxx</li>
<li>CFTF30W
PART=&amp;part IDF=&amp;idf
 IDT=&amp;idt
&amp;diagc</li>
<li>CFTF30W+U=&lt;user&gt; F=&lt;file&gt;
PART=&amp;part IDF=&amp;idf
 IDT=&amp;idt</li>
</ul>
<p>Where &amp;diagc could be:</p>
<ul>
<li><p>SFM_ALLOC: file not found</p></li>
<li>SFM_ALLOC: CFTSU socket: connection refused (this occurs when USERCTRL is set to yes, but the user does not have read-file privileges - <em>Unix only</em>)</li>
<li>HTTP 403: when using AWS the DNS connection was refused</li>
</ul></td>
</tr>
<tr class="odd" data-valign="top">
<td>Action</td>
<td width="80%"><p>If the connection was refused for AWS, check that the server DNS is correctly configured. See the <a href="../../../app_integration_intro/amazon_s3">Amazon 3 (ASW) troubleshooting</a> section.</p></td>
</tr>
</tbody>
</table>

 

<table data-border="1" data-cellspacing="0">
<tbody>
<tr class="odd" data-valign="top">
<td width="20%"><p>V23 format</p>
<p>V24 format</p>
<p>Information</p></td>
<td width="80%"><p>CFTF31I PART=&amp;part IDF=&amp;idf IDT=&amp;idt EXIT=&amp;id
&amp;user1 changed to &amp;user2</p>
<p><span id="CFTF31I"></span>CFTF31I PART=&amp;idf IDF=&amp;idf IDT=&amp;idt EXIT=&amp;id
&amp;user1  User
id changed to &amp;user2 the user id is modified by the exit</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="20%"><p>Explanation</p></td>
<td width="80%"><p>Possibility for a file type exit to change the transfer
owner (userid) in the Before File Allocation
phase for a new transfer. This possibility is offered regardless of the
transfer direction.</p>
<ul>
<li>When sending, to open the file for the 'userid' account
furnished by the exit.</li>
<li>When receiving, to create the file for the 'userid' provided
by the exit.</li>
</ul></td>
</tr>
</tbody>
</table>

 

<table data-border="1" data-cellspacing="0">
<tbody>
<tr class="odd" data-valign="top">
<td width="20%"><p>V23 format</p>
<p>V24 format</p>
<p>Error</p></td>
<td width="80%"><p><span id="CFTF32E"></span>CFTF32E PART=&amp;part IDF=&amp;idf IDT=&amp;idt _ Maximum number of rename retries reached</p>
<p>CFTF32E Maximum number of rename retries reached &lt;IDTU=&amp;idtu PART=&amp;part IDF=&amp;idf IDT=&amp;idt&gt;</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="20%"><p>Explanation</p></td>
<td width="80%"><p>Maximum number of rename retries reached &lt;IDTU=&amp;idtu PART=&amp;part IDF=&amp;idf IDT=&amp;idt&gt;.</p></td>
</tr>
<tr class="odd" data-valign="top">
<td width="20%">Action</td>
<td width="80%"><p>Check why the filename exists (when it should not).</p>
<p>Correct filename issue, for example manually rename the filename in question.</p>
<p>Restart the transfer.</p>
<p>See also <a href="../../../app_integration_intro/spoolout">Post-transfer file renaming</a>.</p></td>
</tr>
</tbody>
</table>

 

<table data-border="1" data-cellspacing="0">
<tbody>
<tr class="odd" data-valign="top">
<td width="20%"><p>V23 format</p>
<p>V24 format</p>
<p>Information</p></td>
<td width="80%"><p><span id="CFTF33I"></span>CFTF33I PART=&amp;part IDF=&amp;idf IDT=&amp;idt _ Rename to FNAME=&amp;FNAME done</p>
<p>CFTF33I Rename to FNAME=&amp;fname done &lt;IDTU=&amp;idtu PART=&amp;part IDF=&amp;idf IDT=&amp;idt&gt;</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="20%"><p>Explanation</p></td>
<td width="80%">The file was renamed, when using RETRYRENAME, and any post-processing or exits are executed.</td>
</tr>
</tbody>
</table>

 

<table data-border="1" data-cellspacing="0">
<tbody>
<tr class="odd" data-valign="top">
<td width="20%"><p>V23 format</p>
<p>V24 format</p>
<p>Error</p></td>
<td width="80%"><p><span id="CFTF34E"></span>CFTF34E PART=&amp;part IDF=&amp;idf IDT=&amp;idt _ WFNAME=&amp;wfname not found</p>
<p>CFTF34E WFNAME=&amp;fname not found &lt;IDTU=&amp;idtu PART=&amp;part IDF=&amp;idf IDT=&amp;idt&gt;</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="20%"><p>Explanation</p></td>
<td width="80%">The rename operation failed because the file referenced by &amp;wfname cannot be accessed (or does not exist).</td>
</tr>
<tr class="odd" data-valign="top">
<td width="20%">Action</td>
<td width="80%"><p>Check that the wfname exists on the receiver side.</p>
<ul>
<li>If not, recreate the transfer on the sender side.</li>
<li>If so, check that the &amp;userid can access the file, fix the user rights if necessary, and restart the transfer on the receiver side.</li>
</ul></td>
</tr>
</tbody>
</table>

 

<table data-border="1" data-cellspacing="0">
<tbody>
<tr class="odd" data-valign="top">
<td width="20%"><p>V23 format</p>
<p>V24 format</p>
<p>Information</p></td>
<td width="80%"><p><span id="CFTF35W"></span>CFTF35W PART=&amp;part IDF=&amp;idf IDT=&amp;idt Rename to FNAME=&amp;fname failed, will be retried at &amp;datetime</p>
<p>CFTF35W Rename to FNAME=&amp;fname failed, will be retried at &amp;datetime &lt;IDTU=&amp;idtu PART=&amp;part IDF=&amp;idf IDT=&amp;idt&gt;</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="20%"><p>Explanation</p></td>
<td width="80%">Could not rename the temporary file to &amp;fname because the file referenced by &amp;fname already exists.
Transfer CFT will try again at &amp;datetime.</td>
</tr>
</tbody>
</table>

 

<table data-border="1" data-cellspacing="0">
<tbody>
<tr class="odd" data-valign="top">
<td width="20%"><p>V23 format</p>
<p>V24 format</p>
Error</td>
<td width="80%"><p><span id="CFTF38E"></span>CFTF38E The file or directory &amp;fname can't be renamed into &amp;newfname for reason code &amp;reason</p>
<p>CFTF38E The file or directory &amp;fname can't be renamed into &amp;newfname for reason code &amp;reason</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="20%">Explanation</td>
<td width="80%">Cannot rename the file or directory.</td>
</tr>
<tr class="odd" data-valign="top">
<td width="20%">Action</td>
<td width="80%">Check the reason code and make the appropriate action if possible.</td>
</tr>
</tbody>
</table>

 

<table data-border="1" data-cellspacing="0">
<tbody>
<tr class="odd" data-valign="top">
<td width="20%"><p>V23 format</p>
<p>V24 format</p>
Error</td>
<td width="80%"><p><span id="CFTF39E"></span>CFTF39E Missing NFNAME when executing RECV &lt;IDTU=&amp;idtu PART=&amp;part IDF=&amp;idf IDT=&amp;idt&gt;</p>
<p>CFTF39E Missing NFNAME when executing RECV &lt;IDTU=&amp;idtu PART=&amp;part IDF=&amp;idf IDT=&amp;idt&gt;</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="20%">Explanation</td>
<td width="80%">The NFNAME parameter was empty or missing when executing a RECV command.</td>
</tr>
<tr class="odd" data-valign="top">
<td width="20%">Action</td>
<td width="80%">Add the NFNAME parameter in your RECV command.</td>
</tr>
</tbody>
</table>

 

<table data-border="1" data-cellspacing="0">
<tbody>
<tr class="odd" data-valign="top">
<td><p>V23 format</p>
<p>V24 format</p>
<p>Information</p></td>
<td width="80%"><p><span id="CFTF40I"></span>CFTF40I The file &amp;fname has been removed</p>
<p>CFTF40I The file &amp;fname has been removed</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>Explanation</p></td>
<td width="80%"><p>A file was removed per an SFTP client request.</p></td>
</tr>
</tbody>
</table>

<table data-border="1" data-cellspacing="0">
<tbody>
<tr class="odd" data-valign="top">
<td><p>V23 format</p>
<p>V24 format</p>
<p>Error</p></td>
<td width="80%"><p><span id="CFTF41E"></span>CFTF41E The file &amp;fname can't be removed for reason code &amp;reason</p>
<p>CFTF41E The file &amp;fname can't be removed for reason code &amp;reason</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>Explanation</p></td>
<td width="80%"><p>Could not remove the file.</p></td>
</tr>
<tr class="odd" data-valign="top">
<td>Action</td>
<td width="80%"><p>Check the reason to code and take the appropriate action if possible.</p></td>
</tr>
</tbody>
</table>

 

<table data-border="1" data-cellspacing="0">
<tbody>
<tr class="odd" data-valign="top">
<td><p>V23 format</p>
<p>V24 format</p>
<p>Information</p></td>
<td width="80%"><p><span id="CFTF42I"></span>CFTF42I The directory &amp;fname has been removed</p>
<p>CFTF42I The directory &amp;fname has been removed</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>Explanation</p></td>
<td width="80%"><p>A directory has been removed as requested by a SFTP client.</p></td>
</tr>
</tbody>
</table>

 

<table data-border="1" data-cellspacing="0">
<tbody>
<tr class="odd" data-valign="top">
<td width="20%"><p>V23 format</p>
<p>V24 format</p>
<p>Error</p></td>
<td width="80%"><p><span id="CFTF43E"></span>CFTF43E The directory &amp;fname can't be removed for reason code &amp;reason</p>
<p>CFTF43E The directory &amp;fname can't be removed for reason code &amp;reason</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="20%"><p>Explanation</p></td>
<td width="80%"><p>Cannot remove the directory.</p></td>
</tr>
<tr class="odd" data-valign="top">
<td width="20%">Action</td>
<td width="80%"><p>Check the reason code and take the appropriate action if possible.</p></td>
</tr>
</tbody>
</table>

 

<table data-border="1" data-cellspacing="0">
<tbody>
<tr class="odd" data-valign="top">
<td width="20%"><p>V23 format</p>
<p>V24 format</p>
<p>Information</p></td>
<td width="80%"><p><span id="CFTF43E"></span>CFTF44E The directory &amp;fname has been created</p>
<p>CFTF44I The directory &amp;fname has been created</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="20%"><p>Explanation</p></td>
<td width="80%">Created a directory per a SFTP client request.</td>
</tr>
</tbody>
</table>

 

<table data-border="1" data-cellspacing="0">
<tbody>
<tr class="odd" data-valign="top">
<td width="20%"><p>V23 format</p>
<p>V24 format</p>
Information</td>
<td width="80%"><p><span id="CFTF44I"></span>CFTF44I The directory &amp;fname has been created</p>
<p>CFTF44I The directory &amp;fname has been created</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="20%">Explanation</td>
<td width="80%">A directory has been created as requested by a SFTP client.</td>
</tr>
</tbody>
</table>

 

<table data-border="1" data-cellspacing="0">
<tbody>
<tr class="odd" data-valign="top">
<td width="20%"><p>V23 format</p>
<p>V24 format</p>
<p>V23 format</p>
<p>V24 format</p>
Error</td>
<td width="80%"><p><span id="CFTF46E"></span>CFTF46E Defined filename not inside WORKINGDIR &lt;IDTU=&amp;idtu PART=&amp;part IDF=&amp;idf IDT=&amp;idt&gt;</p>
<p>CFTF46E Defined filename not inside WORKINGDIR &lt;IDTU=&amp;idtu PART=&amp;part IDF=&amp;idf IDT=&amp;idt&gt;</p>
<p>CFTF46E+&amp;fname &lt;IDTU=&amp;idtu PART=&amp;part IDF=&amp;idf IDT=&amp;idt&gt;</p>
<p>CFTF46E+&amp;fname &lt;IDTU=&amp;idtu PART=&amp;part IDF=&amp;idf IDT=&amp;idt&gt;</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="20%">Explanation</td>
<td width="80%">The selected file must be in the configured WORKINDIR.</td>
</tr>
<tr class="odd" data-valign="top">
<td width="20%">Action</td>
<td width="80%">Select another file or change or remove the WORKINGDIR.</td>
</tr>
</tbody>
</table>

 

<table data-border="1" data-cellspacing="0">
<tbody>
<tr class="odd" data-valign="top">
<td width="20%"><p>V23 format</p>
<p>V24 format</p>
Information</td>
<td width="80%"><p><span id="CFTF47I"></span>CFTF47I The file rights of &amp;fname have been set to &amp;frights</p>
<p>CFTF47I The file rights of &amp;fname have been set to &amp;frights</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="20%">Explanation</td>
<td width="80%">File rights were changed as requested by an SFTP client. The format of rights is the UNIX format, for example 666.</td>
</tr>
</tbody>
</table>

 

<table data-border="1" data-cellspacing="0">
<tbody>
<tr class="odd" data-valign="top">
<td width="20%"><p>V23 format</p>
<p>V24 format</p>
Information</td>
<td width="80%"><p><span id="CFTF48I"></span>CFTF48I The file time of &amp;fname has been set to &amp;time</p>
<p>CFTF48I The file time of &amp;fname has been set to &amp;time</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="20%">Explanation</td>
<td width="80%">The file time was changed as requested by an SFTP client.</td>
</tr>
</tbody>
</table>

 

<table data-border="1" data-cellspacing="0">
<tbody>
<tr class="odd" data-valign="top">
<td width="20%"><p>V23 format</p>
<p>V24 format</p>
Error</td>
<td width="80%"><p><span id="CFTF49E"></span>CFTF49E The file properties of &amp;fname can't be changed for reason code &amp;reason</p>
<p>CFTF49E The file properties of &amp;fname can't be changed for reason code &amp;reason</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="20%">Explanation</td>
<td width="80%">Cannot change the rights or time of a file.</td>
</tr>
<tr class="odd" data-valign="top">
<td width="20%">Action</td>
<td width="80%">Check the reason code and make the appropriate action if possible.</td>
</tr>
</tbody>
</table>

 

<table data-border="1" data-cellspacing="0">
<tbody>
<tr class="odd" data-valign="top">
<td width="20%"><p>V23 format</p>
<p>V24 format</p>
Information</td>
<td width="80%"><p><span id="CFTF50I"></span>CFTF50I The file or directory &amp;fname has been renamed into &amp;newfname</p>
<p>CFTF50I The file or directory &amp;fname has been renamed into &amp;newfname</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="20%">Explanation</td>
<td width="80%">A file or directory has been renamed as requested by a SFTP client.</td>
</tr>
</tbody>
</table>

 

<table data-border="1" data-cellspacing="0">
<tbody>
<tr class="odd" data-valign="top">
<td width="20%"><p>V23 format</p>
<p>V24 format</p>
Warning</td>
<td width="80%"><p><span id="CFTF51W"></span>CFTF51W The file &amp;fname can't been archived into &amp;archivefname for reason code &amp;reason</p>
<p>CFTF51W The &amp;fname file can't be archived as &amp;newfname due to reason code &amp;reason</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="20%">Explanation</td>
<td width="80%">Could not move the file at the end of the transfer.
Check <a href="archivedir.htm">ARCHIVEDIR</a> and <a href="archivefname.htm">ARCHIVEFNAME</a>.</td>
</tr>
</tbody>
</table>

<table data-border="1" data-cellspacing="0">
<tbody>
<tr class="odd" data-valign="top">
<td width="20%"><p>V23 format</p>
<p>V24 format</p>
Error</td>
<td width="80%"><p><span id="CFTF51W"></span><span id="CFTF52E"></span>CFTF52E The IDF &amp;idf is not allowed</p>
<p>CFTF52E The IDF &amp;idf is not allowed</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="20%">Explanation</td>
<td width="80%">You cannot transfer a file using that IDF.</td>
</tr>
<tr class="odd" data-valign="top">
<td width="20%">Action</td>
<td width="80%">Use another IDF on the client, or update the SAUTH/RAUTH parameters on the server.</td>
</tr>
</tbody>
</table>
