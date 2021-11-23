{
    "title": "Working with Logs",
    "linkTitle": "Working with Logs",
    "weight": "240"
}{{< Gateway/componentlongname  >}}: Managing Transfers

[Viewing and managing Logs](#Viewing_Logs)

[Viewing archived logs](#Viewing)

[Viewing Secure Relay Master Agent Logs](#Viewing2)

[Suspending Log recording](#Suspending_logging)

[Archiving the current log](#Archiving_the_log)

[Filtering the Log message display](#Filtering_log_display)

[Refreshing the log display](#Refreshing_log_display)

<span id="Viewing_Logs"></span>

## Viewing and managing Logs

To view a complete list of all log messages contained in the current Log file:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the nodes:

Transfer Management &gt; Monitoring

1.  Click the **Log** node.

Gateway displays all logged messages in a table in the display pane (right pane). Each row of the table represents a logged message. The table columns contain the following information for each message.

<table>
         
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Column heading</p>         </th>
<th class="HeadE-Column1-Header1"><p>Contents</p>         </th>
<th class="HeadD-Column1-Header1"><p>Data format</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Status</p>         </td>
         <td><p>Message identifier, indicating the Gateway component that generated the message and the message type</p>         </td>
         <td><p>Icon and text</p>         </td>
      </tr>
      <tr>
         <td><p>Date</p>         </td>
         <td><p>Date that the message was logged</p>         </td>
         <td><p>dd:MM:yy</p>         </td>
      </tr>
      <tr>
         <td><p>Time</p>         </td>
         <td><p>Time that the message was logged</p>         </td>
         <td><p>HH:mm:SS</p>         </td>
      </tr>
      <tr>
         <td><p>Message</p>         </td>
         <td><p>Message text strings detailing the logged event</p>         </td>
         <td><p>Text</p>         </td>
      </tr>
   </tbody>
</table>

### Customizing the display

By default, Gateway displays the logged messages with each of the above columns visible and with the messages displayed from top to bottom in the order in which they were generated.

<span style="font-weight: bold;">To change the order of the display</span>, click one of the column headers cells.

-   Click the Status header cell once to rearrange the display in ascending alphabetical order of Status column identifiers. Click a second time to display in descending order.

<!-- -->

-   Click the Date or Time header cells to rearrange the display in descending chronological order. Click a second time to return to ascending chronological order.
-   Click the Message header cell to rearrange the display in ascending alphabetical order of Message text strings. Gateway lists non-alphabetic characters (for example, the quotation mark) before alphabetical characters. Click a second time to display in descending alphabetic order of message text strings.

<span style="font-weight: bold;">To change the size of displayed columns</span>, right-click any column.

Gateway displays the following context menu.

<img src="/Images/Gateway/DimensioningMenu.gif" width="154" height="65" />

Select the command:

-   <span style="font-weight: bold;">Autosize the column</span>, to adjust the selected column size to the column contents
-   <span style="font-weight: bold;">Hide the column</span>, to remove the entire column from view
-   <span style="font-weight: bold;">Autosize all the columns</span>, to adjust all columns to the size of their contents

### Managing displayed messages

In the Log display pane, Gateway provides two additional context menus that you can use to handle the displayed messages.

#### Status column context menu

Right-click the <span style="font-style: italic;">Status</span> column of any message in the display pane. Gateway displays the following context menu.

<img src="/Images/Gateway/Status_menu.gif" width="263" height="64" />

Select the command:

-   <span style="font-weight: bold;">Message help</span>, to open a window displaying detailed help information related to the message type
-   <span style="font-weight: bold;">Print the selection</span>, to print the message
-   <span style="font-weight: bold;">Copy the selection onto the clipboard</span>, to record the selected message to the clipboard memory for recopying to a text processing or mail tool

#### Date/Time/Message context menu

Right-click <span style="font-style: italic;">Date</span>, <span style="font-style: italic;">Time</span> or <span style="font-style: italic;">Message</span> column of any message in the display pane. Gateway displays the following context menu.

<img src="/Images/Gateway/Log_Message_context_menu.gif" width="179" height="108" />

Select the command:

-   <span style="font-weight: bold;">Open</span>, to open a new window containing a list of the displayed messages
-   <span style="font-weight: bold;">Find...</span>, to open a search dialog box, enabling you to search the log message list for specific character strings
-   <span style="font-weight: bold;">Select...</span>, to open the Select Log Messages dialog box  
    Use the fields of the Select Log Messages dialog box to create selection criteria for the display of Log messages. See [Filtering the Log message display](#Filtering_log_display) on how to use these fields.

Gateway applies your criteria to regenerate the display results.

-   <span style="font-weight: bold;">Refresh</span>, to refresh the display of Log messages, taking into account the most recent network events.
-   <span style="font-weight: bold;">Automatic refresh...</span>, to open a dialog box that enables you to set an automatic refresh cycle time interval. You can set the refresh interval in units of 10 seconds (10, 20, 30 seconds, etc.)

You can use one or more of the fields described in the following table:

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Field</p>         </th>
<th class="HeadD-Column1-Header1"><p>Use</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Maximum number</p>         </td>
         <td><p>Enter the maximum number of message results you want to view</p>         </td>
      </tr>
      <tr>
         <td><p>Date and start time</p>         </td>
         <td><p>You can select either a starting date or starting time criteria, or combine the two.</p>
<p>You can combine starting time and/or starting date criteria with ending time and/or ending date criteria.</p>
<p>To <span style="font-weight: bold;">set a starting date</span> as selection criteria:</p>
<ol>
<li>Click the down arrow on the starting date field displaying the current date.</li>
</ol>
<p>Gateway displays the calendar selection tool.</p>
<ol start="2">
<li>Use the calendar selection tool to navigate to the start month and start date of your choice.</li>
</ol>
<p>To <span style="font-weight: bold;">set a starting time</span> as selection criteria:</p>
<ol>
<li>Click the check box next to the starting time selection field.</li>
</ol>
<p>Gateway converts the time display from grayed out to normal text to indicate that it is activated.</p>
<ol start="2">
<li>Click to select the time unit you want to modify: hour, minute or second.</li>
</ol>
<p>Gateway highlights the time unit.</p>
<ol start="3">
<li>Type a valid number or use the up and down arrows to set the time unit.</li>
<li>Select and set the other time units (hour, minute, second) as required.</li>
</ol>         </td>
      </tr>
      <tr>
         <td><p>Date and end time</p>         </td>
         <td><p>You can set either an ending date or ending time criteria, or combine the two.</p>
<p>You can combine ending time and/or ending date criteria with starting time and/or starting date criteria.</p>
<p>To <span style="font-weight: bold;">set an ending date</span> as selection criteria:</p>
<ol>
<li>Click the down arrow on the ending date field displaying the current date.</li>
</ol>
<p>Gateway displays the calendar selection tool.</p>
<ol start="2">
<li>Use the calendar selection tool to navigate to the end month and end date of your choice.</li>
</ol>
<p>To <span style="font-weight: bold;">set an ending time</span> as selection criteria:</p>
<ol>
<li>Click the check box next to the ending time selection field.</li>
</ol>
<p>Gateway converts the time display from grayed out to normal text to indicate that it is activated.</p>
<ol start="2">
<li>Click to select the time unit you want to modify: hour, minute or second.</li>
</ol>
<p>Gateway highlights the time unit.</p>
<ol start="3">
<li>Type a valid number or use the up and down arrows to set the time unit.</li>
<li>Select and set the other time units (hour, minute, second) as required.</li>
</ol>         </td>
      </tr>
      <tr>
         <td><p>Sending process</p>         </td>
         <td><p>To select a sending process as display selection criteria:</p>
<ol>
<li>Click the down arrow located in the <span style="font-weight: bold;">Sending process</span> field.</li>
</ol>
<p>Gateway displays a drop-down list:</p>
<ul>
<li>CHK</li>
<li>EDI</li>
<li>EXT</li>
</ul>
<ul>
<li>FPSIT</li>
</ul>
<ul>
<li>FTP</li>
<li>HTTP</li>
<li>JCT</li>
<li>NDSP</li>
<li>NET</li>
<li>NOT</li>
<li>ODT</li>
<li>PCNX</li>
<li>PEL</li>
<li>POP</li>
<li>SECS</li>
<li>SMTP</li>
<li>SNA</li>
<li>SR</li>
<li>SUP</li>
<li>TDRV</li>
<li>TPM (PassPort)</li>
<li>TRADE</li>
<li>TSD</li>
<li>USR</li>
<li>VFD</li>
</ul>
<ol start="2">
<li>Select the sending process you want to use as display selection criteria.</li>
</ol>         </td>
      </tr>
      <tr>
         <td><p>Text extract</p>         </td>
         <td><p>Enter all or part of a text common to all the messages you want to display.</p>         </td>
      </tr>
   </tbody>
</table>

When you have set the criteria that you want to use to filter the display results, click <span style="font-weight: bold;">OK</span>.

Gateway applies your criteria to regenerate the display results.

-   <span style="font-weight: bold;">Refresh</span>, to refresh the display of Log messages, taking into account the most recent network events
-   <span style="font-weight: bold;">Automatic refresh...</span>, to open a dialog box that enables you to set an automatic refresh cycle time interval. You can set the refresh interval in units of 10 seconds (10, 20, 30 seconds, etc.)

<span id="Viewing"></span>

## Viewing Archived Logs

To view a complete list of all archived log files:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the nodes:

**Transfer Management &gt; Monitoring**

1.  Click the **Archived Log** node.

Gateway displays all archived log files in a table in the display pane (right pane). Each row of the table represents a log file. The table columns contain the following information for each message:

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Column heading         </th>
<th class="HeadE-Column1-Header1">Contents         </th>
<th class="HeadD-Column1-Header1">Data format         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>File Name         </td>
         <td>Archived Log file name         </td>
         <td>Icon and text         </td>
      </tr>
      <tr>
         <td>Date         </td>
         <td>Date when was the last writing into file         </td>
         <td>dd.MM.yy         </td>
      </tr>
      <tr>
         <td>Time         </td>
         <td>Date when was the last writing into file         </td>
         <td>HH:mm:SS         </td>
      </tr>
   </tbody>
</table>

1.  Double-click the archived file name to view it. A sub-tree item is created containing the file name for each archived log the user loads.

**Note**: Pay attention to how many archived logs you are loading.

<span id="Viewing2"></span>

## Viewing Secure Relay Master Agent Logs

To view the [log messages for Secure Relay Master Agent related to security termination](../xsr_ma_log_messages):

1.  In the left pane of the UI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the nodes:

Transfer Management &gt; Monitoring

1.  Click the **Secure Relay MA Log** node.

Gateway displays only the Secure Relay Master Agent logged messages related to security termination in a table in the display pane (right pane). Each row of the table represents a logged message. The table column descriptions are the same as for Log.

Security termination for both TLS and SSH requires Passport. If the security termination is not possible because Passport returns an error to the Secure Relay Router Agent, then the Secure Relay Router Agent sends a message to the Secure Relay Master Agent, which is logged in Gateway. If the connection to Passport cannot be established then this message is also sent to Gateway.

There are two types of messages which you will be able to see in the Secure Relay MA Log: Security termination failure and Full Certificate path for successful security termination. However, this depends on the Secure Relay Master Agent log configuration. To control the Secure Relay Master Agent configuration you must access the <span class="code">log.properties</span> file from the <span class="code">&lt;install\_dir>/run\_time/xsr</span> directory. Locate <span class="code">log4j.category.com.axway.xsr.log.securityTermination=ERROR, XSRTERM\_LOGFILE</span>, and set the level you need for logging:

-   ERROR – Logs for security termination failure
-   DEBUG – Logs for both security termination failure and successful security termination (contains the full certificate path)

The filter criteria that can be applied to a Secure Relay MA Log are similar to a log, except for the Sending process which is missing from the filter selection. You can use the same filter that you use on the Log and Archived log, but when applying a filter on Secure Relay MA Log, the Sending process, if set, will be ignored.

If there are several Gateways connected to the same Secure Relay Router Agent, then the error message is sent only to the Gateway that opened the port on which security termination failed.

> **Note:**
>
> You might encounter a "File Not Found” error when selecting a Secure Relay MA Log if Secure Relay is not activated.

### Limitations

If the connection with Secure Relay Master Agent is lost then Secure Relay does not store any messages. As a result, these messages will be lost.

If a connection is closed by a peer before the Secure Relay Router Agent notifies Gateway, or if a connection is dropped by the Secure Relay Router Agent as a result of an internal error, this will not be logged.

<span id="Suspending_logging"></span>

## Suspending Log recording

To suspend the recording of messages to the Log:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the nodes:

Transfer Management &gt; Monitoring

1.  Right-click the <span style="font-weight: bold;">Log</span> node.

Gateway displays a context menu.

1.  From the context menu select <span style="font-weight: bold;">Suspend recording</span>.

<span id="Archiving_the_log"></span>

## Archiving the current Log

To archive the current Log file:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the nodes:

Transfer Management &gt; Monitoring

1.  Right-click the <span style="font-weight: bold;">Log</span> node.

Gateway displays a context menu.

1.  From the context menu select <span style="font-weight: bold;">Archive...</span>

<span id="Filtering_log_display"></span>

## Filtering the Log message display

To select filter criteria for the display of current log messages:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the nodes:

Transfer Management &gt; Monitoring

1.  Right-click the <span style="font-weight: bold;">Log</span> node.

Gateway displays a context menu.

1.  From the Log context menu select <span style="font-weight: bold;">Select...</span>

Gateway displays the <span style="font-style: italic;">Select Log Messages</span> dialog box.

Use the fields of the <span style="font-style: italic;">Select Log Messages</span> dialog box to create selection criteria for the display of Log messages. You can use one or more of the fields described in the following table.

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Field</p>         </th>
<th class="HeadD-Column1-Header1"><p>Use</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Maximum number</p>         </td>
         <td><p>Enter the maximum number of message results you want to view.</p>         </td>
      </tr>
      <tr>
         <td><p>Date and start time</p>         </td>
         <td><p>You can select either starting date or starting time criteria, or combine the two.</p>
<p>You can combine starting time and/or starting date criteria with ending time and/or ending date criteria.</p>
<p>To <span style="font-weight: bold;">set a starting date</span> as selection criteria:</p>
<ol>
<li>Click the down arrow on the starting date field displaying the current date.</li>
</ol>
<p>Gateway displays the calendar selection tool.</p>
<ol start="2">
<li>Use the calendar selection tool to navigate to the start month and start date of your choice.</li>
</ol>
<p>To <span style="font-weight: bold;">set a starting time</span> as selection criteria:</p>
<ol>
<li>Click the check box next to the starting time selection field.</li>
</ol>
<p>Gateway converts the time display from grayed out to normal text to indicate that it is activated.</p>
<ol start="2">
<li>Click to select the time unit you want to modify: hour, minute or second.</li>
</ol>
<p>Gateway highlights the time unit.</p>
<ol start="3">
<li>Type a valid number or use the up and down arrows to set the time unit.</li>
<li>Select and set the other time units (hour, minute, second) as required.</li>
</ol>         </td>
      </tr>
      <tr>
         <td><p>Date and end time</p>         </td>
         <td><p>You can set either ending date or ending time criteria, or combine the two.</p>
<p>You can combine ending time and/or ending date criteria with starting time and/or starting date criteria.</p>
<p>To <span style="font-weight: bold;">set an ending date</span> as selection criteria:</p>
<ol>
<li>Click the down arrow on the ending date field displaying the current date.</li>
</ol>
<p>Gateway displays the calendar selection tool.</p>
<ol start="2">
<li>Use the calendar selection tool to navigate to the end month and end date of your choice.</li>
</ol>
<p>To <span style="font-weight: bold;">set an ending time</span> as selection criteria:</p>
<ol>
<li>Click the check box next to the ending time selection field.</li>
</ol>
<p>Gateway converts the time display from grayed out to normal text to indicate that it is activated.</p>
<ol start="2">
<li>Click to select the time unit you want to modify: hour, minute or second.</li>
</ol>
<p>Gateway highlights the time unit.</p>
<ol start="3">
<li>Type a valid number or use the up and down arrows to set the time unit.</li>
<li>Select and set the other time units (hour, minute, second) as required.</li>
</ol>         </td>
      </tr>
      <tr>
         <td><p>Sending process</p>         </td>
         <td><p>To select a sending process as display selection criteria:</p>
<ol>
<li>Click the down arrow located in the <span style="font-weight: bold;">Sending process</span> field.</li>
</ol>
<p>Gateway displays a drop-down list:</p>
<ol>
</ol>
<ul>
<li>CHK</li>
<li>EDI</li>
<li>EXT</li>
<li>FPSIT</li>
<li>FTP</li>
<li>HTTP</li>
<li>JCT</li>
<li>NDSP</li>
<li>NET</li>
<li>NOT</li>
<li>ODT</li>
<li>PCNX</li>
<li>PEL</li>
<li>POP</li>
<li>SECS</li>
<li>SMTP</li>
<li>SNA</li>
<li>SR</li>
<li>SUP</li>
<li>TDRV</li>
<li>TPM (PassPort)</li>
<li>TRADE</li>
<li>TSD</li>
<li>USR</li>
<li>VFD</li>
</ul>
<ol start="2">
<li>Select the sending process you want to use as display selection criteria.</li>
</ol>         </td>
      </tr>
      <tr>
         <td><p>Text extract</p>         </td>
         <td><p>Enter all or part of a text common to all the messages you want to display.</p>         </td>
      </tr>
   </tbody>
</table>

1.  To create a new filter:
    1.  Click **Add New Filter**, to create a blank template for the new filter.
    2.  Enter a name for the Filter.
    3.  Choose whether the filter is available only for this server, or whether it is global. (This option cannot be changed later).
    4.  Configure Selection criteria.

    <!-- -->

    1.  Add a text comment for this filter. (optional) 

<!-- -->

1.  To delete a filter:
    1.  Select the filter.
    2.  Click **Delete Filter**.

<!-- -->

1.  To modify a filter:
    1.  Select the filter.
    2.  Configure Selection criteria.
    3.  Click **Save and apply**.

<span id="Refreshing_log_display"></span>

## Refreshing the Log display

To refresh the display of Log messages, taking into account the most recent network events:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the nodes:

Transfer Management &gt; Monitoring

1.  Right-click the <span style="font-weight: bold;">Log</span> node.

Gateway displays a context menu.

1.  From the Log context menu select <span style="font-weight: bold;">Refresh...</span>.

Gateway regenerates the display, adding any new event messages.

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
