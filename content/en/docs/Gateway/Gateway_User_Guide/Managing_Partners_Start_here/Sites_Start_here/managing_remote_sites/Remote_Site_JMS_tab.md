{
    "title": "New Remote Site: JMS tab",
    "linkTitle": "JMS tab",
    "weight": "300"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Managing Partners

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Field         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>User name</p>         </td>
         <td><p>The user name (for the MOM user) for connection to the JMS provider.<br />
Maximum: 63 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p>Set Password</p>         </td>
         <td><p>Opens a dialog box to set the password for the MOM user, for connection to the JMS provider.<br />
Maximum: 127 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p>Class loader</p>         </td>
         <td><p>The Java class path used to locate <span class="code">jar</span> files of the JMS provider.</p>
<p>Enter the list of fully qualified <span class="code">jar</span> files (including path) separated by the '<span style="font-weight: bold;">:</span>' character on UNIX systems and '<span style="font-weight: bold;">;</span>' on Windows systems.</p>         </td>
      </tr>
      <tr>
         <td><p>Initial factory</p>         </td>
         <td><p>The Java class name of the Initial Context Factory.</p>
<p>For example:</p>
<p>com.sun.jndi.fscontext.RefFSContextFactory</p>         </td>
      </tr>
      <tr>
         <td><p>Connection factory</p>         </td>
         <td><p>The JNDI lookup name of the connection factory to be used (configured by the JMS provider administrator).</p>         </td>
      </tr>
      <tr>
         <td><p>URL</p>         </td>
         <td><p>The connection URL of the JMS provider. It usually consists of:</p>
<ul>
<li>a protocol</li>
<li>a hostname</li>
<li>a listening port</li>
</ul>
<p>For example:</p>
<p>tcp://localhost:4569</p>
<p>or</p>
<p>file:/var/mqm</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>The type of object used by the JMS provider to store/retrieve messages for this Site.</p>
<p>Select the value:</p>
<ul>
<li>QUEUE</li>
<li>TOPIC</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>JNDI name</p>         </td>
         <td><p>The JNDI lookup name of the queue/topic to be used (configured by the JMS provider administrator).</p>         </td>
      </tr>
      <tr>
         <td><p>Topic subscription</p>         </td>
         <td><p>If topics are used, the subscription name used to subscribe to the topic.</p>         </td>
      </tr>
      <tr>
         <td><p>Topic client Id</p>         </td>
         <td><p>If topics are used, the client identifier used to subscribe to the topic.</p>         </td>
      </tr>
      <tr>
         <td><p>Msg In selector</p>         </td>
         <td><p>The JMS selector used to filter messages coming from JMS and transferred to Gateway.</p>         </td>
      </tr>
      <tr>
         <td><p>Msg In directory</p>         </td>
         <td><p>The output directory used to store the data of JMS messages transferred to Gateway.</p>         </td>
      </tr>
      <tr>
         <td><p>Initialization properties</p>
<p>This section displays the list of initialization properties for JMS connection.</p>
<p>Modify the list according to the requirements of your JMS provider.</p>         </td>
      </tr>
      <tr>
         <td><p>Property</p>         </td>
         <td><p>Property name</p>         </td>
      </tr>
      <tr>
         <td><p>Value</p>         </td>
         <td><p>Property value</p>         </td>
      </tr>
      <tr>
         <td><p>New</p>         </td>
         <td><p>Click <span style="font-weight: bold;">New</span> to add extra initialization properties.</p>         </td>
      </tr>
      <tr>
         <td><p>Delete</p>         </td>
         <td><p>Click <span style="font-weight: bold;">Delete</span> to remove an initialization property.</p>         </td>
      </tr>
   </tbody>
</table>

Related topics

[Working with Remote Sites](../)

[Site objects: Parameters List](../../managing_local_sites_cli/sites_parameter_list)

[JMS connector](../../../../connectors_about/jms_about/jms_connector)

[Configuring the <span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>/JMS environment](../../../../connectors_about/jms_about/jms_configuring)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
