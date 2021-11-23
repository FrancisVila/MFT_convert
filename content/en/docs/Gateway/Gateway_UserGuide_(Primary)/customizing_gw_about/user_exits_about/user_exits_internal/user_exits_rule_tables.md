{
    "title": "User exits and Rule Tables",
    "linkTitle": "User exits and rule tables",
    "weight": "240"
}{{< Gateway/componentlongname  >}}: Customizing Gateway Processes

[Overview](#Overview)

[Activating the exit trigger](#Activating)

[Rule Table exit routines](#Rule_Table_exit_routines) ([ExitAfterTemporalEvent](#ExitAfterTemporalEvent) and [ExitAfterFileStoringEvent](#ExitAfterFileStoringEvent))

<span id="Overview"></span>

## Overview

Gateway provides two user exits related to the handling of Rule Tables. If activated, these exits enable you to create execution conditions based on one or more of the symbolic variables handled by the exit routine.

You can use these exits to:

-   Execute controls that determine whether or not a Table is scanned
-   Return user variables that can be reused in transfer models or in execution conditions
-   Initiate various processes via the APIs that are available to you

<span id="Activating"></span>

## Activating the exit trigger

When you create a Rule Table you define the table as being **with** or <span style="font-weight: bold;">without</span> an associated exit. You can do this using the GUI or the <span class="code" style="font-weight: bold;">peladmin create\_ruletable</span> command.

-   When you define a Rule Table <span style="font-weight: bold;">with</span> exit, Gateway executes the exit that corresponds to the rule table category before executing the normal table scanning process.
-   When you define a Rule Table <span style="font-weight: bold;">without</span> exit, Gateway scans the table without triggering the exit.

<span id="Rule_Table_exit_routines"></span>

## Rule Table exit routines

You can associate exit routines with two types of Rule Table:

-   Scheduling Rule Tables
-   Directory Scanning Rule Tables

<span id="ExitAfterTemporalEvent"></span>

### Scheduling type Rule Tables: ExitAfterTemporalEvent

For Scheduling-type Rule Tables, use the ExitAfterTemporalEvent exit.

Gateway calls the ExitAfterTemporalEvent exit immediately before scanning the Scheduling-type Rule Table. The exit returns a value to the Gateway standard processes that can determine whether or not the Scheduling Rule Table is to be scanned. Gateway transmits to the exit certain scheduling related symbolic variables, as well as the name of the Rule Table. Gateway can also pass user variables that are used in the conditions of the Decision Rules of the table or in the models that are applied when Rule Table conditions are satisfied.

Gateway provides a sample of the ExitAfterTemporalEvent exit file, <span class="code">ExitAfterTemporalEvent.c</span>, that contains a set of default values. The default values have no effect on Rule Table processing.

To customize the exit function, insert your own C-language code into the <span class="code">ExitAfterTemporalEvent.c</span> exit file. Your customized code determines the values that are returned to the standard Rule Table process. Gateway takes the results into account before it scans the table.

When you develop your code, you can create conditions using one or more of the ten variables that are handled by the ExitAfterTemporalEvent exit. You can also include many functions in your customized code by using APIs. For example, Gateway includes an API that enables you to obtain information about the calendar that is associated with a Rule Table.

When you develop your code, you can create conditions using one or more of the variables that are handled by the ExitAfterTemporalEvent exit. Gateway initializes 12 symbolic variables immediately before scanning that Directory Scanning Rule Table. Of these variables, the ExitAfterFileStoringEvent exit can return useful values for the <span class="code">integer\_user\_paramX</span> and <span class="code">string\_user\_paramX</span> variables.

You can also include many functions in your customized code by using APIs.

#### Syntax

int ExitAfterTemporalEvent(In\_ExitTemporal\_t \*in,Out\_ExitRte\_t \*out)

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p>ExitAfterTemporalEvent</p>         </td>
      </tr>
      <tr>
         <td><p>Input parameters</p>         </td>
         <td><p>In_ExitTemporal_t</p>         </td>
         <td><p>Structure that comprises Rule Table parameters.</p>         </td>
      </tr>
      <tr>
         <td><p>Output parameters</p>         </td>
         <td><p>Out_ExitRte_t</p>         </td>
         <td><p>Structure that specifies Rule Table related attributes modified by user code. Refer to <span class="code">exitrte.h</span> for more details on structure used.</p>         </td>
      </tr>
      <tr>
         <td><p>Return</p>         </td>
         <td><p>0</p>         </td>
         <td><p>Task performed successfully. Uses returned parameter value and proceeds normally.</p>         </td>
      </tr>
      <tr>
         <td><p>1</p>         </td>
         <td><p>Nothing done. Discards output parameters and proceeds normally.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="ExitAfterFileStoringEvent"></span>

### Directory Scanning type Rule Tables: ExitAfterFileStoringEvent

For Directory Scanning type Rule Tables, use the ExitAfterFileStoringEvent exit.

Gateway calls the ExitAfterFileStoringEvent exit immediately before scanning the Storing-type Rule Table. The exit returns a value to the Gateway standard processes that can determine whether or not the Directory Scanning Rule Table is to be scanned. Gateway transmits to the exit certain scheduling related symbolic variables, as well as the name of the Rule Table. Gateway can also pass user variables that are used in the conditions of the Decision Rules of the table or in the models that are applied when Rule Table conditions are satisfied.

Gateway provides a sample of the ExitAfterFileStoringEvent exit file, <span class="code">ExitAfterFileStoringEvent.c</span>, that contains a set of default values. The default values have no effect on Rule Table processing.

To customize the exit function you insert your own C-language code into the <span class="code">ExitAfterFileStoringEvent.c</span> exit file. Your customized code determines the values that are returned to the standard Rule Table process. Gateway takes the results into account before it scans the table.

When you develop your code you can create conditions using one or more of the variables that are handled by the ExitAfterFileStoringEvent exit. Gateway initializes 19 symbolic variables immediately before scanning that Directory Scanning Rule Table. Of these variables, the ExitAfterFileStoringEvent exit can return useful values for the <span class="code">integer\_user\_paramX</span> and <span class="code">string\_user\_paramX</span> variables.

You can also include many functions in your customized code by using APIs.

#### Syntax

int ExitAfterFileStoringEvent(In\_ExitFileStoring\_t \*in,Out\_ExitRte\_t \*out)

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p>ExitAfterFileStoringEvent</p>         </td>
      </tr>
      <tr>
         <td><p>Input parameters</p>         </td>
         <td><p>In_ExitFileStoring_t</p>         </td>
         <td><p>Structure that comprises Rule Table parameters.</p>         </td>
      </tr>
      <tr>
         <td><p>Output parameters</p>         </td>
         <td><p>Out_ExitXferBeforeBegin_t</p>         </td>
         <td><p>Structure that specifies Rule Table related attributes modified by user code. Refer to <span class="code">exitrte.h</span> for more details on structure used.</p>         </td>
      </tr>
      <tr>
         <td><p>Return</p>         </td>
         <td><p>0</p>         </td>
         <td><p>Task performed successfully. Uses returned parameter value and proceeds normally.</p>         </td>
      </tr>
      <tr>
         <td><p>1</p>         </td>
         <td><p>Nothing done. Discards output parameters and proceeds normally.</p>         </td>
      </tr>
   </tbody>
</table>

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
