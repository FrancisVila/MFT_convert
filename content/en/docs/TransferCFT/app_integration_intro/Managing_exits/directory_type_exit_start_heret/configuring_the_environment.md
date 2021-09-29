{
    "title": "Configuring the environment",
    "linkTitle": "Configuring the environment",
    "weight": "370"
}# <span id="Configuring_the_environment___directory_exit"></span>Configuring the environment



This topic describes how to configure the environment for a directory

type exit. Before you submit a directory type EXIT, you must customize

the following <span>Transfer CFT</span> objects:



-   [CFTPROT](#Defining_the_CFTPROT_object)

    defines both the application protocol type and profile

-   [CFTEXIT](#Defining_the_CFTEXIT_object)

    describes the EXIT environment and how this EXIT is activated



Each CFTEXIT object corresponds to an EXIT task. The number of EXIT

tasks of all types simultaneously active is limited to a number depending

on the operating system.



EXIT type directory tasks are activated in memory when <span>Transfer CFT</span>

is started and de-activated when the monitor is shut down.



## <span id="Defining_the_CFTPROT_object"></span>Defining the CFTPROT object



The parameters mentioned here are the ones that are specific to this

EXIT.



### Syntax



CFTPROT  

ID = identifier,  

...  

\[EXITA = identifier,..,\]  

....  

\[DYNAM = identifier,\]  

     ...



### Parameters



**[ID](../../../CFTUTIL/Parameter_index/id.htm) =

identifier**



Protocol identifier.



**\[[EXITA](../../../CFTUTIL/Parameter_index/exita.htm) =

identifier\]     **



Directory EXIT identifier.



To activate a directory type EXIT for the protocol considered, an EXIT

identifier of this type should be indicated. There can only be one directory

type EXIT task per protocol command.



The directory type EXIT identifier can include the symbolic variable

&amp;NPART:(EXITA = (&amp;NPART, ...) where NPART designates the remote

partner network name.



**[DYNAM](../../../CFTUTIL/Parameter_index/dynam.htm)  =

identifier**



Identifier of the dynamic partner in server mode.



The value of this identifier corresponds to that of the model [CFTPART](../../../CFTUTIL/Conf/CFTPART.htm)

object ID parameter.



## <span id="Defining_the_CFTEXIT_object"></span>Defining the CFTEXIT object



### Syntax



CFTEXIT  

ID = identifier,  

TYPE = ACCESS,  

\[FORMAT = { V23

| V24 }\]  

\[LANGUAGE = {COBOL | C},\]  

\[MODE = MODE,\]  

\[PARM = string,\]  

\[PROG = {CFTEXIT | string},\]  

\[RESERV = {1024 | n}\]



### Parameters



**[ID](../../../CFTUTIL/Parameter_index/id.htm) =

identifier**



Command identifier.



The value of this identifier corresponds to the identifier defined in

the EXITA parameter of the related CFTPROT object.



\[[FORMAT](../../../CFTUTIL/Parameter_index/format.htm)

= V23 | V24 \]



Optional parameter. Indicates the format

for the communication area.



-   <span>V23 </span>(Default value)

-   <span>V24</span>



**\[[LANGUAGE](../../../CFTUTIL/Parameter_index/language.htm)

= {COBOL | C}\]**



Language in which the user program is written.



The possible values are COBOL and C language.



<span>Transfer CFT</span> uses this attribute to exchange data with the program using

the EXIT via the structure best suited to the language in which it is

implemented.



**\[[PARM](../../../CFTUTIL/Parameter_index/parm.htm) =

string64\]**



Free user field.



**\[[PROG](../../../CFTUTIL/Parameter_index/prog.htm)  =

{CFTEXIT | string512}\]**



Name of the executable module associated with the EXIT task.



This module is built from the interface provided with <span>Transfer CFT</span> linked

to the program written by the user. In order to facilitate identification

of the associated module, it is advised to name it CFTEXIA.



\[[RESERV](../../../CFTUTIL/Parameter_index/reserv.htm)  =

{<u>1024</u> | n}\]    <span> {0 ...1024}    

</span>



Size of the working area reserved for the user.



This area is not used by the <span>Transfer CFT</span> interface. You can use it

to save data required for the processing of the program that you have

written. This area is de-allocated when the <span>Transfer CFT</span> interface de-selects

the file.



**[TYPE](../../../CFTUTIL/Parameter_index/type.htm) =

ACCESS**



EXIT type.

