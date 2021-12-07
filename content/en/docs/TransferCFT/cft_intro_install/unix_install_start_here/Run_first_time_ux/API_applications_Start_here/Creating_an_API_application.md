{
    "title": "Creating  an API application",
    "linkTitle": "Creating an API application",
    "weight": "210"
}The example provided below was designed for the **cft-tcp.conf**  configuration example located in *&lt;installdir>/runtime/conf/*. For
this example, you should have already customized this file using the method described in *Running
  {{< TransferCFT/componentshortname  >}} for the first time*.

## Application components

The *&lt;installdir>/runtime/src/capi* subdirectory contains the:

-   Sample source module,
    called *apixmp1.c*, which interacts with  {{< TransferCFT/componentshortname >}}. This program
    reads the  {{< TransferCFT/componentshortname >}} catalog and displays its contents in part or in
    full, depending on the restrictions set in the command line
-   *makefile*
    compilation procedure, which uses the *apixmp1.c* sample source module
    to generate the APIXMPI executable file

The *&lt;installdir>/lib* subdirectory contains the:

-   *libcftapi.a*
    module required to use  {{< TransferCFT/componentshortname >}} APIs

To generate the *APIXMP1* sample program, proceed as follows.

1.  Access the *&lt;installdir>/runtime/src/capi* directory.
2.  Enter the command:   **<span class="code">make</span>**

## Testing the configuration

To test the configuration, proceed as follows:

1.  Access the *&lt;installdir>/runtime/conf/* directory.
2.  Generate the  <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> internal datafiles
    using *cftinit* with one of the two proposed configuration files:

     cftinit cft-tcp.conf

1.  When the *cftinit complete*
    message is displayed, run  <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> using the command:

     cft start

1.  When the *CFTMAIN process
    ID is xxxxx* message is displayed, perform one or more transfers:

     CFTUTIL send part=BOSTON,idf=TXT

1.  Check that the transfers are
    complete:

     cftcatab

1.  Run the sample program:

     cd &lt;installdir>/runtime/src/capi ; ./APIXMP1

<span class="bold_in_para">Results</span>: The result should correspond to the catalog contents:

> PART=NEW YORK, IDT=&lt;dynamic identifier>,IDF=TXT  
> PART=BOSTON ,IDT=&lt;dynamic identifier>,IDF=TXT  
> APIXMP1 \_ 2 record(s) found

1.  Stop  <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span>:

     cft stop
