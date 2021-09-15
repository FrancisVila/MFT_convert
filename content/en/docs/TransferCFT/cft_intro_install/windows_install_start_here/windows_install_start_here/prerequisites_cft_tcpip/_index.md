{
    "title": "Setting protocol parameters",
    "linkTitle": "Setting protocol parameters",
    "weight": "230"
}Before starting Transfer CFT with TCP/IP for the first time, you must setup your TCP/IP.

Procedure

1.  Install and configure
    the TCP/IP layer.
2.  In the SAMPLE folder, configure
    the PARMTCP.SMP sample file, with the key
    parameter in CFTPARM.
3.  In the SAMPLE folder, configure
    the sample file PARMTCP.SMP. Configure the nspart
    and nrpart parameters in CFTPARM,
    and the host parameter of the
    CFTTCP command.
4.  Start the batch file ..\\CFT\\SAMPLE\\RESETTCP.
5.  Start CFTMAIN.
6.  Check that CFTMAIN
    started correctly.
7.  From a command prompt on a different Windows, and in the Transfer CFT root folder, enter the
    command: &gt; CFTUTIL SEND PART=PART1, IDF=TEST

 
