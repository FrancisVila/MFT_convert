{
    "title": "switch",
    "linkTitle": "switch",
    "weight": "3420"
}<span id="switch"></span>

### switch

#### CFTACCNT

**\[SWITCH = {<u>00000000</u> | *time*}\]**

Time at which the <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span>
automatically switches to the alternate statistical file.

-   <span style="font-weight: bold;">000000</span>
    (default value)
-   <span style="font-weight: bold;">any
    other value</span> in the HHMMSS format

When this parameter is not defined, <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> switches statistical
files daily at midnight.

#### CFTLOG

**\[SWITCH = {<u>00000000</u> | *time*}\]**

The time at which the monitor automatically switches to the alternate
log file:

-   <span style="font-weight: bold;">000000</span>
    (default value)
-   <span style="font-weight: bold;">any
    other value</span> in the HHMMSS format

When this parameter is not defined, log files are switched daily at
midnight.

If you define a value for both <span style="font-weight: bold;">maxrec</span>
and switch fields, log files are automatically switched:

-   Every
    day at the time indicated
-   Depending
    on the number of records in the file

See also <a href="../../../../admin_intro/admin_monitoring_intro/housekeeping_logs" class="MCXref xref">Housekeeping for log files</a>.

 

[Return to Command index](../../)