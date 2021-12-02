{
    "title": "After a transfer interruption",
    "linkTitle": "Stage After a transfer interruption",
    "weight": "370"
}This event occurs if there is a:

-   Mains supply cut
    or protocol fault
-   Request by one
    of the partners (HALT or KEEP command)
-   Request by the
    user function during one of the previous stages (ret1 = 9)

If the user function manages file accessing, it must de-allocate the
file and save the zwork working area for subsequent restarting purposes,
before handing back control to {{< TransferCFT/componentshortname  >}}.

### Fields to define

### Field values
