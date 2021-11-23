{
    "title": "Managing rotation and archiving of trace files ",
    "linkTitle": "Managing rotation/archiving of trace files",
    "weight": "210"
}{{< Gateway/componentlongname  >}}: Managing the Server

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

The parameters used for managing the trace rotation operation are stored in the `dtrace` section of the `dconfsave.ini` configuration file.

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
         <td><code>check_interval</code>         </td>
         <td><p>Determines the responsiveness of the trace rotation functionality. This is the maximum time (in seconds) on which a rotation is triggered after the rotation command was issued.</p>
<p>Default = 300.</p>         </td>
      </tr>
      <tr>
         <td><code>check_file_path</code>         </td>
         <td><p>The directory containing an internal file used to manage the trace rotation operation.<br />
Default = <code>$p_database</code>.</p>         </td>
      </tr>
      <tr>
         <td><code>check_file_name</code>         </td>
         <td><p>For internal use only</p>
<p>The filename of the file used to signal trace rotation. Its last update timestamp is used to check if a rotation needs to be scheduled.<br />
Default = <code>dtrace.chk</code>.</p>         </td>
      </tr>
      <tr>
         <td><code>indirection_file_name</code>         </td>
         <td><p>For internal use only</p>
<p>The full path to the indirection file used for saving the information related to trace files. It is used during trace rotation and collection to determine which files need to be archived. The default values is <code>$p_database/indirection.ref</code>.</p>         </td>
      </tr>
   </tbody>
</table>

You can update these parameters using the `peluconf` online command. You do not need to restart the server to apply the parameters.

### Example

`peluconf [standalone] set -s dtrace check_interval 600`

<span id="modify_archive_paras"></span>

## Modifying trace archiving parameters

You can use the following parameters in the `conffile` to configure the collector task which manages the archiving of trace files at a pre-scheduled interval.

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Parameter         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><code>max_files_to_move</code>         </td>
         <td><p>The maximum number of files to be moved per iteration during a trace file collect operation. This should be a fraction of the <code>max_files_to_collect</code> parameter.<br />
Default = 10.</p>
<p>(This parameter is designed to improve performance)</p>         </td>
      </tr>
      <tr>
         <td><code>max_files_to_collect</code>         </td>
         <td><p>The maximum number of trace files to be considered for a collection per iteration during preparation of the archive operation.<br />
Default = 100.</p>
<p>(This parameter is designed to improve performance)</p>         </td>
      </tr>
      <tr>
         <td><code>collect_interval</code>         </td>
         <td>The interval (in seconds) between two successive trace file collector runs. Default = 600.         </td>
      </tr>
      <tr>
         <td><code>archive_path</code>         </td>
         <td>The directory where the archived traces are to be moved.<br />
Default = <code>%p_home_dir%\run_time\tmp\archive</code>.<br />
You can modify this value if required by editing the <code>pelsetup.def</code> file.         </td>
      </tr>
   </tbody>
</table>

<span id="triggering_rotate"></span>

## Triggering trace rotation

Use the `pelctl trace_rotate` command to trigger the rotation of trace files.

<table>
         
         
         
   
   <tbody>
      <tr>
         <td>Syntax         </td>
         <td><code>pelctl trace_rotate</code>         </td>
      </tr>
      <tr>
         <td>Description         </td>
         <td><p>Triggers the rotation of the trace files generated by Gateway. The rotated traces will be moved into a configurable directory. This command initiates trace rotation dynamically. You do not need to restart the server for the operation to start.</p>
<p>Gateway creates the trace filenames in the format: <code>[process_name-yyyymmdd-hhmmss-process_pid].out</code><br />
where:</p>
<ul>
<li><code>process_name</code> is the name of the process</li>
<li><code>yyyymmdd-hhmmss</code> is the timestamp when the trace file was created</li>
<li><code>process_pid</code> is the pid of the process that created the trace file</li>
</ul>         </td>
      </tr>
      <tr>
         <td>Parameters         </td>
         <td>None         </td>
      </tr>
      <tr>
         <td>Example         </td>
         <td><p><code>pelctl trace_rotate</code></p>
<p>Gateway moves the existing trace files into the archive directory.</p>         </td>
      </tr>
   </tbody>
</table>

Related topics

[Modifying conffile parameters](../../configuration_start_here/t_gw_config_conffile_paras_modify)

[Executing server traces](../server_traces)

 

Links to documentation set for Axway Gateway {{< Gateway/releasenumber  >}}:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
