{
    "title": "Creating a Remote Site object",
    "linkTitle": "Creating a Remote Site object",
    "weight": "90"
}## About the Gateway Remote Site object

To enable Gateway to communicate with remote partners, you require one or more Remote Site objects.

When you install Gateway, the software creates a set of Remote Sites adapted for use with different protocols, and enters these sites in your database. The procedure in this topic describes how to add your own Remote Sites.

## Procedure

In the left pane of the Gateway Navigator main window, click to expand the nodes:
**Partner Management &gt; Sites**

Right-click the Remote Site child node of the Sites node and then from the context menu, select **New...**  
Navigator displays the *New Remote Site* window.  
The set of fields and tabs displayed for Remote Site objects depends on the protocol that you select. The initial screen displays three tabs.

-   **General**
-   **Options**
-   **Network address**

  
When you select the protocol on the **General** tab, the tabs displayed will change.

Complete **General** tab.  

View fields

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Field         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>Alias         </td>
         <td>Enter an alias for the Remote Site object         </td>
      </tr>
      <tr>
         <td>Protocol         </td>
         <td><p>Select the protocol type that you will use for exchanges with this site.</p>
<p>When you select a protocol, the set of available tabs changes dynamically.</p>         </td>
      </tr>
      <tr>
         <td>Role         </td>
      </tr>
      <tr>
         <td>Initiator/Sender         </td>
         <td>Select one or more roles for the Remote Site in message exchanges         </td>
      </tr>
      <tr>
         <td>Initiator/Receiver         </td>
      </tr>
      <tr>
         <td>Responder/Sender         </td>
      </tr>
      <tr>
         <td>Responder/Receiver         </td>
      </tr>
   </tbody>
</table>

Complete the **Options** tab.

View fields

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Field         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>Maximum data block size (in bytes)         </td>
         <td><p>Specify the maximum data block size in bytes.</p>
<p>Integer: 128 - 8000. Default = 4000</p>         </td>
      </tr>
      <tr>
         <td>Maximum number of simultaneous connections to this Site         </td>
         <td><p>Specify the maximum number of connections to this Site.
Integer: 0 - 999. Default = 1.</p>
<p>For POP3 Sites, this value is always set to 1.</p>         </td>
      </tr>
      <tr>
         <td>Maximum number of simultaneous connections from this Site         </td>
         <td><p>Specify the maximum number of connections from this Site.
Integer: 0 - 999. Default = 1.</p>
<p>For POP3 Sites, this value is always set to 0.</p>         </td>
      </tr>
      <tr>
         <td>Maximum number of connection retries before time limit         </td>
         <td><p>Specify the maximum number of times the software tries to connect before stopping the Site.</p>
<p>Integer: 0 - 999. Default = 10.</p>         </td>
      </tr>
      <tr>
         <td>Time before first retry (in seconds)         </td>
         <td><p>Specify the minimum delay before the first connection retry.
Integer: 1 - 9999. Default = 10.</p>
<p>Each subsequent retry doubles the time that you enter here. For example, if you enter 10 seconds, the first retry occurs after 10 seconds, the second after 20 seconds, the third after 40 seconds, and so on until either:</p>
<ul>
<li>the maximum interval between retries is reached</li>
<li>or the maximum number of connection retries is reached</li>
</ul>         </td>
      </tr>
      <tr>
         <td>Maximum interval between retries (in seconds         </td>
         <td><p>Specify the maximum interval between connection retries. The value that you enter here must be greater than or equal to the value entered in the Time before first retry field.
Integer: 1 - 9999. Default = 1800.</p>
<p>For example, if you enter 30 in this field, 10 in the Time before first retry field and 10 in the Maximum number of connection retries field, then the first retry occurs after 10 seconds, the second after 20 seconds and the third after 30 seconds since this is the maximum interval allowed. Each subsequent retry occurs after 30 seconds until the maximum number of retries is reached, in this case 10.</p>         </td>
      </tr>
      <tr>
         <td>Sentinel:
Transfer Filter         </td>
         <td><p>Use this option to send a record of Transfer state changes to Sentinel. Select one of the following:</p>
<ul>
<li><strong>All</strong> – sends all Transfer state changes to Sentinel</li>
<li><strong>Summary</strong> – sends a summary of Transfer state changes. Summary Transfer states are: canceled, ended, acked, created, to begin</li>
<li><strong>None</strong> – sends no Transfer state changes</li>
<li><strong>Undefined</strong> – Axway Gateway uses the value set in the configuration menu</li>
</ul>         </td>
      </tr>
   </tbody>
</table>

Complete the **Network** address tab.

View fields

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Field</p>         </th>
<th class="HeadD-Column1-Header1"><p>Description</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Communication address</p>         </td>
         <td><p>You can define up to four communication addresses for the
Remote Site. You must define the properties for the Main address first.</p>
<p>To view an existing definition, or define the properties
for a new address, select one of the communication paths used to connect
to the Site:</p>
<ul>
<li><strong>Main address</strong> (default)</li>
<li>Alternative
address n°1</li>
<li>Alternative
address n°2</li>
<li>Alternative
address n°3</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Network type</p>         </td>
         <td><p>Select one of the following:</p>
<ul>
<li>TCP/IP</li>
<li>LU
6.2</li>
<li><strong>Empty</strong> (default)</li>
</ul>
<p>The fields displayed in the right pane depend on the type
of network that you select in this field.</p>         </td>
      </tr>
      <tr>
         <td><p>Initial communication path</p>         </td>
         <td><p>This field displays the initial address used to connect
to the Site. By default this field is set to <strong>Main
address</strong> and is grayed out. However, if an error occurs on the Main
address, you can select another communication address from the drop-down
list.</p>         </td>
      </tr>
      <tr>
         <td><p>Right pane - X.25 specific fields:</p>         </td>
      </tr>
      <tr>
         <td><p>Called address</p>         </td>
         <td><p>Specify the destination network address for the Remote
Site.<br />
Maximum: 15 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p>Calling address</p>         </td>
         <td><p>Specify the originator network address for the Site.<br />
Maximum: 15 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p>User data in the call request packet</p>         </td>
         <td><p>Maximum: 18 hexadecimal characters.</p>         </td>
      </tr>
      <tr>
         <td><p>Facilities</p>         </td>
         <td><p>Enter a hexadecimal string with facility services in the
format &lt;code&gt;&lt;value&gt;. The supported facility services are:</p>
<ul>
<li>Negotiate
packet size</li>
<li>Negotiate
window size</li>
<li>Reverse
charging</li>
<li>Throughput</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Logon message</p>         </td>
         <td><p>PEL and PeSIT protocols only</p>
<p>Enter a message to send before the protocol exchange. Use
this message to specify the target Application.</p>
<ul>
<li><strong>PEL</strong>: up to 31 alphanumeric characters</li>
<li><strong>PeSIT</strong>: up to 8 alphanumeric characters</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Logon code</p>         </td>
         <td><p>Select one of the following codes for the logon message:</p>
<ul>
<li>ASCII</li>
<li>EDCDIC</li>
<li>Binary</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Right pane - TCP/IP specific fields:</p>         </td>
      </tr>
      <tr>
         <td><p>IP address or machine name</p>         </td>
         <td><p>Enter the IP address.<br />
Maximum: 63 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p>Port number</p>         </td>
         <td><p>Enter the port number.</p>         </td>
      </tr>
      <tr>
         <td><p>Network Proxy</p>         </td>
         <td><p>This field displays a list of Proxies whose protocol is
either SOCKS4 or HTTPS. This field is available for all protocols.</p>
<p>Select a Proxy from the drop-down list.</p>         </td>
      </tr>
      <tr>
         <td><p>FTP Proxy</p>         </td>
         <td><p>FTP and HTTP only</p>
<p>This field displays the list of available FTP or HTTP Proxies.</p>
<p>Select a Proxy from the drop-down list.</p>         </td>
      </tr>
      <tr>
         <td><p>Right pane - LU 6.2 specific fields:</p>         </td>
      </tr>
      <tr>
         <td><p>Destination</p>
<p>(mandatory)</p>         </td>
         <td><p>Enter the CPI-C symbolic destination defined in the SNA
configuration database.<br />
Maximum: 8 alphanumeric characters.</p>
<p>The symbolic destination identifies the SNA resources to
use to connect to the Remote Site. This field contains a definition of
all the other parameters on this tab. Any values that you enter in the
other fields on this tab will override the values in the CPI-C symbolic
destination.</p>         </td>
      </tr>
      <tr>
         <td><p>User identification</p>         </td>
         <td><p>Enter the login user ID.</p>         </td>
      </tr>
      <tr>
         <td><p>Password</p>         </td>
         <td><p>Enter the login user password.</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Enter the conversation type. This version of the product
supports <em>Basic Conversation</em> only.</p>         </td>
      </tr>
      <tr>
         <td><p>Mode</p>         </td>
         <td><p>Enter the LU 6.2 mode name to use. The Mode Name determines
the session parameters to use.</p>         </td>
      </tr>
      <tr>
         <td><p>LU Partner</p>         </td>
         <td><p>Enter the Logical Unit for the Remote partner.</p>         </td>
      </tr>
      <tr>
         <td><p>LU Local</p>         </td>
         <td><p>Enter the Logical Unit for the Local partner.</p>         </td>
      </tr>
      <tr>
         <td><p>Transaction</p>         </td>
         <td><p>Enter the name of the CPI-C Transaction program that you
want to invoke.</p>         </td>
      </tr>
      <tr>
         <td><p>PIP</p>         </td>
         <td><p>Enter the Program Initialization Parameters.</p>         </td>
      </tr>
   </tbody>
</table>

Complete the **Protocol** tab that is displayed for your selected exchange protocol. The fields that appear on this tab vary greatly depending on the selected protocol. For details about tab content refer to the Gateway online documentation.

After completing the fields, click **OK** to accept the values and close the window.

Links to documentation set for Axway Gateway {{< Gateway/releasenumber  >}}:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
