{
    "title": "Manage user and group access",
    "linkTitle": "Manage user and group access",
    "weight": "280"
}Use the *Denied Users* pane and the *Denied Groups* pane of the *Access Rules* page to add and remove user and groups that {{< SecureTransport/componentshortname  >}} prevents from connecting to the FTP and HTTP servers.

Every group listed as a denied group must be defined at the
operating system level so that {{< SecureTransport/componentshortname  >}} can determine the
group name from the GID in the user account.

The following topics provide how-to instructions for managing user and group access:

-   <a href="#Add" class="MCXref xref">Add a user or group to the denied list</a>
-   <a href="#Remove" class="MCXref xref">Remove users or groups from the denied list</a>

<span id="Add"></span>

## Add a user or group to the denied list

Use the following procedure to add a user or group to the denied list.

1.  Select **Access > Access Rules**.
2.  Click the **Denied Users** tab or the **Denied Groups** tab.  
    The *Denied Users* or *Denied Groups* pane is displayed.
3.  Enter in the field to the left of the **Add** button a user name for denied users or a group name or group ID (GID) for denied groups.
4.  Click **Add**.
5.  The user or group is added to the denied list.

<span id="Remove"></span>

## Remove users or groups from the denied list

Use the following procedure to remove users or groups from the denied list.

1.  Select **Access > Access Rules**.
2.  Click the **Denied Users** tab or the **Denied Groups** tab.  
    The *Denied Users* or *Denied Groups* pane is displayed.
3.  Select the check box for each user or group to remove.
4.  Click **Remove**.
5.  Click **OK** in the confirmation dialog box.
