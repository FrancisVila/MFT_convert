{
    "title": "Manage filesystem restrictions",
    "linkTitle": "Manage filesystem restrictions",
    "weight": "230"
}Use the *Filesystem* pane of the *Restrictions* page to add, enable, disable, or delete filesystem restriction entries.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top"><span>SecureTransport</span> applies filesystem restrictions starting with the last in the list and proceeding to the first. When you create two or more restrictions with the same action and that apply to the same users and the same path, make sure to put an entry with a more general path above one with a more specific path.         </td>
      </tr>
</table>

The following topics provide how-to instructions for managing filesystem restrictions:

-   [Add a filesystem restriction](#add)
-   [Enable or disable a filesystem restriction](#enable)
-   [Edit a filesystem restriction](#edit)
-   [Delete a filesystem restriction](#delete)
-   [Example filesystem restriction](#example)

## <span id="Add"></span>Add a filesystem restriction

Use the following procedure to add a filesystem restrictions.

Select **Access** **&gt;** **Restrictions**.

Click the **Filesystem** tab.  
The *Filesystem Restrictions* pane is displayed.

Click **New Entry**. A new line is displayed in the list.

Select an **Action** from the list. For description of the options, see [Filesystem restrictions](..//securetransport/administrator_guide/c_st_accesscontrol/c_st_filesystemrestrictions).

In the **Allowed** field, select **No** to deny the action or **Yes** to allow it.

In the **Class** field, select a user class. Asterisk (`*`) means all users.

In the **Path** field, type the path of the directory for which the restriction applies.  
Specify the path relative to the file system root for the user. For a real user, the file system root is the operating system root. For a virtual user, the file system root is the user's home directory.  
On Windows, you must use a POSIX path. Specify drives as `/drives/c` and `/drives/d` instead of `C:\` and `D:\`.  
You can use UNIX-style wildcard characters to apply restrictions for an entire directory. Path entries must contain both a forward slash and the asterisk wildcard (`/*)` to allow or deny everything. For example, on Windows, to prevent deletion of the contents of the `C:\temp` directory, specify `/drives/C/temp/*` as the path. In this example, specifying `/drives/C/temp` only prevents the directory itself from being deleted, not its contents.  
With SecureTransport version 5.4, two new parameters are introduced with Filesystem restrictions: `{s}` and `{i}`. These two options are used as prefixes to regular expressions and their purpose is to match the Path in case sensitive (`{s}`)or case insensitive (`{i}`) manner.

-   `{i}` matches Path in an expression in a case-insensitive fashion.  
    Example use: Delete a File action of files that match the expression `{i}/*.xml ` will delete any xml file, regardless of filename extension case: whether it is XML, xml or XmL.  
-   `{s}` matches all files in an expression in a case-sensitive fashion.  
    Example use: Delete a File action of files that match the expression `{s}/*.TXT` will only delete files with TXT extension (uppercase, as defined in the expression) and will not delete files with .txt extension (lowercase, not defined in the expression).

Click the Save icon (![Save](SaveIcon_13x13.png)) in the **Edit** column.  
SecureTransport adds the new entry at the top of the list. The status of a new entry is set to Disabled.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">Along with the two regular expression prefixes, a dedicated configuration option is introduced: <code>Restrictions.pathIgnoreCases</code>. When it is set to <code>false</code>, all expressions that do not use the <code>{i}</code> or <code>{s}</code> prefixes will match the path in case-sensitive manner. Respectively, when set to <code>true</code>, all expressions without  the <code>{i}</code> or <code>{s}</code> prefixes will match in case-insensitive manner.<br/>         </td>
      </tr>
</table>

## <span id="Enable"></span>Enable or disable a filesystem restriction

Use the following procedure to enable or disable a filesystem restriction.

1.  Select **Access** **&gt;** **Restrictions**.
2.  Click the **Filesystem** tab.  
    The *Filesystem Restrictions* pane is displayed.
3.  Select the check box for each entry to modify.
4.  Click **Enable** or **Disable**.  
    The icons in the **Action** column change to indicate the status of the classes.

## <span id="Edit"></span>Edit a filesystem restriction

Use the following procedure to edit a filesystem restriction.

1.  Select **Access** **&gt;** **Restrictions**.
2.  Click the **Filesystem** tab.  
    The *Filesystem Restrictions* pane is displayed.
3.  Click the Edit icon (![Edit](SaveIcon_13x13.png)) in the **Edit** column for the entry to edit.
4.  Make the required changes to the fields.
5.  Click the Save icon (![Save](SaveIcon_13x13.png)) in the **Edit** column.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">To cancel an add operation, select <strong>Access &gt; Restrictions</strong> again.         </td>
      </tr>
</table>

## <span id="Delete"></span>Delete a filesystem restriction

Use the following procedure to delete a filesystem restriction.

1.  Select **Access** **&gt;** **Restrictions**.
2.  Click the **Filesystem** tab.  
    The *Filesystem Restrictions* pane is displayed.
3.  Select the check box for each entry to delete.
4.  Click **Delete**.
5.  Click **OK** in the confirmation dialog box.

## <span id="Example"></span>Example filesystem restriction

The following example supplies some examples for Filesystem restrictions.

-   The first condition defines access to the `/f1` folder only.
-   The second condition restricts access to the root folder.
-   The third condition deletes all entirely lowercase TXT files in the `/f1/Files` folder and omits all other case variations (for example,.TxT and .TXT files will not be deleted with this expression). Also, in case there is a `/f1/files` path, its content will remain untouched by this expression since it exactly matches the `/f1/Files` path.
-   The fourth condition deletes all XML files in the `/f1` folder (.XML, .xml, .XmL, etc.).

  