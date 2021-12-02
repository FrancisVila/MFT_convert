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


| Parameter  | Value  | Description  |
| --- | --- | --- |
| cft.cftlog.fname  | $(cft.cftlog.fname)  | Replaces the CFTLOG logical name.  |
| cft.cftlog.afname  | $(cft.cftlog.fname)  | Replaces the CFTLOGA logical name.  |
| cft.cftlog.backup_count  | 3  | Number of rotate out files.  |


Example
