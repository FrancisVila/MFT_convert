{
    "title": "Configure  the environment",
    "linkTitle": "Configuring the environment",
    "weight": "320"
}This topic describes how to configure the environment for a <span style="font-style: italic;">file
type exit</span>. Before you submit an exit, you must customize the following
<span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> objects:

-   CFTSEND: to define
    the parameters associated with the EXIT on sending the file
-   CFTTRECV: to define
    the parameters associated with the EXIT on receiving the file
-   CFTEXIT: to describe
    the EXIT environment and how this EXIT is activated

<span id="Defining_the_CFTSEND_CFTRECV_objects"></span>

### Defining the CFTSEND/CFTRECV objects

#### Syntax


    CFTSEND/CFRECV  
    ID = identifier,
    EXIT = identifier,
    ...

#### Parameters

**ID = <span style="font-style: italic;">identifier</span>**

File identifier.

**EXIT = <span style="font-style: italic;">identifier</span>**

File type EXIT identifier.

This EXIT parameter establishes the link with the CFTEXIT object described
below. The identifier can include the symbolic variables &IDF, &GROUP
et &PART.

<span id="Defining_the_CFTEXIT_object"></span>

### Defining the CFTEXIT object

#### Syntax


    CFTEXIT 
    ID = identifier,
    TYPE = FILE,
    [FORMAT = { V23 
     | V24 }]
    [LANGUAGE = {COBOL | C},]
    [MODE = {REPLACE | CREATE | DELETE},]
    [PARM = string,]
    [PROG = {CFTEXIT | string},]
    [RESERV = {8192 | n},]
    [WAITTASK = {1441 | n}]

Related topics

-   [CFTSEND](../../../../concepts/cft_configuration_concepts_start_here/default_send_template_concepts)
-   [CFTRECV](../../../../concepts/cft_configuration_concepts_start_here/default_receive_template_concepts)
-   [CFTEXIT](../../../../c_intro_userinterfaces/web_copilot_ui/conf_intro/cftexit)