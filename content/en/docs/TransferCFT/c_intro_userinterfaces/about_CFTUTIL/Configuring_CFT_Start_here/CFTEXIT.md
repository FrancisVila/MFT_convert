{
    "title": "CFTEXIT - Exit tasks",
    "linkTitle": "CFTEXIT - Exit tasks",
    "weight": "370"
}<span id="Activating_an_exit_command_line"></span>This topic describes the
CFTEXIT command, used to start an EXIT task.

Related
topics

-   Command syntax
    [CFTEXIT](../../../command_summary)
-   Object concepts
    [Managing exits](../../../../app_integration_intro/managing_exits)

<table data-cellspacing="0" width="90%">
<thead>
<tr class="header">
<th>Parameters</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd" data-valign="top">
<td><p><a href="../../../command_summary/parameter_intro/id">ID</a></p></td>
<td width="59.777%"><p>Command identifier</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p><a href="../../../command_summary/parameter_intro/language">LANGUAGE</a></p></td>
<td width="59.777%"><p>Language used to write the user program.</p>
<p>The possible values are COBOL and C language.</p>
<p>This attribute enables Transfer CFT to exchange data with
the program using the EXIT task via the structure best suited to the language
in which it is implemented.</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p><a href="../../../command_summary/parameter_intro/parm">PARM</a> </p></td>
<td width="59.777%"><p>Free field available to the user.</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p><a href="../../../command_summary/parameter_intro/prog">PROG</a></p></td>
<td width="59.777%"><p>Name of the executable module corresponding to the EXIT
task to be activated.</p>
<p>This module consists of the interface provided with the
Transfer CFT product and linked with the program written by the user.</p>
<p>To facilitate identification of the associated
modules, it is advised to name these modules as follows:</p>
<ul>
<li>CFTEXA:
Directory type EXIT</li>
<li>CFTEXF:
File type EXIT</li>
<li><p>CFTEXIB: Beginning-of-transfer EXIT</p></li>
<li>CFTEXE:
End-of-transfer type EXIT</li>
</ul>
<p>You can use the last two characters to assign a sequential
number to the name, for example CFTEXA01.</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p><a href="../../../command_summary/parameter_intro/reserv">RESERV</a></p></td>
<td width="59.777%"><p>Size of the work area reserved for the user.</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p><a href="../../../command_summary/parameter_intro/type">TYPE</a></p></td>
<td width="59.777%"><p>Select the exit type, FILE, ACCESS, BOT, or EXEC.</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p><a href="../../../command_summary/parameter_intro/format">FORMAT</a></p></td>
<td width="59.777%"><p>Indicates the format for the communication area.</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p><a href="../../../command_summary/parameter_intro/waittask">WAITTASK</a></p></td>
<td width="59.777%"><p>Inactivity time (in minutes) of the EXIT task. Beyond this
value, this task is deactivated, i.e. unloaded from the memory.</p>
<p>This parameter only applies to file EXIT tasks.</p></td>
</tr>
</tbody>
</table>

Example 1 - Parameter setting for a file
type EXIT

<table data-cellspacing="0" width="90%">
<tbody>
<tr class="odd">
<td colspan="2" width="12%"><p>CFTSEND</p>
<p>ID = PAY,</p>
<p>EXIT = IDEXIT</p></td>
</tr>
</tbody>
</table>

 

<table data-cellspacing="0" width="90%">
<tbody>
<tr class="odd">
<td width="12%"><p>CFTEXIT</p>
<p>ID = IDEXIT,</p>
<p>LANGUAGE = C,</p>
<p>RESERV = 4000,</p>
<p>PROG = FILEXEC</p></td>
</tr>
</tbody>
</table>

Example 2 - Parameter setting for an directory
type EXIT

<table data-cellspacing="0" width="90%">
<tbody>
<tr class="odd">
<td width="12%"><p>CFTPROT</p>
<p>ID = PSIDTH,</p>
<p>TYPE = PESIT,</p>
<p>EXIT = EXAM</p></td>
<td width="66.656%"><p> </p></td>
</tr>
</tbody>
</table>

 

<table data-cellspacing="0" width="90%">
<tbody>
<tr class="odd">
<td width="12%"><p>CFTEXIT</p>
<p>ID = EXA,</p>
<p>PARM = SAMPLE,</p>
<p>LANGUAGE = C,</p>
<p>PROG = MYEXA,</p>
<p>TYPE = ACCESS</p></td>
</tr>
</tbody>
</table>
