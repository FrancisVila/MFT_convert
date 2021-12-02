{
    "title": "File  exit examples",
    "linkTitle": "File exit examples",
    "weight": "340"
}This topic provides examples of file exits and the parameter values
for these exits.

### File type exit parameter settings

<span id="User_program"></span>

### User program

Two user functions are defined in the example below. The IDF is used
to select one of the functions in the exfini initialization function.

The EXFxmp1 user functions:

-   Take charge of
    file-access
-   Take control at
    each step
-   Send 50 records
    ("!!!!! AZERTYUIOP !!!!!...") of 80 bytes
-   Interrupt the
    transfer (ret1 = 9) after 4 consecutive transfers

The EXIT task is deactivated after 5 minutes inactivity (WAITTASK =
5). After de-activation, it is again possible to start a transfer successfully
(the global variable nbsend is reinitialized to 0 on reactivation of the
task).

The EXFxmp2 user function:

-   Does not take charge
    of file access
-   Sends the EXFXMP1.C
    file (in the active directory)
-   Replaces the first
    byte of each non empty record with the ‘?’ character

This sample is delivered with the {{< TransferCFT/componentshortname  >}} product.
Refer to the **exfxmp2.c** header
in the delivered samples.
