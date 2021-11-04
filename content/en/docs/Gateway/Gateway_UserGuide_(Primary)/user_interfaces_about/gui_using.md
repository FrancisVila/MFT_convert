{
    "title": "Using the Graphical User Interface (GUI)",
    "linkTitle": "Using the GUI",
    "weight": "60"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: User Interfaces

[About the Gateway GUI](#About_the_GUI)

[Starting and stopping the GUI](#Starting_and_Stopping_the_GUI)

[How to set and modify your password](#How_to_set_and_modif_your_pw)

[About the main window](#About_the_Main_window)

<span id="About_the_GUI"></span>

## About the Gateway GUI

Gateway Navigator is the Gateway GUI (Graphical User Interface) provided for Windows platforms. Use this interface to manage the behavior and performance of your Gateway:

-   Configure Gateway
-   Create, manage and delete the objects that determine the Gateway processes
-   Manage User Profiles and User Groups
-   Consult log files
-   Monitor connections
-   Link events to Gateway processes
-   Define parameters for Transfer Requests
-   Manage Models for Transfer Requests
-   Manage security features

Before reading and applying the contents of this topic, it is recommended that you are familiar with Gateway. For a short introduction, refer to Overview: About <span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>.

<span id="Starting_and_Stopping_the_GUI"></span>

## Starting and stopping the GUI

### How to start the Windows GUI

To start the Gateway GUI:

1.  From the Windows <span style="font-weight: bold;">Start</span> menu, select <span style="font-weight: bold;">Programs > Axway Software > Axway \[ProjectName\] > Gateway > Start Navigator</span>.  
    Gateway opens the GUI main window.
2.  In the left frame of the main window, double-click the name of your Local Site displayed in the directory structure.  
    Gateway displays the login dialog window.
3.  Enter your user name and password, and click <span style="font-weight: bold;">Connection</span>.  
    In the left frame directory tree structure, Gateway displays the categories of objects that exist for your configuration, or that you can create. Use the GUI tools to create, manage and delete these objects.

### How to stop the GUI

To stop the Gateway GUI:

1.  From the <span style="font-weight: bold;">File</span> menu, select <span style="font-weight: bold;">Exit</span>.  
    Gateway displays a confirmation window.
2.  Select <span style="font-weight: bold;">Yes</span> to exit and close the GUI.

<span id="How_to_set_and_modif_your_pw"></span>

## How to set and modify your password

For local installations, by default the Gateway server is not protected by a password. To create a password for access as a local client, or modify an existing password:

1.  From the Windows <span style="font-weight: bold;">Start</span> menu, select <span style="font-weight: bold;">Programs > Axway Software > Axway \[ProjectName\]&gt; Start Navigator</span>  
    Alternatively, if you are using the <span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span> Navigator:  
    Select **Programs > Axway Software > Axway \[ProjectName\] > Gateway > Start Navigator**  
    Gateway opens the GUI main window.
2.  In the left frame of the main window, double-click the name of your Local Site displayed in the directory structure.  
    Gateway displays the login dialog window.
3.  In the login dialog window:
    -   Enter a user name in the <span style="font-weight: bold;">User</span> field
    -   Enter a password in the <span style="font-weight: bold;">New password</span> field
    -   Reenter the same password in the <span style="font-weight: bold;">Confirm password</span> field
    -   Click <span style="font-weight: bold;">Connection</span>.

Gateway registers the new password and opens a GUI session. The new password is required for the next time you log in with the name you specified in the <span style="font-weight: bold;">User</span> field.

<span id="About_the_Main_window"></span>

## About the main window

When you start and log in to the GUI, Gateway displays the main window:

<img src="/Images/Gateway/GatewayMainMenu_756x612.gif" class="maxWidth" />

### Title bar

The Title bar identifies the product you are using: <span style="font-weight: bold;"><span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span> Navigator</span>.

### Menu bar

The Menu bar contains the following menus.

<table>
         
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><a href="#File_menu">File</a></p>         </td>
         <td><p><a href="#View_menu">View</a></p>         </td>
         <td><p><a href="#Window_menu">Window</a></p>         </td>
         <td><p><a href="#Help_menu">Help</a></p>         </td>
      </tr>
   </tbody>
</table>

<span id="File_menu"></span>

#### File menu

The following table introduces the commands in the <span style="font-weight: bold;">File</span> menu.

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Use the command...</p>         </th>
<th class="HeadD-Column1-Header1"><p>To...</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Print...</p>         </td>
         <td><p>Print a Gateway formatted copy of the information visible in the display pane.</p>         </td>
      </tr>
      <tr>
         <td><p>Print preview</p>         </td>
         <td><p>Preview the page layout of the information visible in the display pane.</p>         </td>
      </tr>
      <tr>
         <td><p>Print setup...</p>         </td>
         <td><p>Open the Windows printer configuration dialog box.</p>         </td>
      </tr>
      <tr>
         <td><p>Save current settings</p>         </td>
         <td><p>Conserve the settings that you choose from the <span style="font-style: italic;">Menu bar</span> menus.</p>         </td>
      </tr>
      <tr>
         <td><p>Exit</p>         </td>
         <td><p>Close the Gateway GUI.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="View_menu"></span>

#### View menu

The <span style="font-weight: bold;">View</span> menu contains commands that enable you to customize the display of the information in the display pane.

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Use the command...</p>         </th>
<th class="HeadD-Column1-Header1"><p>To...</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>List</p>         </td>
         <td><p>Display the information in the display pane in the form of a list of small icons accompanied by labels.</p>         </td>
      </tr>
      <tr>
         <td><p>Details</p>         </td>
         <td><p>Display the information in the display pane in the form of a columned list. Each column of the list contains information concerning the type of object you are viewing. The columns displayed (in other words, the details) vary according to the type of object you select for viewing.</p>         </td>
      </tr>
      <tr>
         <td><p>List font...</p>         </td>
         <td><p>Open the font selection window. Use this window to specify the size, color and font type of the text that is visible in the display pane.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="Window_menu"></span>

#### Window menu

The <span style="font-weight: bold;">Window</span> menu contains commands that enable you to select the elements that are visible in the main window.

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Use the command...</p>         </th>
<th class="HeadD-Column1-Header1"><p>To...</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Toolbar</p>         </td>
         <td><p>Display, or alternatively, hide the Toolbar.</p>         </td>
      </tr>
      <tr>
         <td><p>Status bar</p>         </td>
         <td><p>Display, or alternatively, hide the Status bar.</p>         </td>
      </tr>
      <tr>
         <td><p>Workspace</p>         </td>
         <td><p>Display, or alternatively, hide the Workspace.</p>         </td>
      </tr>
      <tr>
         <td><p>Close all</p>         </td>
         <td><p>Simultaneously close all of the dialog windows that are currently open in the display pane.</p>         </td>
      </tr>
   </tbody>
</table>

Below the list of commands in the <span style="font-weight: bold;">Window</span> menu, Gateway lists the names of the dialog windows and display windows that you have opened from the display pane.

<span id="Help_menu"></span>

#### Help menu

The following table introduces the commands in the <span style="font-weight: bold;">Help</span> menu.

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Use the command...</p>         </th>
<th class="HeadD-Column1-Header1"><p>To...</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Contents...</p>         </td>
         <td><p>Open this online help.</p>         </td>
      </tr>
      <tr>
         <td><p>About...</p>         </td>
         <td><p>Open the <span style="font-weight: bold;">About...</span> window. This window provides information about the product you are using. Additionally, the window displays your:</p>
<ul>
<li>Available disk space</li>
<li>Product serial number</li>
</ul>
<p>When you finish reading the information in this window, click:</p>
<ul>
<li><span style="font-weight: bold;">Close</span> to close the window</li>
<li><span style="font-weight: bold;">Help</span> to close the window and open the online help</li>
</ul>         </td>
      </tr>
   </tbody>
</table>

<span id="Tool_bar"></span>

### Toolbar

The Toolbar displays a test field and a set of buttons that you can use to handle the objects and messages visible in the display pane.

You can choose to display or hide the Toolbar by using the <span style="font-weight: bold;">Toolbar</span> command of the [Window](#Window_menu) menu.

The following table describes the elements of the <span style="font-weight: bold;">Toolbar</span>.

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Element</p>         </th>
<th class="HeadD-Column1-Header1"><p>Use</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p><img src="/Images/Gateway/Connect.gif" width="16" height="16" /> Connect</p>         </td>
         <td><p>Click to open the connection dialog box for the server displayed in the <em>Server selection/ display box</em>.</p>         </td>
      </tr>
      <tr>
         <td><p><img src="/Images/Gateway/Disconnect.gif" width="16" height="16" /> Disconnect</p>         </td>
         <td><p>Click to disconnect from the server displayed in the <em>Server selection/ display box</em>.</p>         </td>
      </tr>
      <tr>
         <td><p><span id="server_display_box"></span>Server selection/ display box</p>         </td>
         <td><p>Displays the name of the Gateway server to which you are applying the toolbar tools.</p>         </td>
      </tr>
      <tr>
         <td><p><img src="/Images/Gateway/Display.gif" width="17" height="16" /> Display transfer requests</p>         </td>
         <td><p>Displays the contents of the Mailbox for the server displayed in the <em>Server selection/ display box</em>.</p>         </td>
      </tr>
      <tr>
         <td><p><img src="/Images/Gateway/LogViw.gif" width="16" height="16" /> Display log messages</p>         </td>
         <td><p>Displays current log messages for the server displayed in the <em>Server selection/ display box</em>.</p>         </td>
      </tr>
      <tr>
         <td><p><img src="/Images/Gateway/Print.gif" width="17" height="16" /> Print</p>         </td>
         <td><p>Prints the current contents of the <a href="#Display_panel">display pane</a>.</p>         </td>
      </tr>
      <tr>
         <td><p><img src="/Images/Gateway/Refresh.gif" width="16" height="16" /> Refresh</p>         </td>
         <td><p>Refreshes the display of the <a href="#Display_panel">display pane</a> with most recently received data.<br />
Alternatively, click anywhere inside the display pane and enter <span style="font-weight: bold;">F5</span>.</p>         </td>
      </tr>
      <tr>
         <td><p><img src="/Images/Gateway/SeltDisplay.gif" width="17" height="16" /> Select and display</p>         </td>
         <td><p>Opens the <span style="font-style: italic;">Select Transfer</span> dialog box, enabling you to filter the <a href="#Display_panel">display pane</a> contents according to various criteria.</p>         </td>
      </tr>
      <tr>
         <td><p><img src="/Images/Gateway/View.gif" width="16" height="16" /> View</p>         </td>
         <td><p>Enables you to select the format in which the display pane content is presented.</p>         </td>
      </tr>
      <tr>
         <td><p><img src="/Images/Gateway/Modify.gif" width="16" height="16" /> Modify</p>         </td>
         <td><p>Opens an editing window that enables you to modify the element you select in the <a href="#Display_panel">display pane</a>.</p>         </td>
      </tr>
      <tr>
         <td><p><img src="/Images/Gateway/Delete.gif" width="17" height="16" /> Delete</p>         </td>
         <td><p>Deletes the element(s) you select in the <a href="#Display_panel">display pane</a>.</p>         </td>
      </tr>
      <tr>
         <td><p><img src="/Images/Gateway/Copy.gif" width="17" height="16" /> Copy</p>         </td>
         <td><p>Copies the elements you select in the <a href="#Display_panel">display pane</a>.</p>         </td>
      </tr>
      <tr>
         <td><p><img src="/Images/Gateway/About.gif" width="17" height="16" /> About</p>         </td>
         <td><p>Opens the <span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span> product information dialog box. This box displays:</p>
<ul>
<li>Version and copyright information</li>
<li>Available disk space</li>
<li>Your product serial number</li>
<li>A <span style="font-weight: bold;">Help</span> button, that provides access to this online help</li>
</ul>         </td>
      </tr>
   </tbody>
</table>

<span id="Directory_tree_structure"></span>

### Directory tree structure

The left pane of the main window contains the <span style="font-style: italic;">Directory tree structure</span>.

#### Expanding and reducing the tree structure

Click the <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> icons in this pane to expand, or alternatively, reduce the displayed development of the directory tree.

#### Viewing folder contents

Each folder and subfolder in the directory tree is represented by an icon accompanied by the folder or subfolder name. Folders at the lowest (expanded) level of each branch of the <span style="font-style: italic;">Directory tree structure</span> can contain objects or messages. Click one of these folders, to view the objects or messages it contains in the display pane.

#### Example 1

When you click the <span style="font-weight: bold;">Log</span> folder in the <span style="font-weight: bold;">Transfer Management &gt; Monitoring</span> subdirectory of a server directory, Gateway displays a list of log messages collected for that server in the display pane.

#### Example 2

When you click the <span style="font-weight: bold;">Local Site</span> folder of the <span style="font-weight: bold;">Partner Management &gt; Sites</span> subdirectory of a server directory, Gateway displays a list of the Local Site objects that contain Site definitions for that server.

#### Managing folder contents: context menus

Folders at the lowest (expanded) level of each branch of the <span style="font-style: italic;">Directory tree structure</span> can contain objects or messages.

Right-click any of these folders, to view a context menu of possible actions you can perform for the folder. The content of the context menus varies according to the folder type.

#### Example 1

When you right-click the <span style="font-weight: bold;">\[ServerName\] &gt; Transfer Management &gt; Monitoring &gt; Log</span> folder, Gateway displays the following context menu.

<img src="/Images/Gateway/ContextMenu.gif" class="smallWidth" width="149" height="99" />

#### Example 2

When you right-click the <span style="font-weight: bold;">\[ServerName\] &gt; Partner Management &gt; Sites &gt; Local Site</span> folder, Gateway displays the following context menu.

<img src="/Images/Gateway/ContextMenu2.gif" class="smallWidth" width="168" height="83" />

In each example, Gateway displays a context menu that:

-   Gives the name of the folder you right-clicked
-   Lists the commands you can perform on the folder contents

When you select any of the commands listed in a context menu, Gateway either:

-   Directly executes the command
-   Opens a dialog window from which you execute the command by entering necessary information

For details on how to complete command dialog windows for the various Gateway objects and elements, refer to the related topics in this online help.

<span id="Display_panel"></span>

### Display pane

The display pane displays the contents of the folder you select in the [Directory tree structure](#Directory_tree_structure). Use the commands of the [View](#View_menu) menu to select the format in which the content is displayed.

#### User actions in the display pane

-   <span style="font-weight: bold;">Click</span> any displayed element in the display pane to select that element. You can then use the tools of the [Toolbar](#Tool_bar) to perform actions on the element.
-   <span style="font-weight: bold;">Double-click</span> any displayed object to open the editing window related to that object. The editing window varies according to the element type. In some cases the editing windows are read-only. For details concerning the contents of the editing windows for the various Gateway objects and elements, refer to the relevant topics in this online help.
-   <span style="font-weight: bold;">Right-click</span> any element in the display pane to view a context menu of the possible actions on that element. The contents of the context menu varies according to the element type. For details of the possible actions you can perform on Gateway objects and elements, refer to the relevant topics in this online help.
-   Press **Ctrl+F** to open the *Find* window. Use this window to search for a string in the display pane.

### Workspace

When you open an editing window in the [display pane](#Display_panel), and then click the window reduction icon in the upper right-hand corner of the editing window, Gateway reduces the window to a labeled button that is visible in the Workspace.

Display of the Workspace is optional. You can choose to display or hide the Workspace by using the <span style="font-weight: bold;">Workspace</span> command of the [Window](#Window_menu) menu.

To restore an editing window to its working dimensions in the display pane, do one of the following:

-   Click the icon that represents the editing window you want to reopen in the Workspace. Then select <span style="font-weight: bold;">Restore</span> in the context menu that is displayed.
-   Double-click the icon that represents the editing window you want to reopen in the Workspace.

To close a single reduced editing window, the Workspace, click the icon that represents the window and then select the <span style="font-weight: bold;">Close</span> command from the displayed context menu.

To close all reduced editing windows as well as all other open editing windows, select the [Window](#Window_menu) menu

### Status bar

The Status bar provides information about the selection you make in the [Directory tree structure](#Directory_tree_structure).

Display of the Status Bar is optional. You can choose to display or hide the Status bar by using the <span style="font-weight: bold;">Status bar</span> command of the [Window](#Window_menu) menu.

The displayed information depends on the type of folder you select and on the state of the elements in the folder.

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
