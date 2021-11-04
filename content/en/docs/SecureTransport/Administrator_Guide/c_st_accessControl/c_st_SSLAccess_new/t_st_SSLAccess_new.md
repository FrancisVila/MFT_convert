{
    "title": "Manage SSL access",
    "linkTitle": "Manage SSL access",
    "weight": "210"
}Use the *Secure Socket Layer* page to add, enable, disable, reorder, or delete SSL encryption entries.

> **Note:**
>
> To enable or disable SSL for HTTP transfers, you must modify the HTTP Server settings on the Server Control page. If you select Enable HTTPS, SecureTransport uses SSL with the HTTP connections. If you do not select Enable HTTPS, SecureTransport does not use SSL with HTTP connections. For more information, see Manage the HTTP server.

The following topics provide how-to instructions for managing SSL access:

-   <a href="#Add" class="MCXref xref">Add an SSL users encryption entry</a>
-   <a href="#Enable_encrypt" class="MCXref xref">Enable or disable an encryption entry</a>
-   <a href="#Edit" class="MCXref xref">Edit an encryption entry</a>
-   <a href="#Reorder" class="MCXref xref">Reorder encryption entries</a>
-   <a href="#Delete" class="MCXref xref">Delete an encryption entry</a>

<span id="Add"></span>

## Add an SSL users encryption entry

You can define SSL encryption settings based on user classes.

1.  Select **Access > Secure Socket Layer**.  
    The *Secure Socket Layer* page is displayed.
2.  At *SSL Encryption Entries*, click **New Entry**. A new line is displayed in the *User Classes List*.
3.  Select a **User Class**. The user class must already be defined in the *User Classes* page. Asterisk (`*`) means all users.
4.  Select an **Encryption** option for the user class. The two option types are: `Required` and `Optional`.
5.  Click the Save icon (![Save](/Images/SecureTransport/SaveIcon_13x13.png)) in the **Edit** column.

> **Note:**
>
> To cancel an add operation, select Access &gt; Secure Socket Layer again.

<span id="Enable_encrypt"></span>

## Enable or disable an encryption entry

Use the following procedure to enable or disable an encryption entry.

1.  Select **Access > Secure Socket Layer**.  
    The *Secure Socket Layer* page is displayed.
2.  Under *SSL Encryption Entries*, select the check box for each entry to modify.
3.  Click **Enable** or **Disable**.  
    The icons in the **User Class** column change to indicate the status of the entries.

<span id="Edit"></span>

## Edit an encryption entry

Use the following procedure to edit an encryption entry.

1.  Select **Access > Secure Socket Layer**.  
    The *Secure Socket Layer* page is displayed.
2.  Under *SSL Encryption Entries*, click the Edit icon (![Edit](/Images/SecureTransport/EditIcon_12x13.png)) in the **Edit** column for the entry to edit.
3.  Make the required changes to the fields in the entry.
4.  Click the Save icon (![Save](/Images/SecureTransport/SaveIcon_13x13.png)) in the **Edit** column.

> **Note:**
>
> To cancel an edit operation, select Access &gt; Secure Socket Layer again.

<span id="Reorder"></span>

## Reorder encryption entries

<span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> applies the first entry in the *SSL Encryption Entries* that matched the user class of the user. So, for <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> to use them, you want the more specific entries before the more general entries in the list.

1.  Select **Access > Secure Socket Layer**.  
    The *Secure Socket Layer* page is displayed.
2.  Under *SSL Encryption Entries*, click **Reorder**.  
    Up and down arrows are displayed in a column before the **User Class** column in the *SSL Encryption Entries*.
3.  Drag the rows of the *SSL Encryption Entries* to the required order.
4.  Click **Save Order**.

> **Note:**
>
> To cancel a reorder operation, select Access &gt; Secure Socket Layer again.

<span id="Delete"></span>

## Delete an encryption entry

Use the following procedure to delete an encryption entry.

1.  Select **Access > Secure Socket Layer**.  
    The *Secure Socket Layer* page is displayed.
2.  Under *SSL Encryption Entries*, select the check box for each entry to delete.
3.  Click **Delete**.
4.  Click **OK** in the confirmation dialog box.

 

**Related topic:**

-   <a href="../c_st_ssl_ssh_new" class="MCXref xref">SSL and SSH</a>
