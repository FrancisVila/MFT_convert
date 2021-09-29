{
    "title": "About exit lists",
    "linkTitle": "About exit lists",
    "weight": "320"
}# <span id="Exit_lists__Start_here"></span><span id="Exit_list_concepts"></span><span id="Using_the_Exit_List"></span>About exit lists



An exit list is an optional component supplied with certain Transfer

CFT products. The Exit list is a file exit designed to allow remote partners to consult

the <span>Transfer CFT</span> server's catalog. The <span>Transfer CFT</span>

Exit list is an EXIT used for consulting the catalog.



The Exit list is not supplied with all <span>Transfer CFT</span> products. In addition,

the form in which EXIT is delivered, as object, executable or other code,

depends on the specific product configuration.



<img src="exit_list.png"/>



The following section explains the high-level steps when using an exit

list.



### <span id="Set_the_exit_parameters"></span>1. Set the exit parameters



Activate the exit list by setting the parameters as shown in the example below.



Remote

requester partner



No specific parameter setting.



Server sender site



<table data-cellspacing="0">
<tbody>
<tr>
<td>CFTSEND  ID

= IDFexit,<br/>

IMPL = YES,<br/>

EXIT = IDExitList</td>
</tr>
</tbody>
</table>
<table data-cellspacing="0">
<tbody>
<tr>
<td>CFTEXIT  ID

= IDExitList,<br/>

LANGUAGE = C,<br/>

PARM = FileName,<br/>

RESERV = 16384,<br/>

PROG = FileExe</td>
</tr>
</tbody>
</table>
<table data-cellpadding="0" data-cellspacing="0">
<tbody>
<tr>
<td data-valign="top"></td>
<td data-valign="top"><span><strong>Note</strong></span></td>
<td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">We recommend that you use the value 16384 for the RESERV

and not modify this parameter value.</td>
</tr>
</tbody>
</table>



### <span id="Prepare_the_selection_criteria_file"></span>2. Prepare the selection criteria file



After you have set the parameters for the sender site,

load the <span>selection criteria</span> file.

The selection commands contained in this file are described in the section *Selection

criteria file*. You must load this file on the server **before**

requesting the catalog.



The LOGICAL name of the <span>Selection

criteria</span> must be the CFTEXIT command identifier. For z/OS environments, the correspondence between the physical name and the

logical name must be given by the JCL initiating <span>Transfer CFT</span>.



The name of the <span>Selection criteria</span>

file may be defined by  either the:



-   Physical name in

    the PARM parameter, *or*







-   Logical name, which

    must be the CFTEXIT object identifier



### <span id="Request_catalog"></span>3. Make a catalog request



After loading the file, you can make a catalog

request. When you make a file reception request, use the CFTSEND object

identifier that is associated with the Exit list as the IDF.



Example



<table data-cellspacing="0">
<tbody>
<tr>
<td>CFTUTIL

<p>RECV     PART

= &amp;part,<br/>

IDF = IDFexit</p></td>
</tr>
</tbody>
</table>



The server:



-   Recognizes the

    request for the catalog list using the transfer IDF

-   Processes the <span>Selection criteria</span> file

-   Consults the catalog

-   Sends the entries

    selected from the catalog to the requesting partner as fixed-length records.

    The selection implicitly chooses only catalog entries concerning this

    partner. This means that

    the Exit list does not allow a partner to consult the transfers sent to

    other partners.

