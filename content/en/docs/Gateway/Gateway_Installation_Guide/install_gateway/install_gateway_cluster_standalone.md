{
    "title": "Install Gateway in cluster mode, standalone",
    "linkTitle": "Install Gateway in cluster mode, standalone",
    "weight": "90"
}This section explains how to perform a standalone installation of Gateway in cluster mode. The tables below describe two sequences of screens:

-   one to install the <a href="#First_node" class="MCXref xref">First node</a>
-   the next to install <a href="#Additional_node" class="MCXref xref">Additional nodes</a>

<span id="First_node"></span>

## First node

<table>
         
         
         
         
   
   <thead>
      <tr>
<th class="TableStyle_print_table_style_Head_0_0_RowSep_ColSep">Screen         </th>
<th class="TableStyle_print_table_style_Head_0_0_RowSep_ColSep">Description         </th>
<th class="TableStyle_print_table_style_Head_0_0_RowSep_ColEnd">Screen type         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>Axway Welcome         </td>
         <td><p>Welcome to <span class="mc-variable axway_variables.Company_Name variable">Axway</span> Installer</p>         </td>
         <td>Common         </td>
      </tr>
      <tr>
         <td>Axway License Agreement         </td>
         <td>Read the LICENSE, SUPPORT AND SERVICES AGREEMENT and accept the terms         </td>
         <td>Common         </td>
      </tr>
      <tr>
         <td>Axway Installation architecture         </td>
         <td>Select the <strong>Cluster</strong> installation architecture:
<ul>
<li>Single (install on a single machine)</li>
<li><strong>&gt; Cluster</strong> (install on up to 4 machines)</li>
</ul>         </td>
         <td>Common         </td>
      </tr>
      <tr>
         <td>Axway Cluster         </td>
         <td><p>Select:</p>
<ul>
<li><strong>&gt; First Node</strong></li>
<li>Additional Node</li>
</ul>         </td>
         <td>Option-dependent         </td>
      </tr>
      <tr>
         <td><p><span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>:<br />
Installation directory</p>         </td>
         <td><ul>
<li>Specify the shared directory to store the data shared between the various cluster nodes. By default: <span class="code">Axway_Shared</span>.</li>
<li>Specify the directory where you want to install Gateway.<br />
By default, Gateway is installed in a sub-directory of the Axway installation directory.</li>
</ul>
<p>Directory paths cannot contain any spaces. </p>         </td>
         <td>Common         </td>
      </tr>
      <tr>
         <td>Axway Gateway Modules         </td>
         <td>Select the module(s) you want to install.
Optional:
<ul>
<li><strong>Access Manager</strong></li>
<li><strong>Windows Service</strong> (Windows only)</li>
</ul>         </td>
         <td>Common         </td>
      </tr>
      <tr>
         <td>Axway Installation directory         </td>
         <td>Select the installation directory for Gateway and the directory that will store shared data         </td>
         <td>Common         </td>
      </tr>
      <tr>
         <td><p><span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>:<br />
Configuration</p>         </td>
         <td><p>Enter the following information:</p>
<ul>
<li><span style="font-weight: bold;">Local site name</span>: The name that you want
to use to refer to your Gateway.</li>
<li><span style="font-weight: bold;">Key label</span>: Your key label (if you have
one).</li>
<li><span style="font-weight: bold;">License key</span><strong>s</strong>: Your license key(s). You
must enter at least one license key to be able to install and operate
<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>. Here you must enter the license key for all the machines where Gateway Additional Nodes will be installed</li>
<li><p><strong>Validate Hostname</strong>: <em>true</em> by default. This option will compare the hostname of the machine with the one from the license key</p></li>
<li><span style="font-weight: bold;">Navigator server port number</span>: The number of the port used for the <span class="mc-variable axway_variables.prodname.Gateway_Navigator_long variable">Gateway Navigator</span> server (GUI server). Default: 6390.</li>
</ul>         </td>
         <td>Common         </td>
      </tr>
      <tr>
         <td><span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Access management         </td>
         <td><p>Select the access management that you want to use:</p>
<ul>
<li><strong>Gateway</strong></li>
<li><strong>PassPort AM</strong> (4.3 and below)</li>
<li><strong>PassPort AM</strong> (from 4.4)</li>
</ul>         </td>
         <td>Option-dependent         </td>
      </tr>
      <tr>
         <td><span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: PassPort AM (<strong>4.3</strong> and below) configuration         </td>
         <td><p>If you select <em>PassPort</em> as the access manager, you need to provide the PassPort AM connection parameters:</p>
<ul>
<li>Hostname</li>
<li>TCP port</li>
<li>Use SSL</li>
<li>Product Instance</li>
<li>PassPort AM Domain</li>
<li>Product Login</li>
<li>Product Password</li>
</ul>         </td>
         <td>Option-dependent         </td>
      </tr>
      <tr>
         <td><span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: PassPort AM (<strong>4.4</strong> and over) configuration         </td>
         <td><p>If you select PassPort as the access manager, you need to provide the PassPort AM connection parameters:</p>
<ul>
<li><strong>Hostname</strong></li>
<li><p><strong>Main SSL/TLS Port</strong></p></li>
<li><p><strong>Shared Secret</strong></p></li>
<li><p><strong>Product Instance</strong></p></li>
<li><p><strong>Client Certificate Password</strong></p></li>
<li><p><strong>Password confirmation</strong></p></li>
</ul>         </td>
         <td>Option-dependent         </td>
      </tr>
      <tr>
         <td><p><span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>:<br />
Gateway Access Manager Configuration</p>         </td>
         <td><p>If you select Gateway Access Manager, you need to provide:</p>
<ul>
<li><strong>Administrator User</strong></li>
<li><strong>Administrator Password</strong></li>
<li><strong>Password confirmation</strong></li>
</ul>         </td>
         <td>Option-dependent         </td>
      </tr>
      <tr>
         <td><p><span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>:<br />
Startup type</p>         </td>
         <td><ul>
<li><strong>Normal mode</strong> (You must manually start and stop Gateway)</li>
<li><strong>Service mode</strong> (Windows automatically starts and stops Gateway)</li>
</ul>
<p>If you selected <strong>Service mode</strong>, enter values for the Windows service parameters:</p>
<ul>
<li><strong>Service Name</strong>: Internal or real name of the service
that the operating system uses. This name is constant no matter what language
version of Windows is used—the <strong>Display
Name</strong> will change depending on the language version of Windows.</li>
<li><strong>Service Display Name</strong>: Name that Windows uses
to display the service in the Windows services list. Display name is the
language-specific friendly version
of the service name.</li>
<li><strong>Service Description</strong></li>
<li><strong>Start Type</strong>: Specifies whether service
starts automatically when the operating system starts or if you must start
it manually (Automatic, Manual or Disabled)</li>
<li><strong>Use another user authentication</strong>: Select <em>Yes</em> or <em>No</em>. If you select <em>Yes</em>, enter the:
<ul>
<li><strong>Username</strong></li>
<li><strong>Domain</strong></li>
<li><strong>Password</strong>: The password value set here will be <strong>ignored</strong> by Gateway, as the way passwords are stored in Gateway has been changed and there is no longer an entry for the password in Gateway.</li>
</ul></li>
</ul>         </td>
         <td>Option dependent         </td>
      </tr>
      <tr>
         <td><p>Axway</p>
<p>Ready to Install</p>         </td>
         <td>Click <strong>Install</strong> to install the listed components.         </td>
         <td>Common         </td>
      </tr>
   </tbody>
</table>

Gateway is successfully installed on the first node.

Now do the following:

1.  Go to the shared directory (by default, <span class="code">Axway\_Shared</span>)
2.  Share it with the users from all additional nodes, respecting the following constraints:
    -   the same user must be used on all machines
    -   the shared directory must have the same path on all machines

The static configuration is shared between all nodes. The shared directory contains the following Gateway sub-directories:

-   run\_time/audit
-   run\_time/data
-   run\_time/etc
-   run\_time/tmp
-   run\_time/vfd

<span id="Additional_node"></span>

## Additional nodes

Run <span class="code">setup.exe </span>on each additional node, and fill up the screens as described in the table below.

<table>
         
         
         
         
   
   <thead>
      <tr>
<th class="TableStyle_print_table_style_Head_0_0_RowSep_ColSep">Screen         </th>
<th class="TableStyle_print_table_style_Head_0_0_RowSep_ColSep">Description         </th>
<th class="TableStyle_print_table_style_Head_0_0_RowSep_ColEnd">Screen type         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>Axway Welcome         </td>
         <td><p>Welcome to <span class="mc-variable axway_variables.Company_Name variable">Axway</span> Installer</p>         </td>
         <td>Common         </td>
      </tr>
      <tr>
         <td>Axway License Agreement         </td>
         <td>Read the LICENSE, SUPPORT AND SERVICES AGREEMENT and accept the terms         </td>
         <td>Common         </td>
      </tr>
      <tr>
         <td>Axway Installation architecture         </td>
         <td>Select the <strong>Cluster</strong> installation architecture:
<ul>
<li>Single (install on a single machine)</li>
<li><strong>&gt; Cluster</strong> (install on up to 4 machines)</li>
</ul>         </td>
         <td>Common         </td>
      </tr>
      <tr>
         <td>Axway Cluster         </td>
         <td><p>Select:</p>
<ul>
<li>First Node</li>
<li><strong>&gt; Additional Node</strong></li>
</ul>         </td>
         <td>Option-dependent         </td>
      </tr>
      <tr>
         <td><p><span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>:<br />
Installation directories</p>         </td>
         <td><ul>
<li>Specify the shared directory where the shared data between the various cluster nodes will be stored.</li>
<li>Specify the directory where you want to install Gateway. For the Additional Node, the path for the installation is already filled out.</li>
</ul>
<p>Directory paths cannot contain any spaces. </p>         </td>
         <td>Option-dependent         </td>
      </tr>
      <tr>
         <td>Axway Gateway Modules         </td>
         <td>Select the module(s) you want to install.
Optional:
<ul>
<li><strong>Access Manager</strong></li>
<li><strong>Windows Service</strong> (Windows only)</li>
</ul>         </td>
         <td>Common         </td>
      </tr>
      <tr>
         <td><p>Axway</p>
<p>Ready to Install</p>         </td>
         <td>Click <strong>Install</strong> to install the listed components.         </td>
         <td>Common         </td>
      </tr>
   </tbody>
</table>

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
