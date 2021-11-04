{
    "title": "nlrecl",
    "linkTitle": "nlrecl",
    "weight": "2220"
}<span id="nlrecl"></span>

### nlrecl

<span id="nlrecl_CFTSEND"></span>

#### CFTSEND, SEND

**\[NLRECL = { <u>FLRECL</u>** **<u>value</u>**
**| n}\]**

For records of:

-   fixed
    format (FRECFM = F) : size in bytes of the records of the receiver file
-   variable
    format (FRECFM = V) : maximum size in bytes of the records

When a file is sent, any record sent whose size is GREATER than the
size declared by NLRECL, is truncated to the value of NLRECL.

For records of fixed format (FRECFM=F), if the size of the records to
be sent is LESS than the value of NLRECL, these records are padded up
to the value of NLRECL:

-   By
    binary zeros (x00) when the local data is declared as binary FCODE = BINARY
-   By
    spaces when the local data are declared as alphanumeric with:
-   CODE = ASCII:
    the space character is then equal to x‘20’

ODETTE: For the ODETTE protocol, refer to the <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> Protocol
topics for more information on this parameter.

[Return to Command index](../../)