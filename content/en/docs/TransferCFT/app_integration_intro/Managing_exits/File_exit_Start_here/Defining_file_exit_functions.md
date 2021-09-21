{
    "title": "Defining functions",
    "linkTitle": "Defining functions",
    "weight": "360"
}# <span id="Title"></span>Define functions

This topic describes the functions in an exit task and the parameters
involved. It is comprised of the following sections:

-   [Initialization
    function](#initialization_function)
-   [User
    function](#user_function_s_)
-   [Interface
    files](#interface_files)

A file exit task comprises the following two modules:

-   Transfer CFT interface
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

## <span id="Initialization_Function"></span>Initialization function

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

<table cellspacing="0">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>
            <p>Parameter</p>
</th>
         <th>
            <p>Explanation</p>
</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>
            <p>ex_name</p>
         </td>
         <td>
            <p>Address 
 of an (512+1) byte area. </p>
            <p>The 
 initialization function can modify this area.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>idf</p>
         </td>
         <td>
            <p>Address 
 of an (32+1) byte area. </p>
            <p>This area contains the file identifier of the transfer 
 in process.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>parm</p>
         </td>
         <td>
            <p>Address 
 of an (64+1) byte area. </p>
            <p>This 
 area contains the value of the PARM parameter of the CFTEXIT command and 
 can be modified by the initialization function.</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>language</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Address 
 of a one-byte area. </p>
            <p>This area contains the value of the LANGUAGE 
 parameter of the CFTEXIT command and can be modified by the initialization 
 function.</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>pfonc</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Address 
 of an area that contains the address of the user function.</p>
            <p>If you want to take 
 control, the initialization function must update this area. The idf, parm 
 and language parameters are initialized by the interface. The idf and 
 parm parameters can be used to select a function when the user has provided 
 several functions.</p>
            <p>The user may use the exfref parameter as required. The 
 contents of this parameter are thereafter provided to the user function.</p>
            <p>The (n+1) byte areas contain characters up to n bytes long 
 followed by a binary zero.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Return 
 codes</p>
         </td>
         <td>
            <p>The possible values are:</p>
            <ul>
               <li>0: the 
 user wants to take control at one stage at least               </li>
               <li>1: the 
 user does not want to take control               </li>
            </ul>
         </td>
      </tr>
   </tbody>
</table>

### Example in C

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>long <b>exfini</b> ( char     *ex_name,<br/>          char     
 *idf,<br/>          char     
 *parm,<br/>          char     
 *language,<br/>          EXF     
 *pfonc);         </td>
      </tr>
   </tbody>
</table>

Where EXF is defined as:

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>typedef long (*EXF)</p>
            <p>(char*,char*,char*,char*);</p>
         </td>
      </tr>
   </tbody>
</table>

## <span id="User_function_s_"></span>User functions

The following table describes the parameters involved in the user functions.

<table cellspacing="0">
   <col/>
   <col/>
   <thead>
      <tr>
         <th> </th>
         <th> </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>
            <p>Parameter</p>
         </td>
         <td>
            <p>Explanation</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>psCtx</p>
         </td>
         <td>
            <p>Address 
 of the interface communication area. </p>
            <p>Also known 
 as context table or transfer context, this area is: </p>
            <ul>
               <li>Allocated by the interface for each transfer               </li>
               <li>Updated by the interface before each call 
 of the user function               </li>
               <li>Freed by the interface at the end of the 
 transfer               </li>
            </ul>
            <p>For simultaneous transfers 
 using a given EXIT, the interface manages the context tables. Each transfer 
 has its own context.</p>
            <p>Some fields of the context table can be updated by the 
 user function. For more information, refer to the <a href="../file_exit_communication_area_">About 
 the communication structure</a> topic.
  </p>
         </td>
      </tr>
      <tr>
         <td>
            <p>psCtxWork</p>
         </td>
         <td>
            <p>Address 
 of the user working area. </p>
            <p>This area, allocated and de-allocated by the interface 
 for each transfer, enables users to save the information they consider 
 necessary for the purposes of the processing performed.</p>
            <p>Its size equals the value of the RESERV parameter of the 
 CFTEXIT object. </p>
         </td>
      </tr>
      <tr>
         <td>
            <p>psData</p>
         </td>
         <td>
            <p>Address of the data area. </p>
            <p>This area, allocated and de-allocated by the interface 
 for each transfer, contains the record to be sent or the record received.</p>
            <p>Its size is limited to 4096 bytes. The effective size of 
 the data is specified in the context table.</p>
            <p>You can modify the data at certain stages. You must then 
 change the effective size of the data in the context table. For more information, 
 refer to <a href="../file_exit_communication_area_">About the communication structure</a>.</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>psWork</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Address 
 of the global communication area (1024 bytes).</p>
            <p>This area is allocated and reset to 0 
 by the interface once and for all at the time the EXIT task is activated, 
 and then freed by the interface at the time it is de-activated.</p>
            <p>You can use this area to save the information common to 
 all the calls of user functions.</p>
            <p>This area must be used with care if the value of the WAITTASK 
 parameter of the CFTEXIT command is not 1441 (EXIT task permanently present 
 in memory).</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Return 
 codes</p>
         </td>
         <td>
            <p>Not used</p>
         </td>
      </tr>
   </tbody>
</table>

### Example in C language

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>long EXFxmp1   (char 
 *psCtx, <br/>           char 
 *psCtxWork,</p>
            <p>         char 
 *psData, </p>
            <p>          char 
 *psWork)</p>
         </td>
      </tr>
   </tbody>
</table>

## <span id="Interface_Files"></span>Interface files

The following table describes the interface files.

<table bgcolor="#FFFFFF" cellspacing="0">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>
            <p>File</p>
</th>
         <th>
            <p>Explanation</p>
</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td colspan="1" rowspan="1" valign="top" width="16.392%">
            <p>EXFUS.H</p>
         </td>
         <td colspan="1" rowspan="1" valign="top" width="83.608%">
            <p>File that contains the definition of the interface/user 
 program communication structure<br/>For the interface and the user program </p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1" valign="top" width="16.392%">
            <p>EXF.H </p>
         </td>
         <td colspan="1" rowspan="1" valign="top" width="83.608%">
            <p>File for the interface </p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1" valign="top" width="16.392%">
            <p>EXF2MN.C </p>
         </td>
         <td colspan="1" rowspan="1" valign="top" width="83.608%">
            <p>Main entry point for the EXIT task </p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1" valign="top" width="16.392%">
            <p>EXF2UT.C</p>
         </td>
         <td colspan="1" rowspan="1" valign="top" width="83.608%">
            <p>Miscellaneous functions for the interface </p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1" valign="top" width="16.392%">
            <p>EXF2RS.C</p>
         </td>
         <td colspan="1" rowspan="1" valign="top" width="83.608%">
            <p>Miscellaneous functions for the interface</p>
         </td>
      </tr>
   </tbody>
</table>