{
    "title": "Manage files and folders",
    "linkTitle": "Manage files and folders",
    "weight": "50"
}You perform all file management and folder sharing actions on *Your Files* page. The layout of *Your files* page is separated into a left-hand panel, which contains your folder tree and the right-hand panel which displays the contents of a selected folder. At first, the left panel only includes the folder 'Your files' folder, which is the top-level folder. All action, like creating child folders, adding files, and sharing selected folders occurs in this folder.

This section covers the following subtopics:

-   [Create folders](#Create)
-   [Upload files](#Upload)
-   [View and select files and folders](#View)
-   [Share folders](#Share)
-   [Manage files: perform actions](#Manage)

<span id="Create"></span>

## Create folders

When you create a folder, it is always a subfolder to the parent 'Your files' folder. You can also create subfolders to subfolders, which allows you to have a more complex structure.

To create a folder, click *Your Files* and, if needed, navigate to the folder you want to create a subfolder to*.*

1.  In the right panel, click the *Actions* menu and select **Create folder**. The *Create folder* box opens.
2.  Enter the folder name and click **Create**.

The new folder is created and displayed on the *Your files* panel and a success message is displayed.

<span id="Upload"></span>

## Upload files

You upload files to the folders and subfolders you select. You cannot upload folders: instead you must create these folders in the and perform your uploads after that.

To upload files to ST Web Client you can either drag and drop the files in *Your Files* or follow the process after clicking the **Upload** button.

### Upload using drag & drop

To upload files using drag and drop:

1.  From a folder on your computer, select one or more files to upload.
    Press **Ctrl** or **Shift** on your keyboard and with your mouse left-click to select multiple files.
2.  Drag and drop the selected file(s) on the *Your files* pane: your file gets uploaded to the chosen folder.

Depending on the filesize and your Internet connection, it might take some while to upload your files. You can track the status of the files in the *Uploads* pane.

### Upload files using the button

To upload files with the **Upload** button, follow the conventional process:

1.  On the *Your files* pane, click **Upload**.
2.  Select one or more files to upload.
    Press **Ctrl** or **Shift** on your keyboard and with your mouse left-click to select multiple files.
3.  Click **Open**: your file(s) gets uploaded to the chosen folder.

You can track the status of the files in the *Uploads* pane. For information on how to manage and monitor file uploads, see <a href="022-managing_uploads" class="MCXref xref">Manage uploads</a>.

<span id="View"></span>

## View and select files and folders

When you have added folders and file content, you can view the tree structure of your space. However, collaborators who share folders with you, also contribute to this structure. For example, the following screen displays a fairly rich structure:

on the Left panel view you can see that:

-   You have 7 alphabetically ordered folders: starting with /documents and ending with /temporary01.
-   One of these folders is shared (by you) with other collaborators: /empty\_ren.
-   One of these folders is shared (with you) by another collaborator: /SharedTest1 is the folder and desi1@st.com is the collaborator.

<img src="/Images/SecureTransport/WC_view-YourFiles.png" class="maxWidth" />

In the right-hand area you can see:

-   all 6 items in 'Your Files' folder: the 4 folders followed by the 2 files.
-   the timestamp of last modification to each item, plus the size of files. does not display size of subfolders. At the bottom right you can see that the total number of items plus the total size of the two files: 413.52 KB.
-   your currently selected folder is /documents: this means that it is on focus for sharing or performing other actions.

### Select and open folders

**Important** To select a folder, either click it in the left panel or click-to-select it from *Your Files* area. Note that when you click the link on a folder, you open it.

If you want to select a folder, you must click anywhere on its row, but not the link. Once selected, you can share this folder or perform actions like rename, view details or delete it.

### Select and download files

With files it is similar: when you click the file link, you download it. If you want to select a file, you must click anywhere on its row, but not the link. Once selected, you can perform actions like move the file, view its details or delete it.

<span id="Share"></span>

## Share folders

> **Note:**
>
> If the Share folders feature is not available, contact your system administrator.

In  you share folders and not files alone. In other words: if you want to share a single file, you must put it in a dedicated folder which you will be sharing with others.

The concept of sharing folders with other users is to authorize users to access files in the folders (or subfolders) you select. Depending on your system configuration, you can share info with Address Book contacts and / or external contacts. Contact your SecureTransport administrator for more info.

The user interface allows you to share one folder at a time. To share a folder:

1.  On the *Your files* page, select a folder to share.
2.  Click **Share**. The *Share* panel is displayed.  
    <img src="/Images/SecureTransport/WC_Share_folder.png" class="maxWidth" alt="ST Web Client Shared window" />
3.  Enter valid email address or group name in the *People:* field. You can add additional valid user email addresses one at time. You can also select the Address Book to add people or groups. See <a href="021-address_book" class="MCXref xref">Address Book</a>.
4.  (Optional) Select **Allow people to view collaborators** to show a list of collaborators.
5.  (Optional) Select **Send notification to collaborators** to send email notifications to the collaborators.
6.  (Optional) Select **Notify me when a file is uploaded** to be notified when a file is uploaded to the shared folder.
7.  Determine the Access level of your collaborators:
    -   **Download only -** collaborators can only download folder contents
    -   **Download and upload** - collaborators can download folder content and upload content to that same folder
    -   **Download, upload, and overwrite files** - collaborators can download , upload, rename and delete folder content
8.  Click **Share**: the folder is shared with your selected collaborators.

### Edit share options or unshare folder

You can change any of the shared folder options, including access level and notifications. Of course, you can also unshare your folder with some or all collaborators.

To edit shared folder options, select the respective folder and follow the steps above to perform the needed changes. When done, click **Share** to apply your changes.

To unshare a folder:

1.  From the *Your files* pane, select the shared folder to unshare.
2.  Click **Share**.The *Share* panel opens.
3.  Click the **Unshare** button. The selected folder is now unshared, the user options are removed and the *Your files* panel is displayed.

<span id="Manage"></span>

## Manage files: perform actions

You can download, rename, move, view details of files, and delete them. To perform any action to a file, you must navigate-to-select your file(s) and either: click Actions or perform a left-button click with your mouse. Either way, the Actions menu appears on display:

<img src="/Images/SecureTransport/WC_files_actions.png" class="maxWidth" />

-   Download a file: either click the file link (the process starts right away) or download it using the menu.
-   Move a file: navigate-to-select the respective file, and click **Move** on the *Actions* menu. Then use the interface to navigate-to-select the destination folder and click **Move** in the box.

![](/Images/SecureTransport/WC_Move_files_300x265.png)

-   You will notice the *source* folder (/documents) is disabled for moving, so as shown on the screen, you can move it to the 'Your Files' parent folder or any of its enabled subfolders.  
    **Tip** You can multi-select files to move several files at once.  
-   Rename a file: click **Rename** on the *Actions* menu and simply enter the new file name.
-   View details of a file: click **View Details** to observe details for the selected file. These include the date and time the file was created, last modified and accessed, as well as the size, owner, user permissions on the file, and the file's CoreID. You can also see the file's MD5 checksum which you can use to verify its authenticity and integrity.
-   Delete a file: click **Delete** on the *Actions* menu or simply press Del on your keyboard to remove the selected file(s).

 

next topic: [Address Book](021-address_book)
