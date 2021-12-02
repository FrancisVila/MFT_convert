{
    "title": "Transfer control commands",
    "linkTitle": "Transfer control commands",
    "weight": "170"
}This topic describes the transfer control commands and provides a link
to more information on these commands. The transfer control commands can
be used to:

-   Interrupt a transfer
    in process
-   Activate or reactivate
    a suspended or held transfer
-   Delete a transfer
    request
-   Submit, or resubmit,
    an end-of-transfer procedure where the transfer in the T state
-   Declare that the
    processing following a transfer is completed

The following table describes the commands associated with these actions.

The parameters relative to these commands determine the transfer selection
criteria, catalog entries, these commands relate to.

The transfer control commands modify the state of the transfers in the
Transfer CFT catalog. This state can be queried by the [LISTCAT](../../../c_intro_userinterfaces/about_cftutil/monitoring_cftutil_intro/listcat_command) command,
both before and after the control command is executed. The meaning of
these states is indicated in the next topic, Transfer
states.
