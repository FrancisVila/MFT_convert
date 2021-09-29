{
    "title": "CFTP messages",
    "linkTitle": "CFTP messages",
    "weight": "360"
}# Transfer CFT messages: CFTP

This topic lists the CFTPxx (CFT xnnx) messages and provides the type, a description, consequence, and corrective actions when applicable.

**Message format**

Earlier versions of Transfer CFT used a different message format than version 3.1.3 and higher. This document displays both formats when applicable and available, otherwise only the v23 is used. Using the CFTLOG Format = V24 setting, the log displays as shown:

CFTXXX: fixed text message &lt;variables>

**Example**

CFTLOG FORMAT=\[V23,V24\]

For V23: CFTT57I PART=&part IDF=&idf IDT=&idt &str transfer started

For V24: `CFTT57I &str transfer started   <IDTU=&idtu PART=&part IDF=&idf IDT=&idt>`

<table data-border="1" data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>V23 format</p>
<p>V24 format</p>
<p>Error</p></td>
<td><p><span id="CFTP01F"></span>CFTP01F CFTPARM &amp;id _ Not found</p>
<p>CFTP01F CFTPARM &amp;id _ Not found</p></td>
</tr>
<tr class="even">
<td><p>Explanation</p></td>
<td><p>The &amp;id identifier of the <span>Transfer CFT</span> parameter file
(see the CFTPARM parameter) is not defined.</p></td>
</tr>
<tr class="odd">
<td><p>Consequence</p></td>
<td><p>The Transfer
CFT initialization phase is stopped.</p></td>
</tr>
<tr class="even">
<td><p>Action</p></td>
<td><p>Check the
CFTPARM parameter settings (see the CFTPARM parameter), correct and restart
<span>Transfer CFT</span>.</p></td>
</tr>
</tbody>
</table>

 

<table data-border="1" data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>V23 format</p>
<p>V24 format</p>
<p>Error</p></td>
<td><p><span id="CFTP02F"></span>CFTP02F CFTTRACE &amp;id for CFTPARM &amp;id _ Not
found</p>
<p>CFTP02F CFTSYST &amp;id for CFTPARM &amp;id _ Not found</p></td>
</tr>
<tr class="even">
<td><p>Explanation</p></td>
<td><p>When initializing
<span>Transfer CFT</span>, the CFTTRACE &amp;id identifier was not found in the Transfer
CFT parameter file.</p></td>
</tr>
<tr class="odd">
<td><p>Consequence</p></td>
<td><p>The Transfer
CFT initialization phase is stopped.</p></td>
</tr>
<tr class="even">
<td><p>Action</p></td>
<td><p>Check the
CFTSYST parameter settings (see the CFTPARM parameter), correct and restart
<span>Transfer CFT</span>.</p></td>
</tr>
</tbody>
</table>

 

<table data-border="1" data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>V23 format</p>
<p>V24 format</p>
<p>Error</p></td>
<td><p>CFTP03F CFTLOG &amp;id for CFTPARM &amp;id _ Not found</p>
<p>CFTP03F CFTLOG &amp;id for CFTPARM &amp;id _ Not found</p></td>
</tr>
<tr class="even">
<td><p>Explanation</p></td>
<td><p>During Transfer
CFT initialization the CFTLOG &amp;id identifier was not found in the
<span>Transfer CFT</span> parameter file.</p></td>
</tr>
<tr class="odd">
<td><p>Consequence</p></td>
<td><p>The Transfer
CFT initialization phase is stopped.</p></td>
</tr>
<tr class="even">
<td><p>Action</p></td>
<td><p>Check the
CFTLOG parameter settings (see the CFTPARM parameter), correct and restart
<span>Transfer CFT</span>.</p></td>
</tr>
</tbody>
</table>

 

<table data-border="1" data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>V23 format</p>
<p>V24 format</p>
<p>Error</p></td>
<td><p><span id="CFTP04F"></span>CFTP04F CFTNET &amp;id for CFTPARM &amp;id _ Not found</p>
<p>CFTP04F CFTNET &amp;id for CFTPARM &amp;id _ Not found</p></td>
</tr>
<tr class="even">
<td><p>Explanation</p></td>
<td><p>During Transfer
CFT initialization the CFTNET &amp;id identifier was not found in the
<span>Transfer CFT</span> parameter file.</p></td>
</tr>
<tr class="odd">
<td><p>Consequence</p></td>
<td><p>The Transfer
CFT initialization phase is stopped.</p></td>
</tr>
<tr class="even">
<td><p>Action</p></td>
<td><p>Check the
CFTNET parameter settings (see the CFTPARM parameter), correct and restart
<span>Transfer CFT</span>.</p></td>
</tr>
</tbody>
</table>

 

<table data-border="1" data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>V23 format</p>
<p>V24 format</p>
<p>Error</p></td>
<td><p><span id="CFTP05F"></span>CFTP05F CFTPROT &amp;id for CFTPARM &amp;id_ Not found</p>
<p>CFTP05F CFTPROT &amp;id for CFTPARM &amp;id _ Not found</p></td>
</tr>
<tr class="even">
<td><p>Explanation</p></td>
<td><p>During Transfer
CFT initialization the CFTPROT &amp;id identifier was not found in the
<span>Transfer CFT</span> parameter file.</p></td>
</tr>
<tr class="odd">
<td><p>Consequence</p></td>
<td><p>The Transfer
CFT initialization phase is stopped.</p></td>
</tr>
<tr class="even">
<td><p>Action</p></td>
<td><p>Check the
CFTPROT parameter settings (see CFTPROT), correct and restart Transfer
CFT.</p></td>
</tr>
</tbody>
</table>

 

<table data-border="1" data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>V23 format</p>
<p>V24 format</p>
<p>Error</p></td>
<td><p><span id="CFTP06F"></span>CFTP06F CFTCAT &amp;id for CFTPARM &amp;id _ Not found</p>
<p>CFTP06F CFTCAT &amp;id for CFTPARM &amp;id _ Not found</p></td>
</tr>
<tr class="even">
<td><p>Explanation</p></td>
<td><p>During Transfer
CFT initialization the CFTCAT &amp;id identifier was not found in the
<span>Transfer CFT</span> parameter file.</p></td>
</tr>
<tr class="odd">
<td><p>Consequence</p></td>
<td><p>The Transfer
CFT initialization phase is stopped.</p></td>
</tr>
<tr class="even">
<td><p>Action</p></td>
<td><p>Check the
CFTCAT parameter settings (see CFTCAT), correct and restart <span>Transfer CFT</span>.</p></td>
</tr>
</tbody>
</table>

 

<table data-border="1" data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>V23 format</p>
<p>V24 format</p>
<p>Error</p></td>
<td><p><span id="CFTP07F"></span>CFTP07F CFTCOM &amp;id for CFTPARM &amp;id _ Not found</p>
<p>CFTP07F CFTCOM &amp;id for CFTPARM &amp;id _ Not found</p></td>
</tr>
<tr class="even">
<td><p>Explanation</p></td>
<td><p>During Transfer
CFT initialization the CFTCOM &amp;id identifier was not found in the
<span>Transfer CFT</span> parameter file.</p></td>
</tr>
<tr class="odd">
<td><p>Consequence</p></td>
<td><p>The Transfer
CFT initialization phase is stopped.</p></td>
</tr>
<tr class="even">
<td><p>Action</p></td>
<td><p>Check the CFTCOM parameter settings (see CFTCOM), correct and
restart <span>Transfer CFT</span>.</p></td>
</tr>
</tbody>
</table>

 

<table data-border="1" data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>V23 format</p>
<p>V24 format</p>
<p>Fatal</p></td>
<td><p><span id="CFTP08F"></span>CFTP08F CFTNET &amp;id for CFTPROT &amp;id _ Not found</p>
<p>CFTP08F CFTNET &amp;id for CFTPROT &amp;id _ Not found</p></td>
</tr>
<tr class="even">
<td><p>Explanation</p></td>
<td><p>During Transfer
CFT initialization the CFTNET &amp;id identifier for a given CFTPROT &amp;id
protocol was not found in the <span>Transfer CFT</span> parameter file.</p></td>
</tr>
<tr class="odd">
<td><p>Consequence</p></td>
<td><p>The Transfer
CFT initialization phase is stopped.</p></td>
</tr>
<tr class="even">
<td><p>Action</p></td>
<td><p>Check:</p>
<ul>
<li>the CFTNET
and CFTPROT parameter settings (see the CFT CFTNET and CFTPROT topics)</li>
<li>the CFTPARM
parameter settings</li>
<li>the list
of authorized protocols and network identifiers (NET=(.,.), PROT=(.,.)
) that the number of items in this list does not exceed the maximum authorized
quota</li>
</ul>
<p>Correct and restart <span>Transfer CFT</span>.</p></td>
</tr>
</tbody>
</table>

 

<table data-border="1" data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>V23 format</p>
<p>V24 format</p>
<p>Error</p></td>
<td><p><span id="CFTP09F"></span>CFTP09F CFTSEND &amp;id for CFTPARM &amp;id _ No default
record found</p>
<p>CFTP09F CFTSEND &amp;id for CFTPARM &amp;id _ No default record found</p></td>
</tr>
<tr class="even">
<td><p>Explanation</p></td>
<td><p>During Transfer
CFT initialization the identifier describing the default file characteristics
used for send transfers (CFTSEND parameter) is unknown.</p></td>
</tr>
<tr class="odd">
<td><p>Consequence</p></td>
<td><p>The Transfer
CFT initialization phase cannot continue correctly and <span>Transfer CFT</span> is
aborted.</p></td>
</tr>
<tr class="even">
<td><p>Action</p></td>
<td><p>Check the
CFTPARM (DEFAULT=.) and CFTSEND parameter settings, correct and restart
<span>Transfer CFT</span>.</p></td>
</tr>
</tbody>
</table>

 

<table data-border="1" data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>V23 format</p>
<p>V24 format</p>
<p>Error</p></td>
<td><p><span id="CFTP10F"></span>CFTP10F CFTRECV &amp;id for CFTPARM &amp;id _ No Default
record found</p>
<p>CFTP10F CFTRECV &amp;id for CFTPARM &amp;id _ No Default record found</p></td>
</tr>
<tr class="even">
<td><p>Explanation</p></td>
<td><p>During Transfer
CFT initialization the identifier describing the default file characteristics
used for receive transfers (CFTRECV parameter) is unknown.</p></td>
</tr>
<tr class="odd">
<td><p>Consequence</p></td>
<td><p>The Transfer
CFT initialization phase cannot continue correctly and <span>Transfer CFT</span> is
aborted.</p></td>
</tr>
<tr class="even">
<td><p>Action</p></td>
<td><p>Check CFTPARM
(DEFAULT=.) and CFTRECV parameter settings, correct and restart Transfer
CFT.</p></td>
</tr>
</tbody>
</table>

 

<table data-border="1" data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>V23 format</p>
<p>V24 format</p>
<p>Error</p></td>
<td><p>CFTP13F CFTXLATE &amp;id _ Not found</p>
<p>CFTP13F CFTXLATE &amp;id not found (DIRECT=&amp;direct FCODE=&amp;fcode NCODE=&amp;ncode</p></td>
</tr>
<tr class="even">
<td><p>Explanation</p></td>
<td><p>There is no CFTXLATE command, the identifier of which is &amp;id.</p></td>
</tr>
<tr class="odd">
<td><p>Consequence</p></td>
<td><p>The transfer requiring this translation table definition cannot
be executed.</p></td>
</tr>
<tr class="even">
<td><p>Action</p></td>
<td><p>Specify a CFTXLATE command for this transfer direction and the
source and target alphabets.</p></td>
</tr>
</tbody>
</table>

 

<table data-border="1" data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>V23 format</p>
<p>V24 format</p>
<p>Error</p></td>
<td><p><span id="CFTP14F"></span>CFTP14F CFTACCNT &amp;id for CFTPARM &amp;id _ Not found</p>
<p>CFTP14F CFTACCNT &amp;id for CFTPARM &amp;id _ Not found</p></td>
</tr>
<tr class="even">
<td><p>Explanation</p></td>
<td><p>During Transfer
CFT initialization the command describing the accounting characteristics
(CFTACCNT command), the ID parameter of which corresponds to the ACCNT
parameter in the CFTPARM command, was not found.</p></td>
</tr>
<tr class="odd">
<td><p>Consequence</p></td>
<td><p>The Transfer
CFT initialization phase cannot continue correctly and <span>Transfer CFT</span> is
aborted.</p></td>
</tr>
<tr class="even">
<td><p>Action</p></td>
<td><p>Check the
CFTACCNT parameter settings, correct and restart <span>Transfer CFT</span>.</p></td>
</tr>
</tbody>
</table>

 

<table data-border="1" data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>V23 format</p>
<p>V24 format</p>
<p>Error</p></td>
<td><p><span id="CFTP15F"></span>CFTP15F CFTPROT &amp;idprot for CFTPARM &amp;idparm
_ Not loading in memory</p>
<p>CFTP15F CFTPROT &amp;id for CFTPARM &amp;id _ Not loading in memory</p></td>
</tr>
<tr class="even">
<td><p>Explanation</p></td>
<td><p>During Transfer
CFT initialization the CFTPROT &amp;idprot card could not be loaded in
memory (insufficient space).</p></td>
</tr>
<tr class="odd">
<td><p>Consequence</p></td>
<td><p>This card cannot be used for transfers.</p></td>
</tr>
<tr class="even">
<td><p>Action</p></td>
<td><p>Reduce the
number of CFTPROT card identifiers in the CFTPARM &amp;idparm command
(see the <span>Transfer CFT</span> topics that correspond to your OS to find out the
parameter setting limits). After correcting your parameter settings, restart
<span>Transfer CFT</span>.</p></td>
</tr>
</tbody>
</table>

 

<table data-border="1" data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>V23 format</p>
<p>V24 format</p>
<p>Error</p></td>
<td><p><span id="CFTP16F"></span>CFTP16F CFTNET &amp;idnet for CFTPARM &amp;idparm _
Not loading in memory</p>
<p>CFTP16F CFTNET &amp;id for CFTPARM &amp;id _ Not loading in memory</p></td>
</tr>
<tr class="even">
<td><p>Explanation</p></td>
<td><p>During Transfer
CFT initialization the CFTNET &amp;idnet card could not be loaded in memory
(insufficient space).</p></td>
</tr>
<tr class="odd">
<td><p>Consequence</p></td>
<td><p>This card cannot be used for transfers.</p></td>
</tr>
<tr class="even">
<td><p>Action</p></td>
<td><p>Reduce the
number of CFTNET card identifiers in the CFTPARM &amp;idparm command (see
the <span>Transfer CFT</span> topics that correspond to your OS to find out the parameter
setting limits).</p>
<p>After correcting
your parameter settings, restart <span>Transfer CFT</span>.</p></td>
</tr>
</tbody>
</table>

 

<table data-border="1" data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>V23 format</p>
<p>V24 format</p>
<p>Error</p></td>
<td><p><span id="CFTP17F"></span>CFTP17F CFTCOM &amp;idcom for CFTPARM &amp;idparm _
Not loading in memory</p>
<p>CFTP17F CFTCOM &amp;id for CFTPARM &amp;id _ Not loading in memory</p></td>
</tr>
<tr class="even">
<td><p>Explanation</p></td>
<td><p>During Transfer
CFT initialization the CFTCOM &amp;idcom card could not be loaded in memory
(insufficient space).</p></td>
</tr>
<tr class="odd">
<td><p>Consequence</p></td>
<td><p>This card cannot be used for transfers.</p></td>
</tr>
<tr class="even">
<td><p>Action</p></td>
<td><p>Reduce the
number of CFTCOM card identifiers in the CFTPARM &amp;idparm command (see
the <span>Transfer CFT</span> topics that correspond to your OS to find out the parameter
setting limits).</p>
<p>After correcting
your parameter settings, restart <span>Transfer CFT</span>.</p></td>
</tr>
</tbody>
</table>

 

<table data-border="1" data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>V23 format</p>
<p>V24 format</p>
<p>Error</p></td>
<td><p><span id="CFTP18F"></span>CFTP18F Error of integrity</p>
<p>CFTP18F Error of integrity</p></td>
</tr>
<tr class="even">
<td><p>Explanation</p></td>
<td><p>An integrity violation has been detected on the parameter or
partner file when the file is sealed. The previous message of the CFTIxxx
(partner file) or CFTPxxx (parameter file) type gives more information
about the operation requested on the file(s).</p></td>
</tr>
<tr class="odd">
<td><p>Consequence</p></td>
<td><p>The Transfer
CFT initialization phase is aborted. </p></td>
</tr>
</tbody>
</table>

 

<table data-border="1" data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>V23 format</p>
<p>V24 format</p>
<p>Error</p></td>
<td><p><span id="CFTP19E"></span>CFTP19E PART=&amp;part IDF=&amp;idf CFTAPPL=&amp;id
DIRECT=&amp;direct not found</p>
<p>CFTP19E PART=&amp;part IDF=&amp;idf CFTAPPL=&amp;id DIRECT=&amp;direct not found</p></td>
</tr>
<tr class="even">
<td><p>Explanation</p></td>
<td><p>The security system is running but the CFTAPPL &amp;id card
used to assign an owner to a transfer and corresponding to IDF=&amp;idf
was not found.</p></td>
</tr>
<tr class="odd">
<td><p>Consequence</p></td>
<td><p>The transfer is rejected and no entry is created in the catalog.</p></td>
</tr>
</tbody>
</table>

 

<table data-border="1" data-cellspacing="0">
<tbody>
<tr class="odd" data-valign="top">
<td width="20%"><p>V23 format</p>
<p>V24 format</p>
Error</td>
<td width="80%"><p><span id="CFTP20E"></span>CFTP20E The client CFTSSH &amp;ssh cannot be found for partner &amp;part</p>
<p>CFTP20E The client CFTSSH &amp;id cannot be found for partner &amp;id</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="20%">Explanation</td>
<td width="80%">A client CFTSSH referenced in a CFTPART cannot be found.</td>
</tr>
<tr class="odd" data-valign="top">
<td width="20%">Action</td>
<td width="80%">Add the CFTSSH.</td>
</tr>
</tbody>
</table>

 

<table data-border="1" data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>V23 format</p>
<p>V24 format</p>
<p>Error</p></td>
<td><p><span id="CFTP20F"></span>CFTP20F direct=server &amp;id for CFTPROT &amp;prot
_ Not found</p>
<p>CFTP20F CFTSSL direct=server &amp;id for CFTPROT &amp;id _ Not found</p></td>
</tr>
<tr class="even">
<td><p>Explanation</p></td>
<td><p>The security (SSL) being activated, the CFTSSL &amp;id direct=server
card whose ID parameter corresponds to the value of the SSL parameter,
CFTPROT command was not found.</p></td>
</tr>
<tr class="odd">
<td><p>Consequence</p></td>
<td><p>The Transfer
CFT initialization phase has shut down.</p></td>
</tr>
</tbody>
</table>

 

<table data-border="1" data-cellspacing="0">
<tbody>
<tr class="odd" data-valign="top">
<td width="20%"><p>V23 format</p>
<p>V24 format</p>
Error</td>
<td width="80%"><p><span id="CFTP21E"></span>CFTP21E The client private key &amp;key cannot be loaded from &amp;origin</p>
<p>CFTP21E The client private key &amp;key cannot be loaded from &amp;origin</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="20%">Explanation</td>
<td width="80%">Could not load the private key defined in the CLIPRIVKEY parameter from file (&amp;origin = file) or PKI database (&amp;origin = PKI database).</td>
</tr>
<tr class="odd" data-valign="top">
<td width="20%">Action</td>
<td width="80%">Check if the key has been inserted in the PKI database and that the key name is correct. For a file, check the file name and file format (should be RSA).</td>
</tr>
</tbody>
</table>

 

<table data-border="1" data-cellspacing="0">
<tbody>
<tr class="odd" data-valign="top">
<td width="20%"><p>V23 format</p>
<p>V24 format</p>
Error</td>
<td width="80%"><p><span id="CFTP22E"></span>CFTP22E The client public key &amp;key cannot be loaded from &amp;origin</p>
<p>CFTP22E The client public key &amp;key cannot be loaded from &amp;origin</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="20%">Explanation</td>
<td width="80%">Could not load the public key defined in the CLIPRIVKEY parameter from file (&amp;origin = file) or PKI database (&amp;origin = PKI database).</td>
</tr>
<tr class="odd" data-valign="top">
<td width="20%">Action</td>
<td width="80%">Check if the key has been inserted in the PKI database and that the key name is correct. For a file, check the file name and file format (should be RSA).</td>
</tr>
</tbody>
</table>

 

<table data-border="1" data-cellspacing="0">
<tbody>
<tr class="odd" data-valign="top">
<td width="20%"><p>V23 format</p>
<p>V24 format</p>
Warning</td>
<td width="80%"><p><span id="CFTP23W"></span>CFTP23W CFTNET &amp;id for CFTPARM &amp;id uses &amp;net network _ Disabled</p>
<p>CFTP23W CFTNET &amp;id for CFTPARM &amp;id uses &amp;net network _ Disabled</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="20%">Explanation</td>
<td width="80%">Only CFTNET TCP type protocols are loaded when starting <span>Transfer CFT</span>.</td>
</tr>
<tr class="odd" data-valign="top">
<td width="20%">Action</td>
<td width="80%">Remove the unsupported protocols if you no longer want this message to display.</td>
</tr>
</tbody>
</table>

 

<table data-border="1" data-cellspacing="0">
<tbody>
<tr class="odd" data-valign="top">
<td width="20%"><p>V23 format</p>
<p>V24 format</p>
Warning</td>
<td width="80%"><p>CFTP24W CFTPROT &amp;id uses CFTNET &amp;id _ Disabled</p>
<p>CFTP24W CFTPROT &amp;id uses CFTNET &amp;id _ Disabled</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="20%">Explanation</td>
<td width="80%">Only CFTNET TCP type protocols are loaded when starting <span>Transfer CFT</span>.</td>
</tr>
<tr class="odd" data-valign="top">
<td width="20%">Action</td>
<td width="80%">Remove the unsupported protocols if you no longer want this message to display.</td>
</tr>
</tbody>
</table>

<table data-border="1" data-cellspacing="0">
<tbody>
<tr class="odd" data-valign="top">
<td><p>V23 format</p>
<p>V24 format</p>
Warning</td>
<td width="80%"><p><span id="CFTP24W"></span>CFTP25W CFTCOM &amp;id uses TYPE 'MBX' Disabled</p>
<p>CFTP25W CFTCOM &amp;id uses TYPE 'MBX' Disabled</p></td>
</tr>
<tr class="even" data-valign="top">
<td>Explanation</td>
<td width="80%">The CFTCOM mailbox is no longer supported on z/OS, Windows platforms.</td>
</tr>
<tr class="odd" data-valign="top">
<td>Action</td>
<td width="80%">Remove the unsupported TYPE.</td>
</tr>
</tbody>
</table>

 

<table data-border="1" data-cellspacing="0">
<tbody>
<tr class="odd" data-valign="top">
<td width="20%"><p>V23 format</p>
<p>V24 format</p>
Error</td>
<td width="80%"><p><span id="CFTP30F"></span>CFTP30F CFTSSH &amp;ssh for CFTPROT &amp;prot cannot be found</p>
<p>CFTP30F CFTSSH &amp;id for CFTPROT &amp;id cannot be found</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="20%">Explanation</td>
<td width="80%">Cannot find the server CFTSSH referenced in a CFTPROT.</td>
</tr>
<tr class="odd" data-valign="top">
<td width="20%">Action</td>
<td width="80%">Add the CFTSSH.</td>
</tr>
</tbody>
</table>

 

<table data-border="1" data-cellspacing="0">
<tbody>
<tr class="odd" data-valign="top">
<td width="20%"><p>V23 format</p>
<p>V24 format</p>
Error</td>
<td width="80%"><p><span id="CFTP30F"></span></p>
<p><span id="CFTP31F"></span>CFTP31F CFTNET &amp;id for CFTPROT &amp;id cannot be found</p>
<p>CFTP31F CFTNET &amp;id for CFTPROT &amp;id cannot be found</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="20%">Explanation</td>
<td width="80%">Cannot find the CFTNET referenced in this CFTPROT.</td>
</tr>
<tr class="odd" data-valign="top">
<td width="20%">Action</td>
<td width="80%">Check the CFTNET referenced in CFTPROT and add the CFTNET if necessary.</td>
</tr>
</tbody>
</table>
