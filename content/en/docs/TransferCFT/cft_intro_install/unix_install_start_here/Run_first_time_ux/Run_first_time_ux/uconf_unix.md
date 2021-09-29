{
    "title": "UNIX specific uconf settings ",
    "linkTitle": "UNIX specific uconf settings ",
    "weight": "300"
}This topic describes the unified configuration values to define for the following Unix options in Transfer CFT:

-   [Command line history: enable readline](#command)
-   [System user: define CFTSU](#system)
-   [Separating filenames from the file extension](#separat)
-   [General Unix-specific parameters](#unix)

## <span id="Command"></span>Command line history (readline)

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
<td>cft.unix.readline.enable</td>
<td>YES | NO</td>
<td>Enable readline history for CFTUTIL PKIUTIL and SECUTIL.</td>
</tr>
<tr class="even">
<td>cft.unix.readline.history_fname</td>
<td>$(HOME)/.cft_history</td>
<td>Readline history file.</td>
</tr>
<tr class="odd">
<td>cft.unix.readline.history_size</td>
<td>1000</td>
<td>Readline history size.</td>
</tr>
</tbody>
</table>

## <span id="System"></span>System user

<table data-cellspacing="0">
<thead>
<tr class="header">
<th>Parameter</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>cft.unix.cftsu.afunix</td>
<td>Defines the address family file for inter-process communications.</td>
</tr>
<tr class="even">
<td>cft.unix.cftsu.isservice</td>
<td>Defines the use of CFTSU as a service.</td>
</tr>
<tr class="odd">
<td>cft.unix.cftsu.fname</td>
<td>Specify the absolute path name to the CFTSU to execute when the user control is enabled, to enable upgrading without being the system administrator.
<p>See Unix: <a href="../t_adding_system_user_unix">Using system users</a>.</p></td>
</tr>
</tbody>
</table>

## <span id="Separat"></span> Separating filename and extension

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
<td>cft.unix.parse_file_name_suffix</td>
<td>No</td>
<td><p>Use this setting for a <span>Transfer CFT</span> running in Unix to separate the extension from the name of the file, as is done in Windows.</p>
<p>Possible values:</p>
<ul>
<li>Yes: Enables Unix to mimic Windows functioning so that the name of the file and the type of extension are presented separately</li>
<li>No: Disables the feature to have normal Unix file functioning with no extension type displayed</li>
</ul></td>
</tr>
</tbody>
</table>

See [Suffix management](../suffix_management).

## <span id="UNIX"></span>UNIX parameters

<table data-cellspacing="0">
<thead>
<tr class="header">
<th>ID</th>
<th>Default</th>
<th>Former value</th>
</tr>
</thead>
<tbody>
<tr class="odd" data-valign="top">
<td width="33.333%"><p>cft.unix.start_timeout
 </p></td>
<td width="33.333%"><p>(int)</p></td>
<td width="33.333%"><p> 30</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="33.333%"><p>cft.unix.stop_timeout</p></td>
<td width="33.333%"><p>(int)</p></td>
<td width="33.333%"><p>30</p></td>
</tr>
<tr class="odd" data-valign="top">
<td width="33.333%"><p>cft.unix.passwd_fname</p></td>
<td width="33.333%"><p> (fname)</p></td>
<td width="33.333%"><p>$(cft.runtime_dir)/conf/passwd</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="33.333%"><p>cft.unix.passwd_temp   </p></td>
<td width="33.333%"><p>(fname)</p></td>
<td width="33.333%"><p>$(cft.runtime_dir)/conf/passwdXXXXXX</p></td>
</tr>
<tr class="odd" data-valign="top">
<td width="33.333%"><p>cft.unix.group_fname</p></td>
<td width="33.333%"><p>(fname)</p></td>
<td width="33.333%"><p>$(cft.runtime_dir)/conf/group</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="33.333%"><p>cft.unix.group_temp</p></td>
<td width="33.333%"><p> (fname)</p></td>
<td width="33.333%"><p> $(cft.runtime_dir)/conf/groupXXXXXX</p></td>
</tr>
<tr class="odd" data-valign="top">
<td width="33.333%"><p>cft.unix.pid_fname</p></td>
<td width="33.333%"><p> (fname)</p></td>
<td width="33.333%"><p>$(cft.runtime_dir)/run/cft.pid</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="33.333%"><p>cft.unix.ipc_fname </p></td>
<td width="33.333%"><p>(fname)</p></td>
<td width="33.333%"><p>$(cft.runtime_dir)/run/cft.ipc</p></td>
</tr>
<tr class="odd" data-valign="top">
<td width="33.333%"><p>copilot.unix.unix_socket_fname </p></td>
<td width="33.333%"><p>(fname)</p></td>
<td width="33.333%"><p>$(cft.runtime_dir)/run/S_COPSMNGFW</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="33.333%"><p>copilot.unix.pid_fname</p></td>
<td width="33.333%"><p> (fname)</p></td>
<td width="33.333%"><p>$(cft.runtime_dir)/run/copilot.pid CFTCOPILOTPID</p></td>
</tr>
</tbody>
</table>
