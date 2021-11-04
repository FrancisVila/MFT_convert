{
    "title": "Creating  a file exit - IBM i",
    "linkTitle": "Creating a file exit",
    "weight": "290"
}This page describes a delivered sample that is designed to create an example file exit. You can use the <span class="code">TCPPARAM </span>configuration sample that is located in <span class="code">CFTPROD/UTIN</span>.

## Prerequisites

You require the ICC and GMAKE utilities for IBM i platforms:

-   gmake: GNU compiler (make)
-   icc: Intel C/C++ compiler (calls ILE)

## Application components

The <span class="code">&lt;installdir>/runtime/src/exit/</span> subdirectory contains:

-   The <span class="code">exfxmp1.c</span> sample source module with its associated <span class="code">exfus.h</span> include file. This program
    demonstrates the various user functions:
    -   ALLOC\_TYP:
        the EXIT allocates the file
    -   OPEN\_TYP: the
        EXIT opens the file
    -   DATA\_TYP: the
        EXIT writes or reads the file, and so on

<!-- -->

-   The <span class="code">makefile </span>
    compilation procedure, which uses <span class="code">exfxmp2.c</span> to generate the CFTEXITF
    program

The CFTPGM library contains the <span class="code">libcftexf.srvpgm</span>
module. This library allows you to use the <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> file EXITs.

## Generating the exit

To generate the sample CFTEXITF application:

1.  Access the <span class="code">&lt;installdir>/runtime/src/exit/</span> directory.
2.  Enter the command: <span class="code">gmake</span>

## Testing the exit

1.  Connect to the IBM session with your Transfer CFT user.

2.  Generate the <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> internal datafiles
    using the <span class="code">cftinit </span>utility with the configuration file:

    CALL PGM(CFTINIT) PARM('CFTPROD/UTIN(TCPPARAM)')

3.  When the <span class="code">cftinit complete</span>
    message is displayed, run <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> using the <span class="code">cftstart </span>utility:

    cftstart

4.  When the <span class="code">CFTMAIN process
    ID is xxxxx </span>message is displayed, run a transfer using the command:

    CALL PGM(CFTUTIL) PARM(SEND 'part=BOSTON, idf=fic1')

5.  After a few seconds, you can
    check the transfer state by entering the following command. If the transfers have not terminated, repeat thecommand.

    CALL PGM(CFTUTIL) PARM(LISTCAT)  

6.  Stop <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> using the <span class="code">cftstop</span>
    utility:

    cftstop

7.  Examine the contents of the <span class="code">CFTPROD/LOG. sav</span> file in the <span class="code">CFTPROD </span>library and locate the messages inserted by the EXIT.  
      
    The files created in the <span class="code">CFTPROD </span>library are empty, as the sample EXIT is
    only a simulation.
