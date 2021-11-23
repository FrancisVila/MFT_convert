{
    "title": "Managing events on Gateway",
    "linkTitle": "Managing events",
    "weight": "120"
}{{< Gateway/componentlongname  >}}: Managing Events

This topic introduces Events, Decision Rules and Rule Tables in Gateway.

[About Event Management on Gateway](#About_GTW_event_management)

[Basic example](#Basic_example)

[Types of triggering event and conditions](#Types_of_triggering_events)

[Types of triggered processes](#Types_of_triggered_processes)

[Rule Table exits](#Rule_Table_exits)

<span id="About_GTW_event_management"></span>

## About Event Management on Gateway

You can configure Gateway to execute tasks triggered by different types of event and platform conditions. To do this, you create **Decision Rule** and <span style="font-weight: bold;">Rule Table</span> objects.

<span id="Decision_Rule_definition"></span>

### Decision Rule objects

In a Decision Rule object, you define one or more events that you want to trigger a specific action. You also specify the action that is carried out when the event occurs. You can create as many Decision Rules as you require. You place Decision Rules in Rule Tables.

There are four categories of Decision Rules and Rule Tables, as described in [Types of triggering event and conditions](#Types_of_triggering_events).

<span id="Rule_Table_definition"></span>

### Rule Table objects

A Rule Table object is an ordered list that contains one or more Decision Rules. For each Decision Rule that it contains, the Rule Table displays the following parameters:

-   Order
-   Decision Rule name
-   Action to be executed
-   Condition parameters

You arrange Decision Rules in a Rule Table in the order of preferred execution priority. When Gateway handles a transfer event or condition and evaluates the table, it evaluates the table entries from top to bottom in the order of priority. It selects the first Decision Rule that presents a complete conditional match.

Additionally, in a Rule Table object you can:

-   Define a default execution type for the Table. If no Decision Rule matches the Transfer parameters, Gateway applies the default execution type.
-   For Transfers, restrict processing to a limited set of Transfers, depending on the following conditions:
    -   Transfer type: TRANS, MSG ...
    -   Transfer mode: Responder, Initiator...
    -   Transfer direction: IN, OUT...
    -   Transfer state: ENDED, ACKED...
-   Set the log level to <span style="font-style: italic;">No Log</span>, <span style="font-style: italic;">Short</span> or <span style="font-style: italic;">Full</span>.

There are four categories of Decision Rules and corresponding Rule Tables, as described in [Types of triggering event and conditions](#Types_of_triggering_events).

You can define more than one Rule Table. You can define multiple Rule Tables in the same category or combine one or more Rule Tables of different categories.

<span id="Basic_example"></span>

### Basic example

As a basic example, you can link the reception event of an FTP transfer from a specified site (Site A in the illustration below) to a forwarding process that redirects the file to a designated server (Site B in the illustration below).

You define the triggering conditions and resulting processing for the transfer in a Decision Rule that you create and place in a Rule Table.

![](/Images/Gateway/EventManager1_756x165.png)

<span id="Types_of_triggering_events"></span>

### Types of triggering event and conditions

You can link many different types of events and conditions to execution processes. Gateway separates these event and condition types into four categories, each with its own set of Decision Rules and Rule Tables. The four different categories are described in the following table.

<table>
         
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Category</p>         </th>
<th class="HeadE-Column1-Header1"><p>Use</p>         </th>
<th class="HeadD-Column1-Header1"><p>Example</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Transfer Change State</p>         </td>
         <td><p>Trigger a specified action using one or more transfer attribute values as the triggering criteria.</p>         </td>
         <td><p>Create a Decision Rule specifying:</p>
<ul>
<li>Transfer Direction: Incoming</li>
<li>Transfer Type: FTP</li>
<li>Originating Site: SiteA</li>
</ul>
<p>To this condition, link an action forwarding the file to a specified server using an outgoing transfer definition model.</p>
<p>When Gateway detects an incoming FTP transfer originating from SiteA, it initiates the Transfer Request.</p>
<p>For a detailed example of routing using Transfer State Change Decision Rules and Rule Tables, refer to <a href="decision_rule_example_routing">Usage example: Routing</a>.</p>         </td>
      </tr>
      <tr>
         <td><p>Directory Scanning</p>         </td>
         <td><p>Trigger a specified action using the detection of a specific file or file type in a directory of the Gateway host machine as the triggering criteria.</p>         </td>
         <td><p>Create a Decision Rule specifying as a condition that a file named <span class="code">example.txt</span> is present in the directory <span class="code">C:\xfb_poll\*</span>.</p>
<p>To this condition, link an action sending the file to a specified monitor via a Transfer Request.</p>
<p>When Gateway detects the specified file in the specified directory, it initiates the Transfer Request.</p>
<p>For a detailed example of a Transfer triggered by the presence of a file in a specified folder, refer to <a href="decision_rule_example_routing/decision_rule_example_dir_scan">Usage example: Directory Scanning</a>.</p>         </td>
      </tr>
      <tr>
         <td><p>Scheduling</p>         </td>
         <td><p>Trigger a specified action at a specific time.</p>
<blockquote>
<p><strong>Note:</strong></p>
<p>There is an application architecture issue that affects all time zones when adjusting for DST one hour back: the scheduled events do not run at all during the 1-hour period between the clocks being moved back and the time from which the clocks were originally moved back. (For example: in Brazil, after the time changes from 00:00 to 23:00, between 23:00 and 00:00 - 1-hour period- no scheduled events will run). After this 1-hour period, the events will resume running without requiring any intervention.</p>
</blockquote>         </td>
         <td><p>Create a Decision Rule specifying that the file <span class="code">todays_log</span> is archived every day at 12 a.m.</p>
<p>For a detailed example of the scheduling of a repeated task, refer to <a href="decision_rule_example_routing/decision_rule_example_scheduling">Usage example: Scheduling</a>.</p>         </td>
      </tr>
      <tr>
         <td><p>XMS</p>         </td>
         <td><p>Trigger a process linking an Axway Messaging transfer to a transfer via Gateway.</p>         </td>
         <td><p>Link an Axway Messaging connector to an XMS-type Decision Rule.</p>
<p>When Gateway detects a transfer over the connector it applies the appropriate Model to the transfer.</p>
<p>Refer to: <a href="../connectors_about/messaging_connector">Axway Messaging connector</a>.</p>         </td>
      </tr>
   </tbody>
</table>

In the main window of the GUI, each of the categories is represented by a separate node containing a specific set of menus and windows.

<span id="Types_of_triggered_processes"></span>

### Types of triggered processes

Decision Rules and Rule Tables link the triggering events to Gateway actions. There is a wide variety of actions that Gateway can execute. For example, when triggered by a Decision Rule, Gateway can:

-   Execute a batch file or Perl script

-   <table>
       <tbody>
          <tr>
             <td>         </td>
             <td><span><strong>Caution  </strong></span>         </td>
             <td><strong>Please note that care should be taken when</strong> <span style="color: #8b0000;font-weight: bold;"><span class="mc-variable gateway_variables.in_Snippet_UserExitsCaution_ variable">writing event scripts</span></span><strong>, as there are some</strong> <span style="color: #8b0000;font-weight: bold;">security risks</span> <strong>involved if the custom code is not properly reviewed and security best practices are not followed. Please see the</strong> <em><strong>Security Guide &gt; Security best practices &gt; </strong><a href="/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/SecurityGuide/Security_best_practices.htm#identified_threats_and_possible_mitigations">Identified threats and possible mitigations</a></em> <strong>section for additional information.<br />
    </strong>         </td>
          </tr>
       </tbody>
    </table>

-   Deposit a Transfer Request

-   Purge a Mailbox or archive a Log file

-   Apply a Model for a message transfer to an Axway Messaging server (XMS category only)

-   ...

<span id="Rule_Table_exits"></span>

### Rule Table exits

Gateway automatically associates three categories of Rule Table with the following exit functions that are called during processing.

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Rule Table category</p>         </th>
<th class="HeadD-Column1-Header1"><p>Associated exit</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Transfer Change State</p>         </td>
         <td><p>exitmisc.c</p>         </td>
      </tr>
      <tr>
         <td><p>Directory Scanning</p>         </td>
         <td><p>exitfs.c</p>         </td>
      </tr>
      <tr>
         <td><p>Scheduling</p>         </td>
         <td><p>exittemp.c</p>         </td>
      </tr>
   </tbody>
</table>

Gateway triggers these exits immediately before it scans the corresponding table for matching.

You can modify these Rule Table related exit functions and then locally recompile the functions in order to integrate the modifications into Gateway. This enables you to add additional control over whether or not Gateway analyzes a specific Rule Table. Alternatively you may choose to modify exits in order to apply reusable user variables to Transfer Models or to triggering conditions, or to apply alternate handling processes via APIs.

Related topics

[Overview: Event management](../ov_gateway/ov_events)

[Transfer states in Gateway](../transfers_start_here/submitting_transfer_requests_start_here/transfer_states)

[Working with Rule Tables and Decision Rules](working_with_rule_tables_and_decision_rules(gui))

[Creating an Axway Messaging connector](creating_an_xms_connector)

[Defining Decision Rule conditions](defining_decision_rule_conditions)

[Working with Decision Rules (command line)](working_with_decision_rules_cli)

[Working with Rule Tables (command line)](working_with_decision_rules_cli/working_with_rule_tables_cli)

[Decision Rules and Rule Tables: Parameters List](working_with_decision_rules_cli/decision_rules_rule_tables_parameter_list)

[Command syntax for Scheduling Event Models](working_with_decision_rules_cli/scheduling_event_model_command_syntax) (date syntax)

[Usage example: Routing](decision_rule_example_routing)

[Usage example: Directory Scanning](decision_rule_example_routing/decision_rule_example_dir_scan)

[Usage example: Scheduling](decision_rule_example_routing/decision_rule_example_scheduling)

[User exits and Rule Tables](../customizing_gw_about/user_exits_about/user_exits_internal/user_exits_rule_tables)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
