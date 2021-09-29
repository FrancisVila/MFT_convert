{
    "title": "Using the rotate script",
    "linkTitle": "Using the rotate script",
    "weight": "370"
}The command CFTLOG manages the Transfer CFT log files and switch process for your multi node configuration. The switch procedure is performed using a script, rotate.cmd/bat by default, and creates log files in the following format:

-   For node 00: cftlog00.1, cftlog00.2, cftlog00.3...
-   For node 01: cftlog01.1, cftlog01.2, cftlog01.3...
-   For node 02: cftlog02.1, cftlog02.2, cftlog02.3...

See also [CFTLOG](../../../web_copilot_ui/conf_intro/cftlog), the [exec](../../../command_summary/parameter_intro/exec) parameter, and [Housekeeping for log files](../../../../admin_intro/admin_monitoring_intro/housekeeping_logs).

## Setting the unified configuration

In either command line or the user interface, set the following:

<table data-cellspacing="0">
<thead>
<tr class="header">
<th>Parameter</th>
<th>Value</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>cft.cftlog.fname</td>
<td>$(cft.cftlog.fname)</td>
<td>Replaces the CFTLOG logical name.</td>
</tr>
<tr class="even">
<td>cft.cftlog.afname</td>
<td>$(cft.cftlog.fname)</td>
<td>Replaces the CFTLOGA logical name.</td>
</tr>
<tr class="odd">
<td>cft.cftlog.backup_count</td>
<td>3</td>
<td>Number of rotate out files.</td>
</tr>
</tbody>
</table>

Example

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>CFTLOG ID = 'LOG0',</p>
<p>FNAME = '$CFTLOG',</p>
<p>AFNAME = '$CFTALOG',</p>
<p>EXEC = 'C:\Work\CFT300\runtime\exec\rotate.bat',</p>
<p>LENGTH = '160',</p>
<p>OPERMSG = '0',</p>
<p>MAXREC = '0',</p>
<p>NOTIFY = ' ',</p>
<p>SWITCH = '00000000',</p>
<p>CONTENT = 'FULL',</p>
<p>NTF = 'NO',</p>
<p>NTFTYP = 'EF',</p>
<p>ORIGIN = 'CFTUTIL',</p>
<p>FORMAT = 'V24',</p>
<p>MODE = 'REPLACE'</p></td>
</tr>
</tbody>
</table>
