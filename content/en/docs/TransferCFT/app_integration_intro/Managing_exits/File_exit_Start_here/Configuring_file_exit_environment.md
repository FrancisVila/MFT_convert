{
    "title": "Configuring the environment",
    "linkTitle": "Configuring the environment",
    "weight": "350"
}# <span id="Title"></span><span id="Configuring_the_environment___File_exit"></span>Configure the environment

This topic describes how to configure the environment for a file
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

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>CFTSEND/CFRECV  <br/>ID = <i>identifier</i>,<br/>EXIT = <i>identifier</i>,<br/>...         </td>
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

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>CFTEXIT <br/>ID = identifier,<br/>TYPE = FILE,<br/>[FORMAT = { V23 
 | V24 }]<br/>[LANGUAGE = {COBOL | C},]<br/>[MODE = {REPLACE | CREATE | DELETE},]<br/>[PARM = string,]<br/>[PROG = {CFTEXIT | string},]<br/>[RESERV = {8192 | n},]<br/>[WAITTASK = {1441 | n}]         </td>
      </tr>
   </tbody>
</table>

Related topics

-   [CFTSEND](../../../../concepts/cft_configuration_concepts_start_here/default_send_template_concepts)
-   [CFTRECV](../../../../concepts/cft_configuration_concepts_start_here/default_receive_template_concepts)
-   [CFTEXIT](../../../../c_intro_userinterfaces/web_copilot_ui/conf_intro/cftexit)