{
    "title": "Migrate to CFTFOLDER folder monitoring",
    "linkTitle": "Migrate to CFTFOLDER folder monitoring",
    "weight": "220"
}You can use the Folder monitoring migration **utility** to help you migrate from the UCONF method of folder monitoring to the CFTFOLDER method. This procedure may be useful if you have migrated or upgraded from Transfer CFT 3.1.2 to Transfer CFT 3.2.4.

Reasons to switch to the CFTFOLDER method include:

-   Folder monitoring is easier to manage via the CFTFOLDER object
-   The UCONF method has a limitation on the number of logical folders that you can monitor

## Procedure

Using the cftmifm migration command creates a text file that the CFTUTIL utility can use to migrate the folder definitions, where the CFTFOLDER definitions are an extraction from the UCONF definitions.

You must stop and start, or restart, Transfer CFT for the modifications to be taken into account.

### Migration command

The folder migration utility is supplied as an executable file, and displays help text when invoked without arguments or options.

Actions

Two actions are available, you can extract the folder definitions to migrate, or purge the UCONF folder definitions after migrating.

cftmifm migrate | purge

Options

<table cellspacing="0">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Option</th>
         <th>Description</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>-s          </td>
         <td>Simulate. No action is taken, simply displays all actions that should be taken.
         </td>
      </tr>
      <tr>
         <td>-f         </td>
         <td>
            <p>Force. Ignores detected errors.</p>
            <p>By default, processing is canceled when error conditions are encountered.</p>
            <p>When the -f option is set, only fatal errors prevent processing.</p>
         </td>
      </tr>
      <tr>
         <td>-p         </td>
         <td>
            <p>Pattern. The folder selection pattern. </p>
            <p>Searches for corresponding folder candidates, allowing you to specify a subset of the folders that must be processed.</p>
            <p>The pattern syntax is the same as the STRJCMP filter type used by CFTFOLDER.</p>
         </td>
      </tr>
      <tr>
         <td>-t         </td>
         <td> Level. The trace level from 0..4. The lower the level, the fewer the messages that are displayed. The default value is 1.
         </td>
      </tr>
      <tr>
         <td>-w         </td>
         <td>Width. The maximum line width for displayed screen messages, between 80..500, where the default is 130.         </td>
      </tr>
      <tr>
         <td>-o         </td>
         <td>Fname. The output file for the CFTFOLDER object containing the definitions required for migration.
               <li>To create the migrated folders in Transfer CFT configuration, you must interpret the generated output file using CFTUTIL.               </li>         </td>
      </tr>
   </tbody>
</table>

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">          </td>
      </tr>
</table>

-   You must enter each option or argument separately.
-   The fname is ignored when using the purge command, or when using the (-s) simulation option.

### How the migration utility works

The Transfer CFT migration utility performs the following steps:

1.  Builds a list all the folder names defined in uconf.
2.  If a pattern was supplied, it restricts the list to nicknames that match this pattern.
3.  Checks that all names have the correct syntax and are all different.
4.  Removes any previously migrated or moved folders from the list.
5.  For each folder of the list, check if it can be migrated to Transfer CFT configuration.
6.  Optionally when using -s (simulate), it stops here and does not process.

### How the purge works

The Transfer CFT purge utility performs the following steps:

Builds a list all the folder names defined in uconf.

If a pattern was supplied, restricts the list to nicknames that match this pattern.

Checks that all names have the correct syntax and are all different.

When folders in the list also exist as CFTFOLDER objects in the Transfer CFT configuration, and STATE=ACTIVE, these folders are targeted to be purged.

At this point the purge is performed unless you have specified - s (simulate).

-   The purge removes all targeted folders from the folder\_monitoring.folders listed in UCONF. As opposed to the migration, this action directly alters the UCONF configuration.
-   If you are using -s (simulate), the tool only displays folders targeted by the purge.

## Examples of how to use the migrate and purge commands

### Examples on Unix or Windows systems

Example 1

Migrate all folders from UCONF to CFTFOLDER objects.

1.  Create CFTFOLDER objects in fm1.cfg file:  
    cftmifm migrate -o fm1.cfg
2.  Save uconf folder configuration:  
    CFTUTIL CFTEXT type=uconf,id=folder\_monitoring.\*,fout=fm\_uconf\_save.cfg
3.  Interpret fm1.cfg file:  
    CFTUTIL config type=input,fname=fm1.cfg
4.  Purge uconf folder configuration:  
    cftmifm purge

Example 2

Only migrate specific folders from the UCONF configuration to the CFTFOLDER option, for example, select all logical folders starting with the letter "A".

1.  Create the CFTFOLDER objects in a file called fm2.cfg, for example:  
    cftmifm migrate -p A\* -o fm2.cfg
2.  Make a backup save of the UCONF folder configuration:  
    CFTUTIL CFTEXT type=uconf,id=folder\_monitoring.\*,fout=fm\_uconf\_save.cfg
3.  Interpret the generated fm2.cfg file:  
    CFTUTIL config type=input,fname=fm2.cfg
4.  Purge the UCONF folder configuration:  
    cftmifm purge -p A\*

### Examples on an IBM i system

Example 1

Call the following programs to migrate from UCONF to CFTFOLDER objects.

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>CALL PGM(CFTMIFM) PARM('migrate' '-o' 'CFTPROD/fm1cfg')
</p>
            <p>CALL PGM(CFTUTIL) PARM(CFTEXT 'type=uconf,id=folder_monitoring.*,fout=CFTPROD/fm_uconf') 
</p>
            <p>CALL PGM(CFTUTIL) PARM(CONFIG 'type=input,fname=fm1cfg') 
</p>
            <p>CALL PGM(CFT324CI/CFTMIFM) PARM('purge')</p>
         </td>
      </tr>
   </tbody>
</table>

Example 2

Call the following programs to migrate specific folders from the UCONF configuration to the CFTFOLDER option. For example, select all logical folders starting with the letter "A".

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>CALL PGM(CFTMIFM) PARM('migrate' '-p' 'A*' '-o' 'CFTPROD/fm2cfg')
</p>
            <p>CALL PGM(CFTUTIL) PARM(CFTEXT 'type=uconf,id=folder_monitoring.*,fout=CFTPROD/fm_uconf') </p>
            <p>CALL PGM(CFTUTIL) PARM(CONFIG 'type=input,fname=fm2cfg') </p>
            <p>CALL PGM(CFTMIFM) PARM('purge' '-p' 'A*')</p>
         </td>
      </tr>
   </tbody>
</table>

### Examples on a z/OS system

Submit the CFTMIFM JCL located in the INSTALL library to migrate from UCONF to CFTFOLDER objects. Next submit the CFTMIFMP JCL, also located in the INSTALL library, to purge the UCONF configuration.

1.  Extracts all folder definitions: cftmifm migrate -p \* -o &lt;temp\_file>
2.  Print the output.
3.  Apply the extracted definitions: CFTUTIL config type=input,fname=&lt;temp\_file>
4.  Purges the all existing UCONF folder definitions: cftmifm purge -p \*

To  migrate or purge using a specific pattern you can modify the CFTMIFM and CFTMIFMP JCLs, otherwise all logical folders are affected.

### Rollback

A prerequisite to performing a rollback is that you must have made a backup of the UCONF folder configuration prior to having migrated. Using the example above, this is the step: CFTUTIL CFTEXT type=uconf,id=folder\_monitoring.\*,fout=fm\_uconf\_save.cfg

1.  Interpret the backup uconf folder file, for example fm\_uconf\_save.cfg.  
    CFTUTIL config type=input,fname=fm\_uconf\_save.cfg
2.  Manually remove all CFTFOLDER objects:  
    CFTFOLDER ID=&lt;folder>,mode=delete

### Limitations and notes

-   It is recommended, but you are not obliged, to purge the migrated UCONF folders. Therefore, if both CFTFOLDER and UCONF folders exists, the CFTFOLDER definitions takes precedence.
-   Case sensitivity: Unlike UCONF, CFTFOLDER identifiers are not case sensitive - for example, a folder called "SamPle" is migrated as SAMPLE.
-   Special characters: If folder names contain special characters (&”#{$€ …) or accents (éàù …), migration fails as the utility cannot read these. However, theses are correctly rewritten if they are part of the SCANDIR and WORKDIR parameters.
-   Folder name length: The length of the folder name in CFTFOLDER cannot exceed 32 characters. If a UCONF defined folder name is too long, it cannot be migrated.

Parameter mapping and descriptions

<table cellspacing="0">
   <col/>
   <col/>
   <col/>
   <col/>
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Parameter</th>
         <th>UCONF</th>
         <th>Type </th>
         <th>
            <p>Default</p>
            <p>UCONF</p>
</th>
         <th>
            <p>Default  </p>
            <p>CFTFOLDER</p>
</th>
         <th>Description</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>
            <p>same as in UCONF</p>
         </td>
         <td>folder_monitoring.enable         </td>
         <td>Boolean         </td>
         <td>No         </td>
         <td>No         </td>
         <td>
            <ul>
               <li>No: No folder monitoring occurs.               </li>
               <li>Yes: Enable <span>Transfer CFT</span> folder monitoring.                </li>
            </ul>
         </td>
      </tr>
      <tr>
         <td>ID<span> </span>         </td>
         <td>folder_monitoring.folders         </td>
         <td>node         </td>
         <td>None         </td>
         <td>None         </td>
         <td>
            <p>Add the logical folders to monitor (list of logical identifiers).
</p>
            <p>You should provide a unique name to identify the set of configuration parameters corresponding to this directory.
 If you have more than one Folder to monitor, use a space between each logical value. </p>
            <p>See the <b>Comment***</b> below this table for additional information. </p>
         </td>
      </tr>
      <tr>
         <td>STATE         </td>
         <td>
            <p>folder_monitoring.folders.</p>
            <p>&lt;logical_name&gt;.enable</p>
         </td>
         <td>Boolean         </td>
         <td>Yes         </td>
         <td>Active         </td>
         <td>
            <p>Enables a scan of the folder.</p>
            <p>Note: NO = NOACTIVE.</p>
         </td>
      </tr>
      <tr>
         <td>SCANDIR         </td>
         <td>
            <p>folder_monitoring.folders.</p>
            <p>&lt;logical_name&gt;.scan_dir
</p>
         </td>
         <td>string         </td>
         <td>None         </td>
         <td>None         </td>
         <td>
            <p>Absolute path name of the top level directory to scan.</p>
            <p>This directory must exist before restarting Transfer CFT.</p>
            <p>*See NOTE.</p>
         </td>
      </tr>
      <tr>
         <td>WORKDIR         </td>
         <td>
            <p>folder_monitoring.folders.</p>
            <p>&lt;logical_name&gt;.work_dir
</p>
         </td>
         <td>string         </td>
         <td>None         </td>
         <td>None         </td>
         <td>
            <p>Absolute path name of the top level directory available for file state information. Do not use the same name as you are using for the corresponding SCANDIR.</p>
            <ul>
               <li>If you are using the MOVE method, files that are ready to be submitted are available in the work_dir.               </li>
               <li>If you are using the FILE method, the .met files are stored in the work_dir.               </li>
            </ul>
            <p>&amp;&amp;&amp; ïïï ùùù</p>
            <p>*See NOTE.</p>
         </td>
      </tr>
      <tr>
         <td>ENABLESUBDIR         </td>
         <td>
            <p>folder_monitoring.folders.</p>
            <p>&lt;logical_name&gt;.enable_subdir
</p>
         </td>
         <td>Boolean         </td>
         <td>Yes         </td>
         <td>Yes         </td>
         <td>
            <p>Values:</p>
            <ul>
               <li>Yes: The entire scan_dir sub-directory tree is monitored.               </li>
               <li>No: No scan is performed.               </li>
            </ul>
         </td>
      </tr>
      <tr>
         <td>METHOD         </td>
         <td>
            <p>folder_monitoring.folders.</p>
            <p>&lt;logical_name&gt;.method
</p>
         </td>
         <td>enum         </td>
         <td>MOVE         </td>
         <td>MOVE         </td>
         <td>
            <p>Values:</p>
            <ul>
               <li>MOVE: Files are moved (by renaming), to the work_dir prior to being submitted.                </li>
               <li>FILE: Files are left in the scan_dir, and a state file with the same name is created in work_dir prior to submitting the file.               </li>
            </ul>
         </td>
      </tr>
      <tr>
         <td>FILEIDLEDELAY         </td>
         <td>
            <p>folder_monitoring.folders.</p>
            <p>&lt;logical_name&gt;.file_idle_delay
</p>
         </td>
         <td>integer          </td>
         <td>5         </td>
         <td>5         </td>
         <td>If the state of a file has not changed within this delay in seconds, the file becomes a candidate for submission.         </td>
      </tr>
      <tr>
         <td>IDF         </td>
         <td>
            <p>folder_monitoring.folders.</p>
            <p>&lt;logical_name&gt;.idf
</p>
         </td>
         <td>string         </td>
         <td>""         </td>
         <td>""         </td>
         <td>
            <p>The IDF  name to use in the SEND command. Use one of the following:</p>
            <ul>
               <li> A fixed name.               </li>
               <li>"(0)":  The name of the first directory sub-level is used.               </li>
               <li>"(1)": The name of the second directory sub-level is used.               </li>
            </ul>
         </td>
      </tr>
      <tr>
         <td>PART         </td>
         <td>
            <p>folder_monitoring.folders.</p>
            <p>&lt;logical_name&gt;.part
</p>
         </td>
         <td>string         </td>
         <td>""         </td>
         <td>""         </td>
         <td>
            <p>The PART name to use in the SEND command. Use one of the following:</p>
            <ul>
               <li> A fixed name.               </li>
               <li>"(0)": The name of the first directory sub-level is used.               </li>
               <li>"(1)": The name of the second directory sub-level is used.               </li>
            </ul>
         </td>
      </tr>
      <tr>
         <td>INTERVAL         </td>
         <td>
            <p>folder_monitoring.folders.</p>
            <p>&lt;logical_name&gt;.interval</p>
         </td>
         <td>int         </td>
         <td>60         </td>
         <td>60         </td>
         <td>The interval between two scans of the directory files in seconds.         </td>
      </tr>
      <tr>
         <td>FILECOUNT         </td>
         <td>
            <p>folder_monitoring.folders.</p>
            <p>&lt;logical_name&gt;.file_count
</p>
         </td>
         <td>int         </td>
         <td>-1         </td>
         <td>0         </td>
         <td>
            <p>Maximum number of file submissions for each scan. Using the default value indicates that there is no maximum.</p>
         </td>
      </tr>
      <tr>
         <td>FILESIZEMIN         </td>
         <td>
            <p>folder_monitoring.folders.</p>
            <p>&lt;logical_name&gt;.file_size_min
</p>
         </td>
         <td>int         </td>
         <td>-1         </td>
         <td>0         </td>
         <td>Files shorter than this value, in bytes, are not candidates for submission.             <p>Using the default value indicates that there is no lower limit on the file size.</p>         </td>
      </tr>
      <tr>
         <td>FILESIZEMAX         </td>
         <td>
            <p>folder_monitoring.folders.</p>
            <p>&lt;logical_name&gt;.file_size_max
</p>
         </td>
         <td>int         </td>
         <td>-1         </td>
         <td>0         </td>
         <td>Files larger than this value, in bytes, are not candidates for submission. Using the default value indicates that there is no upper limit on the file size.         </td>
      </tr>
      <tr>
         <td>INCLUDEFILTER         </td>
         <td>
            <p>folder_monitoring.folders.</p>
            <p>&lt;logical_name&gt;.file_include_filter
</p>
         </td>
         <td>string         </td>
         <td>""         </td>
         <td>""         </td>
         <td>If this parameter is defined, only files whose names match this pattern are monitored.         </td>
      </tr>
      <tr>
         <td>EXCLUDEFILTER         </td>
         <td>
            <p>folder_monitoring.folders.</p>
            <p>&lt;logical_name&gt;.file_exclude_filter
</p>
         </td>
         <td>string         </td>
         <td>""         </td>
         <td>""         </td>
         <td>If this parameter is defined, files whose names match this pattern are not monitored.         </td>
      </tr>
      <tr>
         <td>RESUBMITCHANGED         </td>
         <td>
            <p>folder_monitoring.folders.</p>
            <p>&lt;logical_name&gt;.resubmit_changed_file
</p>
         </td>
         <td>Boolean         </td>
         <td>Yes         </td>
         <td>Yes         </td>
         <td>
            <p>This parameter  has no effect when the configured method is MOVE.</p>
            <p>When the method parameter value is set to FILE:</p>
            <ul>
               <li>Yes: When the state of a previously submitted file is seen as having changed, the file is submitted again.                </li>
               <li>No: Files are not resubmitted, regardless of changes.               </li>
            </ul>
            <p>&amp;&amp;&amp; ïïï ùùù</p>
         </td>
      </tr>
      <tr>
         <td>FILTERTYPE         </td>
         <td>
            <p>folder_monitoring.folders.</p>
            <p>&lt;logical_name&gt;.filter_type</p>
         </td>
         <td>enum         </td>
         <td>WILDMAT         </td>
         <td>WILDMAT         </td>
         <td>
            <p>Defines the pattern matching algorithm to use for file name filtering.
Values:
  </p>
            <ul>
               <li>STRJCMP: The Transfer CFT pattern matching algorithm.
                  </li>
               <li>WILDMAT: A well known public domain algorithm, and is the default. <strong>Unix/Windows only</strong>               </li>
            </ul>
            <p>See  <a href="#defining">Create inclusion and exclusion filters</a> for details.</p>
         </td>
      </tr>
      <tr>
         <td>RENAMEMETHOD         </td>
         <td>
            <p>folder_monitoring.folders.</p>
            <p>&lt;logical_name&gt;.renaming_method</p>
         </td>
         <td>Enum          </td>
         <td>TIMESTAMP          </td>
         <td>TIMESTAMP          </td>
         <td>
            <p>This parameter applies only to the MOVE method. </p>
            <ul>
               <li>NONE or " ": The filename is unchanged (no timestamp is added).   If the file already exists in the work directory, the MOVE process fails.               </li>
               <li> TIMESTAMP, a timestamp of the pattern YYYYMMDDHHMMSS is added at the end of the name of the renamed file but before the last '.'.               </li>
            </ul>For example, using timestamp_separators=".":            <ul>               <li>myfile     is renamed myfile.20131025               </li>               <li> myfile.txt is renamed myfile.20131025.txt               </li>            </ul>         </td>
      </tr>
      <tr>
         <td>RENAMESEPARATOR         </td>
         <td>
            <p>folder_monitoring.folders.</p>
            <p>&lt;logical_name&gt;.renaming_separators </p>
         </td>
         <td>string         </td>
         <td>          </td>
         <td>          </td>
         <td>
            <p>This parameter only applies to the MOVE method.
It must contain at most 2 characters from among the following: </p>
            <p>.[]()i_-
</p>
            <p>The first character defines the separator before the timestamp.
The second one, when present, defines the separator after the timestamp.
</p>
            <p>For example, using timestamp_separators "[]":
 - myfile     is renamed myfile.[20131025]
 - myfile.txt is renamed myfile.[20131025].txt
</p>
         </td>
      </tr>
      <tr>
         <td>N/A in this version         </td>
         <td>
            <p>folder_monitoring.folders.</p>
            <p>&lt;logical_name&gt;.control</p>
         </td>
         <td>string         </td>
         <td>          </td>
         <td>          </td>
         <td>Metadata used to control user changes.         </td>
      </tr>
      <tr>
         <td>
            <p>USEFSEVENTS</p>
            <p> </p>
         </td>
         <td>
            <p>folder_monitoring.folders.</p>
            <p>&lt;logical_name&gt;.</p>
            <p>use_file_system_events</p>
            <p><a href="../folder_monitor_uconf">More information</a>
</p>
         </td>
         <td>Boolean         </td>
         <td>No         </td>
         <td>No         </td>
         <td>Set to YES to enable the file system events monitoring service to detect newly available files.         </td>
      </tr>
      <tr>
         <td>USERID         </td>
         <td>N/A         </td>
         <td>N/A         </td>
         <td>N/A         </td>
         <td>N/A         </td>
         <td>This feature is not available in UCONF folder monitoring.         </td>
      </tr>
   </tbody>
</table>

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Caution  </b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Caution  &lt;/b&gt;" valign="top">   Never delete any .met files.         </td>
      </tr>
</table>

-   UNIX /
-   For Windows \\ / : \* ? " &lt; > |

Related topics

-   [Introduction to folder monitoring](..//transfercft/app_integration_intro/intro_folder_monitor)
-   [Folder monitoring CFTFOLDER](../../../c_intro_userinterfaces/web_copilot_ui/flow_def_intro/cftfolder)
-   [Migrate to CFTFOLDER folder monitoring](#)
-   [Create inclusion and exclusion filters](../folder_customize)
