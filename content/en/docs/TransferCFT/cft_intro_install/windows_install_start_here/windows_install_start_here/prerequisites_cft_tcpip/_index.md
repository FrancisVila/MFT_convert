{
    "title": "Setting up the TCP/IP layer ",
    "linkTitle": "Setting protocol parameters",
    "weight": "220"
}Before starting {{< TransferCFT/componentshortname  >}} with TCP/IP for the first time, you must setup your TCP/IP.

Procedure

1. Install and configure
    the TCP/IP layer.
1. In the SAMPLE folder, configure
    the PARMTCP.SMP sample file, with the **key**
    parameter in CFTPARM.
1. In the SAMPLE folder, configure
    the sample file PARMTCP.SMP. Configure the <span style="font-weight: bold;">nspart</span>
    and <span style="font-weight: bold;">nrpart</span> parameters in CFTPARM,
    and the <span style="font-weight: bold;">host</span> parameter of the
    CFTTCP command.
1. Start the batch file <span class="code">..\\CFT\\SAMPLE\\RESETTCP</span>.
1. Start CFTMAIN.
1. Check that CFTMAIN
    started correctly.
1. From a command prompt on a different Windows, and in the <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> root folder, enter the
    command: <span class="code">&gt; CFTUTIL SEND PART=PART1, IDF=TEST</span>

 
