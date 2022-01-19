{
    "title": "Creating  an API application",
    "linkTitle": "Creating an API application",
    "weight": "210"
}The example provided below was designed for the ****cft-tcp.conf**** configuration example located in *&lt;installdir>/runtime/conf/*. For
this example, you should have already customized this file using the method described in [*Running
Transfer CFT{{< TransferCFT/componentshortname  >}} for the first time*]().

## Application components

The *&lt;installdir>/runtime/src/capi* subdirectory contains the:

- Sample source module,
    called *apixmp1.c*, which interacts with Transfer CFT{{< TransferCFT/componentshortname >}}. This program
    reads the Transfer CFT{{< TransferCFT/componentshortname >}} catalog and displays its contents in part or in
    full, depending on the restrictions set in the command line
- *makefile*
    compilation procedure, which uses the *apixmp1.c* sample source module
    to generate the APIXMPI executable file

The *&lt;installdir>/lib* subdirectory contains the:

- *libcftapi.a*
    module required to use Transfer CFT{{< TransferCFT/componentshortname >}} APIs

To generate the *APIXMP1* sample program, proceed as follows.

1. Access the *&lt;installdir>/runtime/src/capi* directory.
1. Enter the command:   ****`make`****

## Testing the configuration

To test the configuration, proceed as follows:

1. Access the *&lt;installdir>/runtime/conf/* directory.
1. Generate the Transfer CFT{{< TransferCFT/componentshortname >}} internal datafiles
    using *cftinit* with one of the two proposed configuration files:

`     cftinit cft-tcp.conf`

1. When the *cftinit complete*
    message is displayed, run Transfer CFT{{< TransferCFT/componentshortname >}} using the command:

`     cft start`

1. When the *CFTMAIN process
    ID is xxxxx* message is displayed, perform one or more transfers:

`     CFTUTIL send part=BOSTON,idf=TXT`

1. Check that the transfers are
    complete:

`     cftcatab`

1. Run the sample program:

`     cd <installdir>/runtime/src/capi ; ./APIXMP1`

****Results****: The result should correspond to the catalog contents:

> `PART=NEW YORK, IDT=<dynamic identifier>,IDF=TXTPART=BOSTON ,IDT=<dynamic identifier>,IDF=TXTAPIXMP1 _ 2 record(s) found`

1. Stop Transfer CFT{{< TransferCFT/componentshortname >}}:

`     cft stop`
