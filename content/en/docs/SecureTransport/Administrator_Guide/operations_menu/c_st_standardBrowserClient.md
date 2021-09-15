{
    "title": "Standard browser client",
    "linkTitle": "Standard browser client",
    "weight": "170"
}You can use a standard browser, such as Firefox or Microsoft Internet Explorer (IE) to connect to a SecureTransport Server. Using a browser allows easy access to the SecureTransport Server, but it does not offer all the features of Axway Secure Client applications. For example, the browser client does not support the Automatic Restart function. Browsers connecting to SecureTransport must support JavaScript.

No additional configuration is required on the server side for users to connect to the server with a standard browser. You can customize the interface if you prefer.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">Customization of the interface requires knowledge of HTML and JavaScript.         </td>
      </tr>
</table>

The client must have JavaScript and cookies enabled.

## <span id="Customiz"></span>Customize a web client

To create a custom browser client, copy the files for an existing browser HTML template and modify them. You must make the changes on all servers in a cluster.

### Customize the browser client interface

The pages for the SecureTransport default browser client interface are created from HTML template pages. There are template pages for each locale supported by the server. The pages are located in the `<FILEDRIVEHOME>/share/ftdocs/html/<Locale>` directory, where `<Locale>` is the supported locale. The default pages are in the `C` (for English) directory.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">Additional template pages reside in <code>&lt;FILEDRIVEHOME&gt;/share/ftdocs/html/skin/jb9</code> and <code>&lt;FILEDRIVEHOME&gt;/share/ftdocs/html/skin/sm6</code>. A <code>&lt;Locale&gt;</code> subdirectory contains the HTML files for each additional template. For more information about setting the HTML template used for the browser client, see <a href="../../c_st_setup/c_st_miscellaneousconfiguration/t_st_miscellaneousoptions">Select a default HTML template</a>.         </td>
      </tr>
</table>

The pages include embedded macro strings. A macro string is a special string in HTML which the SecureTransport Server understands and replaces with HTML or JavaScript code. A macro string is enclosed in angle brackets and two dashes and includes an exclamation point. For example:

`<!--FDX_PARENT_DIR_FUNC-->`

To customize the browser client interface, edit the HTML template pages. All custom pages must include the appropriate macro strings as listed in the Macro Strings table. Most of the HTML in the templates can be changed. The JavaScript functions can also be changed. Make these changes on each node of the cluster where they are required.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">Editing or creating a JavaScript function must be defined in the template page.         </td>
      </tr>
</table>

Do not change the following parameters while editing the templates:

-   Name/Value in any of the forms  
    These are hardcoded in the server.
-   URLs for listing, downloading, and deleting files. Do not define new macro strings or change the definition of existing macro strings.

The browser interface has template pages for the following functions:

-   Login and logout
-   List
-   Download
-   Session timeout
-   Options
-   Account and password management
-   Message

### Macro strings

The following table provides information on the macro strings that are supported by SecureTransport. Some macro strings are only supported in specific template pages, as indicated in the Description column.

<table cellspacing="0">
   <col/>
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Macro string</th>
         <th>Replaced with:</th>
         <th>Description</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>FDX_CHANGE_PASSWORD_MSGS         </td>
         <td>The policy used in changing passwords. It is replaced by one of four FDX Messages (see <a href="#fdx_message">FDX_MESSAGE</a>).         </td>
         <td>Used only on the <em>Change Passwords</em> page.         </td>
      </tr>
      <tr>
         <td>FDX_CLICK_URL         </td>
         <td>/~         </td>
         <td>Specifies the relative URL to which the user is redirected after displaying the authentication message, for example if the <code>AuthMessage</code> parameter of <code>AuthAgent</code> is set to <code>"Yes"</code>.         </td>
      </tr>
      <tr>
         <td>FDX_DIRECTORY_LIST         </td>
         <td>
            <p>For every file or directory present in the current directory, <span>SecureTransport</span> adds the following line:</p>
            <p><code>PrintFileURL<br>("<em>FileURL</em>", "<em>FileName</em>", "<em>isDir</em>", "<em>size</em>", "<em>date</em>", "<em>icon</em>")</br></code>
</p>
         </td>
         <td>
            <p><em>FileURL</em> – the name of the file which can be used as the URL</p>
            <p><em>FileName</em> – the name of file</p>
            <p><em>isDir</em> – <code>0</code> for directory or <code>1</code> for a file</p>
            <p><em>size</em> – size of the file (for a directory, size is N/A), <code>date</code> is the modification date of a file</p>
            <p><em>icon</em> – the URL of an image file to be used as icon</p>
            <p>Used on the <em>List</em> page only.</p>
         </td>
      </tr>
      <tr>
         <td>FDX_FILE_NAME         </td>
         <td>The current file or directory name.         </td>
         <td>Used in the <em>List</em> and <em>Options</em> pages.         </td>
      </tr>
      <tr>
         <td>FDX_FILE_URL         </td>
         <td>The escaped file name, which can be used as a URL.         </td>
         <td>Used in the <em>List</em> and <em>Options</em> pages.         </td>
      </tr>
      <tr>
         <td>FDX_HIDDEN_START_URL         </td>
         <td>&lt;input type="hidden" name="start-url" value="/myfile.txt"&gt;         </td>
         <td>Specifies the original URL that an unauthenticated user attempted to access. Upon successful login, the user is redirected to this URL.         </td>
      </tr>
      <tr>
         <td><a name="FDX_LIST_PARENT_DIR"></a>FDX_LIST_PARENT_DIR         </td>
         <td>The directory hierarchy of the current directory.         </td>
         <td>
            <p>This is an alternative to <a href="#fdx_parent_dir_func">FDX_PARENT_DIR_FUNC</a>, which displays the directory structure as it is displayed in the default template.</p>
            <p>Used on the <em>List</em> page only.</p>
         </td>
      </tr>
      <tr>
         <td><a name="FDX_MESSAGE"></a>FDX_MESSAGE         </td>
         <td><code>FDX_Msg("<em>message</em>")</code>
         </td>
         <td>
            <p><em>message</em> – the message to be displayed</p>
            <p>Used on the <em>Login</em>, <em>Password Fail</em>, and <em>Password Success</em> pages.</p>
         </td>
      </tr>
      <tr>
         <td>FDX_OPTIONS_PARENT_DIR         </td>
         <td>The directory structure of the current directory.         </td>
         <td>
            <p>An alternative to <a href="#fdx_parent_dir_func">FDX_PARENT_DIR_FUNC</a>, which displays the directory structure as it is displayed in the default template.</p>
            <p>Used only on the <em>Options</em> page.</p>
         </td>
      </tr>
      <tr>
         <td><a name="FDX_PARENT_DIR_FUNC"></a>FDX_PARENT_DIR_FUNC         </td>
         <td><code>ParentDirFunc<br/>("<em>DirName</em>", "<em>DirURL</em>")</code>
         </td>
         <td>
            <p><em>DirName</em> – the name of parent directory.</p>
            <p><em>DirURL</em> – the name of parent directory which is sent as a URL. This string is an alternative to <a href="#fdx_list_parent_dir">FDX_LIST_PARENT_DIR</a>, which can be edited.</p>
            <p>Used in the <em>List</em> and <em>Options</em> pages.</p>
         </td>
      </tr>
      <tr>
         <td>FDX_PASSWORD_PRINT_FORM         </td>
         <td><code>PrintForm()</code>
         </td>
         <td>Used on the <em>Password Success</em> page only when the server needs to include the login form.         </td>
      </tr>
      <tr>
         <td>FDX_SERVER_INFO         </td>
         <td><code>PrintServerInfo(<br/>"<em>name</em>", "<em>version</em>", "<em>build</em>", "<em>host</em>")</code>
         </td>
         <td>
            <p>Server version information:</p>
            <p><em>name</em> – the name of the server</p>
            <p><em>version</em> – the version of the server</p>
            <p><em>build</em> – the build number of server, always <code>0</code></p>
            <p><em>host</em> – the host name of the server computer.</p>
            <p>Used only on <em>Login</em> page.</p>
         </td>
      </tr>
      <tr>
         <td>FDX_XFER_MODE         </td>
         <td><code>PrintXferMode(<em>mode</em>)</code>
         </td>
         <td>
            <p><em>mode</em> – the transfer mode: <code>1</code> for binary or <code>0</code> for ASCII</p>
            <p>Used on the <em>List</em> page only.</p>
         </td>
      </tr>
   </tbody>
</table>

### Customize the browser client login

You can customize the type of login page the browser displays for browser client users. Change the values of the parameters described in the following table in the *Server Configuration* page. After you change any of these parameters, bounce the server.

<table cellspacing="0">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Parameter</th>
         <th>Use</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>Http.FdxAuthReply         </td>
         <td>
            <p>Controls what type of login the server displays to browser client users. Valid values are:</p>
            <p><code>BA</code> – The server displays a basic authentication window for the user to type their name and password.</p>
            <p><code>HTML</code> – The server displays an HTML page for the user to type their name and password.</p>
            <p><code>ERR</code> – This is used for special cases, for example where cookies are used for authentication. When ERR is set, an authentication request does not occur. To get an authentication request, enable auth, and config agents.</p>
            <p><code>PREAUTH</code> – Enable auth and config agents. If authorization fails, the server displays an HTML page for the user to type their name and password.</p>
            <p>&amp;&amp;&amp; ïïï ùùù</p>
         </td>
      </tr>
      <tr>
         <td>Http.FdxAuthAliases         </td>
         <td>This parameter controls whether items in the <code>&lt;FILEDRIVEHOME&gt;/share/ftdocs/icons/</code> and <code>&lt;FILEDRIVEHOME&gt;/share/ftdocs/html/</code> directories are authenticated. Set it to <code>OFF</code> to display custom icons on the login page.         </td>
      </tr>
   </tbody>
</table>

### Remove the server information displayed on the login screen

To remove the display of server information in the SecureTransport browser client, you must modify the `<FILEDRIVEHOME>/share/ftdocs/html/C/login.html` file.

Modify the function `PrintServerInfo` to return `0` as shown in the following code:

    function PrintServerInfo(name, ver, build, host) {
        return 0;
    }

### Customize the browser client login

You can customize the type of login page the browser displays for browser client users. Change the values of the parameters described in the following table in the *Server Configuration* page. After you change any of these parameters, bounce the server.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">When <code>PREAUTH</code> is set for <code>Http.FdxAuthReply</code>, <span>SecureTransport</span> uses <code>*nobody</code> as an internal constant value indicating that no user is authenticated with  internal agents. If a user with the  name <i>*nobody</i> already exists on the operating system, this may cause a conflict that prevents that user from logging in.         </td>
      </tr>
</table>

### Remove the server information displayed on the login screen

To remove the display of server information in the SecureTransport browser client, you must modify the `<FILEDRIVEHOME>/share/ftdocs/html/C/login.html` file.

Modify the function `PrintServerInfo` to return `0` as shown in the following code:

    function PrintServerInfo(name, ver, build, host) {
        return 0;
    }

### Control the display of server information

You can remove or limit the information displayed in the Server HTTP response header using the following server configuration options:

-   `Admin.ServerHeaderTokens` - controls the content of the Server HTTP response header for the Administration tool. Changing the value requires Admin service restart to take effect.
-   `Http.ServerHeaderTokens`- controls the content of the Server HTTP response header for all web clients, including the ST Web Client. Changing the value requires HTTP server restart to take effect.

These two configuration options have the same behavior.

Possible values:

-   `Full`– Default; The header field shows the product name, build number, and the operating system (with the result being, for example, `Server: SecureTransport 5.4 (build: 1111) - Linux).`
-   `Prod`– The header field shows the product name, *SecureTransport*.
-   `OS`– The header field shows the operating system on which SecureTransport is running (with the result being, for example, `Server: Linux`)
-   `None`– Depending on the Jetty version, the Server header is not displayed or its field is empty.

### Configure Cache-Control for SecureTransport Administration tool

You can define response caching policies for the SecureTransport Administration tool via the `Admin.ControlCaching` server configuration option. Changing the option value requires Admin service restart to take effect.

Possible values:

-   `true`- The request cashing is enabled.
-   `false`- The Cache-Control directive is set to n`o-cache, no-store` on all static and non-static requests.

<table cellspacing="0">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Parameter</th>
         <th>Use</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>Http.FdxAuthReply         </td>
         <td>
            <p>Controls what type of login the server displays to browser client users. Valid values are:</p>
            <p><code>BA</code> – The server displays a basic authentication window for the user to type their name and password.</p>
            <p><code>HTML</code> – The server displays an HTML page for the user to type their name and password.</p>
            <p><code>ERR</code> – This is used for special cases, for example where cookies are used for authentication. When ERR is set, an authentication request does not occur. To get an authentication request, enable auth, and config agents.</p>
            <p><code>PREAUTH</code> – Enable auth and config agents. If authorization fails, the server displays an HTML page for the user to type their name and password.</p>
         </td>
      </tr>
      <tr>
         <td>Http.FdxAuthAliases         </td>
         <td>This parameter controls whether items in the <code>&lt;FILEDRIVEHOME&gt;/share/ftdocs/icons/</code> and <code>&lt;FILEDRIVEHOME&gt;/share/ftdocs/html/</code> directories are authenticated. Set it to <code>OFF</code> to display custom icons on the login page.         </td>
      </tr>
   </tbody>
</table>
