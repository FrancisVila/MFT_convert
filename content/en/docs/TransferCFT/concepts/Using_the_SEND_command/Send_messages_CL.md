{
    "title": "Sending a MESSAGE",
    "linkTitle": "Sending a MESSAGE",
    "weight": "250"
}# <span id="Sending_messages"></span>Send a message

You can use the SEND MESSAGE command to send a message to a designated partner, for example small amounts of content that are not considered sensitive content.

-   The message length in the PeSIT protocol has a maximum value of 4096 bytes
-   The message can be extracted from the Catalog file, and redirected to a specified file (fout parameter), using the DISPLAY command:

**Example**

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td>CFTUTIL SEND part=PART, idm=MSG, type=message, msg=’hello’
<p>CFTUTIL DISPLAY content=msg, fout=msgfile, direct=recv, idt=IDT</p></td>
</tr>
</tbody>
</table>

**Result**

The resulting msgfile will contain the message 'hello'.

<table data-cellpadding="0" data-cellspacing="0">
<tbody>
<tr class="odd">
<td data-valign="top"></td>
<td data-valign="top"><span><strong>Note</strong></span></td>
<td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">The <span>&lt;TransferCFTinstallation&gt;\runtime\conf</span> folder contains the <span>dspcnf.xml</span> file, a DISPLAY command template, which includes a specific filter <span>templatel id='msg'</span> that enables message extraction.</td>
</tr>
</tbody>
</table>

### Sending messages

<table data-cellspacing="0">
<thead>
<tr class="header">
<th><p>Parameters</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd" data-valign="top">
<td width="25.296%"><p><a href="../../../c_intro_userinterfaces/command_summary/parameter_intro/ida">IDA</a> </p></td>
<td width="74.704%"><p>Local transfer identifier assigned by the user or user application.</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="25.296%"><p><a href="../../../c_intro_userinterfaces/command_summary/parameter_intro/idm">IDM</a> </p></td>
<td width="74.704%"><p>Message identifier.</p></td>
</tr>
<tr class="odd" data-valign="top">
<td width="25.296%"><p><a href="../../../c_intro_userinterfaces/command_summary/parameter_intro/part">PART</a> </p></td>
<td width="74.704%"><p>Transfer partner identifier.</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="25.296%"><p><a href="../../../c_intro_userinterfaces/command_summary/parameter_intro/type">TYPE</a> =
MESSAGE</p></td>
<td width="74.704%"><p>Characterizes a message send request.</p></td>
</tr>
<tr class="odd" data-valign="top">
<td width="25.296%"><p>OPTIONAL PARAMETERS
for <a href="../send_command_basics">SEND</a></p></td>
<td width="74.704%"><p>The optional common parameters form the SEND subset, used for sending a message (but not applicable to files).</p></td>
</tr>
</tbody>
</table>

#### Example

A message using the identifier ANDREW.

<table data-cellspacing="0" width="90%">
<tbody>
<tr class="odd">
<td width="12%"><p>SEND</p>
<p>IDM = ANDREW,</p>
<p>MSG = ‘ANDREW: call PETER ’,</p></td>
</tr>
<tr class="even">
<td width="12%"><p>PART = HQ,</p>
<p>TYPE = MESSAGE,</p></td>
</tr>
</tbody>
</table>
