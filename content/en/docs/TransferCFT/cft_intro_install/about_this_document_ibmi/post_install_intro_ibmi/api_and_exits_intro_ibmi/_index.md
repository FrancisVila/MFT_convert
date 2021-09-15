{
    "title": "Build APIs and exits",
    "linkTitle": "Build APIs and exits",
    "weight": "250"
}# <span id="Building_CFT_API_applications"></span>About APIs and exits - IBM i

This section introduces the two application families that can be developed using
two interfaces and the development kit contents for building APIs.

-   Applications communicating
    with Transfer CFT to submit and monitor transfers or query the catalog,
    for example.
-   Exits enabling
    user programs to take control during a send operation.

Transfer CFT provides a programming interface in C, which require that you have the development kit, C compiler, and associated tools installed on your system.

This section then describes how to
create the following applications:

-   An API
    application
-   File exit
-   Directory
    exit
-   End-of-transfer exit

## <span id="Development_kit_contents"></span>Development kit contents

The development kit used to integrate the Transfer CFT APIs is divided
into several directories that include the CFTPGM library, which contains all library modules necessary for APIs and exits. These library modules are required to use the corresponding function:

<table cellspacing="0">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Module (in C language)</th>
         <th>Required to use Transfer CFT...</th>
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

To generate a user application based on the Transfer CFT APIs and use
the file exit function, you must link the following with the libapisrv1.srvpgm and libcftexe.srvpgm libraries:

-   &lt;installdir>/runtime/src/capi/ containing
    a command entry and catalog query example
-   &lt;installdir>/runtime/src/exit/ containing
    simple examples of file exits, directory exits, and end
    -of-transfer exits
