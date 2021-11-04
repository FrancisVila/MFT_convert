{
    "title": "scredit",
    "linkTitle": "scredit",
    "weight": "3090"
}<span id="scredit"></span>

### <span class="mc-variable System.Title variable">scredit</span>

#### CFTPROT

**\[RCREDIT     = {4
| n}\] <span style="font-weight: normal;">    {1...999}</span>**

Odette protocol

Value of the "credit" (expressed as a number of "DATA"
messages) proposed by <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> when it is the requester. Enter a value
between 1 and 999. The Default value is <span style="font-weight: bold;">4</span>.

<span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> is authorized to send a number of "DATA" protocol
messages equal to the result of the negotiation (performed when the protocol
session is established), before waiting for a new "credit" to
be sent by the server.

 

[Return to Command index](../../)
