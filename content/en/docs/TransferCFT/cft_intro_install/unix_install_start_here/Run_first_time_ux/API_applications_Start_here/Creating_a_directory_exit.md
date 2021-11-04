{
    "title": "Creating  a directory exit",
    "linkTitle": "Creating a directory exit",
    "weight": "230"
}The following example was designed from a modified version of the <span class="bold_in_para">cft-tcp.conf </span>configuration example, located in <span class="bold_in_para">&lt;installdir>/runtime/conf</span>. For this example, you should have customized
at least one of these files, using the instructions in Running Transfer
CFT for the first time.

## Prerequisites

Before running the directory exit test, you must make a few changes
to the cft-tcp.conf file, depending on the
type of network used.

1.  Edit the relevant file using
    your text editor (*vi* for example) and perform the following operations.
2.  In the edited file, locate
    the *cftprot* command. The following lines are displayed:

<!-- -->


    cftprot 
     id      = PeSITCFT,
    type      = PESIT,
    prof      = CFT,
    ...
    /*** exita      = EXIT_A, ** See Operations Guide **/
    mode      = replace

1.  Delete the comments (delimited
    by /\* at the beginning and \*/ at the end).

When the operation is complete, you should obtain
the following *cftprot* command:


    cftprot id      = PeSITCFT,
    type      = PESIT,
    prof      = CFT,
    ...
    exita= EXIT_A,
    mode      = replace

1.  Locate the *cftexit* command,
    commented as follows:

<!-- -->


    CFTEXIT ID      = EXIT_A,
    PARM = EXAPARM1,
    LANGUAGE = C,
    PROG = 'CFTEXITA',
    TYPE = ACCESS,
    MODE = REPLACE ***/

You must remove the comments to obtain the following
command:


    CFTEXIT ID      
     = EXIT_A,
    PARM      = EXAPARM1,
    LANGUAGE      = C,
    PROG      = 'CFTEXITA',
    TYPE      = ACCESS,
    MODE      = REPLACE

1.  Locate the communication properties
    of your site, which appear at the end of the file.

-   If you are
    modifying the cft-tcp.conf file, you must also find every occurrence
    of the HOST string located in cfttcp-type commands and replace the X character
    strings with your system name or address

### Application components

The *&lt;installdir>/runtime/src/exit/* subdirectory contains:

-   A sample source
    module, called *exaxmpm.c*, with its associated include file (*exaus.h*),
    and an additional file called *exaxmpp.h*  
    This program is used to check the following features:
-   Activation
    of a transfer to a partner known to the directory EXIT but not to Transfer
    CFT
-   Activation
    of a transfer to a partner not known to either <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> or the directory
    EXIT

<!-- -->

-   The *mk\_cftexita*
    compilation procedure used to generate the CFTEXITA program

The *&lt;installdir>/lib* subdirectory contains:

-   The *libcftexa*.*a*
    module required to use the <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> directory EXITs

To generate the sample CFTEXITA application, proceed as follows.

1.  Access the *&lt;installdir>/runtime/src/exit/* directory.
2.  Enter the command:

    <span style="font-family: 'Courier New', monospace;font-weight: bold;">
make -f mk\_cftexita</span>

## Running the test

1.  Access the *&lt;installdir>/runtime/conf* directory.
2.  Generate the <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> databases
    using *cftinit* the configuration file provided
    and modified for this EXIT:<span class="code"> cft-tcp.conf</span>
3.  When the *cftinit complete*
    message is displayed, run <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> using the *cftstart* utility: <span class="code">cftstart</span>
4.  When the *CFTMAIN process
    ID is xxxxx* message is displayed, perform an initial standard transfer
    using the command:  
    <span class="code">CFTUTIL send part=BOSTON, idf=TXT</span>
5.  Now submit a second transfer
    to the NCFT\_OK partner.  
    <span class="code">CFTUTIL send part=NCFT\_OK,idf=TXT</span>
6.  After a few seconds, you can
    check the transfer state by entering the  
    command: <span class="code">cftcatab</span>
7.  The transfer is successful
    because NRPART01 is defined in the DIRECTORY EXIT as being the EXTPTN01
    non- <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> partner.
8.  Now submit a third transfer
    to the NCFT\_OK partner.  
    <span class="code">CFTUTIL send part=NCFT\_NOK,idf=TXT</span>
9.  After a few seconds, you can
    check the transfer state by entering the  
    command:

cftcatab

The transfer fails because the password is invalid, even though NRPART02
is defined in the DIRECTORY EXIT.

1.  Stop <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span>:

cftstop