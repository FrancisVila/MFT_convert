{
    "title": "Deprecated folder monitoring (UCONF)",
    "linkTitle": "Deprecated folder monitoring (UCONF)",
    "weight": "230"
}# Deprecated folder monitoring (UCONF)



This section provides a description of how to use Transfer CFT UCONF values to manage folder monitoring. This method is no longer recommended; you should use the CFTFOLDER object method.



-   [Configure folder monitoring using UCONF](#Configur)

-   [How <span>Transfer CFT</span> handles monitored files](#How2)

-   [Modify and apply configuration changes](#Modifying_existing_configuration)

-   [Directory configuration examples](#Director)

-   [File-system event monitoring](#File-sys)



<table data-cellpadding="0" data-cellspacing="0">
<tbody>
<tr>
<td data-valign="top"></td>
<td data-valign="top"><span><strong>Note</strong></span></td>
<td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">There are two ways to implement Transfer CFT folder monitoring, either using UCONF or Transfer CFT objects. We recommend the CFTFOLDER method of configuring folder monitoring. Users that presently are using UCONF to manage folder monitoring can migrate to a CFTFOLDER configuration as described in <a href="../migrate_uconf_cftfolder">Migrate to CFTFOLDER folder monitoring</a>.</td>
</tr>
</tbody>
</table>



## <span id="Configur"></span>Configure folder monitoring using UCONF



For each monitored directory you must provide a unique name to identify the set of configuration parameters corresponding to this directory. This enables you to individually configure each directory to be monitored.



### Step overview



1.  Activate the folder monitoring option.

    -   Set uconf parameter folder\_monitoring.enable to Yes.

2.  Declare your logical directories to monitor.

    -   Add to your uconf parameter folder\_monitoring.folders 1 logical name by root directory you want to monitor.

3.  For each logical directory defined, configure the specific options you want to use for each:

    -   File management method



    



    -   Define other uconf Folder Monitoring parameters (described in the following sections)



### <span id="Monitori"></span>Folder monitoring parameters



Use the following UCONF parameters to configure folder monitoring for each directory as needed. See the section [UCONF](../../uconf/UCONF.htm) if you are not familiar with unified configuration settings.



Parameter descriptions



<table data-cellspacing="0">
<thead>
<tr>
<th>UCONF parameter</th>
<th>Type</th>
<th><p>Default</p></th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>folder_monitoring.enable</td>
<td>Boolean</td>
<td>No</td>
<td><ul>
<li>No: No folder monitoring occurs.</li>
<li>Yes: Enable <span>Transfer CFT</span> folder monitoring.</li>
</ul></td>
</tr>
<tr>
<td>folder_monitoring.folders</td>
<td>node</td>
<td>None</td>
<td><p>Add the logical folders to monitor (list of logical identifiers).</p>
<p>You should provide a unique name to identify the set of configuration parameters corresponding to this directory.

If you have more than one Folder to monitor, use a space between each logical value.</p>
<p>See the <strong>Comment***</strong> below this table for additional information.</p></td>
</tr>
<tr>
<td><p>folder_monitoring.folders.</p>
<p>&lt;logical_name&gt;.enable</p></td>
<td>Boolean</td>
<td>Yes</td>
<td><p>Enables a scan of the folder, where NO deactivates folder monitoring.</p></td>
</tr>
<tr>
<td><p>folder_monitoring.folders.</p>
<p>&lt;logical_name&gt;.scan_dir</p></td>
<td>string</td>
<td>None</td>
<td><p>Absolute path name of the top level directory to scan.</p>
<p>This directory must exist before restarting CFT.</p>
<p>*See NOTE.</p></td>
</tr>
<tr>
<td><p>folder_monitoring.folders.</p>
<p>&lt;logical_name&gt;.work_dir</p></td>
<td>string</td>
<td>None</td>
<td><p>Absolute path name of the top level directory available for file state information.</p>
<ul>
<li>If you are using the MOVE method, files that are ready to be submitted are available in the work_dir.</li>
<li>If you are using the FILE method, the .met files are stored in the work_dir.</li>
</ul>
<table data-cellpadding="0" data-cellspacing="0">
<tbody>
<tr>
<td data-valign="top"></td>
<td data-valign="top"><span><strong>Caution  </strong></span></td>
<td data-mc-autonum="&lt;b&gt;Caution  &lt;/b&gt;" data-valign="top">  Never delete any .met files.</td>
</tr>
</tbody>
</table>
<p>*See NOTE.</p></td>
</tr>
<tr>
<td><p>folder_monitoring.folders.</p>
<p>&lt;logical_name&gt;.enable_subdir</p></td>
<td>Boolean</td>
<td>Yes</td>
<td><p>Values:</p>
<ul>
<li>Yes: The entire scan_dir sub-directory tree is monitored.</li>
<li>No: No scan is performed.</li>
</ul></td>
</tr>
<tr>
<td><p>folder_monitoring.folders.</p>
<p>&lt;logical_name&gt;.method</p></td>
<td>enum</td>
<td>MOVE</td>
<td><p>Values:</p>
<ul>
<li>MOVE: Files are moved (by renaming), to the work_dir prior to being submitted.</li>
<li>FILE: Files are left in the scan_dir, and a state file with the same name is created in work_dir prior to submitting the file.</li>
</ul>
<p>See also <a href="..//transfercft/app_integration_intro/intro_folder_monitor">Configuring file tracking options (MOVE option)</a>.</p></td>
</tr>
<tr>
<td><p>folder_monitoring.folders.</p>
<p>&lt;logical_name&gt;.file_idle_delay</p></td>
<td>integer</td>
<td>5</td>
<td>If the state of a file has not changed within this delay in seconds, the file becomes a candidate for submission.</td>
</tr>
<tr>
<td><p>folder_monitoring.folders.</p>
<p>&lt;logical_name&gt;.idf</p></td>
<td>string</td>
<td>""</td>
<td><p>The IDF name to use in the SEND command. Use one of the following:</p>
<ul>
<li>A fixed name.</li>
<li>"(0)": The name of the first directory sub-level is used.</li>
<li>"(1)": The name of the second directory sub-level is used.</li>
</ul></td>
</tr>
<tr>
<td><p>folder_monitoring.folders.</p>
<p>&lt;logical_name&gt;.part</p></td>
<td>string</td>
<td>""</td>
<td><p>The PART name to use in the SEND command. Use one of the following:</p>
<ul>
<li>A fixed name.</li>
<li>"(0)": The name of the first directory sub-level is used.</li>
<li>"(1)": The name of the second directory sub-level is used.</li>
</ul></td>
</tr>
<tr>
<td><p>folder_monitoring.folders.</p>
<p>&lt;logical_name&gt;.interval</p></td>
<td>int</td>
<td>60</td>
<td>The interval between two scans of the directory files in seconds.</td>
</tr>
<tr>
<td><p>folder_monitoring.folders.</p>
<p>&lt;logical_name&gt;.file_count</p></td>
<td>int</td>
<td>-1</td>
<td><p>Maximum number of file submissions for each scan. Using the default value indicates that there is no maximum.</p></td>
</tr>
<tr>
<td><p>folder_monitoring.folders.</p>
<p>&lt;logical_name&gt;.file_size_min</p></td>
<td>int</td>
<td>-1</td>
<td>Files shorter than this value, in bytes, are not candidates for submission. Using the default value indicates that there is no lower limit on the file size.</td>
</tr>
<tr>
<td><p>folder_monitoring.folders.</p>
<p>&lt;logical_name&gt;.file_size_max</p></td>
<td>int</td>
<td>-1</td>
<td>Files larger than this value, in bytes, are not candidates for submission. Using the default value indicates that there is no upper limit on the file size.</td>
</tr>
<tr>
<td><p>folder_monitoring.folders.</p>
<p>&lt;logical_name&gt;.file_include_filter</p></td>
<td>string</td>
<td>""</td>
<td>If this parameter is defined, only files whose names match this pattern are monitored.</td>
</tr>
<tr>
<td><p>folder_monitoring.folders.</p>
<p>&lt;logical_name&gt;.file_exclude_filter</p></td>
<td>string</td>
<td>""</td>
<td>If this parameter is defined, files whose names match this pattern are not monitored.</td>
</tr>
<tr>
<td><p>folder_monitoring.folders.</p>
<p>&lt;logical_name&gt;.resubmit_changed_file</p></td>
<td>Boolean</td>
<td>Yes</td>
<td><p>This parameter has no effect when the configured method is MOVE.</p>
<p>When the method parameter value is set to FILE:</p>
<ul>
<li>Yes: When the state of a previously submitted file is seen as having changed, the file is submitted again.</li>
<li>No: Files are not resubmitted, regardless of changes.</li>
</ul>
<table data-cellpadding="0" data-cellspacing="0">
<tbody>
<tr>
<td data-valign="top"></td>
<td data-valign="top"><span><strong>Note</strong></span></td>
<td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">The file is resubmitted after <em>any</em> change regardless of if the modification is a small change, or purging and replacing the file with another file having the same name.</td>
</tr>
</tbody>
</table></td>
</tr>
<tr>
<td><p>folder_monitoring.folders.</p>
<p>&lt;logical_name&gt;.filter_type</p></td>
<td>enum</td>
<td>WILDMAT</td>
<td><p>Defines the pattern matching algorithm to use for file name filtering.

Values:</p>
<ul>
<li>STRJCMP: The Transfer CFT pattern matching algorithm.</li>
<li>WILDMAT: A well known public domain algorithm, and is the default. <strong>Unix/Windows only</strong></li>
</ul>
<p>See <a href="../folder_customize">Create inclusion and exclusion filters</a> for details.</p></td>
</tr>
<tr>
<td><p>folder_monitoring.folders.</p>
<p>&lt;logical_name&gt;.renaming_method</p></td>
<td>Enum</td>
<td>TIMESTAMP</td>
<td><p>This parameter applies only to the MOVE method.</p>
<ul>
<li>NONE or " ": The filename is unchanged (no timestamp is added). If the file already exists in the work directory, the MOVE process fails.</li>
<li>TIMESTAMP: A timestamp having the format YYYYMMDDHHMMSS is added at the end of the name of the renamed file but before the last '.'.</li>
</ul>

For example, using timestamp_separators=".":

<ul>
<li>myfile is renamed myfile.20131025</li>
<li>myfile.txt is renamed myfile.20131025.txt</li>
</ul></td>
</tr>
<tr>
<td><p>folder_monitoring.folders.</p>
<p>&lt;logical_name&gt;.renaming_separators</p></td>
<td>string</td>
<td> </td>
<td><p>This parameter only applies to the MOVE method.

It must contain at most 2 characters from among the following:</p>
<p>.[]()i_-</p>
<p>The first character defines the separator before the timestamp.

The second one, when present, defines the separator after the timestamp.</p>
<p>For example, using timestamp_separators "[]":

- myfile is renamed myfile.[20131025]

- myfile.txt is renamed myfile.[20131025].txt</p></td>
</tr>
<tr>
<td><p>folder_monitoring.folders.</p>
<p>&lt;logical_name&gt;.control</p></td>
<td>string</td>
<td> </td>
<td>Metadata used to control user changes.</td>
</tr>
<tr>
<td><p>folder_monitoring.folders.</p>
<p>&lt;logical_name&gt;.</p>
<p>use_file_system_events</p>
<p><a href="#file-sys">More information</a></p></td>
<td>Boolean</td>
<td>No</td>
<td>Set to YES to enable the file system events monitoring service to detect newly available files.</td>
</tr>
</tbody>
</table>
<table data-cellpadding="0" data-cellspacing="0">
<tbody>
<tr>
<td data-valign="top"></td>
<td data-valign="top"><span><strong>Note</strong></span></td>
<td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">*You cannot use the following characters in the SCANDIR or WORKDIR definition. Additionally you cannot use a comma (,) in the CFTFOLDER SCANDIR or WORKDIR definition.</td>
</tr>
</tbody>
</table>



-   <span>UNIX</span> /

-   For <span>Windows</span> \\ / : \* ? " &lt; &gt; |



**Comment\*\*\***: You can use CFTUTIL to create the list of folders &lt;logical\_names&gt;. When using CFTUTIL, be careful to correctly enter the command. For example, where FM1, FM2 and FM3 are 3 logical folders to be managed by <span>Transfer CFT</span>, enter:



CFTUTIL uconfset id= folder\_monitoring.folders, value= "'FM1 FM2 FM3 '"



## <span id="How2"></span>How <span>Transfer CFT</span> handles monitored files



This section describes how the various file monitoring parameters work.



### Parameter settings and actions



-   The delay between scans of a given directory is defined by its interval parameter value.

-   By default the ENABLESUBDIR \[enable\_subdir\] parameter is set to YES, and the directory and all its sub-directories are scanned.

-   For each file detected, the name is checked against the configured parameters values in the include and exclude file filters. Files that match the combined criteria are monitored, all others are ignored.



For a file to become a candidate to be submitted, the following conditions must be met:



-   File size: If these values are configured, the following rules apply.

    -   FILESIZEMIN \[file\_size\_min\]: The current size must not be less than this value.

    -   FILESIZEMAX \[file\_size\_max\]: The current size must not be greater than this value.

-   The last modification time and duration must not have changed within a number of seconds as defined in the FILEIDLEDELAY \[file\_idle\_delay\] parameter value.



## <span id="Modifying_existing_configuration"></span>Create or modify a monitored folder and apply configuration changes



The act of starting Transfer CFT causes Transfer CFT to check for and reload configuration changes. Alternatively, you can dynamically execute the <span>CFTUTIL RECONFIG type=FOLDER</span> command to check and reload the configuration.



Upon reloading, if there are any modified configuration parameters or detected errors in the new configuration, Transfer CFT records these in the log. Additionally, Transfer CFT verifies that the updated configuration is compatible with the contents of the current directories.



In particular, if you change the METHOD parameter from FILE to MOVE without modifying the scan\_dir and work\_dir parameters, and if the work\_dir directory is not empty, Transfer CFT displays an error message in the log and will not monitor the corresponding directory.



To deactivate compatibility checks of a folder’s new configuration, unset the value of the <span>folder\_monitoring.folders.&lt;logical\_name&gt;.control </span>parameter using the <span>uconfunset </span>command.



**Example**



If the folder's logical name is **A**, execute the following command prior to the reconfiguration (or start) command:



<table data-cellspacing="0">
<tbody>
<tr>
<td><p>CFTUTIL UCONFUNSET id = folder_monitoring.folders.<strong>A</strong>.control</p></td>
</tr>
</tbody>
</table>



When you then reconfigure (or start) Transfer CFT, the **A** folder is not checked.



<table data-cellspacing="0">
<tbody>
<tr>
<td><p>CFTUCONF RECONFIG type=folder</p></td>
</tr>
</tbody>
</table>



## <span id="Director"></span>Directory configuration examples



This section presents an example that consists of configuring 3 directories for monitoring, each having a different set of configuration parameter values. In this example, the three different directories are called A, B, and C.



Note that the configuration parameter folder\_monitoring must contain a list with these directory names, separated by blanks. Additionally, you must enable the folder monitoring functionality.



<table data-cellpadding="0" data-cellspacing="0">
<tbody>
<tr>
<td data-valign="top"></td>
<td data-valign="top"><span><strong>Note</strong></span></td>
<td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">In all of the examples in this topic, you must enter CFTUTIL in upper case.</td>
</tr>
</tbody>
</table>



For this example, you would execute the following command:



<table data-cellspacing="0">
<tbody>
<tr>
<td><p>CFTUTIL uconfset id=folder_monitoring.enable , value='Yes'</p>
<p>CFTUTIL uconfset id=folder_monitoring.folders , value= 'A B C'</p>
<p>*Note that the "' '"characters are used to protect the spaces between each folder monitoring nodes declarations.</p></td>
</tr>
</tbody>
</table>
<table data-cellpadding="0" data-cellspacing="0">
<tbody>
<tr>
<td data-valign="top"></td>
<td data-valign="top"><span><strong>Note</strong></span></td>
<td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">All of the examples in this section were written for a UNIX platform. Modify to suit your environment accordingly.</td>
</tr>
</tbody>
</table>



#### Directory A requirements



The first directory presents the simplest possible configuration, leaving most parameters set to their default values.



-   All of the files in the directory sub-tree are candidates for the SEND submission.

-   The files are sent to a given partner, newyork, using an IDF name of IDFA.



The following commands create the configuration defined for directory A.



<table data-cellspacing="0">
<tbody>
<tr>
<td><p>#</p>
<p># Create all of the needed directories (UNIX platform example)</p>
<p>#</p>
<p>mkdir /home/CFT/fm/dir_a</p>
<p>mkdir /home/CFT/fm/dir_a/scan</p>
<p>mkdir /home/CFT/fm/dir_a/work</p>
<p>#</p>
<p># Define the needed Transfer CFT configuration parameters leaving all others set to their default value.</p>
<p>#</p>
<p>CFTUTIL uconfset id=folder_monitoring.folders.A.scan_dir , value='/home/CFT/fm/dir_a/scan'</p>
<p>CFTUTIL uconfset id=folder_monitoring.folders.A.work_dir , value='/home/CFT/fm/dir_a/work'</p>
<p>CFTUTIL uconfset id=folder_monitoring.folders.A.part , value='NEWYORK'</p>
<p>CFTUTIL uconfset id=folder_monitoring.folders.A.idf , value='IDFA'</p></td>
</tr>
</tbody>
</table>



#### Directory B requirements



For the second directory, directory B, we want to:



-   Be able to send files to the following partners, newyork, berlin, london, rome, brussels, and paris.

-   Use the id given as the IDF, in this example TXT.

-   Send only files suffixed by .txt.



The following commands create the required directory B configuration.



<table data-cellspacing="0">
<tbody>
<tr>
<td><p>#</p>
<p># Create all needed directories (example for UNIX platforms)</p>
<p>#</p>
<p>mkdir /home/CFT/fm/dir_b</p>
<p>mkdir /home/CFT/fm/dir_b/scan</p>
<p>mkdir /home/CFT/fm/dir_b/work</p>
<p>mkdir /home/CFT/fm/dir_b/scan/newyork</p>
<p>mkdir /home/CFT/fm/dir_b/scan/berlin</p>
<p>mkdir /home/CFT/fm/dir_b/scan/london</p>
<p>mkdir /home/CFT/fm/dir_b/scan/rome</p>
<p>mkdir /home/CFT/fm/dir_b/scan/brussels</p>
<p>mkdir /home/CFT/fm/dir_b/scan/paris</p>
<p>#</p>
<p># Define all of the needed Transfer CFT configuration parameters, while leaving the others set to their default value.</p>
<p>#</p>
<p>CFTUTIL uconfset id=folder_monitoring.folders.B.scan_dir , value='/home/CFT/fm/dir_b/scan'</p>
<p>CFTUTIL uconfset id=folder_monitoring.folders.B.work_dir , value='/home/CFT/fm/dir_b/work'</p>
<p>CFTUTIL uconfset id=folder_monitoring.folders.B.part , value='(0)'</p>
<p>CFTUTIL uconfset id=folder_monitoring.folders.B.idf , value='TXT'</p>
<p>CFTUTIL uconfset id=folder_monitoring.folders.B.file_include_filter , value='*.txt'</p></td>
</tr>
</tbody>
</table>



The files to be sent must be moved to the directory that corresponds to the destination partner name, for example <span>/home/CFT/fm/dir\_b/newyork</span> for the partner named newyork.



#### Directory C requirements



For the third directory, directory C, we want to:



-   Be able to send files to multiple partners, newyork and paris.

-   Use idf1, idf2, or idf3 as the newyork partner IDF.

-   Use idfa, idfb, idfc, or idfd as the paris partner IDF.

-   Not send files suffixed by .tmp.

-   Automatically move the files to be sent to the scan\_dir, so the file\_idle\_delay parameter value is set to zero.

-   Submit files within a delay of approximately 10 seconds (interval).

-   Limit the number of send submissions per interval to 4 (file\_count).



The following commands create the described directory C configuration.



<table data-cellspacing="0">
<tbody>
<tr>
<td><p>#</p>
<p># Create all needed directories (example for UNIX platforms)</p>
<p>#</p>
<p>mkdir /home/CFT/fm/dir_c</p>
<p>mkdir /home/CFT/fm/dir_c/scan</p>
<p>mkdir /home/CFT/fm/dir_c/work</p>
<p>mkdir /home/CFT/fm/dir_c/scan/newyork/idf1</p>
<p>mkdir /home/CFT/fm/dir_c/scan/newyork/idf2</p>
<p>mkdir /home/CFT/fm/dir_c/scan/newyork/idf3</p>
<p>mkdir /home/CFT/fm/dir_c/scan/paris/idfa</p>
<p>mkdir /home/CFT/fm/dir_c/scan/paris/idfb</p>
<p>mkdir /home/CFT/fm/dir_c/scan/paris/idfc</p>
<p>mkdir /home/CFT/fm/dir_c/scan/paris/idfd</p>
<p>#</p>
<p># Define all necessary Transfer CFT configuration parameters leaving others set to their default value.</p>
<p>#</p>
<p>CFTUTIL uconfset id=folder_monitoring.folders.C.file_idle_delay , value='0'</p>
<p>CFTUTIL uconfset id=folder_monitoring.folders.C.idf , value='(1)'</p>
<p>CFTUTIL uconfset id=folder_monitoring.folders.C.part , value='(0)'</p>
<p>CFTUTIL uconfset id=folder_monitoring.folders.C.scan_dir , value='/home/CFT/fm/dir_c/scan'</p>
<p>CFTUTIL uconfset id=folder_monitoring.folders.C.work_dir , value='/home/CFT/fm/dir_c/work'</p>
<p>CFTUTIL uconfset id=folder_monitoring.folders.C.interval , value='10'</p>
<p>CFTUTIL uconfset id=folder_monitoring.folders.C.file_count , value='4'</p>
<p>CFTUTIL uconfset id=folder_monitoring.folders.C.file_exclude_filter , value='*.tmp'</p></td>
</tr>
</tbody>
</table>



The files to be sent must be moved to the directory that corresponds to the destination partner and idf names, for example /home/CFT/fm/dir\_c/newyork/idf1 for the partner newyork and idf idf1.



## <span id="Folder"></span>Folder monitoring using the <span>Transfer CFT</span> UI



From the <span>Transfer CFT</span> UI, select the <span>Unified Configuration</span> icon. From the Unified configuration dialog box, select folder\_monitoring. To display all possible parameters, first create at least one folder (folder\_monitoring.folders) for <span>Transfer CFT</span> to monitor, and click **Apply**.



For more information on setting unified configuration parameters, refer to [Using UCONF in CFTUTIL](../../uconf/uconf_w_cftutil.htm) or [About the unified configuration](../../uconf/UCONF.htm) topics.



## <span id="File-sys"></span>File-system event monitoring



This feature enables you to use file-system events monitoring to detect newly available files for an immediate Transfer CFT action.



Available on Linux/Windows only



See [Supported OS for file-system event monitoring](intro_folder_monitor.htm#Supporte).



### Configure file-system event monitoring



Set the following UCONF parameters as shown below. When you set this option for a specific folder, Transfer CFT immediately treats any events that occur in this folder's SCAN directory.



<table data-cellspacing="0">
<tbody>
<tr>
<td>CFTUTIL uconfset id=folder_monitoring.folders.MyFolder.use_file_system_events, value=YES</td>
</tr>
</tbody>
</table>



#### Attention



This feature can be resource intensive for Transfer CFT and the system in general in the following situations:



-   You have a large number of directories and sub-directories monitored using file-system events.

-   The activity in terms of file additions, removals, changes of files in those directories is high.



We recommended that you only use file-system event monitoring when immediate attention by Transfer CFT is a functional requirement.



Related topics



-   <a href="..//transfercft/app_integration_intro/intro_folder_monitor">Introduction to folder monitoring</a>

-   <a href="../../../c_intro_userinterfaces/web_copilot_ui/flow_def_intro/cftfolder">Folder monitoring CFTFOLDER</a>

-   <a href="../migrate_uconf_cftfolder">Migrate to CFTFOLDER folder monitoring</a>

-   <a href="../folder_customize">Create inclusion and exclusion filters</a>
