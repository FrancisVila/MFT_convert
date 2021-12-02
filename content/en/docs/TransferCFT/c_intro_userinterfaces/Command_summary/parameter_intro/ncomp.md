{
    "title": "ncomp",
    "linkTitle": "ncomp",
    "weight": "2120"
}<span id="ncomp"></span>

### ncomp

#### CFTSEND, CFTRECV, SEND, RECV

\[NCOMP = { 0 | 15 }\]

PeSIT D CFT profile, PeSIT E

Compression of on-line data requested.

This parameter is used when the value of the SCOMP or RCOMP parameter
of the CFTPROT object is too high for the file type.

The authorized values and the default values for the NCOMP parameter
are the same as for the SCOMP or RCOMP parameter of the CFTPROT object.
For a transfer, the combination of the values taken for these two parameters
is used as a basis for the on-line data compression protocol negotiation.

[Return to Command index](../../)
