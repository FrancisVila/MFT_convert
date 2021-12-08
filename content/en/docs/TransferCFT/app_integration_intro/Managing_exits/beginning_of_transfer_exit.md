{
    "title": "Using beginning-of-transfer exits",
    "linkTitle": "Beginning-of-transfer exit",
    "weight": "310"
}This page describes how to configure the environment for a beginning-of-transfer
type exit, EXITBOT. This  EXIT task lets you set the IDF to use, and is executed only in SERVER mode for CFTRECV (if not the requester), for CFTSEND (HOLD state), or for an implicit SEND.

{{< TransferCFT/transfercftname  >}} delivers both an `exitbot.c` sample to reference, located in the `<install_dir>/runtime/src/exit` folder, and an `exbus.h` header file which defines the API, located in the `<install_dir>/home/inc` folder.

<span id="Transfer_state"></span><span id="Title"></span><span id="Configuring_the_environment__End_of_transfer_exit"></span>

## Procedure

Before you submit this EXIT, you must customize the following
  {{< TransferCFT/componentshortname  >}} objects:

-   CFTEXIT:  This describes the EXIT environment and how this
    EXIT is activated.

<!-- -->

-   CFTPARM: This indicates the CFTEXIT object identifier.

Each CFTEXIT object corresponds to an EXIT task. The number of EXIT
tasks of all types simultaneously active is limited to a number depending
on the operating system.

<span id="Defining_the_CFTEXIT_object"></span>

### Defining the CFTEXIT object


|  Parameter  |  Definition  |
| --- | --- |
|  <a href="../../../c_intro_userinterfaces/command_summary/parameter_intro/id">ID</a> <br/>(Mandatory)  |  Command identifier (32 +1). The value of this identifier corresponds to the identifier defined in the EXITBOT parameter of the related CFTPARM object.  |
|  <a href="../../../c_intro_userinterfaces/command_summary/parameter_intro/language">LANGUAGE</a>  |  Language in which the user program is written. Possible values are COBOL and C language.  |
|  <a href="../../../c_intro_userinterfaces/command_summary/parameter_intro/prog">PROG</a>  |  Name of the executable module associated with the EXIT task (512 +1). This module is built from the interface provided with Transfer CFT linked to the program written by the user. To facilitate identification of the associated module, we recommend naming it CFTEXIB.  |
|  <a href="../../../c_intro_userinterfaces/command_summary/parameter_intro/type">TYPE</a> <br/>(Mandatory)  |  Available options include: FILE | ACCESS | EXEC | BOT<br/>Use BOT for a beginning-of-transfer exit.  |


**Example**

The following example provides a minimum of arguments:

```
CFTEXIT id=my_exitbot, type=bot, language=C, prog=$(CFTDIRRUNTIME)/bin/CFTEXIB
```
<span id="Defining_the_CFTPARM_object"></span>

### Defining the CFTPARM object

<table>
   <thead>
      <tr>
<th ><p>Parameter</p>         </th>
<th ><p>Definition</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td ><p><a href="../../../c_intro_userinterfaces/command_summary/parameter_intro/id">ID</a></p>
<p>(Mandatory)</p>         </td>
         <td ><p>CFTPARM object identifier.</p>         </td>
      </tr>
      <tr>
         <td ><p>EXITBOT </p>         </td>
         <td ><p>EXIT identifier. To activate a beginning-of-transfer EXIT, you
must specify an identifier that points to a CFTEXIT object.</p>         </td>
      </tr>
      <tr>
         <td colspan="2" >Please refer to the <a href="../../../c_intro_userinterfaces/web_copilot_ui/conf_intro/cftparm">CFTPARM</a> page for additional parameters and details.         </td>
      </tr>
   </tbody>
</table>

**Example**

The following example provides a minimum number of arguments for CFTPARM:

```
cftparm id=IDPARM, exitbot = 'my_exitbot', ...
```
