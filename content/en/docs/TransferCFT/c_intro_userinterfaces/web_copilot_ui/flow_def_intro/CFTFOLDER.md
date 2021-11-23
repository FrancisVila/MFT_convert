{
    "title": "Folder monitoring CFTFOLDER",
    "linkTitle": "Folder monitoring - CFTFOLDER",
    "weight": "270"
}This section provides a description of how to use Transfer CFT objects to manage folder monitoring.

> **Note:**
>
> There are two ways to implement Transfer CFT folder monitoring, either using UCONF or Transfer CFT objects. We recommend the CFTFOLDER method of configuring folder monitoring. Users that presently are using UCONF to manage folder monitoring can migrate to a CFTFOLDER configuration as described in Migrate to CFTFOLDER folder monitoring.

## CFTFOLDER object

The following table describes the parameters you can use to define the CFTFOLDER object. Additionally the table lists the UCONF equivalent for users who have opted for a polling type of folder monitoring.

### Folder monitoring parameters

Use the following CFTFOLDER parameters to configure folder monitoring for each directory as needed.

<table>
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1"><span id="Paramete"></span>Parameter         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Type         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1"><p>Default  </p>         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>same as in UCONF</p>
<p>&lt;folder_monitoring.enable&gt;</p>         </td>
         <td>Boolean         </td>
         <td>No         </td>
         <td><ul>
<li>No: No folder monitoring occurs.</li>
<li>Yes: Enable {{< TransferCFT/componentshortname  >}} folder monitoring.</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>ID</p>
<p><em><em>Mandatory</em></em></p>         </td>
         <td>node         </td>
         <td>None         </td>
         <td><p>Add the logical folders to monitor (list of logical identifiers).</p>
<p>You should provide a unique name to identify the set of configuration parameters corresponding to this directory.
If you have more than one Folder to monitor, use a space between each logical value.</p>         </td>
      </tr>
      <tr>
         <td>STATE         </td>
         <td>Boolean         </td>
         <td>Active         </td>
         <td><p>Enables a scan of the folder.</p>
<blockquote>
<p><strong>Note:</strong></p>
<p>NO = NOACTIVE.</p>
</blockquote>         </td>
      </tr>
      <tr>
         <td><p>SCANDIR</p>
<em>Mandatory</em>         </td>
         <td>string         </td>
         <td>None         </td>
         <td><p>Absolute path name of the top level directory to scan.</p>
<p>This directory must exist before restarting Transfer CFT.</p>
<p>*See <a href="#char_note">NOTE</a>.</p>         </td>
      </tr>
      <tr>
         <td><p>WORKDIR</p>
<em>Mandatory</em>         </td>
         <td>string         </td>
         <td>None         </td>
         <td><p>Absolute path name of the top level directory available for file state information.</p>
<ul>
<li>If you are using the MOVE method, files that are ready to be submitted are available in the work_dir.</li>
<li>If you are using the FILE method, the .met files are stored in the work_dir.</li>
</ul>
<blockquote>
<p><strong>Note:</strong></p>
<p>Caution  
  Never delete any .met files.</p>
</blockquote>
<p>*See <a href="#char_note">NOTE</a>.</p>         </td>
      </tr>
      <tr>
         <td>ENABLESUBDIR         </td>
         <td>Boolean         </td>
         <td>Yes         </td>
         <td><p>Values:</p>
<ul>
<li>Yes: The entire scan_dir sub-directory tree is monitored.</li>
<li>No: No scan is performed.</li>
</ul>         </td>
      </tr>
      <tr>
         <td><span id="METHOD"></span>METHOD         </td>
         <td>enum         </td>
         <td>MOVE         </td>
         <td><p>Values:</p>
<ul>
<li>MOVE: Files are moved to the work_dir prior to being submitted.</li>
<li>FILE: Files are left in the scan_dir, and a state file with the same name is created in work_dir prior to submitting the file.</li>
</ul>
<blockquote>
<p><strong>Note:</strong></p>
<p>Before changing the method from FILE to MOVE, you should remove all files (metadata .met files) located in the associated working directory.</p>
</blockquote>
<blockquote>
<p><strong>Note:</strong></p>
<p>Changing the method from MOVE to FILE, deletes all files located in the associated working directory. Therefore, we recommend removing all files from the scan and working directory before changing the METHOD type.</p>
</blockquote>
<p>Please see the <a href="../../../../app_integration_intro/intro_folder_monitor#Limitati">Limitations</a> for multi-host system recommendations.</p>         </td>
      </tr>
      <tr>
         <td>ARCHIVEDIR         </td>
         <td>String         </td>
         <td>          </td>
         <td>Archive directory where a source file is moved to after a successful transfer. This means the source file is moved from the WORKDIR for METHOD=MOVE or SCANDIR for METHOD=FILE to the ARCHIVEDIR.         </td>
      </tr>
      <tr>
         <td>FILEIDLEDELAY         </td>
         <td>integer         </td>
         <td>5         </td>
         <td>If the state of a file has not changed within this delay in seconds, the file becomes a candidate for submission.         </td>
      </tr>
      <tr>
         <td>GROUPID         </td>
         <td>String         </td>
         <td>          </td>
         <td>Complementary information for the USERID. Maximum length 32 characters.         </td>
      </tr>
      <tr>
         <td><p>IDF</p>
<p><em>Mandatory</em></p>         </td>
         <td>string         </td>
         <td>""         </td>
         <td><p>The IDF name to use in the SEND command. Use one of the following:</p>
<ul>
<li>A fixed name.</li>
<li>"(0)": The name of the first directory sub-level is used.</li>
<li>"(1)": The name of the second directory sub-level is used.</li>
</ul>
<blockquote>
<p><strong>Note:</strong></p>
<p>In the Directory C example/home/CFT/fr/dir_c/scan/newyork/idf1, the (0) represents newyork, and (1) represents idf1.</p>
</blockquote>         </td>
      </tr>
      <tr>
         <td><p>PART</p>
<em>Mandatory</em>         </td>
         <td>string         </td>
         <td>""         </td>
         <td><p>The PART name to use in the SEND command. Use one of the following:</p>
<ul>
<li>A fixed name.</li>
<li>"(0)": The name of the first directory sub-level is used.</li>
<li>"(1)": The name of the second directory sub-level is used.</li>
</ul>
<blockquote>
<p><strong>Note:</strong></p>
<p>In the Directory C example/home/CFT/fr/dir_c/scan/newyork/idf1, the (0) represents newyork, and (1) represents idf1.</p>
</blockquote>         </td>
      </tr>
      <tr>
         <td>INTERVAL         </td>
         <td>int         </td>
         <td>60         </td>
         <td>The interval between two scans of the directory files in seconds.         </td>
      </tr>
      <tr>
         <td>FILECOUNT         </td>
         <td>int         </td>
         <td>0         </td>
         <td><p>Maximum number of file submissions for each scan. Using the default value indicates that there is no maximum.</p>         </td>
      </tr>
      <tr>
         <td>FILESIZEMIN         </td>
         <td>int         </td>
         <td>0         </td>
         <td><p>Files shorter than this value, in bytes, are not candidates for submission. Using the default value indicates that there is no lower limit on the file size.</p>         </td>
      </tr>
      <tr>
         <td>FILESIZEMAX         </td>
         <td>int         </td>
         <td>0         </td>
         <td><p>Files larger than this value, in bytes, are not candidates for submission. Using the default value indicates that there is no upper limit on the file size.</p>         </td>
      </tr>
      <tr>
         <td>INCLUDEFILTER         </td>
         <td>string         </td>
         <td>""         </td>
         <td>If this parameter is defined, only files whose names match this pattern are monitored.         </td>
      </tr>
      <tr>
         <td>EXCLUDEFILTER         </td>
         <td>string         </td>
         <td>""         </td>
         <td>If this parameter is defined, files whose names match this pattern are not monitored.         </td>
      </tr>
      <tr>
         <td>RESUBMITCHANGED         </td>
         <td>Boolean         </td>
         <td>Yes         </td>
         <td><p>This parameter has no effect when the configured method is MOVE.</p>
<p>When the method parameter value is set to FILE:</p>
<ul>
<li>Yes: When the state of a previously submitted file is seen as having changed, the file is submitted again.</li>
<li>No: Files are not resubmitted, regardless of changes.</li>
</ul>
<blockquote>
<p><strong>Note:</strong></p>
<p>The file is resubmitted after any change regardless of if the modification is a small change, or purging and replacing the file with another file having the same name.</p>
</blockquote>         </td>
      </tr>
      <tr>
         <td>FILTERTYPE         </td>
         <td>enum         </td>
         <td>WILDMAT         </td>
         <td><p>Defines the pattern matching algorithm to use for file name filtering.</p>
<p>Values:</p>
<ul>
<li>STRJCMP: The Transfer CFT pattern matching algorithm.</li>
<li>WILDMAT: A well known public domain algorithm, and is the default. <strong>Unix/Windows only</strong></li>
<li>EREGEX:  Extended regular expression syntax.</li>
</ul>
<p>See <a href="../../../../app_integration_intro/intro_folder_monitor/folder_customize#Defining">Create inclusion and exclusion filters</a> for details.</p>         </td>
      </tr>
      <tr>
         <td>RENAMEMETHOD         </td>
         <td>Enum         </td>
         <td>TIMESTAMP         </td>
         <td><p>This parameter applies only to the MOVE method. When set to TIMESTAMP, a timestamp of the pattern YYYYMMDDHHMMSS is added at the end of the name of the renamed file but before the last '.'.</p>
For example, using timestamp_separators=".":
<ul>
<li>myfile is renamed myfile.20131025</li>
<li>myfile.txt is renamed myfile.20131025.txt</li>
</ul>
<blockquote>
<p><strong>Note:</strong></p>
<p>Unset the default value and use " " to MOVE without adding a timestamp.</p>
</blockquote>         </td>
      </tr>
      <tr>
         <td>RENAMESEPARATOR         </td>
         <td>string         </td>
         <td><p>"."</p>         </td>
         <td><p>This parameter only applies to the MOVE method.</p>
<p>You can use no more than two characters from among the following:</p>
<p>.[]()_-</p>
<p>The first character defines the separator before the timestamp.
The second one, when present, defines the separator after the timestamp.</p>
<p>For example, using timestamp_separators "[]":
- myfile is renamed myfile.[20131025]
- myfile.txt is renamed myfile.[20131025].txt</p>         </td>
      </tr>
      <tr>
         <td>N/A in this version         </td>
         <td>string         </td>
         <td>          </td>
         <td>Metadata used to control user changes.         </td>
      </tr>
      <tr>
         <td><p>USEFSEVENTS</p>
<p> </p>
<p><a href="#Enable">More information</a></p>         </td>
         <td>Boolean         </td>
         <td>No         </td>
         <td>Set to YES to enable the file system events monitoring service to detect newly available files.         </td>
      </tr>
      <tr>
         <td><a href="../../../command_summary/parameter_intro/userid">USERID</a>         </td>
         <td>String         </td>
         <td>         </td>
         <td><p><em>Available on UNIX and</em> <em></em></p>
<p>Identifier for a user who can scan a folder. See the section, <a href="../../../../app_integration_intro/intro_folder_monitor/configure_folder_monitoring#Folder2">Folder monitoring using USERCTRL</a>.</p>         </td>
      </tr>
   </tbody>
</table>

> **Note:**
>
> \*You cannot use the following characters in the SCANDIR or WORKDIR definition. Additionally you cannot use a comma (,) in the CFTFOLDER SCANDIR or WORKDIR definition.

-   /
-   For \\ / : \* ? " &lt; > |

Related topics

-   <a href="../../../../app_integration_intro/intro_folder_monitor" class="MCXref xref">Introduction to folder monitoring</a>
-   <a href="../../../../app_integration_intro/intro_folder_monitor/folder_monitor_uconf" class="MCXref xref">Deprecated folder monitoring (UCONF)</a>
-   <a href="../../../../app_integration_intro/intro_folder_monitor/migrate_uconf_cftfolder" class="MCXref xref">Migrate to CFTFOLDER folder monitoring</a>
-   <a href="../../../../app_integration_intro/intro_folder_monitor/folder_customize" class="MCXref xref">Create inclusion and exclusion filters</a>
