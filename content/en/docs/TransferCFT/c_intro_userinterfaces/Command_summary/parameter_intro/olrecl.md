{
    "title": "olrecl",
    "linkTitle": "olrecl",
    "weight": "2450"
}### <span id="olrecl"></span>olrecl

#### COPYFILE

**\[OLRECL = {<u>see the comment</u>
| n}\]  **{0..32768}

Output file record length.

For the following record formats, OLRECL is expressed in bytes:

-   Fixed format (ORECFM
    = F): output file record length
-   Variable format
    (FRECFM = V): maximum record length

If OLRECL is:

-   Less than the actual
    length of the record to be written, the record is then truncated to the
    supplied length
-   Greater than the
    actual length of the record to be written and if:
-   The file is of
    fixed format (ORECFM=F), the record is padded with spaces, i.e. according
    to the value of the OCODE parameter: x‘20’ if OCODE = ASCII, x‘40’ if
    OCODE = EBCDIC
-   File not of fixed
    format  
    This parameter is only meaningful when creating the file

Default values  

If the output file:

-   Does not exist,
    value of ILRECL
-   Exists:
    -   For systems handling
        the file record concept: actual size of the output file records
    -   For the systems below not handling this concept:  
        <table cellspacing="0" width="90%">   <col/>   <col/>      <tr valign="middle">         <td colspan="1" rowspan="1" width="26%">            <p><b>Windows</b> </p>         </td>         <td colspan="1" rowspan="1" width="74%">            <p>512.</p>         </td>      </tr>      <tr valign="middle">         <td colspan="1" rowspan="1" width="26%">            <p><b>UNIX</b></p>         </td>         <td colspan="1" rowspan="1" width="74%">            <p>512 for text files (OTYPE=T, X or O).<br/>	4096 for binary or variable files (OTYPE={B | V}).</p>         </td>      </tr></table>

 

[Return to Command index](../../)
