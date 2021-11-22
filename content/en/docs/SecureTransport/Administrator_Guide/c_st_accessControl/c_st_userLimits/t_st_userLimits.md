{
    "title": "Manage user limits",
    "linkTitle": "Manage user limits",
    "weight": "270"
}Use the *User Limits* pane of the *Access Rules* page to add, enable, disable, reorder, or delete user limits. Using user limits, you can set the maximum number of users who can log in to {{< SecureTransport/componentshortname  >}} for each user class. You can also specify the days and time the limit is in effect.

The following topics provide how-to instructions for managing user limits:

-   <a href="#Add" class="MCXref xref">Add a user limit</a>
-   <a href="#Enable" class="MCXref xref">Enable or disable a user limit</a>
-   <a href="#Edit" class="MCXref xref">Edit a user limit</a>
-   <a href="#Delete" class="MCXref xref">Delete a user limit</a>

<span id="Add"></span>

## Add a user limit

Use the following procedure to add a user limit.

1.  Select **Access > Access Rules**.
2.  Click the **User Limits** tab.  
    The *User Limits* pane is displayed.
3.  Click **New User Limit**. The *New User Limit* page is displayed.
4.  Select a **User Class**. Asterisk (`*`) means all users.
5.  Type the maximum number of concurrent users for that class.
6.  Under *Access Restrictions*, to specify the start and end times for {{< SecureTransport/componentshortname >}} to apply the restriction, enter the time in 24-hour format in the **From** and **To** fields. To specify that {{< SecureTransport/componentshortname >}} apply the restriction all the time, leave the **From** and **To** fields empty.
7.  Under *Access Restrictions*, to specify the days of the week for {{< SecureTransport/componentshortname >}} to apply the restriction, click **Specify Days** and select the days. To specify that {{< SecureTransport/componentshortname >}} apply the restriction on all days, click **Restrict All Days**.
8.  In the field provided, enter a message to be displayed when a user tries to connect to the FTP server and is denied access due to this user limits restriction.
9.  Click **Save.**  
    The *User Limits* pane of the *Access Rules* page is displayed with the new user limit listed. The status of a new user limit is set to Disabled.

<span id="Enable"></span>

## Enable or disable a user limit

Use the following procedure to enable or disable a user limit.

1.  Select **Access > Access Rules**.
2.  Click the **User Limits** tab.  
    The *User Limits* pane is displayed.
3.  Select the check box for each entry to modify.
4.  Click **Enable** or **Disable**.  
    The icons in the **User Class** column change to indicate the status of the classes.  
    The *User Access* page is displayed.

<span id="Edit"></span>

## Edit a user limit

Use the following procedure to edit a user limit.

1.  Select **Access > Access Rules**.
2.  Click the **User Limits** tab.  
    The *User Limits* pane is displayed.
3.  Click the Edit icon (![Edit](/Images/SecureTransport/EditIcon_12x13.png)) in the **Edit** column for the entry to edit. The *User Limit* page is displayed.
4.  Make the required changes in the fields.
5.  Click **Save.**  
    The *User Limits* pane of the *Access Rules* page is displayed with the user limit updated.

<span id="Delete"></span>

## Delete a user limit

Use the following procedure to delete a user limit.

1.  Select **Access > Access Rules**.
2.  Click the **User Limits** tab.  
    The *User Limits* pane is displayed.
3.  Select the check box for each user limit to delete.
4.  Click **Delete**.
5.  Click **OK** in the confirmation dialog box.
