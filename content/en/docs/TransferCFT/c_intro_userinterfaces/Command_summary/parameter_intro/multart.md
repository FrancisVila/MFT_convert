{
    "title": "multart",
    "linkTitle": "multart",
    "weight": "2070"
}### <span id="multart"></span>multart

#### CFTPROT

\[MULTART = { NO
| <u>YES</u> } \]

An option to group several records of the files sent in one FPDU.

-   YES:In sender mode yes is recommended
    if the partner supports multi-record FPDUs (default = yes). In receiver mode the Transfer
    CFT accepts multi-record FPDUs regardless of the value of this
    parameter.
-   NO: One FPDU contains
    only one record. Only applicable in sender mode.

[Return to Command index](../../)