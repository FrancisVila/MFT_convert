{
    "title": "CFTXLATE  - Conversion tables",
    "linkTitle": "CFTXLATE - Conversion tables",
    "weight": "320"
}This topic describes how to define a translation table to be used during
a transfer. There are two ways to generate a translation table, either using the FNAME parameter or the TABLE parameter as described below.

Related
topics

-   Command syntax
    [CFTXLATE](../../../command_summary#CFTXLATE)
-   Object concepts
    [Conversion
    tables](../../../../concepts/cft_configuration_concepts_start_here/translation_table_concepts)

Use this object to define translation tables between 2
alphabets for:

-   Transfer
    direction
-   File
    data code type (FCODE: ASCII or EBCDIC)
-   Data
    network code type (NCODE: ASCII or EBCDIC)


| Parameter  | Description  |
| --- | --- |
|  <a href="../../../command_summary/parameter_intro/direct">DIRECT</a>  |  Transfer direction for which the table applies:<br/> • SEND: translation table for send transfers<br/> • RECV: translation table for receive transfers<br/> • BOTH: translation table which can be used for send transfers and receive transfers<br/>If the value of the parameter is BOTH, the data read in the file allows a translation table for send transfers (SEND) to be created. The translation table for receive transfers (RECV) is deduced automatically.<br/>To provide for bijection (i.e. any character of the source alphabet translated into the target alphabet, and then re-translated from the target alphabet into the source alphabet, takes up its initial value again), the table has to contain 256 different values. It is not essential to strictly comply with this principle for transfer applications using reduced alphabets.  |
|  <a href="../../../command_summary/parameter_intro/fcode">FCODE</a>  |  Data code of the file sent.  |
|  <a href="../../../command_summary/parameter_intro/fname">FNAME</a>  |  Name of the file containing the description of the translation table.<br/>This file must have a sequential organization. Examples of such files are given with the various products (refer to the Operations Guide specific to each system).  |
|  <a href="../../../command_summary/parameter_intro/id">ID</a>  |  Translation table identifier.<br/>Several CFTXLATE commands may have the same identifier, if the values of DIRECT, FCODE or NCODE are different.  |
|  <a href="../../../command_summary/parameter_intro/ncode">NCODE</a>  |  Code of data sent over the network.  |
| TABLE  | A digital representation of the table as a hexadecimal string.  |


**Example using FNAME**

In this example, the Transfer CFT internal translation tables (identifier
DEFAUT) are replaced by the user tables, which can be used in both transfer
directions.

For send transfers, the Transfer CFT translates
from ASCII into EBCDIC and for receive transfers, from EBCDIC into ASCII.
The ASCII to EBCDIC table is defined in the file ATOE and the EBCDIC to
ASCII table is deduced automatically.

Example of generating a translation table using the TABLE parameter

You can use the following `CFTXLATE `command with the TABLE parameter, instead of FNAME, to generate an ASCII CP437 to EBCDIC CP1047 translation table.

Or alternatively, you can use the following `CFTXLATE `command to generate an ASCII CP850 to EBCDIC CP1047 translation table.
