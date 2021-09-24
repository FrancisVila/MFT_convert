{
    "title": "Creating a directory exit",
    "linkTitle": "Creating a directory exit",
    "weight": "250"
}# <span id="Creating_a_directory_exit"></span>Creating a directory exit

The following example was designed from a modified version of the cft-tcp.conf configuration example, located in &lt;installdir>/runtime/conf. For this example, you should have customized
at least one of these files, using the instructions in [Running Transfer
CFT for the first time.](running_cft_for_the_first_time_unix.htm)

## Prerequisites

Before running the directory exit test, you must make a few changes
to the cft-tcp.conf file, depending on the
type of network used.

1.  Edit the relevant file using
    your text editor (*vi* for example) and perform the following operations.
2.  In the edited file, locate
    the *cftprot* command. The following lines are displayed:

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>cftprot 
 id      = PeSITCFT,<br/>type      = PESIT,<br/>prof      = CFT,<br/>...<br/>/*** exita      = EXIT_A, ** See Operations Guide **/<br/><br/>mode      = replace         </td>
      </tr>
   </tbody>
</table>

1.  Delete the comments (delimited
    by /\* at the beginning and \*/ at the end).

When the operation is complete, you should obtain
the following *cftprot* command:

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>cftprot id      = PeSITCFT,<br/>type<span>      = PESIT,</span><br/><span>prof</span>      = CFT,<br/>...<br/>exita= EXIT_A,<br/>mode      = replace         </td>
      </tr>
   </tbody>
</table>

1.  Locate the *cftexit* command,
    commented as follows:

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>CFTEXIT ID      = EXIT_A,<br/><br/>PARM = EXAPARM1,<br/>LANGUAGE = C,<br/>PROG = 'CFTEXITA',<br/>TYPE = ACCESS,<br/><br/>MODE = REPLACE ***/         </td>
      </tr>
   </tbody>
</table>

You must remove the comments to obtain the following
command:

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>CFTEXIT ID      
 = EXIT_A,<br/>PARM      = EXAPARM1,<br/>LANGUAGE      = C,<br/>PROG      = 'CFTEXITA',<br/>TYPE      = ACCESS,<br/>MODE      = REPLACE         </td>
      </tr>
   </tbody>
</table>

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
    of a transfer to a partner not known to either Transfer CFT or the directory
    EXIT

<!-- -->

-   The *mk\_cftexita*
    compilation procedure used to generate the CFTEXITA program

The *&lt;installdir>/lib* subdirectory contains:

-   The *libcftexa*.*a*
    module required to use the Transfer CFT directory EXITs

To generate the sample CFTEXITA application, proceed as follows.

1.  Access the *&lt;installdir>/runtime/src/exit/* directory.
2.  Enter the command:

    
make -f mk\_cftexita

## Running the test

1.  Access the *&lt;installdir>/runtime/conf* directory.
2.  Generate the Transfer CFT databases
    using *cftinit* the configuration file provided
    and modified for this EXIT: cft-tcp.conf
3.  When the *cftinit complete*
    message is displayed, run Transfer CFT using the *cftstart* utility: cftstart
4.  When the *CFTMAIN process
    ID is xxxxx* message is displayed, perform an initial standard transfer
    using the command:  
    CFTUTIL send part=BOSTON, idf=TXT
5.  Now submit a second transfer
    to the NCFT\_OK partner.  
    CFTUTIL send part=NCFT\_OK,idf=TXT
6.  After a few seconds, you can
    check the transfer state by entering the  
    command: cftcatab
7.  The transfer is successful
    because NRPART01 is defined in the DIRECTORY EXIT as being the EXTPTN01
    non- Transfer CFT partner.
8.  Now submit a third transfer
    to the NCFT\_OK partner.  
    CFTUTIL send part=NCFT\_NOK,idf=TXT
9.  After a few seconds, you can
    check the transfer state by entering the  
    command:

cftcatab

The transfer fails because the password is invalid, even though NRPART02
is defined in the DIRECTORY EXIT.

1.  Stop Transfer CFT:

cftstop
