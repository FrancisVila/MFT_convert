{
    "title": "About  APIs and exits - IBM i",
    "linkTitle": "Build APIs and exits",
    "weight": "260"
}This section introduces the two application families that can be developed using
two interfaces and the development kit contents for building APIs.

-   Applications communicating
    with {{< TransferCFT/componentshortname >}} to submit and monitor transfers or query the catalog,
    for example.
-   Exits enabling
    user programs to take control during a send operation.

{{< TransferCFT/componentshortname  >}} provides a programming interface in C, which require that you have the development kit, C compiler, and associated tools installed on your system.

This section then describes how to
create the following applications:

-   An API
    application
-   File exit
-   Directory
    exit
-   End-of-transfer exit

<span id="Development_kit_contents"></span>

## Development kit contents

The development kit used to integrate the {{< TransferCFT/componentshortname  >}} APIs is divided
into several directories that include the CFTPGM library, which contains all library modules necessary for APIs and exits. These library modules are required to use the corresponding function:

<table>
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Module (in C language)         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1">Required to use Transfer CFT...         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>libapisrv1.srvpgm and librdrovrf.srvpgm         </td>
         <td>APIs         </td>
      </tr>
      <tr>
         <td>libcftexa.srvpgm         </td>
         <td>Directory EXITs         </td>
      </tr>
      <tr>
         <td>libcftexf.srvpgm         </td>
         <td>File EXITs         </td>
      </tr>
      <tr>
         <td>libcftexe.srvpgm         </td>
         <td>End-of-transfer EXITs         </td>
      </tr>
   </tbody>
</table>

To generate a user application based on the {{< TransferCFT/componentshortname  >}} APIs and use
the file exit function, you must link the following with the `libapisrv1.srvpgm` and `libcftexe.srvpgm` libraries:

-   `<installdir>/runtime/src/capi/` containing
    a command entry and catalog query example
-   `<installdir>/runtime/src/exit/` containing
    simple examples of file exits, directory exits, and end
    -of-transfer exits
