{
    "title": "Connection and maximum transfer troubleshooting",
    "linkTitle": "Connection / maximum transfer troubleshooting",
    "weight": "250"
}This section provides transfer examples that demonstrate parameter dependencies and typical log outputs, including errors, which you may encounter when using similar values. The goal is to understand the effect of parameter combinations, and be able to adapt settings to your particular needs.

The following examples show the output from both the server and requester sides.

-   <a href="#Example:4" class="MCXref xref">Example: the number of transfers exceeds the CNXINOUT</a>
-   <a href="#Example:3" class="MCXref xref">Example: MAXCNX is greater than MAXTRANS</a>
-   <a href="#Example:4" class="MCXref xref">Example: the number of transfers exceeds the CNXINOUT</a>
-   <a href="#Example:5" class="MCXref xref">Example: MAXCNX greater than MAXTRANS with session limit</a>

See <a href="../session_troubleshooting" class="MCXref xref">Session related troubleshooting</a> for session related output.

See the <a href="../faq" class="MCXref xref">Frequently asked questions</a> for common questions and answers on parameter usage, license keys, and so on.

## Remote (partner) diagnostic codes

When troubleshooting, remember that if the [DIAG](../../../troubleshoot_intro/messages_and_error_codes_start_here/diagi_diagnostic_codes) is greater than 500, it refers to a remote issue. To find the actual DIAG, subtract 500 from the displayed code. If the DIAG is 962, for example, the issue is a remote problem corresponding to DIAG 462 (no data sent on network).

<span id="Example:"></span>

## Examples

<span id="Example:4"></span>

### Example: the number of transfers exceeds the CNXINOUT

##### **Scenario 1 - Requester configuration**

In this example, the number of transfers exceeds the CNXINOUT value defined on the requester side.

**Requester output**

**Server output**

No message on server side.

##### **Scenario 2**

Here the number of transfers exceeds the CNXINOUT value defined on the server side.

**Server output**

**Requester output**

<span id="Example:3"></span>

### Example: MAXCNX is greater than MAXTRANS

MAXCNX is greater than MAXTRANS on the requester side, and there are more than MAXTRANS transfers to be processed.

**Incoming session**

For the server's incoming session the extra transfer(s) is rejected with an error.

**Server output**

**Requester output**

**Outgoing session**

When the requester wants to perform more than MAXTRANS transfers:

<span id="Example:4"></span>

### Example: MAXCNX is less than MAXTRANS

MAXCNX is less than the MAXTRANS value on the requester side, and you want to perform more than MAXCNX transfers (for example MAXCNX = 2, MAXTRANS= 5).

**Scenario 1**

**Requester output**

**Server output**

**Scenario 2**

MAXCNX is less than the MAXTRANS value on the server side, and you want to perform more than MAXCNX transfers on the requester side (for example MAXCNX = 2, MAXTRANS= 5).

**Requester output**

**Server output**

<span id="Example:5"></span>

### Example: MAXCNX greater than MAXTRANS with session limit

In this example, we have a distribution list with 5 partners, which shows an example of when you may want to have a MAXCNX greater than the MAXTRANS value.

**Scenario 1**

The transfers are executed quickly, in rapid succession because {{< TransferCFT/componentlongname  >}} is not limited by the session. As soon as the first 3 transfers are completed, the 2 remaining are executed immediately.

> **Note:**
>
> Remember one session is kept for incoming connections, so in this case only two sessions were used.

MAXTRANS=3, MAXCNX=6, DISCTD=120 (seconds session is still open)

**Scenario 2**

In Scenario 2 Transfer CFT is limited by the session, meaning that the same 5 partner transfers as in Scenario 1 now take over 120 seconds (the DISCTD time defined to keep the session open).

> **Note:**
>
> DISCTD has an effect on latency.

MAXTRANS=6, MAXCNX=3, DISCTD=120 (seconds session is still open)

Related topics

-   [About parallel transfers](../)
-   [FAQ and troubleshooting](../faq)
