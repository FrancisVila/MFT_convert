{
    "title": "Creating  a directory exit - IBM i",
    "linkTitle": "Creating a directory exit",
    "weight": "300"
}This page describes a delivered sample that is designed to create an example directory exit. You can use the <span class="code">TCPPARAM </span>configuration sample that is located in <span class="code">CFTPROD/UTIN</span>.

Before you start

Before running the directory exit test, you must make a few changes to the <span class="code">(TCPPARAM)</span> file depending on the type of network used. Edit the file using
your text editor (EDTF for example) as follows.

1.  In the file, locate
    the *cftprot* command. The following lines are displayed:
2.  Delete the comments (delimited
    by /\* at the beginning and \*/ at the end). The *cftprot* command should resemble the following:
3.  Locate the *cftexit* command,
    commented as follows:
4.  Locate the communication properties
    for your site, which appear at the end of the file. When
    modifying the (<span class="code">TCPPARAM</span>) file, you must also find every occurrence
    of the HOST string located in cfttcp-type commands and replace the X character
    strings with your system name or address.

## Prerequisites

You require the ICC and GMAKE utilities for IBM i platforms:

-   gmake: GNU compiler (make)
-   icc: Intel C/C++ compiler (calls ILE)

## Application components

The *&lt;installdir>/runtime/src/exit/* subdirectory contains several sample source
modules. This program is used to check the following:

-   Activation
    of a transfer to a partner known to the directory EXIT but not to Transfer
    CFT
-   Activation
    of a transfer to a partner not known to either <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> or the directory
    EXIT

The *&lt;installdir>/lib* subdirectory contains:

-   The<span class="code"> libcftexa.a</span>
    module required to use the <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> directory EXITs

## Generating the exit

To generate the sample CFTEXITA application:

1.  Access the <span class="code">&lt;installdir>/runtime/src/exit/ </span>directory.
2.  Enter the command: <span class="code">gmake</span>

## Running the test

1.  Access the <span class="code">&lt;installdir>/runtime/conf </span>directory.
2.  Generate the <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> databases
    using <span class="code">cftinit</span> the configuration file provided
    and modified for this EXIT:<span class="code"> cft-tcp.conf</span>
3.  When the<span class="code"> cftinit complete </span>
    message is displayed, run <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> using the <span class="code">cftstart </span>utility: <span class="code">cftstart</span>
4.  When the<span class="code"> CFTMAIN process
    ID is xxxxx</span> message is displayed, perform an initial standard transfer
    using the command:  
    <span class="code">CFTUTIL send part=BOSTON, idf=TXT</span>
5.  Now submit a second transfer
    to the <span class="code">NCFT\_OK</span> partner:  
    <span class="code">CFTUTIL send part=NCFT\_OK,idf=TXT</span>
6.  After a few seconds, you can
    check the transfer state by entering the command: <span class="code">cftcatab</span>
7.  The transfer is successful
    because NRPART01 is defined in the DIRECTORY EXIT as being the EXTPTN01
    non- <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> partner.
8.  Now submit a third transfer
    to the NCFT\_OK partner:  
    <span class="code">CFTUTIL send part=NCFT\_NOK,idf=TXT</span>
9.  After a few seconds, you can
    check the transfer state by entering the command: <span class="code">cftcatab</span>

The transfer fails because the password is invalid, even though NRPART02
is defined in the DIRECTORY EXIT.

1.  Stop <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span>: <span class="code">cftstop</span>
