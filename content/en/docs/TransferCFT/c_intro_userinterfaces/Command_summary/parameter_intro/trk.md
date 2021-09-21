{
    "title": "trk",
    "linkTitle": "trk",
    "weight": "3610"
}### <span id="trk"></span>trk

#### <span id="trk_CFTRECV"></span>CFTRECV, <span id="trk_CFTSEND"></span>CFTSEND, RECV, SEND

\[TRK = {<u>"value of TRKSEND/TRKRECV from CFTPARM</u>"
| ALL | NO | SUMMARY | UNDEFINED}\]

Specifies how much detail Transfer CFT provides
Sentinel about transfers. Transfer CFT sends detail about the
transfers in the form of tracked instances.

The possible values of this parameter include:

-   NO: The
    monitor never sends tracked instances to Sentinel
-   ALL:
    For each step of each transfer process, the monitor sends a tracked instance
    to Sentinel
-   SUMMARY:
    For both the initial step and the final step of each transfer process,
    the monitor sends a tracked instance to Sentinel
-   UNDEFINED: The
    tracking options are defined in the TRK parameter of the CFTPART command

#### <span id="trk_CFTPART"></span>CFTPART

**\[TRK = { ALL
| NO | SUMMARY | <u>UNDEFINED</u>}\]**

Specification of how much detail Transfer CFT provides Sentinel about transfers
with a partner. Transfer CFT sends detail about the transfers in the form of tracked
instances. The possible values of this parameter include:

-   NO: The monitor
    never sends tracked instances to Sentinel
-   ALL: For each
    step of each transfer process, the monitor sends a tracked instance to
    Sentinel
-   SUMMARY: For both
    the initial step and the final step of each transfer process, the monitor
    sends a tracked instance to Sentinel
-   UNDEFINED: The
    tracking options are defined in the TRK parameter of the CFTPART command

[Return to Command index](../../)