{
    "title": "Using beginning-of-transfer exits",
    "linkTitle": "Beginning-of-transfer exit",
    "weight": "330"
}This page describes how to configure the environment for a beginning-of-transfer
type exit, EXITBOT. This EXIT task lets you set the IDF to use, and is executed only in SERVER mode for CFTRECV (if not the requester), for CFTSEND (HOLD state), or for an implicit SEND.

Transfer CFT delivers both an `exitbot.c` sample to reference, located in the `<install_dir>/runtime/src/exit` folder, and an `exbus.h` header file which defines the API, located in the `<install_dir>/home/inc` folder.

## <span id="Transfer_state"></span><span id="Title"></span><span id="Configuring_the_environment__End_of_transfer_exit"></span>Procedure

Before you submit this EXIT, you must customize the following
Transfer CFT objects:

-   CFTEXIT: This describes the EXIT environment and how this
    EXIT is activated.

<!-- -->

-   CFTPARM: This indicates the CFTEXIT object identifier.

Each CFTEXIT object corresponds to an EXIT task. The number of EXIT
tasks of all types simultaneously active is limited to a number depending
on the operating system.

### <span id="Defining_the_CFTEXIT_object"></span>Defining the CFTEXIT object

<table data-cellspacing="0">
   <thead>
      <tr class="header">
         <th>            <p>Parameter</p></th>
         <th>            <p>Definition</p></th>
      </tr>
   </thead>
   <tbody>
      <tr class="odd">
         <td>            <p><a href="../../c_intro_userinterfaces/command_summary/parameter_intro/id">ID</a> </p>
            <p>(Mandatory)</p>         </td>
         <td>            <p>Command identifier (32 +1). The value of this identifier
corresponds to the identifier defined in the EXITBOT parameter of the
related CFTPARM object.</p>         </td>
      </tr>
      <tr class="even">
         <td>            <p><a href="../../c_intro_userinterfaces/command_summary/parameter_intro/language">LANGUAGE</a></p>         </td>
         <td>            <p>Language in which the user program is written. Possible values are COBOL and C language.</p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p><a href="../../c_intro_userinterfaces/command_summary/parameter_intro/prog">PROG</a>  </p>         </td>
         <td>            <p>Name of the executable module associated with the EXIT
task (512 +1). This module is built from the interface provided with Transfer
CFT linked to the program written by the user. To facilitate
identification of the associated module, we recommend naming it CFTEXIB.</p>         </td>
      </tr>
      <tr class="even">
         <td>            <p><a href="../../c_intro_userinterfaces/command_summary/parameter_intro/type">TYPE</a> </p>
            <p>(Mandatory)</p>         </td>
         <td>            <p>Available options include: FILE | ACCESS | EXEC | BOT</p>
            <p>Use BOT for a beginning-of-transfer exit.</p>         </td>
      </tr>
   </tbody>
</table>

Example

The following example provides a minimum of arguments:

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>CFTEXIT id=my_exitbot, type=bot, language=C, prog=$(CFTDIRRUNTIME)/bin/CFTEXIB</p>         </td>
      </tr>
   </tbody>
</table>

### <span id="Defining_the_CFTPARM_object"></span>Defining the CFTPARM object

<table data-cellspacing="0">
   <thead>
      <tr class="header">
         <th>            <p>Parameter</p></th>
         <th>            <p>Definition</p></th>
      </tr>
   </thead>
   <tbody>
      <tr class="odd">
         <td>            <p><a href="../../c_intro_userinterfaces/command_summary/parameter_intro/id">ID</a></p>
            <p>(Mandatory)</p>         </td>
         <td>            <p>CFTPARM object identifier.</p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>EXITBOT </p>         </td>
         <td>            <p>EXIT identifier. To activate a beginning-of-transfer EXIT, you
must specify an identifier that points to a CFTEXIT object.</p>         </td>
      </tr>
      <tr class="odd">
         <td colspan="2">Please refer to the <a href="../../c_intro_userinterfaces/about_cftutil/configuring_cft_start_here/cftparm">CFTPARM</a> page for additional parameters and details.         </td>
      </tr>
   </tbody>
</table>

Example

The following example provides a minimum number of arguments for CFTPARM:

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>cftparm id=IDPARM, exitbot = 'my_exitbot', ...</p>         </td>
      </tr>
   </tbody>
</table>
