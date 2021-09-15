{
    "title": "Configure the support tool",
    "linkTitle": "Configure the support tool",
    "weight": "170"
}Use the *Support Tool Configuration* page to specify the information that the support tool saves in the support information file and where it saves the file.

1.  Select **Operations > Support Tool** to display the *Support Tool Configuration* page.
2.  Specify the fields listed below.
3.  Click **Save**.  
    SecureTransport saves the configuration and replicates it to all nodes in a Server cluster or to all synchronized Edge servers.
4.  (AIX only) If you selected or deselected the **Collect TM thread dump** or **Collect TM heap dump** option, restart the Transaction Manager on all clustered SecureTransport Servers or all synchronized SecureTransport Edge servers using the `stop_tm` and `start_tm` commands in `<FILEDRIVEHOME>/bin`.
5.  Under *Files and Folders to Save*, add, remove, or edit the path names of files and folders to include in the support tool information file. Relative path names are relative to `<FILEDRIVEHOME>`. You can also add absolute path names.  
    SecureTransport saves each the change and replicates it to all nodes in a SecureTransport Server cluster or to all synchronized SecureTransport Edge servers.

The following topics describe the support tool fields and how-to instructions for excluding files:

-   [Fields](#fields)
-   [Exclude files](#exclude)

**Related topics:**

-   [Add custom information to the support information file](../t_st_customizesupporttool)
-   [Run the support tool](../t_st_runsupporttool)

## <span id="Fields"></span>Fields

This topic includes information about the fields you must complete.

-   **Support Access Code** - The support tool includes the value of this field in the name of the support information file. Enter the Support Access Code for the support contact that covers this system. Axway Global Support uses the code in the file name to make sure the file is handled correctly.
-   **Output Directory** - Enter the path to the directory where the support tool writes the support information file. The default is `${FILEDRIVEHOME}/support` where `${FILEDRIVEHOME}` represents the
    SecureTransport installation directory.
-   **Collect ...** - Select the check box for each category of information that the support tool saves. For the log information, specify the period by selecting a predefined period for the list or specifying the start and end dates and times. The information available for collection is different on SecureTransport Server and SecureTransport Edge.
-   **Collect files and folders** - Select this to specify that the support tool save the files listed in the **Files and Folder to Save** table.
-   **Files and Folders to Save** - If **Collect files and folders** is selected, the support tool saves the contents of the files listed in this table in the support information file.  
    To add a file, click **Add File or Folder**, type the file or folder name in the File/Folder Name column, and click the Save icon (![Save](SaveIcon_13x13.png)) in the right column. To remove files from the list, select the files in left column, and click **Remove**. To change a file or folder name in the list, click the Edit icon (![Edit](SaveIcon_13x13.png)) in the right column, type the file or folder name in the File/Folder Name column, and click the Save icon (![Save](SaveIcon_13x13.png)).

## <span id="Exclude"></span>Exclude files

The support tool does not save the contents of files or folders whose names are listed in the `SupportTool.ExcludeFilesFoldersList` server configuration parameter. By default, the excluded names are `certs` and
`passwd`.

To add or remove names from the excluded files list, see [Change a parameter value](../../c_st_serverconfiguration/t_st_serverconfigurationparameters).
