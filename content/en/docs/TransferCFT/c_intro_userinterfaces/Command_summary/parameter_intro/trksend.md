{
    "title": "trksend",
    "linkTitle": "trksend",
    "weight": "3620"
}<span id="trksend"></span>

### trksend

#### **CFTPARM**

**\[TRKSEND = {** **UNDEFINED
|** **ALL | NO | SUMMARY }\]**

Specifications concerning transfers via CFTSEND for which the [trk](../trk)
value is not defined.

Select one of the following options:

- ****NO**** (default value): the monitor never sends
    Tracked Instances to Sentinel
- ****ALL****: for each step of each transfer
    process, the monitor sends a Tracked Instance to Sentinel
- ****SUMMARY****:
    for both the initial step and the final step of each transfer process,
    the monitor sends a Tracked Instance to Sentinel

 

[Return to Command index](../../)
