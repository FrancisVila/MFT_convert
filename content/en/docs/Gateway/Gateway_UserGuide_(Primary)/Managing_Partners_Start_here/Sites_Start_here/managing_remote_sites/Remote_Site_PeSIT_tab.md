{
    "title": "New Remote Site: PeSIT tab",
    "linkTitle": "PeSIT tab",
    "weight": "220"
}{{< Gateway/componentlongname  >}}: Managing Partners

This topic describes the fields on the following tab of the *New Remote Site* window:

-   **PeSIT** (the fields displayed depend on whether the selected protocol is PeSIT HS D or E)

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Field         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Pre-connection phase:</p>         </td>
      </tr>
      <tr>
         <td><p><strong>ID to send to partner</strong> (field)<strong></strong></p>
<p>+ <em>Set password to send to partner</em> (button)</p>         </td>
         <td><p><span style="font-style: italic;">Optional</span></p>
<p>Set the identifier and password to send to the partner Site in the pre-connection phase.<br />
Maximum: 8 alphanumeric characters in each field.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>ID to receive from partner</strong> (field)<strong></strong></p>
<p>+ <em><strong>Set password to receive from partner</strong></em> (button)</p>         </td>
         <td><p><span style="font-style: italic;">Optional</span></p>
<p>Enter the identifier and password to receive from the partner Site in the pre-connection phase. Gateway checks that the received partner ID and password correspond to the values that you enter here.</p>         </td>
      </tr>
      <tr>
         <td><p>Connection phase:</p>         </td>
      </tr>
      <tr>
         <td><p>Set Client password to send / to receive <span style="font-weight: normal;"><br />
(buttons)</span></p>         </td>
         <td><p><span style="font-style: italic;">Optional</span></p>
<p>Open dialog boxes to enter the client password to send and to check during the connection phase.</p>         </td>
      </tr>
      <tr>
         <td><strong>Set Server password to send / to receive</strong><br />
<span style="font-weight: normal;">(buttons)</span>         </td>
         <td><p>Optional</p>
<p>Enter the server password to send and to check during the connection phase.</p>
<ul>
<li>PeSIT HS D: enter a numeric value less than 65536</li>
<li>PeSIT HS E: enter up to 8 alphanumeric characters</li>
</ul>         </td>
      </tr>
      <tr>
         <td>          </td>
      </tr>
      <tr>
         <td><p>Restart allowed</p>         </td>
         <td><p>Select this option to enable the restart function. The restart function allows you to restart an interrupted Transfer from a specified synchronization point. It is always the sender who initiates the restart, and the data receiver who decides from which synchronization point to restart the Transfer.</p>         </td>
      </tr>
      <tr>
         <td><p>Resynchronization allowed</p>         </td>
         <td><p>Select this option to enable the resynchronization function. If an incident occurs during data transfer, this option allows you to ask the partner to restart the Transfer from a previous synchronization point. The file remains open during this operation, which either user can initiate.</p>         </td>
      </tr>
      <tr>
         <td><p>Synchronization acknowledgment window</p>         </td>
         <td><p>The synchronization acknowledgment window allows you to:</p>
<ul>
<li>Specify the number of synchronization points between two acknowledgment messages</li>
<li>Restart an interrupted Transfer from a specific synchronization point</li>
</ul>
<p>Integer: 0 - 4. Default = 4.<br />
0 = acknowledgments not used.</p>
<p>For example, if you enter 3 in this field and 100 in the <span style="font-weight: bold;">Interval between synchronization points</span> field, Gateway sends 100 KB three times and then waits for an acknowledgment.</p>         </td>
      </tr>
      <tr>
         <td><p>Interval between synchronization points</p>         </td>
         <td><p>Specify the interval in Kbytes between synchronization points, that is the number of KB transmitted before the sender Site sends another synchronization point to the receiver Site.</p>
<p>Integer: –1 - 999.<br />
–1 = synchronization points not used.</p>         </td>
      </tr>
      <tr>
         <td><p>acknowledgment option</p>
<p>PeSIT HS E only</p>         </td>
         <td><p>Select one of the following acknowledgment options:</p>
<ul>
<li><span style="font-weight: bold;">Undefined</span>: acknowledgment behavior not known (default)</li>
<li><span style="font-weight: bold;">Not to ack</span>: no reply expected</li>
<li><span style="font-weight: bold;">By monitor</span>: Gateway automatically sends an acknowledgment request</li>
<li><span style="font-weight: bold;">By user</span>: waits for a user acknowledgment request</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Negative acknowledgment option</p>
<p>PeSIT HS E only</p>         </td>
         <td><p>The PeSIT HS E protocol supports END-TO-END acknowledgment, that is, the final destination of a file transfer can send a message to the originator to acknowledge reception of the file. This is a positive acknowledgment.</p>
<p>The <span style="font-weight: bold;">Negative acknowledgment option</span> allows the final destination to indicate that an error occurred during the Transfer.</p>
<p>Select this option to indicate that this Remote Site supports the negative acknowledgment extension. If you do not select this option, all negative acknowledgment requests are denied.</p>         </td>
      </tr>
      <tr>
         <td><p>Message</p>         </td>
         <td><p>Optional</p>
<p>Enter a free-format user message (PI 99).</p>
<p>Maximum: 512 alphanumeric characters.</p>
<p>For PeSIT HS only:</p>
<p>You can also use this field to transmit specific values to Axway Transfer CFT during the connection phase.</p>         </td>
      </tr>
      <tr>
         <td><p>Change direction support</p>         </td>
         <td><p>Select this option to poll this Remote Site on Gateway startup and to enable the Change Direction functionality, that is, to invert the Initiator/Responder roles between the partner Sites.</p>         </td>
      </tr>
      <tr>
         <td><p>Polling interval</p>         </td>
         <td><p>Specify the time (in minutes) to wait before starting the next polling cycle.</p>
<p>Format: <span style="font-style: italic;">MM</span>. Default = 0.</p>         </td>
      </tr>
      <tr>
         <td><p>Maximum connections</p>         </td>
         <td><p>Specify the maximum number of concurrent active connections in <span style="font-style: italic;">Change direction</span> mode. Note that <span style="font-style: italic;">change direction</span> connections are counted separately from the normal Initiator/Responder connections with this Site.</p>
<p>Integer: 0 - 999. Default = 0.</p>         </td>
      </tr>
      <tr>
         <td><p>Activated</p>         </td>
         <td><p>Select this option to activate the polling functionality.</p>
<p>If you do not select this option, all fields in the <span style="font-weight: bold;">Change direction support</span> section are ignored.</p>         </td>
      </tr>
      <tr>
         <td><p>Permanent connection</p>
<p>PeSIT HS only</p>         </td>
         <td><p>Select this option to establish permanent polled connections between server and client when <span style="font-weight: bold;">Change direction support</span> (the polling option) is configured.</p>         </td>
      </tr>
      <tr>
         <td><p>Connection hold delay</p>         </td>
         <td><p>Specify the time (in seconds) that the connection remains active without any transmission events.</p>         </td>
      </tr>
      <tr>
         <td><p>Heartbeat rate</p>         </td>
         <td><p>Specify the interval (in seconds) between Heartbeat messages emitted by the server to confirm the presence of a file-requestor client.</p>
<p>Integer: 0 - (2^31 - 1).</p>         </td>
      </tr>
   </tbody>
</table>

Related topics

[Working with Remote Sites](../)

[Site objects: Parameters List](../../managing_local_sites_cli/sites_parameter_list)

[About PeSIT Hors SIT](../../../../protocols_about/pesit_about)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
