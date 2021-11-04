{
    "title": "End-of-transfer  exit example",
    "linkTitle": "End-of-transfer exit example",
    "weight": "370"
}This page introduces the following end-of-transfer elements, Parameter
settings, Structure
in C language, User
program in C.

Parameter settings


    /* CFTPARM Card */
    cftparm id = idparm0          ,
            
     exiteot = exe1          ,
    .....
    .....



    /* CFTEXIT Card */
    cftexit id = exe1          ,
         language = c          ,
         type = exec          ,
         prog = cftexie         ,
         parm = exe1          ,
         mode = replace

Structure in C

Refer to the <span style="font-weight: bold;font-family: 'Courier New', monospace;">exeus.h</span>
delivered with the <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> product samples.

User program in C

Refer to the <span style="font-weight: bold;font-family: 'Courier New', monospace;">exexmp1.c</span>
delivered with the <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> product samples.
