{
    "title": "New Rule Table: Scheduling Event tab ",
    "linkTitle": "Scheduling Event tab",
    "weight": "200"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Managing Events

When you create or update a Scheduling-type Rule Table, Gateway displays the <span style="font-weight: bold;">Scheduling Event</span> tab in the <span style="font-style: italic;">New Rule Table</span> window. The <span style="font-weight: bold;">Scheduling Event</span> tab, in turn, links you to the <span style="font-style: italic;">[New calendar](#Calendar_definition_window)</span> window.

Use the <span style="font-weight: bold;">Scheduling Event</span> tab to define one or more sets of dates that can trigger a Gateway action.

<span id="Scheduling_event_tab"></span>

## Scheduling Event tab

Use the <span style="font-weight: bold;">Scheduling Event</span> tab to specify the date(s) and time(s) a process is triggered.

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Element         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p><span id="scheduling_event_cal"></span>Calendars</p>         </td>
         <td><p>The <span style="font-weight: bold;">Calendars</span> frame contains a list of the scheduling calendars that have been created to trigger events.</p>
<p>You create scheduling calendars in the <a href="#Calendar_definition_window">New calendar window</a>.</p>         </td>
      </tr>
      <tr>
         <td><p>Dates</p>         </td>
         <td><p>For any line (calendar) you select in the <span style="font-weight: bold;">Calendars</span> frame, the <span style="font-weight: bold;">Dates</span> frame displays all triggering dates for the selected calendar.</p>         </td>
      </tr>
      <tr>
         <td><p>Hours</p>         </td>
         <td><p>For any line (calendar) you select in the <span style="font-weight: bold;">Calendars</span> frame, the <span style="font-weight: bold;">Hours</span> frame displays all triggering times for the selected calendar.</p>         </td>
      </tr>
      <tr>
         <td><p>New</p>         </td>
         <td><p>Click <span style="font-weight: bold;">New</span> to open the <a href="#Calendar_definition_window">New calendar window</a>, enabling you to schedule an event time.</p>         </td>
      </tr>
      <tr>
         <td><p>Update</p>         </td>
         <td><p>Click <span style="font-weight: bold;">Update</span> to open the <a href="#Calendar_definition_window">New calendar window</a> and modify a selected calendar.</p>         </td>
      </tr>
      <tr>
         <td><p>Delete</p>         </td>
         <td><p>Select the name of a scheduling calendar in the <span style="font-weight: bold;">Calendars</span> frame, and then click <span style="font-weight: bold;">Delete</span> to remove the selected calendar.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Delay</strong><br />
In the event that your Gateway server is out of service during a period when events are scheduled, this section enables you to specify the handling of the un-triggered events on server restoration.</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Select one of the following values:</p>
<ul>
<li><span style="font-weight: bold;">Until next delay</span> (default) – when Gateway restarts, it executes the next scheduled action at the normal scheduled time, ignoring programmed actions that were not executed when the server was out of service.</li>
<li><span style="font-weight: bold;">Infinite delay</span> – when Gateway restarts, it executes all actions that were scheduled but not executed due to server incapacity.</li>
<li><span style="font-weight: bold;">Special value</span> – when, on restart, the delay value you specify in the <span style="font-weight: bold;">Value</span> field is exceeded, the programmed action is abandoned.</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Value</p>         </td>
         <td><p>This field is active when you select <span style="font-style: italic;">Special value</span> in the <span style="font-weight: bold;">Type</span> field above. Enter a value to specify the maximum time within which a scheduled action can be executed on server restart. If this delay is exceeded, the programmed action is abandoned.<br />
<span style="font-weight: bold;">Example:</span><br />
You schedule an action to be triggered at 12:30 p.m. on Friday and you enter a <span style="font-weight: bold;">Special value</span> delay of one hour.<br />
If the server is out of service from 12:00 p.m. to 1:00 p.m. on Friday, the action is triggered on server restart because restart occurs within the specified delay.<br />
However, if the server is out of service from 12:00 p.m. to 2:00 p.m. on Friday, the action is abandoned because the allowed delay value is exceeded.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="Calendar_definition_window"></span>

## New calendar window

When you click the <span style="font-weight: bold;">New</span> button or the <span style="font-weight: bold;">Update</span> button of the <span style="font-weight: bold;">Scheduling Event</span> tab, Gateway opens the <span style="font-style: italic;">New calendar</span> window.

Use the <span style="font-style: italic;">New calendar</span> window to create or modify the times and dates when a Gateway action is triggered.

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Section         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p><span id="Calendar_pane"></span><strong>Calendar pane</strong></p>         </td>
         <td><p>Use the calendars displayed in the Calendar pane to select dates on which events are triggered.</p>
<ul>
<li>To display different months, click the left and right arrows situated to the left and right of the month names.</li>
<li>To select a date, click the date in any calendar. When you select the date, Gateway displays the date in the <a href="#Dates_pane">Dates pane</a>.</li>
<li>To select additional dates, click on more dates.<br />
Gateway adds the additional selections to the display in the <a href="#Dates_pane">Dates pane</a>.</li>
<li>To display the calendar of the month that contains today's date, click the <span style="font-weight: bold;">Today</span> button.</li>
<li>To remove a selected date, use the <span style="font-weight: bold;">Delete</span> button of the <a href="#Dates_pane">Dates pane</a>.</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span id="Dates_pane"></span>Dates</p>         </td>
         <td><p>The Dates pane displays the results of actions you perform in the <a href="#Calendar_pane">Calendar pane</a> and <a href="#selected_date">Selected Date</a> sections of the New calendar window.</p>
<p>Use the Dates pane to view and verify your scheduling data.</p>
<ul>
<li>To add a line to the scheduling display, create a date in the <a href="#Calendar_pane">Calendar pane</a> and <a href="#selected_date">Selected Date</a> section.</li>
<li>To remove a line from the scheduling display, click the line to select it and then click <span style="font-weight: bold;">Delete</span>. button situated immediately below the pane.</li>
<li>To modify a line of the scheduling display, select the line and then use the tools of the <a href="#selected_date">Selected Date</a> section to change the line contents.</li>
<li>To associate one or more time of day with a date, click to select the date, and then use the tools of Selected Hour section to create time triggers.</li>
</ul>
<p>When you are satisfied with the scheduling data, click the <span style="font-weight: bold;">OK</span> button at the bottom of the New calendar window.</p>
<p>Gateway closes the <span style="font-style: italic;"><a href="#Calendar_definition_window">New calendar</a></span> window and creates a new entry in the <a href="#scheduling_event_cal">Calendars list</a> of the <a href="#Scheduling_event_tab">Scheduling Event</a> tab main window.</p>         </td>
      </tr>
      <tr>
         <td><p><span id="selected_date"></span>Selected Date</p>         </td>
         <td><p>The Selected Date section contains elements that enable you to define and edit the date or series of dates that trigger a Gateway action.</p>
<p>The Selected Date section contains the following elements:</p>
<ul>
<li><span style="font-weight: bold;"><span id="date_selection_box"></span>Selected Date data entry box</span>:<br />
To work in this box, first click the radio button located immediately to the left of the box.<br />
You can:
<ul>
<li>Enter a date directly in this box. Be sure to respect the syntax for dates. For syntax information see <a href="../../working_with_decision_rules_cli/scheduling_event_model_command_syntax">Scheduling Event Model command syntax</a>.</li>
<li>Enter a date by using the interactive calendars in the <a href="#Calendar_pane">Calendar pane</a>. After you enter a date via the a calendar, you can edit the date in the data entry box.</li>
<li>Enter a date by using the Date Syntax boxes, located below the Selected Date data entry box. When you use the Data Syntax boxes to create a date and then click <span style="font-weight: bold;">Add</span> or <span style="font-weight: bold;">Apply</span>, Gateway enters the data in the data entry box.</li>
<li>Edit existing dates by selecting an entry in the <a href="#selected_date">Selected Date</a> pane and then editing the time in the Selected Date data entry box.</li>
</ul></li>
<li><strong>Date Syntax boxes:</strong><br />
The Date Syntax boxes help you define dates by providing you with a series of choices that ensure a syntactically correct date definition.<br />
To work with these boxes, first click the radio button located immediately to the left of the first box.<br />
When you begin creating a new date, only one Date Syntax box is visible. When you work with this box, more boxes appear depending on the date syntax you are creating. To create a date, follow this procedure:</li>
</ul>
<div class="indentTable">
<ol>
<li>Click the first Date Syntax box to display the drop-down list. From the list, select the beginning of a date expression. The list comprises the following choices:
<ul>
<li>add</li>
<li>remove</li>
<li>keep</li>
<li>and</li>
</ul>
<br />
When you make a selection from the drop-down list, a second Date Syntax box appears to the right of the first box.</li>
<li>Click the second box to display the drop-down list. Choose a second element of your date definition expression from the list.<br />
When you make a selection from the drop-down list, a third Date Syntax box appears to the right of the second box.</li>
<li>Select elements from selection boxes as long as new boxes appear. When your date selection syntax is complete, the selected item in the last box terminates with a period, indicating the end of the expression.</li>
<li>Click <strong>Add</strong> to accept the date definition and add it to the <a href="#selected_date">Selected Date pane</a>.</li>
</ol>
</div>
<ul>
<li><span style="font-weight: bold;">Apply</span> button: Click <span style="font-weight: bold;">Apply</span> to update a selected entry in the Selected Date pane after you edit it in the Selected Date data entry box.</li>
<li><span style="font-weight: bold;">Add</span> button: Click <span style="font-weight: bold;">Add</span> to add the time currently displayed in the Selected Date entry box to the Selected Date pane.</li>
<li><span style="font-weight: bold;">Clear</span> button: Click clear to abandon the creation of a date selection expression and clear all data from the Date Syntax boxes.</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Hours (applied to all dates)</p>         </td>
         <td><p>The Hours pane displays the results of actions you perform in the Hour section of the <span style="font-style: italic;">New calendar</span> window.</p>
<p>Use the Hours pane to view and verify your triggering time data. You can associate multiple triggering times with a single entry in the <a href="#Dates_pane">Dates pane</a>.</p>
<ul>
<li>To add a triggering time to the Hours display pane, create a time trigger in the <a href="#selected_hour">Selected Hour</a> section.<br />
The triggering times you create apply to every date in the <a href="#selected_date">Selected Date</a> pane.</li>
<li>To remove a triggering time from the Hours display pane, click the line to select it, then click the <span style="font-weight: bold;">Delete</span> button situated immediately below the pane.</li>
<li>To modify a triggering time in the Hours display pane, click the line to select it, then use the tools of the <a href="#selected_hour">Selected Hour</a> section to change the line contents.</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span id="selected_hour"></span>Selected Hour</p>         </td>
         <td><p>The Selected Hour section contains elements that enable you to define a time of day when Gateway triggers an action. The triggering times you define in this section apply to every date in the <a href="#selected_date">Selected Date</a> pane.</p>
<p>The Selected Hour section contains the following elements:</p>
<ul>
<li><span style="font-weight: bold;"><span id="hour_selection_box"></span>Selected Hour data entry box</span>:<br />
You can:
<ul>
<li>Enter trigger times directly in this box.<br />
Be sure to respect the syntax for time data. Refer to the syntax examples in the <a href="#examples">Examples of hour syntax</a> section.<br />
For additional syntax information see <a href="../../working_with_decision_rules_cli/scheduling_event_model_command_syntax">Scheduling Event Model command syntax</a>.</li>
<li>Enter times by using the <a href="#time_selection">Time-selection bar</a>.</li>
<li>Edit existing trigger times by selecting an entry in the <a href="#selected_hour">Selected Hour</a> pane and then editing the time in the Selected Hour data entry box.</li>
</ul></li>
<li><span style="font-weight: bold;">Apply</span> button: Click <span style="font-weight: bold;">Apply</span> to update a selected entry in the <a href="#selected_hour">Selected Hour</a> pane after you edit it in the Selected Hour data entry box.</li>
<li><span style="font-weight: bold;">Add</span> button: Click <span style="font-weight: bold;">Add</span> to add the time currently displayed in the Selected Hour data entry box to the <a href="#selected_hour">Selected Hour</a> pane.</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span id="time_selection"></span>Time-selection bar</p>         </td>
         <td><p>Use the <span style="font-style: italic;">Time-selection bar</span> to enter triggering times in the <a href="#hour_selection_box">Selected Hour data entry box</a> of the <a href="#selected_hour">Selected Hour</a> section.</p>
<p>To select a time of day that triggers an event, double-click anywhere on the Time selection bar. A pointer appears on the bar. Now click-drag the pointer on the bar to the time of your choice. You can choose an hour and minute, with a granularity limit of 5 minutes.</p>
<p>For example, using the selection bar you can choose 11:35 or 11:40 but not minutes between these times. For greater precision, choose a time using the selection bar, then edit the result directly in the <a href="#hour_selection_box">Selected Hour data entry box</a>.</p>         </td>
      </tr>
      <tr>
         <td><p><span id="examples"></span>Examples of hour syntax</p>         </td>
         <td><p>This pane displays examples of the correct syntax for time trigger entries.</p>
<p>Refer to <a href="../../working_with_decision_rules_cli/scheduling_event_model_command_syntax">Scheduling Event Model command syntax</a>.</p>         </td>
      </tr>
      <tr>
         <td><p>OK</p>         </td>
         <td><p>After creating date and time combinations that you want to use as triggering events, select <span style="font-weight: bold;">OK</span> to validate.<br />
Gateway closes the <span style="font-style: italic;"><a href="#Calendar_definition_window">New calendar</a></span> window and creates a new entry in the <a href="#scheduling_event_cal">Calendars list</a> of the <a href="#Scheduling_event_tab">Scheduling Event</a> tab main window.</p>         </td>
      </tr>
      <tr>
         <td><p>Cancel</p>         </td>
         <td><p>To abandon the creation of a triggering calendar, click <span style="font-weight: bold;">Cancel</span>.<br />
Gateway closes the <span style="font-style: italic;"><a href="#Calendar_definition_window">New calendar</a></span> window and without changing the <a href="#Scheduling_event_tab">Scheduling Event</a> tab.</p>         </td>
      </tr>
   </tbody>
</table>

Related topics

[Working with Rule Tables and Decision Rules](../../working_with_rule_tables_and_decision_rules(gui))

[Defining Decision Rule conditions](../../defining_decision_rule_conditions)

[Decision Rules and Rule Tables: Parameters List](../../working_with_decision_rules_cli/decision_rules_rule_tables_parameter_list)

[Command syntax for Scheduling Event Models](../../working_with_decision_rules_cli/scheduling_event_model_command_syntax) (date syntax)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
