{
    "title": "Creating an exit file",
    "linkTitle": "Creating an exit file",
    "weight": "240"
}# <span id="Creating_an_exit_file"></span>Creating an exit file

The example described in this topic was designed to operate using the cft-tcp.conf configuration example located in &lt;installdir>/runtime/conf.
For this example, you should have already customized the
file using the instructions in [*Running Transfer
CFT for the First Time*](running_cft_for_the_first_time_unix.htm).

## Application components

The *&lt;installdir>/runtime/src/exit/* subdirectory contains:

-   A sample source
    module, called *exfxmp1.c*, with its associated include file *exfus.h*
-   This program
    demonstrates the various user functions:
-   ALLOC\_TYP:
    the EXIT allocates the file
-   OPEN\_TYP: the
    EXIT opens the file
-   DATA\_TYP: the
    EXIT writes or reads the file

<!-- -->

-   And so on

<!-- -->

-   The *mk\_cftexitf*
    compilation procedure, which uses *exfxmp2.c* to generate the *CFTEXITF*
    program

The *&lt;installdir>/lib* subdirectory contains the:

-   *libcftexf.a*
    module; this library allows you to use the Transfer CFT file EXITs

To generate the sample CFTEXITF application, proceed as follows:

1.  Access the *&lt;installdir>/runtime/src/exit/* directory.
2.  Enter the command:

     make
-f mk\_cftexitf

## Testing the exit

1.  Access the *&lt;installdir>/runtime/conf/* directory.

2.  Generate the Transfer CFT internal datafiles
    using the *cftinit* utility with the configuration file:

    cftinit cft-tcp.conf

3.  When the *cftinit complete*
    message is displayed, run Transfer CFT using the cftstart utility:

    cftstart

4.  When the *CFTMAIN process
    ID is xxxxx* message is displayed, run a transfer using the command:

    CFTUTIL send part=BOSTON, idf=fic1

5.  After a few seconds, you can
    check the transfer state by entering the following command. If the transfers have not terminated, repeat the *cftcatab* command.

    cftcatab  

6.  Stop Transfer CFT using the *cftstop*
    utility:

    cftstop

7.  Examine the contents of the
    *cft\_log. sav* file in the *&lt;installdir>/runtime/log/* directory and locate the
    messages inserted by the EXIT.  
      
    The files created in *&lt;installdir>/runtime/* are empty, as the sample EXIT is
    only a simulation.