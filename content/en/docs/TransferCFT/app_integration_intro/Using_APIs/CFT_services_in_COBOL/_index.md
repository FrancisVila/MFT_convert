{
    "title": "Using services in COBOL",
    "linkTitle": "Using services in COBOL",
    "weight": "330"
}# <span id="Using_CFT_services_in_COBOL__Start_here"></span>About <span>Transfer CFT</span> services in COBOL



This book begins with <span>this topic</span>

which provides information about using the <span>Transfer CFT</span> services in COBOL.



The programming interface is implemented by the calling application

module link, with the <span>Transfer CFT</span> interface function module or modules.



The library of modules supplied provides everything programmers can

require.



This library also contains a programming example and the following COPY

CLAUSE: CFTAPI

to be included in the application which uses the <span>Transfer CFT</span> programming

interfaces.



## <span id="Call Syntax"></span>Call syntax



<table data-cellspacing="0">
<tbody>
<tr>
<td>CALL <span>CFTx</span> USING &lt;verb&gt;

&lt;blk&gt;

&lt;param&gt; &lt;rc&gt;</td>
</tr>
</tbody>
</table>



Where:



-   CFTx indicates:



&gt; -   CFTI:

&gt;     <span>Transfer CFT</span> catalog querying services

&gt;

&gt; 

&gt;

&gt; -   CFTU:

&gt;     transfer services with syntax analysis

&gt; -   CFTC:

&gt;     transfer services without syntax analysis



-   &lt;verb&gt; is the  command

    you want to process

-   &lt;blk&gt; is the internal control block

-   &lt; is a character string of

    variable length that contains the function parameters&gt;param

-   &lt;rc&gt; is the return code



The variables described in this documentation are defined in the <span>cftapi.cop</span> file supplied in the library

of delivered modules. The programming example and the corresponding COPY

files are shipped with the product.



## Return codes



The return codes are returned by the programming interfaces in the form

of mnemonics.



<table data-cellpadding="0" data-cellspacing="0">
<tbody>
<tr>
<td data-valign="top"></td>
<td data-valign="top"><span><strong>Note</strong></span></td>
<td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">It is strongly recommended that you test the return codes of services

provided by the <span>Transfer CFT</span> programming interfaces through mnemonics,

the corresponding values being able to <em>change without notice</em>.</td>
</tr>
</tbody>
</table>



The return codes are listed in the <span>cftapi.cop</span>

source file.

