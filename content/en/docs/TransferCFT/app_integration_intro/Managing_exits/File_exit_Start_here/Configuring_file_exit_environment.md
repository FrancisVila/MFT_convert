{
    "title": "Configuring the environment",
    "linkTitle": "Configuring the environment",
    "weight": "350"
}# <span id="Title"></span><span id="Configuring_the_environment___File_exit"></span>Configure the environment



This topic describes how to configure the environment for a <span>file

type exit</span>. Before you submit an exit, you must customize the following

<span>Transfer CFT</span> objects:



-   CFTSEND: to define

    the parameters associated with the EXIT on sending the file

-   CFTTRECV: to define

    the parameters associated with the EXIT on receiving the file

-   CFTEXIT: to describe

    the EXIT environment and how this EXIT is activated



### <span id="Defining_the_CFTSEND_CFTRECV_objects"></span>Defining the CFTSEND/CFTRECV objects



#### Syntax



<table data-cellspacing="0">
<tbody>
<tr>
<td>CFTSEND/CFRECV  <br/>

ID = <em>identifier</em>,<br/>

EXIT = <em>identifier</em>,<br/>

...</td>
</tr>
</tbody>
</table>



#### Parameters



**ID = <span>identifier</span>**



File identifier.



**EXIT = <span>identifier</span>**



File type EXIT identifier.



This EXIT parameter establishes the link with the CFTEXIT object described

below. The identifier can include the symbolic variables &amp;IDF, &amp;GROUP

et &amp;PART.



### <span id="Defining_the_CFTEXIT_object"></span>Defining the CFTEXIT object



#### Syntax



<table data-cellspacing="0">
<tbody>
<tr>
<td>CFTEXIT <br/>

ID = identifier,<br/>

TYPE = FILE,<br/>

[FORMAT = { V23

| V24 }]<br/>

[LANGUAGE = {COBOL | C},]<br/>

[MODE = {REPLACE | CREATE | DELETE},]<br/>

[PARM = string,]<br/>

[PROG = {CFTEXIT | string},]<br/>

[RESERV = {8192 | n},]<br/>

[WAITTASK = {1441 | n}]</td>
</tr>
</tbody>
</table>



Related topics



-   [CFTSEND](../../../GUI/Concepts/Default_SEND_template_concepts.htm)

-   [CFTRECV](../../../GUI/Concepts/Default_receive_template_concepts.htm)

-   [CFTEXIT](../../../CFTUTIL/Conf/CFTEXIT.htm)

