{
    "title": "Folder monitoring CFTFOLDER",
    "linkTitle": "Folder monitoring CFTFOLDER",
    "weight": "190"
}This section provides a description of how to use Transfer CFT objects to manage folder monitoring.

<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Note</strong></span>         </td>
         <td>There are two ways to implement Transfer CFT folder monitoring, either using UCONF or Transfer CFT objects. We recommend the CFTFOLDER method of configuring folder monitoring. Users that presently are using UCONF to manage folder monitoring can migrate to a CFTFOLDER configuration as described in <a href="../migrate_uconf_cftfolder">Migrate to CFTFOLDER folder monitoring</a>.         </td>
      </tr>
   </tbody>
</table>

## Folder monitoring set up

1.  Activate the folder monitoring option.
    -   Set uconf parameter folder\_monitoring.enable to <span class="bold_in_para">Yes</span>.
2.  Declare your logical directories to monitor.
    -   Add CFTFOLDER objects.
3.  For each logical directory defined, configure the specific options you want to use for each:
    -   File management method

    <!-- -->

    -   Used sub-directories

    <!-- -->

    -   Set the IDF

    <!-- -->

    -   Set the partner name

    <!-- -->

    -   Define the delay to take into account the file

    <!-- -->

    -   Define other Folder Monitoring parameters
4.  Optionally, to specify file-system event monitoring you additionally must set this in [CFTFOLDER object.](#Enable)

<span id="CFTFOLDE"></span>

## CFTFOLDER object

The following table describes the parameters you can use to define the CFTFOLDER object. Additionally the table lists the UCONF equivalent for users who have opted for a polling type of folder monitoring.

<span id="Folder"></span>

### Folder monitoring parameters

Use the following CFTFOLDER parameters to configure folder monitoring for each directory as needed.

Parameter descriptions

<table>
   <th>
      <tr>
<th><span id="Paramete"></span>Parameter         </th>
<th>Type         </th>
<th><p>Default  </p>         </th>
<th>Description         </th>
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
<li>Yes: Enable <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> folder monitoring.</li>
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
<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Note</strong></span>         </td>
         <td>NO = NOACTIVE.         </td>
      </tr>
   </tbody>
</table>         </td>
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
<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Caution  </strong></span>         </td>
         <td>  Never delete any .met files.         </td>
      </tr>
   </tbody>
</table>
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
<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Note</strong></span>         </td>
         <td>Before changing the method from FILE to MOVE, you should remove all files (metadata .met files) located in the associated working directory.         </td>
      </tr>
   </tbody>
</table>
<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Note</strong></span>         </td>
         <td>Changing the method from MOVE to FILE, deletes all files located in the associated working directory. Therefore, we recommend removing all files from the scan and working directory before changing the METHOD type.         </td>
      </tr>
   </tbody>
</table>
<p>Please see the <a href="../#Limitati">Limitations</a> for multi-host system recommendations.</p>         </td>
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
<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Note</strong></span>         </td>
         <td>In the <a href="#example_for_description">Directory C example</a><span class="code">/home/CFT/fr/dir_c/scan/newyork/idf1, </span>the (0) represents newyork, and (1) represents idf1.         </td>
      </tr>
   </tbody>
</table>         </td>
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
<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Note</strong></span>         </td>
         <td>In the <a href="#example_for_description">Directory C example</a><span class="code">/home/CFT/fr/dir_c/scan/newyork/idf1, </span>the (0) represents newyork, and (1) represents idf1.         </td>
      </tr>
   </tbody>
</table>         </td>
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
<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Note</strong></span>         </td>
         <td>The file is resubmitted after <em>any</em> change regardless of if the modification is a small change, or purging and replacing the file with another file having the same name.         </td>
      </tr>
   </tbody>
</table>         </td>
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
<p>See <a href="../folder_customize#Defining">Create inclusion and exclusion filters</a> for details.</p>         </td>
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
<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Note</strong></span>         </td>
         <td>Unset the default value and use " " to MOVE without adding a timestamp.         </td>
      </tr>
   </tbody>
</table>         </td>
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
<p><a href="../../../c_intro_userinterfaces/web_copilot_ui/flow_def_intro/cftfolder#Enable">More information</a></p>         </td>
         <td>Boolean         </td>
         <td>No         </td>
         <td>Set to YES to enable the file system events monitoring service to detect newly available files.         </td>
      </tr>
      <tr>
         <td><a href="../../../c_intro_userinterfaces/command_summary/parameter_intro/userid">USERID</a>         </td>
         <td>String         </td>
         <td>         </td>
         <td><p><em>Available on UNIX and</em> <span class="mc-variable Primary.for_Windows variable" style="font-style: italic;">Windows</span> <em></em></p>
<p>Identifier for a user who can scan a folder. See the section, <a href="#Folder2">Folder monitoring using USERCTRL</a>.</p>         </td>
      </tr>
   </tbody>
</table>

<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Note</strong></span>         </td>
         <td><span id="char_note"></span>*You cannot use the following characters in the SCANDIR or WORKDIR definition. Additionally you cannot use a comma (,) in the CFTFOLDER SCANDIR or WORKDIR definition.         </td>
      </tr>
   </tbody>
</table>

-   <span class="mc-variable Primary.For_unix variable">UNIX</span> /
-   For <span class="mc-variable Primary.for_Windows variable">Windows</span> \\ / : \* ? " &lt; > |

### Parameter settings and actions

-   The delay between scans of a given directory is defined by its interval parameter value.
-   By default the ENABLESUBDIR \[enable\_subdir\] parameter is set to YES, and the directory and all its sub-directories are scanned.
-   For each file detected, the name is checked against the configured parameters values in the include and exclude file filters. Files that match the combined criteria are monitored, all others are ignored.

For a file to become a candidate to be submitted, the following conditions must be met:

-   File size: If these values are configured, the following rules apply.
    -   FILESIZEMIN \[file\_size\_min\]: The current size must not be less than this value.
    -   FILESIZEMAX \[file\_size\_max\]: The current size must not be greater than this value.
-   The last modification time and duration must not have changed within a number of seconds as defined in the FILEIDLEDELAY \[file\_idle\_delay\] parameter value.

## Create or modify a CFTFOLDER object

The act of starting Transfer CFT causes Transfer CFT to check for and reload configuration changes. Alternatively, you can dynamically execute the <span class="code">CFTUTIL RECONFIG type=FOLDER</span> command to check and reload the configuration.

Upon reloading, if there are any modified configuration parameters or detected errors in the new configuration, Transfer CFT records these in the log. Additionally, Transfer CFT verifies that the updated configuration is compatible with the contents of the current directories.

In particular, if you change the METHOD parameter from FILE to MOVE without modifying the scan\_dir and work\_dir parameters, and if the work\_dir directory is not empty, Transfer CFT displays an error message in the log and will not monitor the corresponding directory.

If you create or modify a folder while Transfer CFT is running, you must execute the ACT command to reload the configuration.

<span class="bold_in_para">Example</span>

The following command reloads the FM40 configuration.


    ACT ID=FM40, type=FOLDER 

<span id="Enable"></span>

## Enable the file-system event monitoring

This feature enables you to use file-system events monitoring to detect newly available files for an immediate Transfer CFT action.

Available on Linux/Windows only

See [Supported OS for file-system event monitoring](../#Supporte).

To enable file-system event monitoring modify as follows:


    CFTFOLDER ID=<myfolderobject>, USEFSEVENTS=YES, ...

#### Attention

This feature can be resource intensive for Transfer CFT and the system in general in the following situations:

-   You have a large number of directories and sub-directories monitored using file-system events.
-   The activity in terms of file additions, removals, changes of files in those directories is high.

We recommended that you only use file-system event monitoring when immediate attention by Transfer CFT is a functional requirement.

<span id="Activate"></span>

## Activate and deactivate folder monitoring

To turn the file-system event monitoring off for a given folder object, use the command:


     INACT TYPE=FOLDER,ID=<myfolderobject>

To turn on the file-system event monitoring for a given folder object, use the command:


     ACT TYPE=FOLDER,ID=<myfolderobject>

To view all of the CFTFOLDER objects, use the command:


     LISTPARM TYPE=FOLDER

To extract the folder objects, use the command:


     CFTEXT TYPE=FOLDER

## Remove or change a folder

### Change a folder

If Transfer CFT is running and you create or change a folder or multiple folders, you can execute RECONFIG TYPE=FOLDER so that all changes are taken into account.

### Delete a folder

Prior to deleting a folder object, check that it is inactive. You can execute INACT on this folder if unsure.



    INACT TYPE=FOLDER, ID=<myfolder>
    CFTFOLDER ID=<myfolder>, MODE=DELETE

<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Note</strong></span>         </td>
         <td>If you delete an active folder object while Transfer CFT is running without first deactivating the folder (INACT), you must execute a RECONFIG TYPE=FOLDER. If you do not, the folder remains active.         </td>
      </tr>
   </tbody>
</table>

## Directory configuration examples

This section presents an example that consists of configuring 3 directories for monitoring, each having a different set of configuration parameter values. In this example, the three different directories are called A, B, and C.

<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Note</strong></span>         </td>
         <td>All of the examples in this section were written for a UNIX platform. Modify to suit your environment accordingly.         </td>
      </tr>
   </tbody>
</table>

### Directory A requirements

The first directory presents the simplest possible configuration, leaving most parameters set to their default values.

-   All of the files in the directory sub-tree are candidates for the SEND submission.
-   The files are sent to a given partner, <span class="code">newyork</span>, using an IDF name of IDFA.

The following commands create the configuration defined for directory A.



    #
    # Create all of the needed directories (UNIX platform example)
    #
    mkdir /home/CFT/fm/dir_a
    mkdir /home/CFT/fm/dir_a/scan
    mkdir /home/CFT/fm/dir_a/work
    #
    CFTUTIL CFTFOLDER ID=A, SCANDIR='/home/CFT/fm/dir_a/scan',  WORKDIR='/home/CFT/fm/dir_a/work', PART='NEWYORK', IDF='IDFA'

### Directory B requirements

For the second directory, directory B, we want to:

-   Be able to send files to the following partners, newyork, berlin, london, rome, brussels, and paris.
-   Use the id given as the IDF, in this example TXT.
-   Send only files suffixed by .txt.

The following commands create the required directory B configuration.



    #
    # Create all needed directories (example for UNIX platforms)
    #
    mkdir /home/CFT/fm/dir_b
    mkdir /home/CFT/fm/dir_b/scan
    mkdir /home/CFT/fm/dir_b/work
    mkdir /home/CFT/fm/dir_b/scan/newyork
    mkdir /home/CFT/fm/dir_b/scan/berlin
    mkdir /home/CFT/fm/dir_b/scan/london
    mkdir /home/CFT/fm/dir_b/scan/rome
    mkdir /home/CFT/fm/dir_b/scan/brussels
    mkdir /home/CFT/fm/dir_b/scan/paris
    #
    CFTUTIL CFTFOLDER ID=B, SCANDIR='/home/CFT/fm/dir_b/scan', WORKDIR='/home/CFT/fm/dir_b/work', PART='(0)', IDF='TXT', INCLUDEFILTER='*.txt'

The files to be sent must be moved to the directory that corresponds to the destination partner name, for example <span class="code">/home/CFT/fm/dir\_b/newyork </span>for the partner named <span class="code">newyork</span>.

### Directory C requirements

For directory C we want to:

-   Send files to multiple partners, newyork and paris.
-   Use idf1, idf2, or idf3 as the newyork partner IDF.
-   Use idfa, idfb, idfc, or idfd as the paris partner IDF.
-   Not send files suffixed by .tmp.
-   Automatically move the files to be sent to the SCANDIR, so the FILEIDLEDELAY parameter value is set to zero.
-   Submit files within a delay of approximately 10 seconds (INTERVAL).
-   Limit the number of send submissions per interval to 4 (FILECOUNT).

The following commands create the described directory C configuration.



    #
    # Create all needed directories (example for UNIX platforms)
    #
    mkdir /home/CFT/fm/dir_c
    mkdir /home/CFT/fm/dir_c/scan
    mkdir /home/CFT/fm/dir_c/work
    mkdir /home/CFT/fm/dir_c/scan/newyork/idf1
    mkdir /home/CFT/fm/dir_c/scan/newyork/idf2
    mkdir /home/CFT/fm/dir_c/scan/newyork/idf3
    mkdir /home/CFT/fm/dir_c/scan/paris/idfa
    mkdir /home/CFT/fm/dir_c/scan/paris/idfb
    mkdir /home/CFT/fm/dir_c/scan/paris/idfc
    mkdir /home/CFT/fm/dir_c/scan/paris/idfd
    #
    CFTUTIL CFTFOLDER ID=C, FILEIDLEDELAY='0', PART='(0)', IDF='(1)', SCANDIR='/home/CFT/fm/dir_c/scan', 
    WORKDIR='/home/CFT/fm/dir_c/work', INTERVAL='10', FILECOUNT='4', FILEEXCLUDEFILTER='*.tmp'

The files to be sent must be moved to the directory that corresponds to the destination partner and idf names, for example /home/CFT/fm/dir\_c/newyork/idf1 for the partner <span class="code">newyork </span>and idf <span class="code">idf1</span>.

<span id="Customiz"></span>

## Customize SEND with folder monitoring

You can customize the transfer related metadata, such as the IDA, PARM, SUSER, etc. using the file name value. This allows folder monitoring to provide a functionality that resembles a SEND command.

For example, you have a file named <span class="code">A0001.appli1.cft.XXX</span> in the <span class="code">scan1 </span>folder, and you have the following two objects in your configuration:


    CFTFOLDER id=folder1,scandir=scan1,idf=idf1,par=part1,...CFTSEND id=idf1,ida=&%.1froot,sappl="&%.2froot",suser="&%.3froot",...

Consequently, Transfer CFT automatically creates a request based on the above syntax:


    SEND part=part1,idf=idf1,ida=A0001,sappl="appli1",suser="cft"

-   For more information on how to effectively use separators with symbolic variables, please see [Separate fields in symbolic variables.](../../../c_intro_userinterfaces/command_summary/symbolic_variables#Separate)
-   For more information on the various symbolic variables to use in CFTSEND with CFTFOLDER, see [List of symbolic variables.](../../../c_intro_userinterfaces/command_summary/symbolic_variables#List_of_symbolic_variables)

## Archiving with folder monitoring

Archiving is a way to store files after they have been moved from the scanned folder to the receiving folder.

1.  A file is deposited in the folder to be scanned.  
    ![](/Images/TransferCFT/folder5.png)
2.  Depending on the folder monitoring method you have enabled, the file is picked up and moved to the working directory.  
    ![](/Images/TransferCFT/folder6.png)
3.  The file transfer and any related processing occur and the file is then moved to the storage folder.  
    ![](/Images/TransferCFT/folder7.png)

### Use case scenario

The following example describes how to scan a folder, send any new file, and then store a backup of the file. Additionally, the scenario provides instructions on how to then rename the transferred file as it is stored in the backup folder.

<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Note</strong></span>         </td>
         <td>If you create a new transfer with the same name as a previous file, it overwrites the existing file in the archive folder.         </td>
      </tr>
   </tbody>
</table>

### Prerequisites

Create the following:

-   A folder to scan, for example: `mkdir myScanFolder`
-   A working folder, for example: <span class="code">mkdir myWorkFolder</span>
-   An archive folder, for example: `mkdir myArchiveFolder`
-   A test file, for example: `myFile.txt`
-   Folder monitoring must be enabled: `uconfset id=folder_monitoring.enable, value=yes`
-   Stop <span class="mc-variable suite_variables.TransferCFTName variable">Transfer CFT</span> prior to start the procedure, enter: `cft stop `

In the **Steps** below, we use the absolute paths, that is, the folders are located in the runtime directory.

### Archive with no file renaming afterward

1.  Create the CFTFOLDER object.  

2.  

        cftfolder id=app1, PART=paris, idf=myfile, scandir=MyScanFolder, workdir=MyWorkFolder, renamemethod=none, archivedir=MyArchiveFolder,method=move,interval=1,fileidledelay=0

3.  Activate the new CFTFOLDER object:  

4.  

        ACT type=folder, id=app1

5.  Start Transfer CFT: <span class="code">cft start</span>

6.  Put the test file in the <span class="code">runtime/MyScanFolder</span> folder.

7.  Navigate to the `runtime/MyArchivedFolder` and check that the <span class="code">MyFile.txt</span> is stored there.

8.  Check in the log for a message similar to the following:  



        CFTT89I Faction on FNAME=MyWorkFolder\MyFile.txt archived as MyArchivedFolder\MyFile.txt <IDTU=A000000F PART=PARIS IDF=MYFILE IDT=C1918185>

### Archive and rename in the archive folder

1.  Create the CFTFOLDER object.  

2.  

        cftfolder id=app1, PART=paris, idf=MyFile, SCANDIR=MyScanFolder, workdir=MyWorkFolder, renamemethod=none, archivedir=MyArchivedFolder,method=move,interval=1,fileidledelay=0

3.  Create a SEND model using `archivefname`. In this example the transfer's IDTU is appended on the filename:



        CFTSEND id=MYFILE, archivefname=&FROOT&(-.)FSUF_&IDTU, faction=ARCHIVE

4.  Activate the new CFTFOLDER object:  

5.  

        ACT type=folder, id=app1

6.  Start Transfer CFT: <span class="code">cft start</span>

7.  Put the test file in the <span class="code">runtime/MyScanFolder</span> folder.

8.  Navigate to the `runtime/MyArchiveFolder` and check that the <span class="code">MyFile.txt</span> is stored there.

9.  Check in the log for a message similar to the following:  



        CFTT89I Faction on FNAME=MyWorkFolder\MyFile.txt archived as MyArchiveFolder\MyFile.txt_A000000F <IDTU=A000000F PART=PARIS IDF=MYFILE IDT=C1918185>

<span id="Folder2"></span>

### Folder monitoring using USERCTRL

The following example demonstrates how to use the [USERCTRL](../../../c_intro_userinterfaces/command_summary/parameter_intro/userctrl) parameter to define access control for another user. See the sections on user rights in <a href="#" class="MCXref xref">Using system users - UNIX</a> or <a href="#" class="MCXref xref">How to enable system users - Windows</a> for details.

<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Note</strong></span>         </td>
         <td>USEFSEVENTS=YES is not supported on UNIX systems in this use case.         </td>
      </tr>
   </tbody>
</table>

1.  Enable USERCTRL in the CFTPARM command:  


        CFTPARM ID=IDPARM0,…,USERCTRL=YES

2.  Start Transfer CFT with `usercft `as the user.

3.  User1 creates the <span class="code">/home/user1/scandir\_app1</span> and `/home/user1/workdir` folders:  

4.  `App1 `writes files to this specific scandir folder, e.g. `/home/user1/scandir_app1`, which belongs to user1. Notice that the usercft user does not have access to`  scandir_app1`.

5.  From CFTUTIL, create a CFTFOLDER:  

6.  Activate the CFTFOLDER object:  

7.  Create a file called<span class="code"> Myfile.txt</span>, and copy it to the `/home/user1/scandir_app1` folder.

<span class="bold_in_para">Results</span>

The  transfer is executed on the behalf of user1. Notice that there is a message indicating that the folder is activated on behalf of the specified user.


    CFTR20I folder "/home/user1/scandir_app1" registered as nickname <APP1>
    CFTR20I on behalf of "user1" user
