{
    "title": "fblksize",
    "linkTitle": "fblksize",
    "weight": "1050"
}<span id="fblksize"></span>

### fblksize

<span id="fblksize_CFTFILE"></span>

#### CFTFILE

**\[FBLKSIZE = {<u>see
table below</u> | n}\]  **{0...32768}

According to TYPE/**OS**

Defines the block size, in bytes, of the file to be created.

The table below indicates, for each system, the default value supported
according to the type of file to be created.When the default
value of the block size of the file to be created is "no" in the following table, the
FBLKSIZE parameter does not need to be defined.

#### CFTRECV, RECV

**\[FBLKSIZE = n \]              **{0..62563}

This parameter, in bytes, controls the "blocking factor" of
the receiver file records: according to the system, it defines the disk
block size and/or the file input/output buffer size.

<span id="fblksize_CFTSEND"></span>

#### CFTSEND, SEND

\[FBULKSIZ = n\]   {
0...65536}

Block size of file to be sent.

Typically you do not need to define this parameter as {{< TransferCFT/componentshortname  >}} is
able to locate the value for the file to be sent. This real value is then
taken into account when activating the transfer.

[Return to Command index](../../)
