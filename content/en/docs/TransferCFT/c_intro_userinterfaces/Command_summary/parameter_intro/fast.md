{
    "title": "fast",
    "linkTitle": "fast",
    "weight": "1050"
}### fast

#### SHUT

\[FAST = {<u>NO</u> | YES | KILL}\]

Type of shutdown:

- YES: Immediate shutdown of {{< TransferCFT/componentshortname >}}.
    All the transfers in process are interrupted and change
    to the D state. No pending transfer is activated.

<!-- -->

- NO: {{< TransferCFT/componentshortname >}} completes all the transfers
    in process and shuts down. No new transfer is initialized.
- KILL: Immediate {{< TransferCFT/componentshortname >}} shutdown occurs
    but without updating the transfer states.

[Return to Command index](../../)
