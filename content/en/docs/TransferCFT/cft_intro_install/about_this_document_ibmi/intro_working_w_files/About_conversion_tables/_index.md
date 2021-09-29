{
    "title": "Conversion tables",
    "linkTitle": "Conversion tables",
    "weight": "210"
}This section describes how to use a conversion table in Transfer CFT Transfer CFT IBM i in the following sections:

-   Using a conversion table
-   Configuration sample

## Using conversion tables

During Transfer CFT operations conversion problems may occur when:

-   A file to be transferred contains various special characters:  
          |, !, \\, \`, #, ~, \[, \], ^, {, }, /, $ and £

<!-- -->

-   The transfer is performed between two heterogeneous systems with different character sets (CCSID) and the default conversion fails.

<!-- -->

-   The transfer is performed between international sites.

### Default values

The default EBCDIC character set used by Transfer CFT has code 297 (EBCDIC France).

The default ASCII character set used by Transfer CFT is not fully compatible with code 850 (IBM multilingual personal computer). For more information refer to the *Transfer CFT User Guide*. ADD LINK

Consequently, two files supplied in the production library are used to enter and create a conversion table in Transfer CFT:

-   TABEBAS: file to be used to convert EBCDIC into ASCII (generally for send operations)

<!-- -->

-   TABASEB: file to be used to convert ASCII into EBCDIC (generally for receive operations)

These two files can be modified by DFU (Option 18 in PDM - Member Management).

### Creating the conversion table

To create the actual conversion table, you must run the make\_tcd.c utility program after modifying the characters at fault: `call make_tcd.c parm('CFTPROD/tabaseb')`

The CFTPROD/tabaseb.x binary file is created: it constitutes the conversion table to be specified in the Transfer CFT configuration. The same applies to tabebas.x.

## Configuration sample

The following is a full Transfer CFT Transfer CFT IBM i configuration sample for a Windows system, which is a typical and frequent scenario.

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>Transfer CFT IBM i configuration</p>
<p>CFTXLATE MODE=REPLACE,</p>
<p>         ID=TABASEB,</p>
<p>         DIRECT=RECV,</p>
<p>         FNAME=CFTPROD/TABASEB.X</p>
<p>CFTXLATE MODE=REPLACE,</p>
<p>         ID=TABEBAS,</p>
<p>         DIRECT=SEND,</p>
<p>         FNAME=CFTPROD/TABEBAS.X</p>
<p> </p>
<p>CFTSEND MODE=REPLACE, ID=……..,</p>
<p>         XLATE=TABEBAS,</p>
<p>          …………………….</p>
<p> </p>
<p>CFTRECV MODE=REPLACE, ID=………,</p>
<p>         XLATE=TABASEB,</p>
<p>          …………………….</p>
<p> </p>
<p> </p>
<p>Transfer CFT WIN/NT configuration</p>
<p>============</p>
<p> </p>
<p>cftrecv  id       = …………,</p>
<p>        fcode    = binary,  /* to avoid needing conversion */</p>
<p>         …………………</p>
<p> </p>
<p>cftsend  id       = …………,</p>
<p>        fcode    = binary,  /* to avoid needing conversion */</p>
<p>         ………………….</p></td>
</tr>
</tbody>
</table>
