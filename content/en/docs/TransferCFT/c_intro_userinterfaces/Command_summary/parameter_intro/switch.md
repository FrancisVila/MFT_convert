{
    "title": "switch",
    "linkTitle": "switch",
    "weight": "3430"
}<span id="switch"></span>

### switch

#### CFTACCNT

**\[SWITCH = {<u>00000000</u> | *time*}\]**

Time at which the Transfer CFT{{< TransferCFT/componentshortname  >}}
automatically switches to the alternate statistical file.

- 000000
    (default value)
- any
    other value in the HHMMSS format

When this parameter is not defined, Transfer CFT{{< TransferCFT/componentshortname  >}} switches statistical
files daily at midnight.

#### CFTLOG

**\[SWITCH = {<u>00000000</u> | *time*}\]**

The time at which the monitor automatically switches to the alternate
log file:

- 000000
    (default value)
- any
    other value in the HHMMSS format

When this parameter is not defined, log files are switched daily at
midnight.

If you define a value for both maxrec
and switch fields, log files are automatically switched:

- Every
    day at the time indicated
- Depending
    on the number of records in the file

See also <a href="../../../../admin_intro/admin_monitoring_intro/housekeeping_logs" class="MCXref xref">Housekeeping for log files</a>.

 

[Return to Command index](../../)
