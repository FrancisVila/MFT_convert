{
    "title": "notify",
    "linkTitle": "notify",
    "weight": "2230"
}<span id="notify"></span>

### notify

#### CFTLOG, CFTSEND, **<span id="notify_CFTRECV"></span>**CFTRECV, SEND, RECV

NOTIFY = {string see
below}

Defines the destination of the operator
messages selected according to the value of the OPERMSG parameter as follows:

-   All
    log file messages if defined in the CFTLOG object
-   For
    all transfer messages with the IDF if defined in CFTSEND or CFTRECV
-   For
    all messages from a transfer that was requested with the command if used
    in SEND or RECV

The value of this parameter is a left aligned 8-character string.

The destination of these messages may be, according to the system:

-   the
    {{< TransferCFT/componentshortname >}} "submitter" corresponding to the standard
    output associated with the {{< TransferCFT/componentshortname >}} (the submittal screen,
    for example)  
    The value of the NOTIFY parameter must be then be set to ‘ ’ (8 blank
    characters)
-   an
    operator console  
    The NOTIFY parameter value must begin by the 2 characters OP

<!-- -->

-   a computer
    user  
    The value of the NOTIFY parameter indicates the user system identifier
    according to the format "xxxxxxxx"

The following table indicates the possible recipients for each system
involved:

-   YES indicates that the corresponding
    recipient type exists
-   NO indicates the corresponding recipient
    type does not exist

The following table indicates, for each system, the default values of
the NOTIFY parameter supported. The value ‘ ’ corresponds to 7 blank characters.

In the operator console, the possible choices are indicated in
the following table. If ‘OP’ is indicated for the interpreted characters,
only these two characters (OP) are interpreted; the following characters
are not significant.

For the user:

[Return to Command index](../../)
