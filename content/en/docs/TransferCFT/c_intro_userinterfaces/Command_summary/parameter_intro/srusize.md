{
    "title": "srusize",
    "linkTitle": "srusize",
    "weight": "3310"
}<span id="srusize"></span>

### srusize

#### CFTPROT

**\[SRUSIZE     = { <u>32750</u>
| n} \]    ** { 254..32750}

Maximum size of NSDUs being sent (default = 32750). This parameter is negotiated with
the partner, rrusize parameter
if Transfer CFT{{< TransferCFT/componentshortname  >}}, the smallest value being adopted as the size of the NSDU
sent.

To transfer a record longer than SRUSIZE - 6, the segmentation operation
is implemented.

Refer to the Transfer CFT{{< TransferCFT/componentshortname  >}} *[*Protocols sections*](../../../../protocols_start_here)*
to learn more about optimizing these values.

[Return to Command index](../../)
