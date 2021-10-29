{
    "title": "Configure  the environment",
    "linkTitle": "Configuring the environment",
    "weight": "350"
}This topic describes how to configure the environment for a file
type exit. Before you submit an exit, you must customize the following
Transfer CFT objects:

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
      <tr class="odd">
         <td>CFTSEND/CFRECV  <br />
ID = <em>identifier</em>,<br />
EXIT = <em>identifier</em>,<br />
...         </td>
      </tr>
   </tbody>
</table>

#### Parameters

**ID = identifier**

File identifier.

**EXIT = identifier**

File type EXIT identifier.

This EXIT parameter establishes the link with the CFTEXIT object described
below. The identifier can include the symbolic variables &IDF, &GROUP
et &PART.

### <span id="Defining_the_CFTEXIT_object"></span>Defining the CFTEXIT object

#### Syntax

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>CFTEXIT <br />
ID = identifier,<br />
TYPE = FILE,<br />
[FORMAT = { V23
| V24 }]<br />
[LANGUAGE = {COBOL | C},]<br />
[MODE = {REPLACE | CREATE | DELETE},]<br />
[PARM = string,]<br />
[PROG = {CFTEXIT | string},]<br />
[RESERV = {8192 | n},]<br />
[WAITTASK = {1441 | n}]         </td>
      </tr>
   </tbody>
</table>

Related topics

-   [CFTSEND](../../../concepts/cft_configuration_concepts_start_here/default_send_template_concepts)
-   [CFTRECV](../../../concepts/cft_configuration_concepts_start_here/default_receive_template_concepts)
-   [CFTEXIT](../../../c_intro_userinterfaces/about_cftutil/configuring_cft_start_here/cftexit)
