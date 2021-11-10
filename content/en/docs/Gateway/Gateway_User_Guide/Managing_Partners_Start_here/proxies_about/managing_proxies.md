{
    "title": "Working with Proxies",
    "linkTitle": "Working with Proxies",
    "weight": "160"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Managing Partners

[Creating a Proxy object](#Creating_a_new_Proxy_object)

[Displaying a list of all Proxy objects](#Displaying_a_list_of_all_Proxy_objects)

[Displaying selected Proxy objects](#Displaying_selected_Proxy_objects)

[Viewing Proxy object attributes](#Viewing_the_attributes_of_a_Proxy_object)

[Modifying a Proxy object](#Modifying_a_Proxy_object)

[Deleting a Proxy object](#Deleting_a_Proxy_object)

<span id="Creating_a_new_Proxy_object"></span>

## Creating a new Proxy object

To define a new Proxy object:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the nodes:

Partner Management &gt; Sites

1.  Right-click <span style="font-weight: bold;">Proxy...</span>

Gateway displays the <span style="font-style: italic;">New Proxy</span> window.

1.  Complete the fields in the <span style="font-style: italic;">New Proxy</span> window as described in the following table.

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p>Field</p>         </td>
         <td><p>Description</p>         </td>
      </tr>
      <tr>
         <td><p>Name</p>         </td>
         <td><p>Enter the name of the Proxy.</p>
<p>Maximum: 31 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p>Comments</p>         </td>
         <td><p>Optional</p>
<p>Enter a free-text description of the Proxy.</p>
<p>Maximum: 80 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p>IP address</p>         </td>
         <td><p>Enter the IP address or host name for the Proxy.</p>         </td>
      </tr>
      <tr>
         <td><p>Port</p>         </td>
         <td><p>Enter the port number for the Proxy.</p>         </td>
      </tr>
      <tr>
         <td><p>User</p>         </td>
         <td><p>Optional</p>
<p>Enter a unique User name for the server.</p>
<p>Maximum: 25 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p>Password</p>         </td>
         <td><p>Optional</p>
<p>Enter the user password.</p>
<p>Maximum: 15 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p>Protocol</p>         </td>
         <td><p>Select one of the following protocols:</p>
<ul>
<li>FTP</li>
<li>HTTP</li>
<li>HTTPS</li>
<li>SOCKS4</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p><span style="font-style: italic;">Mandatory for FTP</span></p>
<p>Use this field to define the <a href="../../../protocols_about/ftp_about/ftp_using_proxy#Generic_FTP_Proxy_definitions">connection sequence at the session level</a>.</p>
<p>Select one of the following types:</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p><strong>Syntax</strong></p>         </td>
      </tr>
      <tr>
         <td><p>USER_AT_SITE</p>         </td>
         <td><p>USER &amp;(user)@&amp;(host_port)</p>
<p>PASS &amp;(password)</p>         </td>
      </tr>
      <tr>
         <td><p>USER_PASS_ACCT</p>         </td>
         <td><p>USER &amp;(user)@&amp;(host):&amp;(port) &amp;(proxy_user)</p>
<p>PASS &amp;(password)</p>
<p>ACCT &amp;(proxy_password)</p>         </td>
      </tr>
      <tr>
         <td><p>SITE</p>         </td>
         <td><p>USER &amp;(proxy_user)</p>
<p>PASS &amp;(proxy_password)</p>
<p>SITE &amp;(host):&amp;(port)</p>
<p>USER &amp;(user)</p>
<p>PASS &amp;(password)</p>         </td>
      </tr>
      <tr>
         <td><p>OPEN</p>         </td>
         <td><p>USER &amp;(proxy_user)</p>
<p>PASS &amp;(proxy_password)</p>
<p>OPEN &amp;(host):&amp;(port)</p>
<p>USER &amp;(user)</p>
<p>PASS &amp;(password)</p>         </td>
      </tr>
      <tr>
         <td><p>USER_OPEN</p>         </td>
         <td><p>OPEN &amp;(host_port)</p>
<p>USER &amp;(user)</p>
<p>PASS &amp;(password)</p>         </td>
      </tr>
      <tr>
         <td><p>User script</p>         </td>
         <td><p>Complete the script field.</p>         </td>
      </tr>
      <tr>
         <td><p>Script</p>         </td>
         <td><p>Complete this field if you selected <span style="font-weight: bold;">User script</span> as the Type.</p>
<p>Enter the user script to execute. You can enter the script name directly. Alternatively, specify the name of a text file that the script references. For example: <span class="code">file=proxy.txt</span></p>
<p>Set the end-of-line character using ‘<span class="code">\n</span>’.</p>         </td>
      </tr>
      <tr>
         <td><p>Allow different IP addresses for control and data sessions</p>         </td>
         <td><p>The remote IP address of a proxy control session may be different from the remote address of its data session. This is not normally allowed in Gateway for protection against bounce attacks.</p>
<p>If you check this option, FTP no longer verifies that the remote IP address is the same for the control session and data session.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="Displaying_a_list_of_all_Proxy_objects"></span>

## Displaying a list of all Proxy objects

To display a list of all Proxy objects stored in the database:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the nodes:

Partner Management &gt; Sites

1.  Click the <span style="font-weight: bold;">Proxy</span> sub-node.

In the right panel, Gateway displays a list of all <span style="font-weight: bold;">Proxy</span> objects.

<span id="Displaying_selected_Proxy_objects"></span>

## Displaying selected Proxy objects

If your Gateway configuration includes multiple Proxy objects, you can limit the display by applying display selection criteria:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the nodes:

Partner Management &gt; Sites

1.  Click the <span style="font-weight: bold;">Proxy</span> sub-node.

Gateway displays a list of all existing Proxy objects in the right pane.

1.  Right-click the <span style="font-weight: bold;">Proxy</span> sub-node, then select <span style="font-weight: bold;">Select...</span> from the context menu.

Gateway displays the <span style="font-style: italic;">Select Proxies</span> window.

1.  In the <span style="font-style: italic;">Select Proxies</span> window, select the name of the protocol with which you link to the Proxies you want to display and click <span style="font-weight: bold;">OK</span>.

Gateway regenerates the right window Proxy list, taking into account your selection criteria.

<span id="Viewing_the_attributes_of_a_Proxy_object"></span>

## Viewing Proxy attributes

To view the attributes of an existing Proxy:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the nodes:

Partner Management &gt; Sites

1.  Click to select <span style="font-weight: bold;">Proxy...</span>

Gateway displays all existing Proxies in the right (display) pane.

1.  In the right pane, right-click to select the Proxy that you want to modify.

Gateway displays a context menu.

1.  Select <span style="font-weight: bold;">View...</span> from the context menu.

Gateway opens the <span style="font-style: italic;">Proxy (read only)</span> window. This window provides you with a view of all attributes for the selected Proxy.

1.  When you have finished viewing the information, click <span style="font-weight: bold;">Close</span> to quit the window.

<span id="Modifying_a_Proxy_object"></span>

## Modifying a Proxy object

To modify an existing Proxy:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the nodes:

Partner Management &gt; Sites

1.  Click to select <span style="font-weight: bold;">Proxy...</span>

Gateway displays all existing Proxies in the right (display) pane.

1.  In the right pane, right-click to select the Proxy that you want to modify.

Gateway displays a context menu.

1.  Select <span style="font-weight: bold;">Modify</span> from the context menu.

Gateway opens the <span style="font-style: italic;">Proxy</span> editing window.

1.  Use the Proxy editing window to modify the Proxy characteristics and then click <span style="font-weight: bold;">OK</span> to confirm.

<span id="Deleting_a_Proxy_object"></span>

## Deleting a Proxy object

To delete an existing Proxy object:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the nodes:

Partner Management &gt; Sites

1.  Click the Proxy sub-node.

Gateway displays a list of all Proxies in the right pane.

1.  In the right pane, right-click the name of the Proxy you want to delete. Select <span style="font-weight: bold;">Delete...</span> from the context menu.

Gateway displays a confirmation dialog box.

1.  In the confirmation dialog box, click <span style="font-weight: bold;">Yes</span> to confirm the delete operation.  
    Alternatively, click <span style="font-weight: bold;">No</span> or <span style="font-weight: bold;">Cancel</span> to abandon the operation.
2.  Gateway deletes the Proxy object from the database and removes the entry from the display window.

Related topics

[Working with Proxies (command line)](../managing_proxies_cli)

[Using an FTP proxy](../../../protocols_about/ftp_about/ftp_using_proxy)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
