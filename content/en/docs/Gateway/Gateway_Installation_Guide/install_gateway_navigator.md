{
    "title": "Gateway Navigator",
    "linkTitle": "Gateway Navigator",
    "weight": "90"
}<span class="mc-variable axway_variables.prodname.Gateway_Navigator_long variable">Gateway Navigator</span> is a remote GUI that you can use to access <span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>. It only runs on Windows platforms.

> **Note:**
>
> You must install the same version of Gateway Navigator (including the Service Pack level) as Axway Gateway.

## Installing Gateway Navigator

To configure Gateway Navigator for installation, complete the following procedure:

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><strong>Screen</strong>         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p><span class="mc-variable axway_variables.prodname.Gateway_Navigator_long variable">Gateway Navigator</span>:<br />
Modules</p>         </td>
         <td><p>Make sure the <span class="mc-variable axway_variables.prodname.Gateway_Navigator_long variable">Gateway Navigator</span> items you want to install are selected:</p>
<ul>
<li><span style="font-weight: bold;"><span class="mc-variable axway_variables.prodname.Gateway_Navigator_long variable">Gateway Navigator</span></span></li>
<li><span style="font-weight: bold;">Extract Package and update environment</span>
<ul>
<li><span style="font-weight: bold;">Shortcut</span></li>
</ul></li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="mc-variable axway_variables.prodname.Gateway_Navigator_long variable">Gateway Navigator</span>:<br />
Installation directory</p>         </td>
         <td><p>Specify the directory where you want to install Gateway Navigator.</p>
<p>By default, Gateway Navigator is installed in a sub-directory
of the Axway installation directory. Use the default directory, or
specify a new directory.</p>
<p>Directory paths cannot contain any spaces.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="mc-variable axway_variables.prodname.Gateway_Navigator_long variable">Gateway Navigator</span>:<br />
Shortcuts</p>         </td>
         <td><p>Select whether or not you want to create a shortcut in
the Windows <span style="font-weight: bold;">Start</span> menu.</p>
<p>To create desktop shortcuts, select <span style="font-weight: bold;">Start
Navigator</span> and/or <strong>Signature Etebac 5</strong>.</p>         </td>
      </tr>
   </tbody>
</table>

## Navigator Post-installation

This section describes how to start and stop <span class="mc-variable axway_variables.prodname.Gateway_Navigator_long variable">Gateway Navigator</span>
after installation. It also explains how to configure <span class="mc-variable axway_variables.prodname.Gateway_Navigator_long variable">Gateway Navigator</span> the first time you use it.

### Starting <span class="mc-variable axway_variables.prodname.Gateway_Navigator_long variable">Gateway Navigator</span>

To start <span class="mc-variable axway_variables.prodname.Gateway_Navigator_long variable">Gateway Navigator</span>, from the Windows <span style="font-weight: bold;">Start</span>
menu, select:

Programs &gt; Axway Software &gt; Axway \[ProjectName\]
&gt; Gateway Navigator &gt; Start Navigator

### Configuring <span class="mc-variable axway_variables.prodname.Gateway_Navigator_long variable">Gateway Navigator</span>

The first time you use <span class="mc-variable axway_variables.prodname.Gateway_Navigator_long variable">Gateway Navigator</span>, you need to configure
it to communicate with your <span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>.

1.  In the left-hand frame of the
    GUI, right-click <span style="font-weight: bold;">Session</span>.
2.  Select <span style="font-weight: bold;">New
    Server...</span>

The <span style="font-style: italic;">New Server</span>
window appears.

1.  In the <span style="font-weight: bold;">TCP/IP</span>
    tab, fill-in the following parameters.

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Field         </th>
<th class="HeadD-Column1-Header1">Value         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Server alias</p>         </td>
         <td><p>The name you want to use to refer to your <span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>.</p>         </td>
      </tr>
      <tr>
         <td><p>Server address</p>         </td>
         <td><p>The IP address of the machine that hosts <span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>.</p>         </td>
      </tr>
      <tr>
         <td><p>Port number</p>         </td>
         <td><p>The port number to use to communicate with <span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>.<br />
Default = 6390.</p>         </td>
      </tr>
   </tbody>
</table>

1.  Click OK.

### Connecting to the <span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span> server

Each time you use <span class="mc-variable axway_variables.prodname.Gateway_Navigator_long variable">Gateway Navigator</span>, you need to log in to
connect to your <span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>.

1.  In the right-hand frame of
    the GUI, double-click the Gateway server to which you want to connect.

The <span class="mc-variable axway_variables.prodname.Gateway_Navigator_long variable">Gateway Navigator</span> window appears.

1.  If required, enter your password.
2.  Click <span style="font-weight: bold;">Connection</span>.

<span class="mc-variable axway_variables.prodname.Gateway_Navigator_long variable">Gateway Navigator</span> connects to the <span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span> server. You can now access all available services.

### Stopping <span class="mc-variable axway_variables.prodname.Gateway_Navigator_long variable">Gateway Navigator</span>

To stop <span class="mc-variable axway_variables.prodname.Gateway_Navigator_long variable">Gateway Navigator</span>, go to the <span style="font-weight: bold;">File</span>
menu and select <span style="font-weight: bold;">Exit</span>.

<span style="font-weight: bold;">Note:</span> It is recommended to stop (or disconnect) <span class="mc-variable axway_variables.prodname.Gateway_Navigator_long variable">Gateway Navigator</span> <span style="font-weight: bold;">before</span> you stop
the <span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span> server.

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
