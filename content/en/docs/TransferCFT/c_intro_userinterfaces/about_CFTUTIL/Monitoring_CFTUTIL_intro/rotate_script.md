{
    "title": "Log management using the rotate script",
    "linkTitle": "Using the rotate script",
    "weight": "350"
}The command CFTLOG manages the Transfer CFT log files and switch process for your multi node configuration. The switch procedure is performed using a script, rotate.cmd/bat by default, and creates log files in the following format:

-   For node 00: cftlog00.1, cftlog00.2, cftlog00.3...
-   For node 01: cftlog01.1, cftlog01.2, cftlog01.3...
-   For node 02: cftlog02.1, cftlog02.2, cftlog02.3...

See also [CFTLOG](../../../web_copilot_ui/conf_intro/cftlog), the [exec](../../../command_summary/parameter_intro/exec) parameter, and <a href="../../../../admin_intro/admin_monitoring_intro/housekeeping_logs" class="MCXref xref">Housekeeping for log files</a>.

## Setting the unified configuration

In either command line or the user interface, set the following:

<table>
   <th>
      <tr>
<th>Parameter         </th>
<th>Value         </th>
<th>Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>cft.cftlog.fname         </td>
         <td>$(cft.cftlog.fname)         </td>
         <td>Replaces the CFTLOG logical name.         </td>
      </tr>
      <tr>
         <td>cft.cftlog.afname         </td>
         <td>$(cft.cftlog.fname)         </td>
         <td>Replaces the CFTLOGA logical name.         </td>
      </tr>
      <tr>
         <td>cft.cftlog.backup_count         </td>
         <td>3         </td>
         <td>Number of rotate out files.         </td>
      </tr>
   </tbody>
</table>

Example



    CFTLOG       ID       = 'LOG0',
    FNAME    = '$CFTLOG',
    AFNAME   = '$CFTALOG',
    EXEC     = 'C:\Work\CFT300\runtime\exec\rotate.bat',
    LENGTH   = '160',
    OPERMSG  = '0',
    MAXREC   = '0',
    NOTIFY   = '        ',
    SWITCH   = '00000000',
    CONTENT  = 'FULL',
    NTF      = 'NO',
    NTFTYP   = 'EF',
    ORIGIN   = 'CFTUTIL',
    FORMAT   = 'V24',
    MODE     = 'REPLACE'
