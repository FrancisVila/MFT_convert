{
    "title": "Using services in COBOL",
    "linkTitle": "Using services in COBOL",
    "weight": "330"
}This book begins with this topic
which provides information about using the Transfer CFT services in COBOL.

The programming interface is implemented by the calling application
module link, with the Transfer CFT interface function module or modules.

The library of modules supplied provides everything programmers can
require.

This library also contains a programming example and the following COPY
CLAUSE: CFTAPI
to be included in the application which uses the Transfer CFT programming
interfaces.

## <span id="Call Syntax"></span>Call syntax

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td>CALL <span>CFTx</span> USING &lt;verb&gt;
&lt;blk&gt;
&lt;param&gt; &lt;rc&gt;</td>
</tr>
</tbody>
</table>

Where:

-   CFTx indicates:

> -   CFTI:
>     Transfer CFT catalog querying services
>
> <!-- -->
>
> -   CFTU:
>     transfer services with syntax analysis
> -   CFTC:
>     transfer services without syntax analysis

-   &lt;verb> is the  command
    you want to process
-   &lt;blk> is the internal control block
-   &lt; is a character string of
    variable length that contains the function parameters>param
-   &lt;rc> is the return code

The variables described in this documentation are defined in the cftapi.cop file supplied in the library
of delivered modules. The programming example and the corresponding COPY
files are shipped with the product.

## Return codes

The return codes are returned by the programming interfaces in the form
of mnemonics.

<table data-cellpadding="0" data-cellspacing="0">
<tbody>
<tr class="odd">
<td data-valign="top"></td>
<td data-valign="top"><span><strong>Note</strong></span></td>
<td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">It is strongly recommended that you test the return codes of services
provided by the <span>Transfer CFT</span> programming interfaces through mnemonics,
the corresponding values being able to <em>change without notice</em>.</td>
</tr>
</tbody>
</table>

The return codes are listed in the cftapi.cop
source file.
