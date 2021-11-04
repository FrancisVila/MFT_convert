{
    "title": "tlvclear",
    "linkTitle": "tlvclear",
    "weight": "3510"
}<span id="tlvclear"></span>

### <span class="mc-variable System.Title variable">tlvclear</span>

#### CFTCAT, CFTCOM FILE

\[ TLVCLEAR = { 0...100
} \]

Fill level below which an alert ceases. This value is a percentage of filling, where 0% indicates the file is empty and 100% that it is full. Overall, the TLV parameters enable <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> to
issue alerts when a critical CAT or COM threshold is reached.

This
alert generates 2 actions:

-   Sends a message
    to the LOG
-   Executes
    a batch to react to the alert, the [TLVWEXEC](../tlvcexec)
    parameter

Default values:

-   CFTCAT: The default is equal to [TLVWARN](../tlvwarn) - 10.
-   CFTCOM FILE: The default is equal to [TLVWARN](../tlvwarn) - 20.

[Return to Command index](../../)