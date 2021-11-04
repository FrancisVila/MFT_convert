{
    "title": "fast",
    "linkTitle": "fast",
    "weight": "1040"
}### fast

#### SHUT

\[FAST = {<u>NO</u> | YES | KILL}\]

Type of shutdown:

-   YES: Immediate shutdown of <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span>.
    All the transfers in process are interrupted and change
    to the D state. No pending transfer is activated.

<!-- -->

-   NO: <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> completes all the transfers
    in process and shuts down. No new transfer is initialized.
-   KILL: Immediate <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> shutdown occurs
    but without updating the transfer states.

[Return to Command index](../../)
