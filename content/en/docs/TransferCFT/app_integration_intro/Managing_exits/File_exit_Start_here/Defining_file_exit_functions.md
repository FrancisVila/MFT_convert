{
    "title": "Define  functions",
    "linkTitle": "Defining functions",
    "weight": "330"
}This topic describes the functions in an exit task and the parameters
involved. It is comprised of the following sections:

-   [Initialization
    function](#Initialization_Function)
-   [User
    function](#User_function_s_)
-   [Interface
    files](#Interface_Files)

A file exit task comprises the following two modules:

-   {{< TransferCFT/componentshortname >}} interface
-   User program

The interface is written in C language. The main entry point of the
EXIT task, the main function in C language, is located in the interface.
You do not need to know how this interface works to write a user program.

The user program can be written in C or in COBOL. If you use COBOL,
you must comply with the standard C-COBOL interfacing rules.

Once the user program has been written and compiled, the two modules
are linked together with the appropriate system libraries. The result
of link editing forms an EXIT task.

You must define two types of functions in your programs:

-   An initialization
    function: **exfini**
-   One or more functions
    that will be referred to as: **EXFxmp1**

A file type EXIT task:

-   Calls the main
    entry point (interface code) on activating the task
-   Calls the initialization
    function **exfini** at the beginning of a transfer whose identifier
    (idf) is linked to the EXIT task
-   Calls the user
    function **EXFxmp1** whenever the user wants to take control

<span id="Initialization_Function"></span>

## Initialization function

### About the initialization function

The initialization function **exfini** must specify the stages at
which you want to take control. It must supply the address of the **EXFxmp1**
function to be called if you want to take control at one stage at least.

Restrictions

-   You cannot change a user function during the transfer.
-   The initialization function cannot be written in COBOL since its main
    purpose is to indicate the address of a user function. You must use a
    language such as C language or Assembler.

### Parameters

The following table lists all the parameters of the initialization function.

### Example in C

Where EXF is defined as:

<span id="User_function_s_"></span>

## User functions

The following table describes the parameters involved in the user functions.

### Example in C language

<span id="Interface_Files"></span>

## Interface files

The following table describes the interface files.
