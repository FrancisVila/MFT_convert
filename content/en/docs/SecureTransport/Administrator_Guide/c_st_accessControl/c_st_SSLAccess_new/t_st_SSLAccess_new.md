{
    "title": "Manage SSL\u00a0access",
    "linkTitle": "Manage SSL\u00a0access",
    "weight": "220"
}Use the *Secure Socket Layer* page to add, enable, disable, reorder, or delete SSL encryption entries.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">To enable or disable SSL for HTTP transfers, you must modify the <strong>HTTP Server</strong> settings on the <em>Server Control</em> page. If you select <strong>Enable HTTPS</strong>, <span>SecureTransport</span> uses SSL with the HTTP connections. If you do not select <strong>Enable HTTPS</strong>, <span>SecureTransport</span> does not use SSL with HTTP connections. For more information, see <a href="t_st_httpserver.htm#top">Manage the HTTP server</a>.         </td>
      </tr>
</table>

The following topics provide how-to instructions for managing SSL access:

-   [Add an SSL users encryption entry](#add)
-   [Enable or disable an encryption entry](#enable_encrypt)
-   [Edit an encryption entry](#edit)
-   [Reorder encryption entries](#reorder)
-   [Delete an encryption entry](#delete)

## <span id="Add"></span>Add an SSL users encryption entry

You can define SSL encryption settings based on user classes.

1.  Select **Access > Secure Socket Layer**.  
    The *Secure Socket Layer* page is displayed.
2.  At *SSL Encryption Entries*, click **New Entry**. A new line is displayed in the *User Classes List*.
3.  Select a **User Class**. The user class must already be defined in the *User Classes* page. Asterisk (`*`) means all users.
4.  Select an **Encryption** option for the user class. The two option types are: `Required` and `Optional`.
5.  Click the Save icon (![Save](SaveIcon_13x13.png)) in the **Edit** column.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">When using certificate-based authentication on Windows with real users, add the real user to the password vault to log in without being prompted for a password. For more information, see <a href="../../../c_st_advancedaccountadministration/c_st_systemusers/c_st_real_users">Real users</a>.         </td>
      </tr>
</table>

## <span id="Enable_encrypt"></span>Enable or disable an encryption entry

Use the following procedure to enable or disable an encryption entry.

1.  Select **Access > Secure Socket Layer**.  
    The *Secure Socket Layer* page is displayed.
2.  Under *SSL Encryption Entries*, select the check box for each entry to modify.
3.  Click **Enable** or **Disable**.  
    The icons in the **User Class** column change to indicate the status of the entries.

## <span id="Edit"></span>Edit an encryption entry

Use the following procedure to edit an encryption entry.

1.  Select **Access > Secure Socket Layer**.  
    The *Secure Socket Layer* page is displayed.
2.  Under *SSL Encryption Entries*, click the Edit icon (![Edit](SaveIcon_13x13.png)) in the **Edit** column for the entry to edit.
3.  Make the required changes to the fields in the entry.
4.  Click the Save icon (![Save](SaveIcon_13x13.png)) in the **Edit** column.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">To cancel an add operation, select <strong>Access &gt; Secure Socket Layer</strong> again.         </td>
      </tr>
</table>

## <span id="Reorder"></span>Reorder encryption entries

SecureTransport applies the first entry in the *SSL Encryption Entries* that matched the user class of the user. So, for SecureTransport to use them, you want the more specific entries before the more general entries in the list.

1.  Select **Access > Secure Socket Layer**.  
    The *Secure Socket Layer* page is displayed.
2.  Under *SSL Encryption Entries*, click **Reorder**.  
    Up and down arrows are displayed in a column before the **User Class** column in the *SSL Encryption Entries*.
3.  Drag the rows of the *SSL Encryption Entries* to the required order.
4.  Click **Save Order**.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">To cancel an edit operation, select <strong>Access &gt; Secure Socket Layer</strong> again.         </td>
      </tr>
</table>

## <span id="Delete"></span>Delete an encryption entry

Use the following procedure to delete an encryption entry.

1.  Select **Access > Secure Socket Layer**.  
    The *Secure Socket Layer* page is displayed.
2.  Under *SSL Encryption Entries*, select the check box for each entry to delete.
3.  Click **Delete**.
4.  Click **OK** in the confirmation dialog box.

 

**Related topic:**

-   [SSL and SSH](../c_st_ssl_ssh_new)
