{
    "title": "Folder Monitor transfer sites",
    "linkTitle": "Folder Monitor transfer sites",
    "weight": "210"
}The settings for Folder Monitor transfer sites can be divided as *Download settings* and *Upload settings*.

## Download settings for Folder Monitor transfer sites

The following screen presents the download settings for the Folder Monitor transfer sites.

<img src="/Images/SecureTransport/Account_TransferSite_FolderMonitor.jpg" class="mediumWidth" alt="Add Transfer Site - Folder Monitor transfer protocol" />

The following table describes the download settings Folder Monitor protocol options for a transfer site.

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Field         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><strong>Download Folder Settings</strong>         </td>
      </tr>
      <tr>
         <td>Download Folder         </td>
         <td><p>The full path to the folder to which incoming file transfers are saved. You cannot enter spaces-only values in this field.</p>
<p><strong>Note:</strong> The download folder should not be set to the root (/) folder of the operating system, because that can lead to the corruption of the whole Operating System.</p>
<p><strong>Note:</strong> <code>${DXAGENT_TRANSFERSAPI_*}</code> expressions are not supported.</p>
<p>You can use the following expression to append dates:<br />
<code>folder_${date("yyyyMMdd")}</code></p>
<p>The download folder will be evaluated using the current date when the transfer site is being executed. For example <code>folder_20210130</code>.</p>         </td>
      </tr>
      <tr>
         <td><strong>Download File Filter</strong>         </td>
      </tr>
      <tr>
         <td>Pattern Type         </td>
         <td>Select one of two types: <strong>Regular Expression</strong> or <strong>File Globbing</strong>. For regular expression syntax, see <a href="../../../c_st_regularexpressions#Appendix_Reg_Ex_3207565968_1044920" class="MCXref xref">Regular expressions</a>. File globbing uses simple wildcards to specify a pattern. A question mark (<code>?</code>) matches any one character. An asterisk (<code>*</code>) matches any number of characters.         </td>
      </tr>
      <tr>
         <td>Download Pattern         </td>
         <td><p>The file name pattern or regular expression used to match file names to determine whether a file is processed.</p>
<ul>
<li><p>Using it together with <strong>File Globbing</strong> Pattern Type selected:<br />
The download pattern will be evaluated using the current date when the transfer site is being executed, for example <code>*_20210130.txt</code>. This will match all files ending with <code>_20210130.txt</code>.<br />
Example:
<code>*_${date("yyyyMMdd")}.txt</code></p></li>
<li><p>Using it together with <strong>Regular Expression</strong> Pattern Type selected:<br />
The download pattern will be evaluated using the current date when the transfer site is being executed, for example <code>*[a-z]_20210130.txt</code>. This will match all files starting with any combination of letters from <span class="code">a</span> to <code>z</code> and ending with<span class="code"> _20210130.txt</span>.<br />
Example:
<code>*[a-z]_${date("yyyyMMdd")}.txt</code></p></li>
</ul>         </td>
      </tr>
      <tr>
         <td>Case Sensitive         </td>
         <td>Select this check box to enable case-sensitive file name matching.         </td>
      </tr>
      <tr>
         <td><strong>Subfolder Monitoring</strong>         </td>
      </tr>
      <tr>
         <td>Do Not Monitor Subfolders         </td>
         <td>Apply the download pattern to the download folder only.         </td>
      </tr>
      <tr>
         <td>Monitor All Subfolders         </td>
         <td>Apply the download pattern to the download folder and all subfolders.         </td>
      </tr>
      <tr>
         <td>Monitor Subfolders to a Maximum Depth of ___         </td>
         <td>Apply the download pattern to the download folder and subfolders to the depth specified. For example, if the maximum depth is <code>2</code>, apply the download pattern to the download folder and its immediate subfolders.         </td>
      </tr>
      <tr>
         <td>Download Subfolder Pattern Type         </td>
         <td>(Displayed only when monitoring subfolders) Select one of two types: <strong>Regular Expression</strong> or <strong>File Globbing</strong>. For regular expression syntax, see <a href="../../../c_st_regularexpressions#Appendix_Reg_Ex_3207565968_1044920" class="MCXref xref">Regular expressions</a>. File globbing uses simple wildcards to specify a pattern. A question mark (<code>?</code>) matches any one character. An asterisk (<code>*</code>) matches any number of characters.         </td>
      </tr>
      <tr>
         <td>Download Subfolder Pattern         </td>
         <td>(Displayed only when monitoring subfolders) The pattern used to match folder names to determine whether to apply the download pattern to the folder. You cannot enter spaces-only values in this field.         </td>
      </tr>
      <tr>
         <td>Case Sensitive         </td>
         <td>(Displayed only when monitoring subfolders) Select this check box to enable case-sensitive folder name matching.         </td>
      </tr>
      <tr>
         <td><strong>Post Transformation Settings</strong>         </td>
      </tr>
      <tr>
         <td>Receive File As         </td>
         <td>Select the check box to specify a file name. You can use the expression language to specify the criteria you want to match. The expression uses the criteria provided to create a new file name from the original file name when the transfer is received. You can use the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span>-specific variable <code>${stenv.site_target}</code> which takes the value from the remote file path. See <a href="../../../c_st_expressionlanguage" class="MCXref xref">Expression Language</a> for information on <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span>-specific variables.         </td>
      </tr>
   </tbody>
</table>

## Upload settings for Folder Monitor transfer sites

The following screen presents the upload settings for the Folder Monitor transfer sites.

<img src="/Images/SecureTransport/Account_TransferSite_FolderMonitor02.jpg" class="mediumWidth" alt="Add Transfer Site - Folder Monitor transfer protocol" />

The following table describes the upload settings Folder Monitor protocol options for a transfer site.

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Field         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>Upload Folder         </td>
         <td><p>The folder from which files to be transferred to the remote host are taken. You cannot enter spaces-only values in this field.</p>
<blockquote>
<p><strong>Note:</strong></p>
<p>Making the Upload Folder the same as the Download folder may lead to an infinite loop condition when the Transfer Site is used.</p>
</blockquote>         </td>
      </tr>
      <tr>
         <td>Automatically create upload folder if it doesn't exist         </td>
         <td>Upload Folder will be automatically created if it doesn't exist.
The automatically created folder will be owned by the user running the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> TM Server process.         </td>
      </tr>
      <tr>
         <td>Allow Overwrite         </td>
         <td><p>Taken into account when the site is used by the Send To Partner step. If checked the value of "Upload folder" will be overwritten with the value of "Overwrite upload folder". For more details see <a href="../../../c_st_advanced_routing" class="MCXref xref">Advanced Routing</a></p>         </td>
      </tr>
      <tr>
         <td><strong>Post Transmission Settings</strong>         </td>
      </tr>
      <tr>
         <td>Send File As         </td>
         <td>Select the check box to specify a file name. You can use the expression language to specify the criteria you want to match. The expression uses the criteria provided to create a new file name from the original file name.         </td>
      </tr>
      <tr>
         <td>On Failure         </td>
         <td>A failure occurs when the transfer is incomplete and all retry attempts were unsuccessful. Select one of the three choices: <strong>No Action</strong>, <strong>Delete Destination File</strong>, or <strong>Move/Rename File To</strong>. Selecting <strong>No Action</strong> causes the file to stay in the new location with the file name you specified. If another file with the same name is transferred to this location, the original file is overwritten. Selecting <strong>Delete Destination File</strong> removes the file from the new location. Selecting <strong>Move/Rename File To</strong> requires you to specify a directory in the location where you are transferring the files to and to provide an expression used to rename the file.         </td>
      </tr>
      <tr>
         <td>On Success         </td>
         <td>Select one of the choices: <strong>No Action</strong>, or <strong>Move/Rename File To</strong>. Selecting <strong>No Action</strong> causes the file to stay in the new location with the file name you specified. If another file with the same name is transferred to this location, the original file is overwritten. Selecting <strong>Move/Rename File To</strong> requires you to specify a directory in the location where you are transferring the files to and to provide an expression used to rename the file.         </td>
      </tr>
   </tbody>
</table>

 

## Folder Monitor specifics

The Folder Monitor protocol differs from the other supported protocols in the following aspects:

-   The folders listed in `<FILEDRIVEHOME>/conf/unsafe.paths.conf` file (and their sub-folders) cannot be specified in the **Upload Folder** and **Download Folder** fields.
-   The paths, specified in the **Upload Folder** and **Download Folder** fields, must be full system paths (not relative paths), such as:  
    `/tmp/folder_name/opt/TMWD/folder_name/`  
-   The files uploaded/moved into the specified upload folder are owned by the root user of the system.
-   If <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> is installed as a non-root deployment, the files in upload folder are owned by the user running the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Server.
-   If you configure the account to impersonate a user, the impersonated user must have full rights to the directories specified in the Folder Monitor.
-   If you upload or move a file in the specified upload folder and such a file already exists there, it is overwritten without a prompt.
-   If <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> is installed as a non-root deployment, the user running the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Server must have the necessary permissions to overwrite the file.
-   When the Folder Monitor starts to monitor the download folder, the download pattern is applied to all the files in the folder, even if they existed in the download folder before the Folder Monitor began monitoring.
-   If <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> is installed as a non-root deployment, the user running the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Server must have the necessary permissions to write to the upload folder.
-   <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> does not support placing the download folder and the upload folder under a repository encryption user home folder.
-   If you create a service account and a Standard Router application that uses a Folder Monitor transfer site, and you specify the same directory for sending and receiving messages, file transfers fail.
-   A Folder Monitor transfer site can be used to receive messages for only one subscription.
-   The names of the download folder and the upload folder of a Folder Monitor transfer site cannot contain two or more of the following characters in a sequence: `( ) _ - + = { } ~ ! @ # $ % ^ & ; “ ” ‘ ’`. For example, `folder_name` is supported, but `folder_+name` is not supported.
-   The name of a file processed by a Folder Monitor transfer site cannot contain two more of the following characters in sequence: `< > | : ? " * / \ % [ ] ~` (at the beginning of the file only).
-   Two Folder Monitor transfer sites cannot have the same download folder and download pattern.
-   The Folder Monitor service runs on the primary server in a Standard Cluster (SC). If that server fails, the Folder Monitor service automatically fails over to the new primary server.
-   The Folder Monitor service runs on one server in an Enterprise Cluster (EC). If that server fails, the Folder Monitor service automatically fails over to the server in the cluster with the Transaction Manager that has been running the longest.

**Related topics:**

-   <a href="../r_st_as2transfersites" class="MCXref xref">AS2 transfer sites</a>
-   <a href="../r_st_connectdirecttransfersites" class="MCXref xref">Connect:Direct transfer sites</a>
-   <a href="../r_st_fileservicesinterfaceprotocoltransfersites" class="MCXref xref">File services interface transfer sites</a>
-   <a href="../transfersites-ftp" class="MCXref xref">FTP(S) transfer sites</a>
-   <a href="../transfersites-generichttp" class="MCXref xref">Generic HTTP transfer sites</a>
-   <a href="../transfersites-http" class="MCXref xref">HTTP(S) transfer sites</a>
-   <a href="../transfersites-pesit" class="MCXref xref">PeSIT transfer sites</a>
-   <a href="../transfersites-ssh" class="MCXref xref">SSH transfer sites</a>
-   <a href="../transfersites-s2h" class="MCXref xref">System to Human transfer sites</a>
-   <a href="../t_st_transfersites" class="MCXref xref">Manage transfer sites</a>
