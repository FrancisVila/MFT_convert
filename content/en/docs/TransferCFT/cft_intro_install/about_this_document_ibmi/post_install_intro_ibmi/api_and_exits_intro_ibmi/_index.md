{
    "title": "About  APIs and exits - IBM i",
    "linkTitle": "Build APIs and exits",
    "weight": "260"
}This section introduces the two application families that can be developed using
two interfaces and the development kit contents for building APIs.

-   Applications communicating
    with <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> to submit and monitor transfers or query the catalog,
    for example.
-   Exits enabling
    user programs to take control during a send operation.

<span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> provides a programming interface in C, which require that you have the development kit, C compiler, and associated tools installed on your system.

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

The development kit used to integrate the <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> APIs is divided
into several directories that include the CFTPGM library, which contains all library modules necessary for APIs and exits. These library modules are required to use the corresponding function:

<table>
   <th>
      <tr>
<th>Module (in C language)         </th>
<th>Required to use Transfer CFT...         </th>
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

To generate a user application based on the <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> APIs and use
the file exit function, you must link the following with the <span class="code">libapisrv1.srvpgm</span> and <span class="code">libcftexe.srvpgm</span> libraries:

-   <span class="code">&lt;installdir>/runtime/src/capi/</span> containing
    a command entry and catalog query example
-   <span class="code">&lt;installdir>/runtime/src/exit/</span> containing
    simple examples of file exits, directory exits, and end
    -of-transfer exits
