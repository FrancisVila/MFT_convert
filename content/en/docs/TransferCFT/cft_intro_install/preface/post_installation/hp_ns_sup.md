{
    "title": "Use the NonStop mode ",
    "linkTitle": "Use the NonStop mode",
    "weight": "200"
}Transfer CFT HP NonStop provides a start-process supervisor (CFTSUP) that can restart the Transfer CFT server or UI server in case of an unexpected stop. This section presents the following NonStop information:

-   [Overview](#Overview): describes the non-stop feature and compares it with the NonStop functionality delivered in previous versions
-   [Enable](#Enable): how to activate the non-stop mode
-   [Configure](#Configur): how to set additional non-stop mode parameters
-   [Syntax](#Syntax): the commands and their syntax
    -   [Messages](#Conventi): provides examples of using CFTSUP commands and returned messages
-   [Help](#Help): information on using command line help

## <span id="Overview"></span>Overview

The CFTSUP interface consist of:

-   A component watchdog called the supervisor
-   A utility that allows you to:
    -   Start and stop the supervisor
    -   Start and stop the Transfer CFT server and Transfer CFT Copilot server
    -   Display the status of these components

The differences between the CFTSUP interface and the NonStop mode delivered in Transfer CFT 2.3 are:

-   The Transfer CFT server and Transfer CFT Copilot server are both managed in NonStop mode.
-   The CFTSUP interface replaces the former CFTNSMON and CFTNSHUT commands.
-   Transfer CFT stops and is not restarted unless the reset command is set to RESTART=YES when you execute the Transfer CFT command CFTUTIL SHUT &lt;...&gt;.

## <span id="Enable"></span>Enable NonStop mode

This section describes how to enable the NonStop mode and start Transfer CFT.

1.  Activate the option:
2.  Start the Transfer CFT server, for example, using the supervisor:
3.  Optionally, check the Transfer CFT server status. For example:

More information and additional commands are described in the following sections.

### Recommendations

-   You can use the cftsup cft start command to start Transfer CFT, which also starts the supervisor. However, this does not mean the NonStop mode is running. To implement the NonStop mode, you must activate cft.guardian.nonstop in the UCONF configuration.
-   If you need to kill the Transfer CFT server, for example, use the cftsup cft kill command to keep the component from restarting.

## <span id="Configur"></span>Configure

The following table lists the UCONF parameters related to the NonStop option configuration. See the [UCONF parameters](../intro_os_features/hp_ns_batch) descriptions for more detailed information.

<table data-cellspacing="0">
   <thead>
      <tr class="header">
         <th>Parameter</th>
         <th>Default value</th>
         <th>Description</th>
      </tr>
   </thead>
   <tbody>
      <tr class="odd">
         <td>cft.guardian.nonstop         </td>
         <td>No         </td>
         <td>            <p>Enable the nonstop mode.</p>
            <ul>
               <li>Yes: Activate               </li>
               <li>No: Deactivate               </li>
            </ul>         </td>
      </tr>
      <tr class="even">
         <td>cft.guardian.collector         </td>
         <td>&lt;no value&gt;         </td>
         <td>Name of the EMS collector where the supervisor sends messages. See <a href="#Customiz">Customize the EMS collector</a> for details.         </td>
      </tr>
      <tr class="odd">
         <td>cft.guardian.processor         </td>
         <td>-1         </td>
         <td>Processor on which Transfer CFT is started.         </td>
      </tr>
      <tr class="even">
         <td>cft.guardian.backup_processor         </td>
         <td>-1         </td>
         <td>Backup processor on which Transfer CFT is started.         </td>
      </tr>
      <tr class="odd">
         <td>cft.guardian.process_name_prefix         </td>
         <td>LA         </td>
         <td>The first two letters of the Guardian process names.         </td>
      </tr>
   </tbody>
</table>

### <span id="Customiz"></span>Customize the EMS collector

To use the same collector for the supervisor as for Transfer CFT log messages, perform the following steps:

1.  Set the uconf cft.guardian.collector value to the name of the collector.  
    <table data-cellspacing="0">
       <tbody>
          <tr class="odd">
             <td>CFTUTIL uconfset id=cft.guardian.collector,value='$QACOL'         </td>
          </tr>
       </tbody>
    </table>
2.  In the Transfer CFT configuration, modify the CFTLOG definition to: NOTIFY=’%uconf:cft.guardian.collector%’. For example:  
    <table data-cellspacing="0">
       <tbody>
          <tr class="odd">
             <td>            <p>CFTLOG ID = 'LOG0',</p>
    <blockquote>
                <p>FNAME = '_CFTLOG',</p>
                <p>AFNAME = '_CFTLOGA',</p>
                <p>...</p>
                <p><strong>NOTIFY = ’%uconf:cft.guardian.collector%’,</strong></p>
                <p>CONTENT = 'FULL',</p>
                <p>...</p>
    </blockquote>         </td>
          </tr>
       </tbody>
    </table>
3.  Interpret the modified CFTLOG object.

## <span id="Syntax"></span>Syntax

Format

cftsup \[component\] Actions \[Options\]

Where:

component \[<u>ALL</u> | SUPV | CFT | COPILOT\]

-   ALL (default): Action applies to all components
-   SUPV: Watchdog utility
    -   Process is started with the name: prefix added to SUP
        -   For example: CFTL50I Started the supervisor with process id $**LASUP**
        -   Prefix = cft.guardian.process\_name\_prefix (the prefix in the example is LA)
    -   Stops when all components are terminated except if it was started explicitly as standalone process:
    -   cftsup SUPV START
    -   In this case, it only stops with an explicit stop:
    -   cftsup SUPV STOP
-   CFT: Action applies to the Transfer CFT server
-   COPILOT: Action applies to Transfer CFT Copilot server

Actions \[ START | STOP | STATUS | KILL | SHUT (for Transfer CFT server only)\]

-   KILL is only valid for the Transfer CFT and Transfer CFT Copilot servers.

<table data-cellpadding="0" data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td data-valign="top">         </td>
         <td data-valign="top"><span><strong>Note</strong></span>         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">The SHUT option only apply to the Transfer CFT sever.         </td>
      </tr>
   </tbody>
</table>

-   CFTUTIL SHUT FAST=YES the equivalent is cftsup CFT SHUT FAST=YES

### <span id="Conventi"></span>Messages

Message when starting the supervisor and all components

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>cftsup start</p>
            <p> </p>
            <p>CFTL50I Started supervisor with process id $MDSUP</p>
            <p>CFTL50I Started Transfer CFT with process id $MDAIN</p>
            <p>CFTL50I Started COPILOT with process id $MDCOP</p>         </td>
      </tr>
   </tbody>
</table>

Message when checking the status

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>cftsup status</p>
            <p> </p>
            <p>CFTL50I SUPV ($MDSUP) status Running</p>
            <p>CFTL50I CFT ($MDAIN) status Running</p>
            <p>CFTL50I COPILOT ($MDCOP) status Running</p>         </td>
      </tr>
   </tbody>
</table>

Message when performing a stop

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>cftsup stop</p>
            <p> </p>
            <p>CFTL50I Processing command</p>
            <p>CFTL50I Started COPSTOP with process id $MDCST</p>
            <p>CFTL57E Error: Transfer CFT is still active (status=TERMINATING)</p>         </td>
      </tr>
   </tbody>
</table>

Message when the supervisor is not started

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>cftsup supv status</p>
            <p> </p>
            <p>CFTL59E Supervisor $MDSUP is not started</p>         </td>
      </tr>
   </tbody>
</table>

## <span id="Help"></span>Help

From the home directory, enter the help command. For example:

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>/home/axway/&lt;user&gt;: cftsup help</p>
            <p> </p>
            <p>Syntax: cftsup [ALL|CFT|COPILOT|SUPV] Actions [Options]</p>
            <p>: cftsup ? (or HELP) for a list of the component and actions</p>
            <p>: cftsup Component ? (HELP) for actions to perform on components</p>         </td>
      </tr>
   </tbody>
</table>

Use command ? to display the parameter list:

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>/home/axway/&lt;user&gt;: cftsup "action" ?         </td>
      </tr>
   </tbody>
</table>
