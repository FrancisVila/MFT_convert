{
    "title": "Managing rotation and archiving of trace files ",
    "linkTitle": "Managing rotation/archiving of trace files",
    "weight": "210"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Managing the Server

[Modifying trace rotation parameters](#modify_rotate_paras)

[Modifying trace archiving parameters](#modify_archive_paras)

[Triggering trace rotation](#triggering_rotate)

This version of Gateway archives the trace files at regular intervals to prevent them becoming too large. This is achieved using *trace rotation* and *trace archiving* (also known as *trace collection*).

-   **Trace rotation** is the act of closing the old trace files and creating the new trace files.
-   **Trace archiving (or "collection")** is the act of moving the rotated (old) trace files into a configured archive folder.

Both of these processes are performed automatically by Gateway. You can modify the default parameters depending on your requirements.

You can manually trigger trace file rotation at any time. Gateway will move the old files into the configured archive directory without the need to restart.

<span id="modify_rotate_paras"></span>

## Modifying trace rotation parameters

The parameters used for managing the trace rotation operation are stored in the <span class="code">dtrace</span> section of the <span class="code">dconfsave.ini</span> configuration file.

These parameters include:

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Parameter         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><span class="code">check_interval</span>         </td>
         <td><p>Determines the responsiveness of the trace rotation functionality. This is the maximum time (in seconds) on which a rotation is triggered after the rotation command was issued.</p>
<p>Default = 300.</p>         </td>
      </tr>
      <tr>
         <td><span class="code">check_file_path</span>         </td>
         <td><p>The directory containing an internal file used to manage the trace rotation operation.<br />
Default = <span class="code">$p_database</span>.</p>         </td>
      </tr>
      <tr>
         <td><span class="code">check_file_name</span>         </td>
         <td><p>For internal use only</p>
<p>The filename of the file used to signal trace rotation. Its last update timestamp is used to check if a rotation needs to be scheduled.<br />
Default = <span class="code">dtrace.chk</span>.</p>         </td>
      </tr>
      <tr>
         <td><span class="code">indirection_file_name</span>         </td>
         <td><p>For internal use only</p>
<p>The full path to the indirection file used for saving the information related to trace files. It is used during trace rotation and collection to determine which files need to be archived. The default values is <span class="code">$p_database/indirection.ref</span>.</p>         </td>
      </tr>
   </tbody>
</table>

You can update these parameters using the <span class="code">peluconf</span> online command. You do not need to restart the server to apply the parameters.

### Example

<span class="codeBold_in_para">peluconf \[standalone\] set -s dtrace check\_interval 600</span>

<span id="modify_archive_paras"></span>

## Modifying trace archiving parameters

You can use the following parameters in the <span class="code">conffile</span> to configure the collector task which manages the archiving of trace files at a pre-scheduled interval.

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Parameter         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><span class="code">max_files_to_move</span>         </td>
         <td><p>The maximum number of files to be moved per iteration during a trace file collect operation. This should be a fraction of the <span class="code">max_files_to_collect</span> parameter.<br />
Default = 10.</p>
<p>(This parameter is designed to improve performance)</p>         </td>
      </tr>
      <tr>
         <td><span class="code">max_files_to_collect</span>         </td>
         <td><p>The maximum number of trace files to be considered for a collection per iteration during preparation of the archive operation.<br />
Default = 100.</p>
<p>(This parameter is designed to improve performance)</p>         </td>
      </tr>
      <tr>
         <td><span class="code">collect_interval</span>         </td>
         <td>The interval (in seconds) between two successive trace file collector runs. Default = 600.         </td>
      </tr>
      <tr>
         <td><span class="code">archive_path</span>         </td>
         <td>The directory where the archived traces are to be moved.<br />
Default = <span class="code">%p_home_dir%\run_time\tmp\archive</span>.<br />
You can modify this value if required by editing the <span class="code"><a href="../../configuration_start_here/t_gw_config_conffile_paras_modify">pelsetup.def</a></span> file.         </td>
      </tr>
   </tbody>
</table>

<span id="triggering_rotate"></span>

## Triggering trace rotation

Use the <span class="code">pelctl trace\_rotate</span> command to trigger the rotation of trace files.

<table>
         
         
         
   
   <tbody>
      <tr>
         <td>Syntax         </td>
         <td><span class="code">pelctl trace_rotate</span>         </td>
      </tr>
      <tr>
         <td>Description         </td>
         <td><p>Triggers the rotation of the trace files generated by Gateway. The rotated traces will be moved into a configurable directory. This command initiates trace rotation dynamically. You do not need to restart the server for the operation to start.</p>
<p>Gateway creates the trace filenames in the format: <span class="code">[process_name-yyyymmdd-hhmmss-process_pid].out</span><br />
where:</p>
<ul>
<li><span class="code">process_name</span> is the name of the process</li>
<li><span class="code">yyyymmdd-hhmmss</span> is the timestamp when the trace file was created</li>
<li><span class="code">process_pid</span> is the pid of the process that created the trace file</li>
</ul>         </td>
      </tr>
      <tr>
         <td>Parameters         </td>
         <td>None         </td>
      </tr>
      <tr>
         <td>Example         </td>
         <td><p><span class="code">pelctl trace_rotate</span></p>
<p>Gateway moves the existing trace files into the archive directory.</p>         </td>
      </tr>
   </tbody>
</table>

Related topics

[Modifying conffile parameters](../../configuration_start_here/t_gw_config_conffile_paras_modify)

[Executing server traces](../server_traces)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
