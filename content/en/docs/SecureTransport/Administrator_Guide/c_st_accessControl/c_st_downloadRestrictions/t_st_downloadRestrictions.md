{
    "title": "Manage download restrictions",
    "linkTitle": "Manage download restrictions",
    "weight": "240"
}Use the *Download* pane of the *Restrictions* page to add, enable, disable, reorder, or delete download restriction entries.

The following topics provide how-to instructions for managing download restrictions:

-   [Add a download restriction](#Add)
-   [Enable or disable a download restriction](#Enable)
-   [Edit a download restriction](#Edit)
-   [Reorder download restrictions](#Reorder)
-   [Delete a download restriction](#Delete)

<span id="Add"></span>

## Add a download restriction

Use the following procedure to add a download restriction.

1.  Select **Access > Restrictions**.
2.  Click the **Download** tab.  
    The *Download Restrictions* pane is displayed.
3.  Click **New Entry**. A new line is displayed in the list.
4.  Complete the fields in the following table.  
    <table>
       <thead>
          <tr>
    <th class="HeadE-Column1-Header1">Field         </th>
    <th class="HeadD-Column1-Header1">Description         </th>
          </tr>
       </thead>
       <tbody>
          <tr>
             <td><strong>Path</strong>         </td>
             <td><p>The file name or directory you want to apply a restriction to.</p>
    <p>Specify the path relative to the file system root for the user. For a real user, the file system root is the operating system root. For a virtual user, the file system root is the user's home directory.</p>
    <p>On Windows, you must use a POSIX path. Specify drives as <code>/drives/c</code> and <code>/drives/d</code> instead of <code>C:\</code> and <code>D:\</code>.</p>
    <p>You can use UNIX-style wildcard characters to apply restrictions for an entire directory and its subdirectories. Path entries must contain both a forward slash and the asterisk wildcard (<code>/*)</code> to deny or allow everything. For example, on Windows, to prevent deletion of the contents of the <code>C:\temp</code> directory, specify <code>/drives/C/temp/*</code> as the path. In this example, specifying <code>/drives/C/temp</code> applies the restriction only to the directory itself, not its contents.</p>
    <p>With {{< SecureTransport/componentshortname  >}} version 5.4, two new parameters are introduced with Filesystem restrictions: <code>{s}</code> and <code>{i}</code>. These two options are used as prefixes to regular expressions and their purpose is to match the Path in case sensitive (<code>{s}</code>)or case insensitive (<code>{i}</code>) manner.</p>
    <ul>
    <li><code>{i}</code> matches Path in an expression in a case-insensitive fashion.<br />
    Example use: Access to path that matches the expression <code>{i}/*.xml</code> will allow the user to download any xml file, regardless of filename extension case: whether it is XML, xml or XmL.<br />
    </li>
    <li><code>{s}</code> matches all files in an expression in a case-sensitive fashion.<br />
    Example use: Access to path that matches the expression <code>{s}/*.TXT</code> will allow the user to download only files with TXT extension (uppercase, as defined in the expression) and will not be able to download files with .txt extension (lowercase, not defined in the expression).</li>
    </ul>
    Along with the two regular expression prefixes, a dedicated configuration option is introduced: <code>Restrictions.pathIgnoreCases</code>. When it is set to <code>false</code>, all expressions that do not use the <code>{i}</code> or <code>{s}</code> prefixes will match the path in case-sensitive manner. Respectively, when set to <code>true</code>, all expressions without the <code>{i}</code> or <code>{s}</code> prefixes will match in case-insensitive manner.         </td>
          </tr>
          <tr>
             <td><strong>Allowed</strong>         </td>
             <td>Select <strong>Yes</strong> or <strong>No</strong> based on whether you want to restrict downloading.         </td>
          </tr>
          <tr>
             <td><strong>User Class</strong>         </td>
             <td>Select a user class. Asterisk (<code>*</code>) means all users.         </td>
          </tr>
       </tbody>
    </table>
5.  Click the Save icon (![Save](/Images/SecureTransport/SaveIcon_13x13.png)) in the **Edit** column.  
    The status of a new entry is set to Disabled.

> **Note:**
>
> To cancel an add operation, select Access &gt; Restrictions again.

<span id="Enable"></span>

## Enable or disable a download restriction

Use the following procedure to enable or disable a download restriction.

1.  Select **Access** **&gt;** **Restrictions**.
2.  Click the **Download** tab.  
    The *Download Restrictions* pane is displayed.
3.  Select the check box for each entry to modify.
4.  Click **Enable** or **Disable**.  
    The icons in the **Path** column change to indicate the status of the classes.

<span id="Edit"></span>

## Edit a download restriction

Use the following procedure to edit a download restriction.

1.  Select **Access** **&gt;** **Restrictions**.
2.  Click the **Download** tab.  
    The *Download Restrictions* pane is displayed.
3.  Click the Edit icon (![Edit](/Images/SecureTransport/EditIcon_12x13.png)) in the **Edit** column for the entry to edit.
4.  Make the required changes in the fields.
5.  Click the Save icon (![Save](/Images/SecureTransport/SaveIcon_13x13.png)) in the **Edit** column.

> **Note:**
>
> To cancel an edit operation, select Access &gt; Restrictions again.

<span id="Reorder"></span>

## Reorder download restrictions

Use the following procedure to reorder download restrictions.

1.  Select **Access** **&gt;** **Restrictions**.
2.  Click the **Download** tab.  
    The *Download Restrictions* pane is displayed.
3.  Click **Reorder**.  
    Up and down arrows are displayed in a column before the **Path** column.
4.  Drag the rows of the entries to the required order.
5.  Click **Save Order**.

> **Note:**
>
> To cancel a reorder operation, select Access &gt; Restrictions again.

<span id="Delete"></span>

## Delete a download restriction

Use the following procedure to delete a download restriction.

1.  Select **Access** **&gt;** **Restrictions**.
2.  Click the **Download** tab.  
    The *Download Restrictions* pane is displayed.
3.  Select the check box for each entry to delete.
4.  Click **Delete**.
5.  Click **OK** in the confirmation dialog box.
