{
    "title": "Defining  functions",
    "linkTitle": "Defining functions",
    "weight": "350"
}<span id="About_the_Functions"></span>This topic describes the directory exit task components and functions.
A directory EXIT task comprises two modules:

-   The interface supplied
    with {{< TransferCFT/componentshortname >}}
-   The user program

The interface is written in C language. The main entry point of the
EXIT task, the principle function in C language, is located in the interface.
You do not need to know how this interface works to write a user program.

The user program can be written in C or in COBOL. When you use COBOL,
you must comply with C-COBOL interfacing rules.

Once you have written the user program, the two modules are linked together
with the appropriate system libraries. The result of link editing forms
an EXIT task.

You must define two types of functions in your programs:

-   An initialization
    function **exaini**
-   One or more functions
    that will be referred to as **usrfct**

A directory EXIT task:

-   Calls the main
    entry point, interface code, on activating the task
-   Calls the initialization
    function **exaini** function in server mode, when a connection is indicated,
    or in requester mode, when a connection request is made. If this function
    returns a 0 code, the **usrfct** function
    is called. If not, <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> considers that the user does not want
    to take control

<span id="Initialization_Function"></span>

## Initialization function

### About the initialization function

The initialization function **exaini** must specify the stages at
which you want to take control. It must supply the address of the **usrfct**
function to be called if the user wants to take control at one stage at
least.

Restriction

The initialization function cannot be written in COBOL since its main
purpose is to indicate the address of a user function. You must use a
language such as C language or Assembler.

### Parameters

The following table lists all the parameters of the
initialization function.

### Example in C

long **exaini** ( char     \*exaref,  
          char    
\*mode,  
          char    
\*part,  
          char    
\*parm,  
          char    
\*language,  
          EXA    
\*function );

Where EXA is defined as:

typedef long (\*EXA)(char\*,char\*);

<span id="User_Function"></span>

## User Function

Example in C

long usrfct (     char
\*zecom,

  char
\*zgcom            );

<span id="Interface_Files"></span>

## Interface files

Interface files are listed in the following table.
