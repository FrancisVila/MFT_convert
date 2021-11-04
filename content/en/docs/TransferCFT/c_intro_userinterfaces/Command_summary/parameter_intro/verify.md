{
    "title": "verify",
    "linkTitle": "verify",
    "weight": "3710"
}<span id="verify"></span>

### <span class="mc-variable System.Title variable">verify</span>

#### LISTCOM

\[VERIFY = { YES | <span style="text-decoration: underline;">NO</span>
}\]

Request to verify the validity of each record in the file at the time
it is listed or displayed.

#### CFTTCP

\[VERIFY = {<span style="text-decoration: underline;">0</span>
| n } \]

Option to verify the partner number (DIALNO) on an incoming connection
request (the first "n" digits of the caller number are checked).

If VERIFY = 0 no verification is performed.

#### CFTSSL DIRECT=SERVER

\[VERIFY = { NONE | <span style="text-decoration: underline;">REQUIRED</span>
| OPTIONAL } \]

-   NONE: Only the server must be authenticated. 
-   REQUIRED: The server and the client must be authenticated.
-   OPTIONAL: Requests mutual authentication, but even if the client does not send a valid certificate the handshake is successful.

#### CFTSSL DIRECT=CLIENT

The DIRECT=CLIENT VERIFY options are available as of <span class="mc-variable axway_variables.Component_Long_Name variable">Transfer CFT</span> 3.3.2 SP2.

\[VERIFY = { <u>NONE</u> | REQUIRED
| OPTIONAL | ENFORCED } \]

-   ENFORCED: Ensures client authentication with the server. During the handshake, if the server does not ask for the client certificate, then the transfer fails.
-   OPTIONAL and REQUIRED: The same as NONE (for backward compatibility), but should not be used.
-   NONE: Only the server must be authenticated.

 

Example 1

This example demonstrates the use of the client <span class="code">NONE</span> value.

CFTSSL type=client, verify=none and CFTSSL type=server, verify=none

<img src="/Images/TransferCFT/verify2.png" class="mediumWidth" />

Example 2

This example demonstrates the use of the client <span class="code">ENFORCED </span>value.

CFTSSL type=client, verify=ENFORCED and CFTSSL type=server, verify=required

<img src="/Images/TransferCFT/verify1.png" class="mediumWidth" />

 

Example 3

This example demonstrates a different use of the <span class="code">ENFORCED </span>value. When acting as a client, <span class="code">ENFORCED </span>enables Transfer CFT to cancel a transfer if the server does not require the client authentication. Here, the transfer fails with diagi 260 due to the fact that the client requires authentication:

CFTSSL type=client, verify=ENFORCED and CFTSSL type=server, verify=NONE

[Return to Command index](../../)
