{
    "title": "Configure the support tool",
    "linkTitle": "Configure the support tool",
    "weight": "160"
}Use the *Support Tool Configuration* page to specify the information that the support tool saves in the support information file and where it saves the file.

1.  Select **Operations > Support Tool** to display the *Support Tool Configuration* page.
2.  Specify the fields listed below.
3.  Click **Save**.  
    {{< SecureTransport/componentshortname >}} saves the configuration and replicates it to all nodes in a Server cluster or to all synchronized Edge servers.
4.  (AIX only) If you selected or deselected the **Collect TM thread dump** or **Collect TM heap dump** option, restart the Transaction Manager on all clustered {{< SecureTransport/componentshortname >}} Servers or all synchronized {{< SecureTransport/componentshortname >}} Edge servers using the `stop_tm` and `start_tm` commands in `<FILEDRIVEHOME>/bin`.
5.  Under *Files and Folders to Save*, add, remove, or edit the path names of files and folders to include in the support tool information file. Relative path names are relative to `<FILEDRIVEHOME>`. You can also add absolute path names.  
    {{< SecureTransport/componentshortname >}} saves each the change and replicates it to all nodes in a {{< SecureTransport/componentshortname >}} Server cluster or to all synchronized {{< SecureTransport/componentshortname >}} Edge servers.

The following topics describe the support tool fields and how-to instructions for excluding files:

-   <a href="#Fields" class="MCXref xref">Fields</a>
-   <a href="#Exclude" class="MCXref xref">Exclude files</a>

**Related topics:**

-   <a href="../t_st_customizesupporttool" class="MCXref xref">Add custom information to the support information file</a>
-   <a href="../t_st_runsupporttool" class="MCXref xref">Run the support tool</a>

<span id="Fields"></span>

## Fields

This topic includes information about the fields you must complete.

-   **Support Access Code** - The support tool includes the value of this field in the name of the support information file. Enter the Support Access Code for the support contact that covers this system. {{< SecureTransport/companyname >}} Global Support uses the code in the file name to make sure the file is handled correctly.
-   **Output Directory** - Enter the path to the directory where the support tool writes the support information file. The default is `${FILEDRIVEHOME}/support` where `${FILEDRIVEHOME}` represents the
    SecureTransport installation directory.
-   **Collect ...** - Select the check box for each category of information that the support tool saves. For the log information, specify the period by selecting a predefined period for the list or specifying the start and end dates and times. The information available for collection is different on {{< SecureTransport/componentshortname >}} Server and {{< SecureTransport/componentshortname >}} Edge.
-   **Collect files and folders** - Select this to specify that the support tool save the files listed in the **Files and Folder to Save** table.
-   **Files and Folders to Save** - If **Collect files and folders** is selected, the support tool saves the contents of the files listed in this table in the support information file.  
    To add a file, click **Add File or Folder**, type the file or folder name in the File/Folder Name column, and click the Save icon (![Save](/Images/SecureTransport/SaveIcon_13x13.png)) in the right column. To remove files from the list, select the files in left column, and click **Remove**. To change a file or folder name in the list, click the Edit icon (![Edit](/Images/SecureTransport/EditIcon_12x13.png)) in the right column, type the file or folder name in the File/Folder Name column, and click the Save icon (![Save](/Images/SecureTransport/SaveIcon_13x13.png)).

<span id="Exclude"></span>

## Exclude files

The support tool does not save the contents of files or folders whose names are listed in the `SupportTool.ExcludeFilesFoldersList` server configuration parameter. By default, the excluded names are `certs` and
`passwd`.

To add or remove names from the excluded files list, see <a href="../../c_st_serverconfiguration/t_st_serverconfigurationparameters#Change" class="MCXref xref">Change a parameter value</a>.
