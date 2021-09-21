{
    "title": "state",
    "linkTitle": "state",
    "weight": "3410"
}### <span id="state"></span>state

#### <span id="state_CFTRECV"></span>CFTRECV, <span id="state_CFTSEND"></span>CFTSEND, RECV, SEND

**\[STATE = { DISP
| HOLD | KEEP}\]**

Defines the transfer request state:

-   DISP:
    the request is saved in the "D" state (at disposal) in the catalog;
    this state corresponds to an "immediate" transfer (i.e. one
    which is executed as soon as possible, given time slot and parallel transfer
    constraints, etc.)
-   HOLD:
    the request is saved in the "H" state in the catalog; this state
    corresponds to a deferred transfer. The transfer is executed later:
-   either
    on acceptance of a remote receive request
-   or
    as a result of a local START command having changed this transfer to the
    available state (‘D’),
-   KEEP:
    the request is saved in the "K" state in the catalog; this state
    corresponds to deferred transfer: the transfer can only be executed later
    as a result of a local START command having changed this transfer to the
    available state

#### LISTCAT, DELETE, START, KEEP, HALT, RESUME, SUBMIT, END, DISPLAY

**\[STATE = {\* | C | CDHKTX } \]**

Select one of the following transfer states:

-   **\***

<!-- -->

-   **C**
-   **CDHKTX**

#### CFTPART

**\[STATE = string \]**

State of the partner:

-   ACTIVEBOTH (default)- partner active
    in all modes
-   ACTIVEREQ - partner active in request
    mode only
-   ACTIVESERV - partner active in server
    mode only
-   NOACTIVE - partner not active

#### PKICER (PKIUTIL tool)

State is the status of an imported certificate.
If activated, it can be used by Transfer CFT. Options are:

-   Act - activated
-   Inact - deactivated

#### CFTCRON

**\[STATE = { <u>ACTIVE</u> | NOACTIVE } \]**

-   To activate CFTCRON, set the state=ACTIVE.
-   Use NOACTIVE to disable use of CFTCRON.

[Return to Command index](../../)