{
    "title": "Manage the server ",
    "linkTitle": "Manage the server ",
    "weight": "240"
}# <span id="Using_the_command_line_interface__Start_here"></span>CFTUTIL command line interface



CFTUTIL is the command line interface for Transfer CFT. The Transfer

CFT utility is a program which can be activated in batch or interactive

mode. The CFTUTIL interface is able to translate Transfer CFT parameter

setting commands and operating commands.



## <span id="About_the_Command_line_interface_CFTUTIL"></span>Overview



All Transfer CFT actions are controlled

by a series of Transfer CFT commands. CFTUTIL makes it possible to create the working environment and configure

the Transfer CFT application, performing the following operations:



-   Transfer CFT configuration,

    which is the customization for a given operating environment

-   Transfer CFT use,

    which includes the initiation and monitoring of transfers



More precisely, with CFTUTIL you can:



-   Create and delete

    parameter, partner, catalog, log, and account files. Such operations can

    be performed only when the Transfer CFT is stopped.

-   Change and add

    to certain parameters.

-   View parameter,

    partner, catalog, log, and account files.

-   Send commands to

    Transfer CFT.



For a complete listing of all Transfer

CFT commands, a description of their function, and a link to the specific

command topic, refer to the [Command index](../Command_summary.htm).



### <span id="Command_syntax"></span>Command syntax



For each command, CFTUTIL checks the command syntax and enters the command. Refer to *[Typographical

conventions](../CFTUTIL/Parameter_index/typographical_conventions.htm)* for the Transfer CFT command syntax conventions used in this document.



### <span id="CFTUTIL_commands"></span>CFTUTIL command categories



The CFTUTIL commands can be divided into three categories:



-   Transfer CFT services

-   Querying and extracting

-   File management



When querying or extracting, the files read do not necessarily correspond

to the ones which Transfer CFT is currently using. The files

accessed can be selected for a CFTUTIL execution, using the CONFIG command.



The CONFIG command redefines the data media that the CFTUTIL utility

uses. A medium, in the Transfer CFT meaning of the term, refers to any data

medium or local communication means.



### CFTUTIL modes



CFTUTIL can be used in three different modes:



-   Command mode, for

    example:



<table data-cellspacing="0">
<tbody>
<tr>
<td>&gt; CFTUTIL SEND PART=PART1, IDF=IDF1,</td>
</tr>
</tbody>
</table>



-   Batch mode, for

    example:



<table data-cellspacing="0">
<tbody>
<tr>
<td>&gt; CFTUTIL #file.smp</td>
</tr>
</tbody>
</table>



-   Interactive line

    mode, for example:



<table data-cellspacing="0">
<tbody>
<tr>
<td>&gt; CFTUTIL</td>
</tr>
</tbody>
</table>
