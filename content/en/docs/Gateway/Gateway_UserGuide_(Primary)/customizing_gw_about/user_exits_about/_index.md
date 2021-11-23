{
    "title": "User exits",
    "linkTitle": "User exits",
    "weight": "200"
}{{< Gateway/componentlongname  >}}: Customizing Gateway Processes

<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Caution  </strong></span>         </td>
         <td><strong>Please note that care should be taken when</strong> <strong><span class="mc-variable gateway_variables.in_Snippet_UserExitsCaution_ variable">customizing user exits</span>, as there are some</strong> <span style="color: #8b0000;font-weight: bold;">security risks</span> <strong>involved if the custom code is not properly reviewed and security best practices are not followed. Please see the</strong> <em><strong>Security Guide &gt; Security best practices &gt; </strong><a href="/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/SecurityGuide/Security_best_practices.htm#identified_threats_and_possible_mitigations">Identified threats and possible mitigations</a></em> <strong>section for additional information.<br />
</strong>         </td>
      </tr>
   </tbody>
</table>

[User exits](#intro)

[Internal and External exits](#Internal_and_external_exits)

[Exit families](#Exit_families)

[Exit-related files](#Exit_related_files)

[Exit management overview](#Exit_management_overview)

<span id="intro"></span>

## About User exits

A user exit is a point in a software program at which a user-developed program can take control of program processes.

Axway provides a set of C-language user exits with Gateway. You can find them in <span class="code">&lt;Gateway installation directory></span><span class="code" style="font-weight: bold;">/src</span>.

The exits are triggered by different types of Gateway processing event. They enable you to integrate your own custom processing routines with Gateway standard processing activity.

<span id="Internal_and_external_exits"></span>

## Internal and External exits

Gateway provides two basic categories of user exit: internal and external.

### Internal exits

Internal user exits are routines that Gateway invokes directly in synchronous calls from normal internal processes. The internal process waits for the result of the exit call before continuing with the programmed series of processing events. Internal exit implementation has the following limitations:

-   Gateway reliability can be affected by unexpected behavior of user exit code
-   C user API routines cannot be called from user exit code
-   Any load (CPU, IO, memory), overhead or latency due to user exit code may affect performances and trigger time-outs, due to file transfer and user exit code sharing monitor processes and related resources

You do not have to perform any particular procedure to activate internal exits in Gateway. Internal exit trigger points are automatically active in the processing code for each protocol.

### External exits

External user exits are routines that Gateway invokes in <span style="font-style: italic;">asynchronous</span> calls from the normal internal processes. Gateway sends a notification message to a separate set of user processes called <span style="font-style: italic;">notif</span> processes. On reception of the notification message, <span style="font-style: italic;">notif</span> calls the user exit routine corresponding to the event.

Contrary to the case for internal exits, Gateway continues other tasks while <span style="font-style: italic;">notif</span> manages exit processes. On reception of the expected response, Gateway re-synchronizes transfer processing from information saved in the associated exit context.

One set of <span style="font-style: italic;">notif</span> processes handles a single exit routine at a given time. Several sets of <span style="font-style: italic;">notif</span> processes can be active simultaneously, handling several exit routines.

#### How <span style="font-style: italic;">notif</span> operates

<span style="font-style: italic;">Notif</span> uses a request/response protocol to communicate with the Gateway Supervisor process. This protocol is encapsulated into a notification API that is similar to the standard C user API. The notification API is not directly available to user applications.

A state engine based on the notification API gets notification events from the Gateway supervisor process and schedules exit routine calls according to event descriptors. This engine contains the main program entry point of executable files linked with external user exit routines.

In order to enable user applications based on exit routines to easily follow protocol exchanges, all notification messages related to a protocol session instance are sent to the same user notification process.

<span id="Exit_families"></span>

## Exit families

User exit routines are classified into exit families.

The exit families delivered with Gateway are:

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p>INIT</p>         </td>
         <td><p>Initialization and end of the user notification routines</p>         </td>
      </tr>
      <tr>
         <td><p>FT</p>         </td>
         <td><p>File Transfer protocol events: protocol session establishment/ release, file transfer beginning/ completion/ abort</p>         </td>
      </tr>
      <tr>
         <td><p>XFER</p>         </td>
         <td><p>Transfer request state transition</p>         </td>
      </tr>
      <tr>
         <td><p>SITE</p>         </td>
         <td><p>Dynamic Site state transition</p>         </td>
      </tr>
      <tr>
         <td><p>LOG</p>         </td>
         <td><p>User selected log message</p>         </td>
      </tr>
      <tr>
         <td><p>SECS</p>         </td>
         <td><p>TLS and SSH handshake events</p>         </td>
      </tr>
      <tr>
         <td><p>EVENT</p>         </td>
         <td><p>Scheduling and File Storage Rule Tables for Event Management</p>         </td>
      </tr>
   </tbody>
</table>

<span id="Exit_related_files"></span>

## Exit-related files

To process an exit, Gateway reads from two files that provide information for the exit processes: the *header file* and the *source file*.

#### Header file

The header file describes the structure of the information that the exit sends as output or returns as input to the Gateway process. A header file contains separate sections for each exit routine in a given exit family.

Header files have names with <span class="code">.h</span> file extensions, for example, <span class="code">exitsecu.h</span>.

Header files are located in the <span class="code">&lt;Gateway installation directory></span><span class="code" style="font-weight: bold;">/inc</span> directory.

<span style="font-style: italic;">Do not modify the contents of this file</span>.

<span id="Source_files"></span>

#### Source file

The source file contains the customized user code that enables you to obtain the return values you require during exit processing.

The source files have names with <span class="code">.c</span> file extensions, for example, <span class="code">exitsecu.c</span>.

Gateway provides source file models in which you can insert your own code. You can find these models in the <span class="code">&lt;Gateway installation directory></span><span class="code" style="font-weight: bold;">/src</span> directory.

<span style="font-weight: bold;">Do not</span> move exit header files or exit source files from the directories where they are installed.

<span id="Exit_management_overview"></span>

## Exit management overview

To manage a user exit:

1.  Execute the <span class="code" style="font-weight: bold;">profile</span> batch file to set the environment variables for your platform.

-   For UNIX: execute the <span class="code" style="font-weight: bold;">profile</span> batch file located in <span class="code">&lt;Gateway installation directory></span><span class="code" style="font-weight: bold;">/run\_time/etc</span>
-   For Windows: execute the <span class="code" style="font-weight: bold;">profile.bat</span> batch file located in <span class="code">&lt;Gateway installation directory></span><span class="code" style="font-weight: bold;">\\run\_time\\etc</span>

Edit the source files that correspond to your exits, inserting the required code.  
After modifying a source file you must [compile the file](user_exits_c).

For security-related exits:

-   Activate the <span class="code" style="font-weight: bold;">secs\_exit\_scheduling</span> option (in the [advanced options](../../configuration_start_here/config_gateway_paras#Advanced_parameters) of the configuration menu).
-   For TLS, activate the <span class="code" style="font-weight: bold;">exit\_scheduling</span> parameter of the TLS Security Profile.

Related topics

[Configuration: Gateway parameters](../../configuration_start_here/config_gateway_paras)

[Internal user exits](user_exits_internal)

[User exits and Rule Tables](user_exits_internal/user_exits_rule_tables)

[User exits in Perl](user_exits_internal/user_exits_perl)

[External user exits](user_exits_external)

[User exits: Security functions](user_exits_external/user_exits_security_functions)

[TLS user exits](user_exits_external/user_exits_tls)

[SSH user exits](user_exits_external/user_exits_ssh)

[Compiling C user exits](user_exits_c)

[SWIFTNet-specific user exits](../../connectors_about/swiftnet_about/swiftnet_sig_list/swiftnet_user_exits)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
