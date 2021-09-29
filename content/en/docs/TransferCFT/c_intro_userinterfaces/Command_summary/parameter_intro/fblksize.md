{
    "title": "fblksize",
    "linkTitle": "fblksize",
    "weight": "1080"
}### <span id="fblksize"></span>fblksize

#### <span id="fblksize_CFTFILE"></span>CFTFILE

**\[FBLKSIZE = {<u>see
table below</u> | n}\]  **{0...32768}

According to TYPE/**OS**

Defines the block size, in bytes, of the file to be created.

The table below indicates, for each system, the default value supported
according to the type of file to be created.When the default
value of the block size of the file to be created is "no" in the following table, the
FBLKSIZE parameter does not need to be defined.

<table data-cellspacing="0">
<thead>
<tr class="header">
<th colspan="7">FBLKSIZE</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>OS </p></td>
<td><p>PARM </p></td>
<td><p>PART </p></td>
<td><p>CAT </p></td>
<td><p>COM </p></td>
<td><p>LOG </p></td>
<td><p>ACCNT </p></td>
</tr>
<tr class="even">
<td><p> z/OS (MVS)</p></td>
<td><p>no </p></td>
<td><p>no </p></td>
<td><p>no </p></td>
<td><p>no </p></td>
<td><p>1028</p></td>
<td><p>482 </p></td>
</tr>
<tr class="odd">
<td><p>IBM i (OS400) </p></td>
<td><p>0 </p></td>
<td><p>0 </p></td>
<td><p>0 </p></td>
<td><p>0 </p></td>
<td><p>0 </p></td>
<td><p>0 </p></td>
</tr>
<tr class="even">
<td><p>UNIX </p></td>
<td><p>no </p></td>
<td><p>no </p></td>
<td><p>no </p></td>
<td><p>no </p></td>
<td><p>no </p></td>
<td><p>no </p></td>
</tr>
<tr class="odd">
<td><p>Windows</p></td>
<td><p>no </p></td>
<td><p>no </p></td>
<td><p>no </p></td>
<td><p>no </p></td>
<td><p>no </p></td>
<td><p>no </p></td>
</tr>
</tbody>
</table>

#### CFTRECV, RECV

**\[FBLKSIZE = n \]              **{0..62563}

This parameter, in bytes, controls the "blocking factor" of
the receiver file records: according to the system, it defines the disk
block size and/or the file input/output buffer size.

<table data-cellspacing="0" width="90%">
<thead>
<tr class="header">
<th>System</th>
<th>FBLKSIZE used</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td data-valign="top" width="22%"><p>MVS (z/OS)</p></td>
<td data-valign="top" width="78%"><p>YES </p></td>
</tr>
<tr class="even">
<td data-valign="top" width="22%"><p>OS400 (IBM i)</p></td>
<td data-valign="top" width="78%"><p>NO </p></td>
</tr>
<tr class="odd">
<td data-valign="top" width="22%"><p>UNIX </p></td>
<td data-valign="top" width="78%"><p>NO </p></td>
</tr>
<tr class="even">
<td data-valign="top" width="22%"><p>Windows</p></td>
<td data-valign="top" width="78%"><p>NO </p></td>
</tr>
</tbody>
</table>

<table data-cellspacing="0" width="90%">
<tbody>
<tr class="odd">
<td data-valign="top" width="13.997%"><p><strong>z/OS (MVS)</strong> </p></td>
<td data-valign="top" width="86.003%"><p>For protocols other than PeSIT, CFT profile, if this parameter
is not defined, its value is set as follows: </p>
<ul>
<li>For fixed
format files: this value equals the largest multiple of FLRECL which is
less than the constant (related to the track length) defined on installation
(default value: 19069), or FLRECL if FLRECL is greater than this constant</li>
<li>For variable
format files: this value equals the constant (related to the track length)
defined on installation of the <span>Transfer CFT</span> in a z/OS environment
(default value: 19065), or to FLRECL + 4 if FLRECL is greater than this
constant</li>
<li>For undefined
format files: this value is equal to 32760</li>
</ul></td>
</tr>
</tbody>
</table>

#### <span id="fblksize_CFTSEND"></span>CFTSEND, SEND

\[FBULKSIZ = n\]   {
0...65536}

Block size of file to be sent.

Typically you do not need to define this parameter as Transfer CFT is
able to locate the value for the file to be sent. This real value is then
taken into account when activating the transfer.

<table data-cellspacing="0" width="90%">
<thead>
<tr class="header">
<th><p>System </p></th>
<th><p>FBLKSIZE used </p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td data-valign="top" width="22%"><p>MVS (z/OS)</p></td>
<td data-valign="top" width="78%"><p>YES </p></td>
</tr>
<tr class="even">
<td data-valign="top" width="22%"><p>OS400 (IBM i)</p></td>
<td data-valign="top" width="78%"><p>NO </p></td>
</tr>
<tr class="odd">
<td data-valign="top" width="22%"><p>UNIX </p></td>
<td data-valign="top" width="78%"><p>NO </p></td>
</tr>
<tr class="even">
<td data-valign="top" width="22%"><p>Windows </p></td>
<td data-valign="top" width="78%"><p>NO </p></td>
</tr>
</tbody>
</table>

[Return to Command index](../../)
