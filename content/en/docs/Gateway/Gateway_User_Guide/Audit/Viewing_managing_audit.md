{
    "title": "Viewing and managing Audit",
    "linkTitle": "Viewing and Managing Audits",
    "weight": "220"
}## Viewing Audits

To view a complete list of all audit messages contained in the current audit file:

1.  In the left pane of the GUI main window, click **+** to expand the nodes:  
    **Transfer Management** > **Monitoring**
2.  Click the **Audit** command

Gateway displays all audit messages in a pair of tables in the display pane (to the right). Each row of the main table represents an audit message. Selecting a row from the main display loads the second display to show what changes have been made.

The main table columns contain the following information for each message.

<table>
   <tbody>
      <tr>
         <td><strong>Column heading</strong>         </td>
         <td><strong>Contents</strong>         </td>
         <td><strong>Data format</strong>         </td>
      </tr>
      <tr>
         <td><strong>Action Result</strong>         </td>
         <td>The result of the audited action         </td>
         <td>Icon and text         </td>
      </tr>
      <tr>
         <td><strong>Date</strong>         </td>
         <td>Date and time when the message was audited         </td>
         <td>dd:MM:yy HH:mm:SS         </td>
      </tr>
      <tr>
         <td><strong>User</strong>         </td>
         <td>The user who altered the configuration         </td>
         <td>Text         </td>
      </tr>
      <tr>
         <td><strong>Resource Type</strong>         </td>
         <td>The resource type that was altered         </td>
         <td>Text         </td>
      </tr>
      <tr>
         <td><strong>Resource Name</strong>         </td>
         <td>The name of the resource that was altered         </td>
         <td>Text         </td>
      </tr>
      <tr>
         <td><strong>Action Type</strong>         </td>
         <td>The action type that was performed on the altered resource         </td>
         <td>Text         </td>
      </tr>
      <tr>
         <td><strong>Changes</strong>         </td>
         <td>Number of changes done with this action. You can see all the changes in the table from the bottom part.         </td>
         <td>Text         </td>
      </tr>
   </tbody>
</table>

### Customizing the main display

By default, Gateway displays the audit messages with each of the above columns visible and with the messages displayed from top to bottom in the reverse order in which they were generated.

**To change the order of the display**, click one of the column headers cells to sort according to that column. Click again to sort in reverse order.

The second table columns contain the following information for each message.

<table>
   <tbody>
      <tr>
         <td><strong>Column heading</strong>         </td>
         <td><strong>Contents</strong>         </td>
         <td><strong>Data format</strong>         </td>
      </tr>
      <tr>
         <td><strong>Id</strong>         </td>
         <td>Id of the change         </td>
         <td>Text         </td>
      </tr>
      <tr>
         <td><strong>Parameter Name</strong>         </td>
         <td>The parameter that was altered         </td>
         <td>Text         </td>
      </tr>
      <tr>
         <td><strong>Old Value</strong>         </td>
         <td>Old value of the altered parameter         </td>
         <td>Text         </td>
      </tr>
      <tr>
         <td><strong>New Value</strong>         </td>
         <td>New value of the altered parameter         </td>
         <td>Text         </td>
      </tr>
   </tbody>
</table>

### Customizing the second display

Click one of the column headers cells to sort according to that column. Click again to sort in reverse order. 

**To change the size of displayed columns**, right-click any column.

Gateway displays the following context menu.

Select the command:

-   **Autosize the column**, to adjust the selected column size to the column contents
-   **Hide the column**, to remove the entire column from view
-   **Autosize all the columns**, to adjust all columns to the size of their contents

<span id="Archive_Audit"></span>

## Viewing Archived Audits

To view a complete list of all archived audit files:

1.  In the left pane of the GUI main window, click **+** to expand the nodes:  
    **Transfer Management > Monitoring**
2.  Click the **Archived Audit**

Gateway displays all archived audit files in a table in the display pane (to the right). Each row of the table represents an audit file. The table columns contain the following information for each message:

<table>
   <tbody>
      <tr>
         <td><strong>Column heading</strong>         </td>
         <td><strong>Contents</strong>         </td>
         <td><strong>Data format</strong>         </td>
      </tr>
      <tr>
         <td>File Name         </td>
         <td>Archived Audit file name         </td>
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

1.  Double-click the archived file name to view it. A sub-tree item is created, containing the file name for each archived log the user loads.

> **Note:**
>
> Pay attention to how many archived audit you are loading.

### Archiving the current Audit

To archive the current Audit file:

1.  In the left pane of the GUI main window, click **+** to expand the nodes:  
    **Transfer Management > Monitoring**
2.  Right-click the **Audit  
    **Gateway displays a context menu.
3.  From the context menu select **Archive**

<span id="Filter_Audit"></span>

## Filtering the Audit message display

To select filter criteria for the display of current audit messages:

1.  In the left pane of the GUI main window, click **+** to expand the nodes:  
    **Transfer Management > Monitoring**

2.  Right-click the **Audit** command**  
    **Gateway displays a context menu.

3.  From the Audit context menu select **Filtering**

     

Gateway displays the *Select Audit Messages* dialog box. Use the fields of the *Select Audit Messages* dialog box to create selection criteria for the display of Audit messages. You can use one or more of the fields described in the following table.

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><strong>Field</strong>         </td>
         <td><strong>Use</strong>         </td>
      </tr>
      <tr>
         <td><strong>Maximum number</strong>         </td>
         <td>Enter the maximum number of message results you want to view.         </td>
      </tr>
      <tr>
         <td><strong>Date and start time</strong>         </td>
         <td>You can select either starting date or starting time criteria, or combine the two.<br />
You can combine starting time and/or starting date criteria with ending time and/or ending date criteria.<br />
To <strong>set a starting date</strong> as selection criteria:<br />
1. Click the down arrow on the starting date field displaying the current date.<br />
Gateway displays the calendar selection tool.<br />
2. Use the calendar selection tool to navigate to the start month and start date of your choice.<br />
To <strong>set a starting time</strong> as selection criteria:<br />
1. Click the check box next to the starting time selection field.<br />
Gateway converts the time display from grayed out to normal text to indicate that it is activated.<br />
2. Click to select the <strong>time unit</strong> you want to modify: hour, minute or second.<br />
Gateway highlights the time unit.<br />
3. Type a valid number or use the up and down arrows to set the time unit.<br />
4. Select and set the other time units (hour, minute, second) as required.         </td>
      </tr>
      <tr>
         <td><strong>Date and end time</strong>         </td>
         <td>You can set either ending date or ending time criteria, or combine the two.<br />
You can combine ending time and/or ending date criteria with starting time and/or starting date criteria.<br />
To <strong>set an ending date</strong> as selection criteria:<br />
1. Click the down arrow on the ending date field displaying the current date.<br />
Gateway displays the calendar selection tool.<br />
2. Use the calendar selection tool to navigate to the end month and end date of your choice.<br />
To <strong>set an ending time</strong> as selection criteria:<br />
1. Click the check box next to the ending time selection field.<br />
Gateway converts the time display from grayed out to normal text to indicate that it is activated.<br />
2. Click to select the <strong>time unit</strong> you want to modify: hour, minute or second.<br />
Gateway highlights the time unit.<br />
3. Type a valid number or use the up and down arrows to set the time unit.<br />
4. Select and set the other time units (hour, minute, second) as required.         </td>
      </tr>
      <tr>
         <td><strong>Username</strong>         </td>
         <td>Enter the name of the user you want to display         </td>
      </tr>
      <tr>
         <td><strong>Resource Type</strong>         </td>
         <td><p>To select a resource type as a display selection criteria:<br />
1. Click the down arrow located in the <strong>Resource type</strong> field.<br />
Gateway displays a drop-down list:<br />
Application, Audit, Certificate, CGate, CGateGroup, Config, ConnectedUser, DecisionRule, DiffusionList, Key, LocalSite, Log, Model, NetworkProfile, Profile, PropertyList, Proxy, PurgeModel, RuleTable, SGate, SGateGroup, Site, SshProfile, Statistics, TlsProfile, Trace, TradinPartner, Transfer, User, VFD, a nd others.</p>
<p>Select the resource type you want to use as display selection criteria.</p>         </td>
      </tr>
      <tr>
         <td><strong>Resource Name</strong>         </td>
         <td>Enter the name of the resource you want to filter         </td>
      </tr>
      <tr>
         <td><strong>Action Type</strong>         </td>
         <td><p>To select an action type as adisplay selection criteria:<br />
2. Click the down arrow located in the <strong>Action type</strong> field.<br />
Gateway displays a drop-down list:<br />
Admin, Append, Archive, Block, Cancel, Create, Delete, Load, Login, Logout, Mount, Purge, Read, Rebuild, Resume, Rotate, Start, Stop, Suspend, Truncate, Unblock, Unmount, Update, and others.</p>
<p>Select the action type you want to use as display selection criteria.</p>         </td>
      </tr>
      <tr>
         <td><strong>Action Result</strong>         </td>
         <td>To select an action result as a display selection criteria:<br />
3. Click the down arrow located in the <strong>Action result</strong> field.<br />
Gateway displays a drop-down list:<br />
· Attempt<br />
· Denied<br />
· Failure<br />
· Success<br />
Select the action result you want to use as adisplay selection criteria.         </td>
      </tr>
   </tbody>
</table>

**To create a new filter**:

1.  Click **Add New Filter**, to create a blank template for the new filter.
2.  Enter a name for the Filter.
3.  Choose whether the filter is available only for this server, or whether it is global. (This option cannot be changed later).
4.  Configure Selection criteria.
5.  Add a text comment for this filter. (optional)

**To delete a filter:**

1.  Select the filter.
2.  Click **Delete Filter**.

**To modify a filter:**

1.  Select the filter.
2.  Configure Selection criteria.
3.  Click **Save and apply**.

<span id="Refresh_Audit"></span>

## Refreshing the Audit display

To refresh the display of Audit messages, taking into account the most recent network events:

1.  In the left pane of the GUI main window, click **+** to expand the nodes:  
    **Transfer Management > Monitoring**
2.  Right-click the **Audit** command  
    Gateway displays a context menu.
3.  From the Audit context menu select **Refresh**

Gateway regenerates the display, adding any new audit messages.

<span id="Export_Audit"></span>

## Exporting the Audit display

To export Audit messages:

1.  In the left pane of the GUI main window, click **+** to expand the nodes:**  
    Transfer Management > Monitoring**
2.  Right-click the **Audit** command  
    Gateway displays a context menu.
3.  From the Audit context menu select **Export...  
    **Gateway then exports the view to the selected file.

## Exporting the Archived Audit display

To export Archived Audit messages:

1.  In the left pane of the GUI main window, click **+** to expand the nodes:  
    **Transfer Management > Monitoring**

<!-- -->

1.  Click on the **Archived** **Audit** node to expand the nodes  
    **Transfer Management > Monitoring**
2.  Right-click the desired Archived audit node  
    Gateway displays a context menu.
3.  From the Audit context menu select **Export...  
    **Gateway then exports the view to the selected file.

## Archiving audit files automatically

### About automatic audit archiving

With automatic audit archiving, Gateway can run without interruption while archiving audit data. You can set automatic audit archiving to be triggered either:

-   at regular intervals in time,
-   or once a set number of lines of audit is reached.

When it’s time to archive an audit file, Gateway renames the file currently in use, appending a timestamp; then it creates and opens a new empty audit file.

### How to set up automatic audit file archiving

To set up automatic archiving of audit files you can use the following parameters from the audit section:

-   `arc_active` values: *0* (inactive) or *1* (active)
-   <span class="code">auto\_arc\_lines</span> the number of lines at which you want to trigger audit file archiving.
-   <span class="code">auto\_arc\_period</span> the period, in the format: `MM:DD hh:mm:ss`
-   <span class="code">start\_arc\_period</span> start date and time, in the format: `MM:DD hh:mm:ss`

You can alter these parameters using the <span class="code">peluconf </span>command. Gateway takes the changes into account after the next restart.

**Example**: to set an automatic archive for the audit file every morning at 9:00 AM, enter the following command:

peluconf set -s audit arc\_active 1 auto\_arc\_period "00:01 00:00:00" start\_arc\_period "00:00 09:00:00"

### Disabling Sentinel audit replication

You can disable Sentinel replication when SWIFT protocol is not in use. To do that you can set the `sentinel_replication` parameter from audit section to 0. This parameter is ignored when SWIFT protocol is in use: in this case, Sentinel replication remains on.

Command: `peluconf set -s audit sentinel_replication 0`

> **Note:**
>
> You must restart Gateway before this takes effect, as this is a static parameter.

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
