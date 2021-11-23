{
    "title": "Manage upload restrictions",
    "linkTitle": "Manage upload restrictions",
    "weight": "230"
}Use the *Upload* pane of the *Restrictions* page to add, enable, disable, reorder, or delete upload restriction entries. Using upload restrictions, for each user class, you can allow or deny permission to upload files based on the destination and set the owner, group, or file system permission (mode) of the uploaded file on a UNIX-based system.

The following topics provide how-to instructions for managing upload restrictions:

-   [Add an upload restriction](#Add)
-   [Enable or disable an upload restriction](#Enable)
-   [Edit an upload restriction](#Edit)
-   [Reorder upload restrictions](#Reorder)
-   [Reorder upload restrictions](#Reorder)

<span id="Add"></span>

## Add an upload restriction

Use the following procedure to add an upload restriction.

1.  Select **Access** **&gt;** **Restrictions**.
2.  Click the **Upload** tab.  
    The *Upload Restrictions* pane is displayed.
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
             <td><p>The file name or directory you want to apply a restriction to. Specify the path relative to the file system root for the user. For a real user, the file system root is the operating system root. For a virtual user, the file system root is the user's home directory. On Windows, you must use a POSIX path. Specify drives as <code>/drives/c</code> and <code>/drives/d</code> instead of <code>C:\</code> and <code>D:\</code>. You can use UNIX-style wildcard characters to apply restrictions for an entire directory and its subdirectories.</p>
    <p>Path entries must contain both a forward slash and the asterisk wildcard (<code>/*</code>) to deny or allow everything. Specifying <code>/temp</code> applies the restriction only to the directory itself, not its contents. To apply the restriction to the directory and its contents, you must specify <code>/temp/*</code>.</p>
    <p>For example, if you specify <code>/drives/C/temp</code> as the path and allow uploads, uploading will be allowed but Owner, Group, and Mode will not be applied to the uploaded file. To apply Owner, Group, and Mode or to allow uploads to subdirectories of <code>/temp</code>, you must specify <code>/drives/C/temp/*</code> as the path.</p>
    <p>With {{< SecureTransport/componentshortname  >}} version 5.4, two new parameters are introduced with Filesystem restrictions: <code>{s}</code> and <code>{i}</code>. These two options are used as prefixes to regular expressions and their purpose is to match the Path in case sensitive (<code>{s}</code>)or case insensitive (<code>{i}</code>) manner.</p>
    <ul>
    <li><code>{i}</code> matches Path in an expression in a case-insensitive fashion.<br />
    Example use: Access to path that matches the expression <code>{i}/*.xml</code> will allow the user to upload any xml file, regardless of filename extension case: whether it is XML, xml or XmL.<br />
    </li>
    <li><code>{s}</code> matches all files in an expression in a case-sensitive fashion.<br />
    Example use: Access to path that matches the expression <code>{s}/*.TXT</code> will allow the user to upload only files with TXT extension (uppercase, as defined in the expression) and will not be able to upload files with .txt extension (lowercase, not defined in the expression).</li>
    </ul>
    Along with the two regular expression prefixes, a dedicated configuration option is introduced: <code>Restrictions.pathIgnoreCases</code>. When it is set to <code>false</code>, all expressions that do not use the <code>{i}</code> or <code>{s}</code> prefixes will match the path in case-sensitive manner. Respectively, when set to <code>true</code>, all expressions without the <code>{i}</code> or <code>{s}</code> prefixes will match in case-insensitive manner.         </td>
          </tr>
          <tr>
             <td><strong>Allowed</strong>         </td>
             <td>Select <strong>Yes</strong> or <strong>No</strong> based on whether you want to restrict uploading.         </td>
          </tr>
          <tr>
             <td><strong>User Class</strong>         </td>
             <td>Select a user class. Asterisk (<code>*</code>) means all users.         </td>
          </tr>
          <tr>
             <td><strong>Owner</strong>         </td>
             <td><p>(UNIX-based systems only) User ID to be set for the uploaded file when <strong>Allowed</strong> is <strong>Yes</strong>.</p>
    <p>When the <code>Users.Uploads.RestrictionsApplication</code> server configuration parameter is set to <code>limited</code>, the value of this field is ignored if the file mode is set by the client.</p>
    <p>The <code>Users.Uploads.RestrictionsApplication</code> server configuration parameter default value is: <code>limited</code></p>
    <p>When the <code>Users.Uploads.RestrictionsApplication</code> server configuration parameter is set to <code>full</code>, the value of this field is always applied.</p>         </td>
          </tr>
          <tr>
             <td><strong>Group</strong>         </td>
             <td><p>(UNIX-based systems only) Group name or ID to be set for the uploaded file when <strong>Allowed</strong> is <strong>Yes</strong>.</p>
    <p>When the <code>Users.Uploads.RestrictionsApplication</code> server configuration parameter is set to <code>limited</code>, the value of this field is ignored if the file mode is set by the client.</p>
    <p>The <code>Users.Uploads.RestrictionsApplication</code> server configuration parameter default value is: <code>limited</code></p>
    <p>When the <code>Users.Uploads.RestrictionsApplication</code> server configuration parameter is set to <code>full</code>, the value of this field is always applied.</p>         </td>
          </tr>
          <tr>
             <td><strong>Mode</strong>         </td>
             <td><p>(UNIX-based systems only) File access permissions to be applied to the uploaded file when <strong>Allowed</strong> is <strong>Yes</strong>.</p>
    <p>When the <code>Users.Uploads.RestrictionsApplication</code> server configuration parameter is set to <code>limited</code>, the value of this field is ignored if the file mode is set by the client.</p>
    <p>The <code>Users.Uploads.RestrictionsApplication</code> server configuration parameter default value is: <code>limited</code></p>
    <p>When the <code>Users.Uploads.RestrictionsApplication</code> server configuration parameter is set to <code>full</code>, the value of this field is always applied.</p>
    <p>If you leave this field empty, the file mode set by the client is applied regardless of the value of <code>Users.Uploads.RestrictionsApplication</code> server configuration parameter.</p>         </td>
          </tr>
       </tbody>
    </table>
5.  Click the Save icon (![Save](/Images/SecureTransport/SaveIcon_13x13.png)) in the **Edit** column.  
    The status of a new entry is set to Disabled.

> **Note:**
>
> To cancel an add operation, select Access &gt; Restrictions again.

<span id="Enable"></span>

## Enable or disable an upload restriction

Use the following procedure enable or disable an upload restriction.

1.  Select **Access** **&gt;** **Restrictions**.
2.  Click the **Upload** tab.  
    The *Upload Restrictions* pane is displayed.
3.  Select the check box for each entry to modify.
4.  Click **Enable** or **Disable**.  
    The icons in the **Path** column change to indicate the status of the classes.

<span id="Edit"></span>

## Edit an upload restriction

Use the following procedure to edit an upload restriction.

1.  Select **Access** **&gt;** **Restrictions**.
2.  Click the **Upload** tab.  
    The *Upload Restrictions* pane is displayed.
3.  Click the Edit icon (![Edit](/Images/SecureTransport/EditIcon_12x13.png)) in the **Edit** column for the entry to edit.
4.  Make the required changes in the fields.
5.  Click the Save icon (![Save](/Images/SecureTransport/SaveIcon_13x13.png)) in the **Edit** column.

> **Note:**
>
> To cancel an edit operation, select Access &gt; Restrictions again.

<span id="Reorder"></span>

## Reorder upload restrictions

Use the following procedure to reorder upload restrictions.

1.  Select **Access** **&gt;** **Restrictions**.
2.  Click the **Upload** tab.  
    The *Upload Restrictions* pane is displayed.
3.  Click **Reorder**.  
    Up and down arrows are displayed in a column before the **Path** column.
4.  Drag the rows of the entries to the required order.
5.  Click **Save Order**.

> **Note:**
>
> To cancel a reorder operation, select Access &gt; Restrictions again.

<span id="Delete"></span>

## Delete an upload restriction

Use the following procedure to delete an upload restriction.

1.  Select **Access > Restrictions**.
2.  Click the **Upload** tab.  
    The *Upload Restrictions* pane is displayed.
3.  Select the check box for each entry to delete.
4.  Click **Delete**.
5.  Click **OK** in the confirmation dialog box.
