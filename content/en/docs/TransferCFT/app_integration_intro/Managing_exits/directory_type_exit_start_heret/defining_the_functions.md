{
    "title": "Defining  functions",
    "linkTitle": "Defining functions",
    "weight": "380"
}<span id="About_the_Functions"></span>This topic describes the directory exit task components and functions.
A directory EXIT task comprises two modules:

-   The interface supplied
    with Transfer CFT
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
    returns a 0 code, the usrfct function
    is called. If not, Transfer CFT considers that the user does not want
    to take control

## <span id="Initialization_Function"></span>Initialization function

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

<table data-cellspacing="0" width="90%">
   <thead>
      <tr class="header">
         <th>Parameter</th>
         <th>Description</th>
      </tr>
   </thead>
   <tbody>
      <tr class="odd">
         <td width="32.45%">            <p>exafref</p>         </td>
         <td width="67.55%">            <p>Address
of an (512+1) byte area.</p>
            <p>The
initialization function can modify this area.</p>         </td>
      </tr>
      <tr class="even">
         <td width="32.45%">            <p>mode</p>         </td>
         <td width="67.55%">            <p>Address
of a one-byte area</p>
            <p>Processing mode:</p>
            <ul>
               <li>S: call
in server mode               </li>
               <li>R: call
in requester mode (Requester)               </li>
            </ul>         </td>
      </tr>
      <tr class="odd">
         <td width="32.45%">            <p>part</p>         </td>
         <td width="67.55%">            <p>Address
of an (32+1) byte area.</p>
            <p>Partner local identifier if this identifier is known to
<span>Transfer CFT</span>.</p>         </td>
      </tr>
      <tr class="even">
         <td width="32.45%">            <p>parm</p>         </td>
         <td width="67.55%">            <p>Address
of an (64+1) byte area.</p>
            <p>This
area contains the value of the PARM parameter of the CFTEXIT command and
can be modified by the initialization function.</p>         </td>
      </tr>
      <tr class="odd">
         <td width="32.45%">            <p>language</p>         </td>
         <td width="67.55%">            <p>Address
of a one-byte area.</p>
            <p>This area contains the value of the LANGUAGE
parameter of the CFTEXIT command and can be modified by the initialization
function.</p>         </td>
      </tr>
      <tr class="even">
         <td width="32.45%">            <p>function</p>         </td>
         <td width="67.55%">            <p>Address
of an area that contains the address of the user function.</p>
            <p>If you want to take
control, the initialization function must update this area. The mode,
part, parm and language parameters are initialized by the interface. The
mode, part and parm parameters can be used to select a function when the
user has provided several functions.</p>
            <p>The user can use the exaref parameter as required. The
contents of this parameter are thereafter provided to the user function.</p>
            <p>The (n+1) byte areas contain characters up to n bytes long
followed by a binary zero.</p>         </td>
      </tr>
      <tr class="odd">
         <td width="32.45%">            <p>Return
codes</p>         </td>
         <td width="67.55%">            <p>The possible values are:</p>
            <ul>
               <li>0: the
user wants to take control at one stage at least               </li>
               <li>1: the
user does not want to take control               </li>
            </ul>         </td>
      </tr>
   </tbody>
</table>

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

## <span id="User_Function"></span>User Function

<table data-cellspacing="0">
   <thead>
      <tr class="header">
         <th>Parameter</th>
         <th>Description</th>
      </tr>
   </thead>
   <tbody>
      <tr class="odd">
         <td width="24.272%">            <p>zecom</p>
            <p> </p>
            <p> </p>         </td>
         <td width="75.728%">            <p>Address
of the interface communication area. Also
known as context table or transfer context, this area is:</p>
            <ul>
               <li>allocated by the interface for each transfer               </li>
               <li>updated by the interface before each call
of the user function               </li>
               <li>freed by the interface at the end of the
transfer               </li>
            </ul>
            <p>Some fields of this area can be updated by the user function.</p>         </td>
      </tr>
      <tr class="even">
         <td width="24.272%">            <p>zgcom</p>         </td>
         <td width="75.728%">            <p>Address
of the global communication area (1024 bytes).</p>
            <p>This area is allocated and reset to 0
by the interface once and for all at the time the EXIT task is activated,
and then freed by the interface at the time it is de-activated.</p>
            <p>You can use this area to save the information common to
all the calls of user functions.</p>
            <p> </p>         </td>
      </tr>
      <tr class="odd">
         <td width="24.272%">            <p>Return
codes</p>         </td>
         <td width="75.728%">            <p>Not used</p>         </td>
      </tr>
   </tbody>
</table>

Example in C

long usrfct (     char
\*zecom,

  char
\*zgcom            );

## <span id="Interface_Files"></span>Interface files

Interface files are listed in the following table.

<table data-cellspacing="0">
   <thead>
      <tr class="header">
         <th>File</th>
         <th>Description</th>
      </tr>
   </thead>
   <tbody>
      <tr class="odd">
         <td>            <p>EXAUS.H</p>         </td>
         <td>            <p>File that contains the definition of the interface/user
program communication structure<br />
For the interface and the user program </p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>EXA.H </p>         </td>
         <td>            <p>File for the interface </p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p>EXA2MN.C </p>         </td>
         <td>            <p>Main entry point for the EXIT task </p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>EXA2UT.C</p>         </td>
         <td>            <p>Miscellaneous functions for the interface </p>         </td>
      </tr>
   </tbody>
</table>
