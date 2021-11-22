{
    "title": "Manage transfer sites",
    "linkTitle": "Manage transfer sites",
    "weight": "280"
}Use the *Transfer Sites* page to create, edit, and delete transfer sites.

The following topics provide how-to instructions for managing transfer sites:

-   <a href="#Create" class="MCXref xref">Create a transfer site</a>
-   <a href="#Edit" class="MCXref xref">Edit a transfer site</a>
-   <a href="#Delete" class="MCXref xref">Delete a transfer site</a>

<span id="Create"></span>

## Create a transfer site

This topic provides a general procedure for creating a transfer site for an account. All supported protocols require custom settings. For details, see the reference topic for each protocol.

1.  Select **Accounts > User Accounts**. The *User Accounts* page is displayed.
2.  Click the name of the account to which you want to add a transfer site.  
    The *Account Settings* page for that account is displayed.
3.  Click **Transfer Sites**.  
    The *Transfer Sites* page is displayed.
4.  Click **Add New.**  
    The *Add Transfer Site* page is displayed.
5.  In the **Site Name** box, enter a unique name for the transfer site.
6.  The Site Name is unique per account. Two sites could have the same names if they are associated with different accounts.
7.  Select an **Site Type**. Use this parameter to differentiate between sites that transfer files internally and those that transfer files between partners. Choose from the following:
    -   **Unspecified** – Default value. All transfer sites created using previous versions of {{< SecureTransport/componentshortname >}} have this value.
    -   **Internal** – Transfers for this site occur within a single organization.
    -   **Partner** – Transfers for this site occur between organizations.
8.  Select the protocol that the transfer site uses for file transfers. The supported protocols are AS2, FTP(S), HTTP(S), SSH (SFTP and SCP), PeSIT, Connect:Direct, Folder Monitor, System to Human, Generic-HTTP(S), and SharePoint.
9.  By default, the AS2 protocol settings are displayed first. This example displays the settings for creating an FTP(S) transfer site.
10. Edit the custom options depending on the selected transfer protocol.
11. Click **Add**  
    The transfer site is added to the list of transfer sites available to the current account.

<span id="Edit"></span>

## Edit a transfer site

1.  Select **Accounts > User Accounts**. The *User Accounts* page is displayed.
2.  Click the name of the account that owns the transfer site to edit.
3.  Click the **Transfer Sites** tab.
4.  Click the name of the transfer site to edit.
5.  The *Edit Transfer Site* page is displayed.
6.  Edit the desired settings for the transfer site.
7.  Click **Save**.

<span id="Delete"></span>

## Delete a transfer site

1.  Select **Accounts > User Accounts**. The *User Accounts* page is displayed.
2.  Click the name of the account that owns the transfer site to delete.
3.  Click the **Transfer Sites** tab.
4.  Select the checkboxes next to the names of the transfer sites to delete.
5.  Click **Delete**.

**Related topics:**

-   <a href="../r_st_as2transfersites" class="MCXref xref">AS2 transfer sites</a>
-   <a href="../r_st_connectdirecttransfersites" class="MCXref xref">Connect:Direct transfer sites</a>
-   <a href="../r_st_foldermonitortransfersites" class="MCXref xref">Folder Monitor transfer sites</a>
-   <a href="../r_st_fileservicesinterfaceprotocoltransfersites" class="MCXref xref">File services interface transfer sites</a>
-   <a href="../transfersites-ftp" class="MCXref xref">FTP(S) transfer sites</a>
-   <a href="../transfersites-http" class="MCXref xref">HTTP(S) transfer sites</a>
-   <a href="../transfersites-pesit" class="MCXref xref">PeSIT transfer sites</a>
-   <a href="../transfersites-s2h" class="MCXref xref">System to Human transfer sites</a>
-   <a href="../transfersites-ssh" class="MCXref xref">SSH transfer sites</a>
-   <a href="../transfersites-generichttp" class="MCXref xref">Generic HTTP transfer sites</a>
