{
    "title": "format",
    "linkTitle": "format",
    "weight": "1260"
}<span id="format"></span>

### format

<span id="format_CFTLOG"></span>

#### CFTLOG

\[FORMAT =
| V24 \]

Optional parameter. Indicates the format for log messages.

-   **V23** (Default value): The Identifier’s
    length is truncated to 8 characters.
-   <span style="font-weight: bold;">V24</span>: The complete Identifier is displayed.
    The length of the Identifier can be up to 32 characters. Some messages
    related to a transfer includes the IDTU (Local transfer counter identifier)
    value.

<span id="format_CFTACCNT"></span>

#### CFTACCNT

\[FORMAT = <span style="text-decoration: underline;">V23</span>
| V24 \]

Optional parameter. The FORMAT parameter indicates whether the former
record structure should be used (V23 values for compatibility reasons)
or if the new structure is to be applied (V24 values).

-   <span style="font-weight: bold;">V23 </span>(Default value)
-   V24

<span id="format_CFTEXIT"></span>

#### CFTEXIT

\[ FORMAT = { string } \]

Indicates the file format of the communication area for an exit list. The possible values are 1, 2 C, T, J or X, where <span class="code">1 </span>is the default.

Example

##### Format 1

Displays using the same format as in <span class="mc-variable header_footer_variables.hf_long_product_name variable">Transfer CFT</span> 3.5 and lower, though phase and phasestep no longer display.

##### Format 2


|  Type  |  V24 length  |  V23 length  |  Description  |
| --- | --- | --- | --- |
|  CHAR  |  1  |  1  |  'L': start of record marker  |
|  CHAR  |  1  |  1  |  SEND/RECV flag  |
|  CHAR  |  1  |  1  |  STATE  |
|  CHAR  |  1  |  1  |  PHASE  |
|  CHAR  |  1  |  1  |  PHASESTEP  |
|  CHAR  |  64  |  8  |  Send partner (PART)  |
|  CHAR  |  64  |  8  |  Receive partner (PART)  |
|  CHAR  |  32  |  8  |  IDF file identifier  |
|  CHAR  |  8  |  8  |  IDT transfer identifier  |
|  CHAR  |  10  |  10  |  Number of records  |
|  CHAR  |  512  |  64  |  Filename  |
|  CHAR  |  3  |  3  |  Transfer priority  |
|  CHAR  |  8  |  8  |  Date of submission to catalog  |
|  CHAR  |  8  |  8  |  Time submitted to catalog, or time of last modification  |
|  CHAR  |  512  |  80  |  User parameter (PARM)  |
|  CHAR  |  32  |  15  |  Send USER  |
|  CHAR  |  32  |  15  |  Receive USER  |
|  CHAR  |  160  |  160  |  Local user parameter  |
|  CHAR  |  3  |  3  |  Diagi  |
|  CHAR  |  64  |  8  |  Diagp  |


##### Format C: CSV - Comma Separated Value

Each field is separated by a comma.

For example: <span class="code">S,X,X,X,MARTIN,PARIS,BIN,L1111482,2,,128,20191211,11481147,,,,,0,CP NONE</span>

##### Format T: TSV - Tab Separated Value

Each field is separated by a tab.

##### Format J: JSON

##### Format X: XML

                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    

[Return to Command index](../../)
