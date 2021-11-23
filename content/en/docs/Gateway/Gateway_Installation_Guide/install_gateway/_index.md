{
    "title": "Install Gateway",
    "linkTitle": "Install Gateway",
    "weight": "70"
}To configure Gateway for installation, fill out the installation screens as described below.

If you wish to install Gateway in *cluster* mode, refer to the relevant section: <a href="install_gateway_cluster_standalone" class="MCXref xref">Install Gateway in cluster mode, standalone</a>

 

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
         <td>{{< Gateway/componentlongname  >}}:<br />
Modules         </td>
         <td><p>Make sure the {{< Gateway/componentlongname  >}} items you want to install are selected:</p>
<ul>
<li><strong>Extract Package and update environment</strong></li>
<li><strong>Access Manager</strong></li>
<li><strong>Windows Service</strong> (Windows only)</li>
</ul>         </td>
         <td>Common         </td>
      </tr>
      <tr>
         <td>Axway License Agreement         </td>
         <td>Read the LICENSE, SUPPORT AND SERVICES AGREEMENT and accept the terms         </td>
         <td>Common         </td>
      </tr>
      <tr>
         <td>Axway Installation architecture         </td>
         <td>Select installation architecture:
<ul>
<li><strong>Single</strong> (install on a single machine)</li>
<li><strong>Cluster</strong> (install on up to 4 machines)</li>
</ul>         </td>
         <td>Common         </td>
      </tr>
      <tr>
         <td><p>{{< Gateway/componentlongname  >}}:<br />
Installation directory</p>         </td>
         <td><p>Specify the directory where you want to install Gateway.</p>
<p>By default, Gateway is installed in a sub-directory of
the Axway installation directory. Use the default directory, or specify
a new directory.</p>
<p>Directory paths cannot contain any spaces.</p>         </td>
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
         <td>Specify the installation directory for Gateway         </td>
         <td>Common         </td>
      </tr>
      <tr>
         <td><p>{{< Gateway/componentlongname  >}}:<br />
Configuration</p>         </td>
         <td><p>Enter the following information:</p>
<ul>
<li><strong>Local site name</strong>: The name that you want
to use to refer to your Gateway.</li>
<li><span style="font-weight: bold;">Key label</span>: Your key label (if you have
one).</li>
<li><span style="font-weight: bold;">License key</span><strong>s</strong>: Your license key(s). You
must enter at least one license key to be able to install and operate
<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>.</li>
<li><p><strong>Validate Hostname</strong>: true by default. This option will compare the hostname of the machine with the one from the license key</p></li>
<li><span style="font-weight: bold;">Navigator server port number</span>: The number of the port used for the <span class="mc-variable axway_variables.prodname.Gateway_Navigator_long variable">Gateway Navigator</span> server (GUI server). Default: 6390.</li>
</ul>         </td>
         <td>Common         </td>
      </tr>
      <tr>
         <td><p><span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>:<span style="font-weight: normal;"><br />
Shortcuts</span></p>         </td>
         <td><p>Select whether or not you want to create shortcuts in the
Windows <span style="font-weight: bold;">Start</span> menu.</p>
<p>Select the required desktop shortcuts.</p>         </td>
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
         <td>Common         </td>
      </tr>
      <tr>
         <td><span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: PassPort AM (4.3 and below) configuration         </td>
         <td><p>If you select PassPort as the access manager, you need to provide the PassPort AM connection parameters:</p>
<ul>
<li><strong>Hostname</strong></li>
<li><strong>TCP port</strong></li>
<li><p><strong>Use SSL</strong></p></li>
<li><p><strong>Product Instance</strong></p></li>
</ul>
<ul>
<li>PassPort AM Domain</li>
<li><p><strong>Product Login</strong></p></li>
<li><p><strong>Product Password</strong></p></li>
</ul>         </td>
         <td>Option-dependent         </td>
      </tr>
      <tr>
         <td><span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: PassPort AM (4.4 and over) configuration         </td>
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
         <td>Axway Gateway SWIFTNet HA: Correlation type         </td>
         <td>Select the correlation type that you want to use:
<ul>
<li>HA Disabled</li>
<li>Use correlation exit</li>
<li>Use external correlation</li>
</ul>         </td>
         <td>Common         </td>
      </tr>
      <tr>
         <td>Axway Gateway: SWIFTNet HA: Database type (<strong>Use correlation exit</strong> option selected)         </td>
         <td>Select database type:
<ul>
<li>Oracle</li>
<li>MySQL</li>
</ul>
<p>Optional: skip Database configuration</p>         </td>
         <td>Option-dependent         </td>
      </tr>
      <tr>
         <td><span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span> SWIFTNet HA: Database options (<strong>Use correlation exit</strong> option selected)         </td>
         <td><ul>
<li><strong>Verify database configuration</strong>: Must be checked</li>
<li><strong>Use custom URL</strong> (Oracle 11 only). You can set a custom URL for the database connection.<br />
Normally the URL is computed automatically and is similar to this:<br />
jdbc.url=jdbc:oracle:thin:@alicia.lab1.lab.ptx.axway.int:
1570:SWFRDQ1</li>
</ul>         </td>
         <td>Option-dependent         </td>
      </tr>
      <tr>
         <td>Axway Gateway SWIFTNet HA: MySQL/Oracle setup (<strong>Use correlation exit</strong> option selected)         </td>
         <td><p>If you select <strong>Oracle</strong> Database, you need to provide:</p>
<ul>
<li><strong>DSN</strong> (data source name). Enter the system variable (UNIX) or environment variable (Windows) that references the database drivers that you installed.</li>
<li><strong>SID</strong>: identifies the database instance</li>
<li><strong>Hostname</strong></li>
<li><strong>Port Number</strong>: 1521 (default)</li>
<li><strong>Connection User</strong></li>
<li><strong>Connection Password</strong></li>
<li><strong>Data tablespace name</strong></li>
<li><strong>Index tablespace name</strong></li>
</ul>         </td>
         <td>Option-dependent         </td>
      </tr>
      <tr>
         <td>Axway Gateway SWIFTNet HA: MySQL/Oracle setup (<strong>Use correlation exit</strong> option selected)         </td>
         <td><p>If you select the <strong>MySQL</strong> Database, you need to provide:</p>
<ul>
<li><strong>DSN</strong> (data source name). Enter the system variable (UNIX) or environment variable (Windows) that references the database drivers that you installed.</li>
<li><strong>Database name</strong></li>
<li><strong>Hostname</strong></li>
<li><strong>Port Number</strong>: 3306 (default)</li>
<li><strong>Connection User</strong></li>
<li><strong>Connection Password</strong></li>
</ul>         </td>
         <td>Option-dependent         </td>
      </tr>
      <tr>
         <td><span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span> SWIFTNet RMA: Server configuration         </td>
         <td><p>Select the default ports:</p>
<ul>
<li><strong>RMA Control port</strong>: Command line TCP port. Used for stopping or getting the status of the product.</li>
<li><strong>RMA API Port</strong>: Webservice port number. Used by the RMA Exit inside Gateway to communicate with the RMA server.</li>
</ul>         </td>
         <td>Option dependent         </td>
      </tr>
      <tr>
         <td><span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span> SWIFTNet RMA: Passport AM Configuration         </td>
         <td>You need to provide:
<ul>
<li><strong>Main SSL/TLS Port</strong></li>
<li><strong>Shared secret</strong>: Enter the database connection parameters.</li>
<li><strong>Product Instance</strong>: Enter the Component Instance used to identify RMA.</li>
<li><strong>Passport AM Domain</strong></li>
<li><strong>RMA Login Name</strong></li>
<li><strong>RMA Password</strong></li>
</ul>         </td>
         <td>Option-dependent         </td>
      </tr>
      <tr>
         <td><span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span> SWIFTNet RMA: Service attributes         </td>
         <td><ul>
<li><strong>Normal mode</strong> (You must manually start and stop the application)</li>
<li><strong>Service mode</strong> (Windows automatically starts and stops the application)</li>
</ul>
<p>If you selected <strong>Service mode</strong>, enter values for the Windows service parameters:</p>
<ul>
<li><strong>Service Name</strong>: Internal or real name of the service that the operating system uses. This name is constant no matter what language version of Windows is used—the Display Name will change depending on the language version of Windows.</li>
<li><strong>Service Display Name</strong>: Name that Windows uses to display the service in the Windows services list. Display name is the language-specific friendly version of the service name.</li>
<li><strong>Service Description</strong></li>
<li><strong>Start Type</strong>: Specifies whether the service starts automatically when the operating system starts, or whether you must start it manually (<em>Automatic</em>, <em>Manual</em> or <em>Disabled</em>).</li>
<li><strong>Use another user authentication</strong>: Yes or No. If you select <strong>Yes</strong>, enter the:
<ul>
<li><strong>Username</strong></li>
<li><strong>Domain</strong></li>
<li><strong>Password</strong> The password value set here will be ignored by Gateway as the way passwords are stored in Gateway has been changed and there is no longer an entry for the password in Gateway</li>
</ul></li>
</ul>         </td>
         <td>Option-dependent         </td>
      </tr>
      <tr>
         <td><span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span> RMA Application: Database type         </td>
         <td><p>Select the database type</p>
<ul>
<li><strong>Oracle</strong></li>
<li><strong>MySQL</strong></li>
</ul>         </td>
         <td>Option-dependent         </td>
      </tr>
      <tr>
         <td><span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span> SWIFTNet RMA Application: Database options         </td>
         <td><ul>
<li><strong>Verify database configuration</strong>: must be checked</li>
<li><strong>Use custom URL</strong> (Oracle only). You can set a custom URL for the database connection.<br />
Normally the URL is computed automatically and is similar to this:<br />
jdbc.url=jdbc:oracle:thin:@alicia.lab1.lab.ptx.axway.int:
1570:SWFRDQ1</li>
</ul>         </td>
         <td>Option-dependent         </td>
      </tr>
      <tr>
         <td>Axway Gateway RMA Application: MySQL/Oracle setup         </td>
         <td>If you select <em>Oracle</em> Database, you need to provide the connection parameters
<ul>
<li><strong>SID</strong>: identifies the database instance</li>
<li><strong>Hostname</strong></li>
<li><strong>Port Number</strong>: 1521 (default)</li>
<li><strong>Connection User</strong></li>
<li><strong>Connection Password</strong></li>
<li><strong>Data tablespace name</strong></li>
<li><strong>Index tablespace name</strong></li>
</ul>         </td>
         <td>Option-dependent         </td>
      </tr>
      <tr>
         <td>Axway Gateway RMA Application: MySQL/Oracle setup         </td>
         <td>If you select <strong>MySQL</strong> Database, you need to provide the connection parameters.
<ul>
<li><strong>Database name</strong></li>
<li><strong>Hostname</strong></li>
<li><strong>Port Number</strong>: 3306 (default)</li>
<li><strong>Connection User</strong></li>
<li>Connection Password</li>
</ul>         </td>
         <td>Option-dependent         </td>
      </tr>
      <tr>
         <td><p>Axway</p>
<p>Ready to Install</p>         </td>
         <td>Click <strong>Install</strong> to install the listed components.         </td>
         <td>Common         </td>
      </tr>
   </tbody>
</table>

**Notes:**

-   For cluster installation you need to share the shared directory specified in the installation process with all the additional nodes (up to 3). On the additional nodes the mounting point to the shared directory must be identical to the shared directory path from the main node.
-   For security reasons you must restrict the access to the folder `%GatewayInstallDir%/run_time/agent/data/keys/` at operating system level.

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
