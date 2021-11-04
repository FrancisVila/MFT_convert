{
    "title": "Importing an ASP package",
    "linkTitle": "Importing an ASP package",
    "weight": "100"
}{
"title": "About RMA",
"linkTitle": "About RMA",
"weight": "90"
}{
"title": "Relationship Management Application (RMA)",
"linkTitle": "Relationship Management Application (RMA)",
"weight": "70"
}{
"title": "Application Service Profiles (ASP) ",
"linkTitle": "Application Service Profiles (ASP) ",
"weight": "60"
}{
"title": "Modifying conffile parameters ",
"linkTitle": "Modifying conffile parameters",
"weight": "140"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Configuration
You can modify certain configuration parameters in the <span class="code">conffile</span>. To make the modification permanent, you must modify the <span class="code">pelsetup.def</span> file and then rebuild the configuration file.
\\\\\\\\\\\\\\\[Modifying pelsetup.def\\\\\\\\\\\\\\\](#Modifyin)
<a href="#SWIFTNet" class="MCXref xref">SWIFTNet parameters in the pelsetup.def file</a>
<a href="#Configur" class="MCXref xref">Configure where log files are stored in the pelsetup.def file</a>
<span id="Modifyin"></span>
## Modifying pelsetup.def
1. Go to the directory: <span class="code">&lt;Gateway installation directory>/run\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\_time/etc</span>.
2. Edit the <span class="code">pelsetup.def</span> file as required. (See the examples for SWIFTNet below.)
3. Rebuild the configuration file using the following command:
<span class="code" style="font-weight: bold;">peluconf standalone rebuild –f</span>
4. <span style="font-weight: bold;">Restart</span> Gateway so that the new values are taken into account.
Gateway's environment variables may contain either absolute or relative paths. You must run the profile before any operation related to your Gateway installation.
If you have issues after an update or upgrade (e.g: upgrade pack), you can use peluconf standalone rebuild -f to regenerate the configuration.
<span id="SWIFTNet"></span>
## SWIFTNet parameters in the pelsetup.def file
The table below provides details of SWIFTNet parameters in the <span class="code">pelsetup.def</span> file. You can find these parameters (or add them) in the SUP section of the file.

<table>
         
         
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Parameter         </th>
<th class="HeadE-Column1-Header1">Description         </th>
<th class="HeadE-Column1-Header1">Exists by default?         </th>
<th class="HeadD-Column1-Header1">Default value         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>swift_job_retry_count_max</p>         </td>
         <td><p>This parameter controls the number of retries in the case of a connection error with SAG. The parameter value is taken into account by client and server processes.</p>
<p><span style="font-weight: bold;">Example:</span> If the connection to SAG is broken, the client/server process tries to reestablish the connections as many times as specified by this parameter.</p>         </td>
         <td><p>no</p>         </td>
         <td><p>10</p>         </td>
      </tr>
      <tr>
         <td><p>swift_job_restart_delay</p>         </td>
         <td><p>This parameter stores the timeout (in seconds) between two successive connections attempts to SAG. The parameter value is taken into account by client and server processes.</p>
<p><span style="font-weight: bold;">Example:</span> If the connection to SAG is broken, the client/server process tries to reestablish the connections after the period of time given by this parameter.</p>         </td>
         <td><p>no</p>         </td>
         <td><p>30</p>         </td>
      </tr>
   </tbody>
</table>

### Example of part of pelsetup.def file contents
\\\\\\\\\\\\\\\[SUP\\\\\\\\\\\\\\\]
trace=0
………
swift\\\\\\\\\\\\\\\_job\\\\\\\\\\\\\\\_retry\\\\\\\\\\\\\\\_count\\\\\\\\\\\\\\\_max = 7
swift\\\\\\\\\\\\\\\_job\\\\\\\\\\\\\\\_restart\\\\\\\\\\\\\\\_delay = 600
………
<span id="Configur"></span>
## Configure where log files are stored in the pelsetup.def file
You can determine where log files are stored.
To do that, set the \\\\\\\\\\\\\\\`archived\\\\\\\\\\\\\\\_logdir \\\\\\\\\\\\\\\`parameter in the \\\\\\\\\\\\\\\`\\\\\\\\\\\\\\\[LOG\\\\\\\\\\\\\\\]\\\\\\\\\\\\\\\` section of \\\\\\\\\\\\\\\`pelsetup.def\\\\\\\\\\\\\\\` file. For example:
\\\\\\\\\\\\\\\[LOG\\\\\\\\\\\\\\\]
archived\\\\\\\\\\\\\\\_logdir="%p\\\\\\\\\\\\\\\_database%"
If the <span class="code">archived\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\_logdir </span>parameter is not set, the archived logs will be saved in the same folder where the \\\\\\\\\\\\\\\`log.dat \\\\\\\\\\\\\\\`file is located.
\\\\\\\\\\\\\\\[Configuring the <span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>/SWIFTNet environment\\\\\\\\\\\\\\\](../../connectors\\\\\\\\\\\\\\\_about/swiftnet\\\\\\\\\\\\\\\_about/swiftnet\\\\\\\\\\\\\\\_connector/swiftnet\\\\\\\\\\\\\\\_configuring)
\\\\\\\\\\\\\\\[Backup Remote Sites for SWIFTNet\\\\\\\\\\\\\\\](../../connectors\\\\\\\\\\\\\\\_about/swiftnet\\\\\\\\\\\\\\\_about/swiftnet\\\\\\\\\\\\\\\_backup\\\\\\\\\\\\\\\_sites)
\\\\\\\\\\\\\\\[Managing rotation and archiving of trace files\\\\\\\\\\\\\\\](../../starting\\\\\\\\\\\\\\\_and\\\\\\\\\\\\\\\_stopping\\\\\\\\\\\\\\\_server/trace\\\\\\\\\\\\\\\_rotate)
 
Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:
- \\\\\\\\\\\\\\\[Installation\\\\\\\\\\\\\\\](#) -- \\\\\\\\\\\\\\\[User\\\\\\\\\\\\\\\](#) -- \\\\\\\\\\\\\\\[Unix Configuration\\\\\\\\\\\\\\\](#) -- \\\\\\\\\\\\\\\[Upgrade\\\\\\\\\\\\\\\](#) -- \\\\\\\\\\\\\\\[Interoperability\\\\\\\\\\\\\\\](#) -- \\\\\\\\\\\\\\\[Security\\\\\\\\\\\\\\\](#), requires login -- \\\\\\\\\\\\\\\[Release Notes\\\\\\\\\\\\\\\](#)
