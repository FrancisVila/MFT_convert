{
    "title": "trkrecv",
    "linkTitle": "trkrecv",
    "weight": "3610"
}<span id="trkrecv"></span>

### trkrecv

#### CFTPARM

**\[TRKRECV = {** **UNDEFINED
|** **ALL | NO | SUMMARY }\]**

Specifications concerning transfers via CFTRECV for which the [trk](../trk)
value is not defined.

Select one of the following options:

- NO
    (default value): the monitor never sends Tracked Instances to Sentinel.
- ALL:
    for each step of each transfer process, the monitor sends a Tracked Instance
    to Sentinel.
- SUMMARY:
    for both the initial step and the final step of each transfer process,
    the monitor sends a Tracked Instance to Sentinel.

 

[Return to Command index](../../)
