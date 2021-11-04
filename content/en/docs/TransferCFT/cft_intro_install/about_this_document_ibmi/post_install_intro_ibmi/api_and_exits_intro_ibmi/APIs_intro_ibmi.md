{
    "title": "Using Application programming interfaces (API)",
    "linkTitle": "Using APIs",
    "weight": "280"
}<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Note</strong></span>         </td>
         <td>Only ILE (Integrated Language Environment) is supported.         </td>
      </tr>
   </tbody>
</table>

You perform Transfer CFT service calls differently depending on the programming language that you use (C, COBOL, or RPG). For more information, refer to the programming topics in <a href="../../../../about_this_document_zos/using_apis" class="MCXref xref">About APIs</a>

The Transfer CFT service called (CFTI, CFTU or CFTC) executes the request, either with or without analyzing command syntax, and then initializes the response zone.

The client application receives from Transfer CFT:

-   A return code

<!-- -->

-   The requested data, if applicable

## Prerequisites

You require the ICC and GMAKE utilities for IBM i platforms:

-   gmake: GNU compiler (make)
-   icc: Intel C/C++ compiler (calls ILE)

## Call from a COBOL/ILE or RPG/ILE program

### Querying the Catalog: CFTI function

Available commands include OPEN, SELECT, NEXT, MODIFY and CLOSE.

### Requesting a transfer: CFTU and CFTC functions

Available parameters include: F-SEND, F-RECV, F-START, F-HALT, F-KEEP, F-DELETE, F-END and F-COM.

COBOL/ILE Programming samples

All COBOL sample files are available in CFTPGM/CFTSRC. However, you should not directly modify them as this library is proprietary to Axway, and updating the product may modify these samples. Therefore, we recommend that you copy the samples you need into CFTPROD/UTIN and configure them according to your production requirements.

<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Note</strong></span>         </td>
         <td>The product installation copies and configures some samples.         </td>
      </tr>
   </tbody>
</table>

RPG/ILE programming examples

Refer to the programming examples, RPG COPY clauses, and procedures, which are supplied in the Transfer CFT library CFTPGM/CFTSRC (CPYRPGCILE, CPYRPGIILE, CPYRPGCIL4, CPYRPGIIL4):

-   TCFTI2\_RPG (API structure V24)
-   TCFTU\_RP1 (API asynchronous)
-   TCFTU\_RP2 (API synchronous)
-   I\_TCFTI\_RP (executes CFTI or CFTIX functions)
-   I\_TCFTU\_RP (executes CFTU function), etc.

## Creating an API application

The <span class="code">TCPPARAM</span> configuration sample is located in <span class="code">CFTPROD/UTIN</span>.

## Application components

The <span class="code">&lt;installdir>/runtime/src/capi </span>subdirectory contains the:

-   Sample source module,
    called <span class="code">apixmp1.c,</span> which interacts with <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span>. This program
    reads the <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> catalog and displays its contents in part or in
    full, depending on the restrictions set in the command line.
-   <span class="code">makefile</span>
    compilation procedure, which uses the<span class="code"> apixmp1.c </span>sample source module
    to generate the APIXMPI executable file.

The <span class="code">CFTPGM </span>library subdirectory contains the <span class="code">libapisrv1.srvpgm</span>
module required to use <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> APIs.

## Generating the application

To generate the *APIXMP1* sample program:

1.  Access the <span class="code">&lt;installdir>/runtime/src/capi </span>directory.
2.  Enter the command:  <span class="code">gmake</span>

## Testing the configuration

To test the configuration:

1.  Connect to the IBM session with your Transfer CFT user.
2.  Generate the <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> internal datafiles
    using <span class="code">cftinit</span> with the configuration file:  
    CALL PGM(CFTINIT) PARM('CFTPROD/UTIN(TCPPARAM)')
3.  When the<span class="code"> cftinit complete</span>
    message is displayed, run <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> using the command:  
    cftstart
4.  When the <span class="code">CFTMAIN process
    ID is xxxxx </span>message is displayed, perform a transfer:  
    CALL PGM(CFTUTIL) PARM(SEND 'part=boston,idf=txt')
5.  Check that the transfer is
    complete:  
    CALL PGM(CFTUTIL) PARM(LISTCAT)
6.  Run the sample program in the IFS environment:  
    cd &lt;installdir>/runtime; . ./profile; APIXMP1
7.  Run the sample program on NATIF environment:  
    CALL PGM(APIXMP1)

<span class="bold_in_para">Results</span>

The result should correspond to the catalog contents:

> PART=NEW YORK, IDT=&lt;dynamic identifier>,IDF=TXT  
> PART=BOSTON ,IDT=&lt;dynamic identifier>,IDF=TXT  
> APIXMP1 \_ 2 record(s) found

Stop <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span>:

     cftstop
