{
    "title": "Managing Network Profiles",
    "linkTitle": "Managing Network Profiles",
    "weight": "190"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Managing Security

[Creating Network Profiles](#Defining_Network_Profiles)

[Displaying Network Profiles](#Displaying_Net_Prof)

[Filtering the Network Profile display](#Filtering_Net_Prof_display)

[Deleting a Network Profile](#Deleting_net_prof)

[Updating a Network Profile](#Updating_Net_Prof)

<span id="Defining_Network_Profiles"></span>

## Creating Network Profiles

To create a Network profile:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the nodes:

Security Management &gt; Transfer Security Management

1.  Right-click the <span style="font-weight: bold;">Network Profile</span> sub-node, and then select <span style="font-weight: bold;">New</span> from the context menu.

Gateway displays the <span id="New_Network_Profile_window"></span><span style="font-style: italic;">New Network Profile</span> window.

1.  Complete the fields of the <span style="font-style: italic;">New Network Profile</span> window as described in the following table. Click <span style="font-weight: bold;">OK</span> to confirm.

Depending on the fields and options that you select, the other options may change dynamically.

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Field</p>         </th>
<th class="HeadD-Column1-Header1"><p>Description</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;">Network Profile</span></p>         </td>
         <td><p>Enter a name for the Network Profile. The Profile name must be unique in the Network Profile database.<br />
Maximum: 31 characters.</p>         </td>
      </tr>
      <tr>
         <td><p><span style="font-weight: bold;">Origin address/ Port</span></p>         </td>
         <td><p>Enter the originating address and <span style="font-weight: bold;">Port</span> number that this Profile is associated with.</p>         </td>
      </tr>
      <tr>
         <td><p><span style="font-weight: bold;">Destination address/ Port</span></p>         </td>
         <td><p>Enter the destination address and <span style="font-weight: bold;">Port</span> number that this Profile is associated with.</p>         </td>
      </tr>
      <tr>
         <td><p><span style="font-weight: bold;">Network type</span></p>         </td>
         <td><p>Select the Network type:</p>
<ul>
<li>TCP/IP</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span style="font-weight: bold;">Network security</span></p>         </td>
         <td><p>Select the type of security required for this Profile:</p>
<ul>
<li>None</li>
<li>TLS</li>
<li>SSH</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span style="font-weight: bold;">Security Profile</span></p>         </td>
         <td><p>Select the Security Profile to associate with this Network Profile.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="Displaying_Net_Prof"></span>

## Displaying Network Profiles

To display all Network Profiles in the database:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the nodes:  
    <span style="font-weight: bold;">Security Management > Transfer Security Management</span>
2.  Click to select the <span style="font-weight: bold;">Network Profile</span> sub-node.  
    Gateway displays all existing Network Profiles in the display pane (right pane). The following information is listed for each Network Profile:
    -   Name
    -   Type
    -   Communication network type
    -   Origination address
    -   Destination address
    -   Security profile

<span id="Filtering_Net_Prof_display"></span>

## Filtering the Network Profile display

To regenerate a display of Network Profiles according to filtering criteria:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the nodes:

Security Management &gt; Transfer Security Management

1.  Right-click the <span style="font-weight: bold;">Network Profile</span> sub-node, and then choose <span style="font-weight: bold;">Select</span> from the context menu.

Gateway displays the <span style="font-style: italic;">Select Network Profiles</span> window.

1.  In the <span style="font-style: italic;">Select Network Profiles</span> window, enter values in the fields you want to use as selection criteria. For example, to display all Network Profiles for TCP/IP networks, select <span style="font-weight: bold;">TCP/IP</span> in the Network type selection box.
2.  When you have completed the fields you want to use as filtering criteria, click <span style="font-weight: bold;">OK</span> to confirm.

Gateway refreshes the display list of Network Profiles, applying your filtering criteria to determine the display content.

<span id="Deleting_net_prof"></span>

## Deleting a Network Profile

To remove a Network Profile from the database:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the nodes:

Security Management &gt; Transfer Security Management

1.  Click to select the <span style="font-weight: bold;">Network Profile</span> sub-node.

Gateway displays all existing Network Profiles in the display pane (right pane).

1.  In the display pane (right pane), right-click the icon at the beginning of the line that represents the Network Profile you want to delete, and then select <span style="font-weight: bold;">Delete</span> from the context menu.

Gateway displays a confirmation dialog box.

1.  In the confirmation dialog box, click <span style="font-weight: bold;">Yes</span> to continue with the deletion process.

Gateway removes the Network Profile from the database and from the display pane.

<span id="Updating_Net_Prof"></span>

## Updating a Network Profile

To modify and update a Network Profile:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the nodes:

Security Management &gt; Transfer Security Management

1.  Click to select the <span style="font-weight: bold;">Network Profile</span> sub-node.

Gateway displays all existing Network Profiles in the display pane (right pane).

1.  In the display pane (right pane), right-click the icon at the beginning of the line that represents the Network Profile you want to modify and update.

Gateway displays the a context menu.

1.  Select <span style="font-weight: bold;">Modify</span> from the context menu.

Gateway opens the <span style="font-style: italic;">Network Profile</span> editing window. This window contains the same fields as the [New Network Profile window](#New_Network_Profile_window), used for creating a Network Profile above.

Modify the contents of any of the displayed fields as required.

1.  Click <span style="font-weight: bold;">OK</span> to validate your changes.

Gateway closes the <span style="font-style: italic;">Network Profile</span> editing window, and updates the Network profile. The new values are visible in the display pane.

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
