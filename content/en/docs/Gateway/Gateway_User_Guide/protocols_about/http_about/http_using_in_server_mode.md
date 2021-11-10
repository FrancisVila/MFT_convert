{
    "title": "Using HTTP in server mode",
    "linkTitle": "Using HTTP in server mode",
    "weight": "200"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Protocols

 

<span id="HTTP_Server"></span>

## About the HTTP server

Use HTTP in server mode, to perform one of the following tasks:

-   <span style="font-weight: bold;">Upload files</span>  
    Accept a file that a client (Initiator/Receiver) is sending. When you download files, the URL points to a file on the server.
-   <span style="font-weight: bold;">Download files</span>  
    Make files available to a client (Initiator/Sender). The client request contains the file to be stored in the directory to which the URL points.
-   <span style="font-weight: bold;">List directories</span>  
    Display a list of available files (Responder/Sender). The URL points to a directory.

For each request received, the Gateway HTTP server must identify the action requested by the client. The server first extracts relevant elements from the client request (for example, URL, and CGI parameters). It then verifies user identification, checks the URL and executes the requested action.

<span id="Before_you_transfer_a_file"></span>

## Before you transfer a file

Before you send or receive an HTTP transfer, you must configure CGates and VFDs in Gateway. These objects assign directories and directory rights to connecting parties. It is also recommended that you configure the identification method.

### CGates

CGates associate certain product elements (for example, Sites or Templates) with a protocol connection (identification). They are required to initialize and manage the virtual file system.

The HTTP server uses CGates to set up certain variables (for example, the user home page, or the directory listing template).

### VFD

The Virtual File Directory (VFD) is a virtual file system that HTTP clients see when they connect to Gateway. This file system can monitor transfers, display virtual directories, and provide links to real file system directories.

The HTTP server first initializes a new VFD session with the identified CGate parameters (including root directory, and access rights details) and then uses the VFD to associate the requested URL to a file, a transfer, or a directory.

### Configuration

Throughout this topic, references are made to HTTP configurable elements, such as the authentication type, that you can modify using the [configuration menu](../../../configuration_start_here/config_protocols_about/config_http_options).

<span id="Processing_HTTP_client_requests"></span>

## Processing HTTP client requests

The HTTP server processes a client request in the following sequence:

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p>1</p>         </td>
         <td><p>Analyzes the first line of the request and extracts the relevant elements:</p>
<ul>
<li>HTTP transfer method (GET, PUT, POST)</li>
<li>URL accessed</li>
<li>CGI parameters</li>
<li>Protocol used (HTTP/1.0, HTTP/1.1)</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Stores received HTTP headers</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Extracts CGI parameters sent in the body of the request (POST method only)</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Suspends the incoming TCP flow once the entire request is received</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Identifies the connected party via the user, password or session ID received in CGI parameters or HTTP headers (depending on the server identification mode set in the configuration menu)</p>         </td>
      </tr>
      <tr>
         <td><p>6</p>         </td>
         <td><p>Identifies the requested URL and checks access rights</p>         </td>
      </tr>
      <tr>
         <td><p>7</p>         </td>
         <td><p>Releases the incoming TCP flow</p>         </td>
      </tr>
      <tr>
         <td><p>8</p>         </td>
         <td><p>Processes the request (upload, download, or directory listing)</p>         </td>
      </tr>
   </tbody>
</table>

If an error occurs during the execution of one of these steps, an error page is returned to the connected client. For more details, refer to [Error pages](#Error_pages) further on in this topic.

<span id="Identification_methods"></span>

## Identification methods

### How the Gateway server identifies the client

Before the Gateway HTTP server can execute an HTTP request and before it checks the URL provided, it must identify the connected party. The Gateway HTTP server retrieves the *user/password* pair and assigns CGate and Site parameters to it.

The Gateway HTTP server can collect identification parameters in various ways, but it can only be configured to use one identification method at a time. The Gateway HTTP server uses **Web** identification by default.

You can change identification parameters (*user*, *password*, and *sessionid*) in the [configuration menu](../../../configuration_start_here/config_protocols_about/config_http_options). This menu also enables you to configure session management (including, for example, the maximum number of created sessions).

Supported identification methods:

-   Web
-   CGI user and password
-   CGI session ID
-   Cookie user and password
-   Cookie session ID

### Web

Web identification, which can be called WWW authorization, is the only standard identification method defined by the HTTP protocol. The other methods presented in this topic are application-level mechanisms.

Summary of the Gateway HTTP server search mechanism and specific actions using the <span style="font-style: italic;">Web</span> identification method:

<table>
         
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Search method (in sequence)</p>         </th>
<th class="HeadE-Column1-Header1"><p>If element found</p>         </th>
<th class="HeadD-Column1-Header1"><p>If login fails</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Searches in the request header for an <span style="font-weight: bold;">Authorization</span> field and identifies the connected party from the parameters found</p>         </td>
         <td><p>Server logs in the user</p>         </td>
         <td><p>Server adds a negative response to the header and returns it with an error page informing the client that the credentials were not valid and prompting the user to try again</p>         </td>
      </tr>
      <tr>
         <td><p>Uses <span style="font-weight: bold;">anonymous</span> to log in</p>         </td>
      </tr>
   </tbody>
</table>

<span style="font-weight: bold;">Note:</span> Browsers typically try to access the requested URL anonymously the first time they connect to a server. If <span style="font-weight: bold;">anonymous</span> is not allowed to log in, the connected user is prompted for a login and password.

### CGI user and password

Clients can send these parameters in either or both of these elements:

-   URL, separated from the path by a question mark ("?")
-   Body of the request (POST requests only)

As the CGI parameters are user-level parameters, standard HTTP clients, such as browsers, do not send them on each request. It is the role of the Gateway server to send parameters to the HTML pages that are requested and to elements such as links and forms.

Summary of the Gateway HTTP server search mechanism and specific actions using the *CGI user and password* identification method:

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Search method (in sequence)</p>         </th>
<th class="HeadD-Column1-Header1"><p>If element found</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>User-level parameters received</p>         </td>
         <td><p>Server logs in the user</p>         </td>
      </tr>
      <tr>
         <td><p>Uses <strong>anonymous</strong> to log in</p>         </td>
      </tr>
   </tbody>
</table>

### CGI session ID

Using CGI session identification, it is the role of the Gateway HTTP server to send the *sessionid* parameter to the returned HTML pages.

Summary of the Gateway HTTP server search mechanism and specific actions using the *CGI session ID* identification method:

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Search method (in sequence)</p>         </th>
<th class="HeadD-Column1-Header1"><p>If found and login correct</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Searches for <em>user</em> and <em>password</em> parameters in the CGI parameters received</p>         </td>
         <td><p>Server uses them as credentials and if login succeeds, creates a session ID</p>         </td>
      </tr>
      <tr>
         <td><p>Searches for the <em>sessionid</em> parameter used to retrieve the <em>user</em> and <em>password</em> provided during session creation</p>         </td>
         <td><p>Server logs in the user</p>         </td>
      </tr>
      <tr>
         <td><p>Uses <strong>anonymous</strong> to log in</p>         </td>
      </tr>
   </tbody>
</table>

### Cookie user and password

Cookies are set for the whole directory tree (everything under path "<span class="code">/</span>"). No expiration dates are attached to them: Web browsers store cookies for the current session and automatically destroy them when the current session is closed.

Summary of the Gateway HTTP server search mechanism and specific actions using the <span style="font-style: italic;">Cookie user and password</span> identification method:

<table>
         
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Search method (in sequence)</p>         </th>
<th class="HeadE-Column1-Header1"><p>If element found</p>         </th>
<th class="HeadD-Column1-Header1"><p>If login fails</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>CGI parameter list</p>         </td>
         <td><p>Sever logs in the user</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>Cookies sent by the client</p>         </td>
         <td><p>Server returns two <strong>Set-Cookie</strong> fields with empty values in order to clear cookies set on the browser side</p>         </td>
      </tr>
      <tr>
         <td><p>Uses <strong>anonymous</strong> to log in</p>         </td>
         <td><p>Server returns two Set-Cookie header fields to the client. These fields request the client to store user and password within its cookies.</p>         </td>
         <td><p> </p>         </td>
      </tr>
   </tbody>
</table>

### Cookie session ID

Summary of the Gateway HTTP server search mechanism and specific actions using the <span style="font-style: italic;">Cookie session ID</span> identification method:

<table>
         
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Search method (in sequence)</p>         </th>
<th class="HeadE-Column1-Header1"><p>If element found and login correct</p>         </th>
<th class="HeadD-Column1-Header1"><p>If login fails</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Searches for user and password in the CGI parameters list</p>         </td>
         <td><p>Server logs in the user and creates a new session</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>Searches for a session ID in the cookies sent by the client</p>         </td>
         <td><p>Server logs in the user with the <em>user</em> and <em>password</em> values saved for this session ID</p>         </td>
         <td><p>Server returns a <span style="font-weight: bold;">Set-Cookie</span> field with an empty value in order to clear the cookie set on the browser side</p>         </td>
      </tr>
   </tbody>
</table>

When the Gateway HTTP server creates a new session, it returns a **Set-Cookie** field to the client. This field requests the client to store *sessionid* in its cookies list. When stored as a cookie, *sessionid* is automatically re-sent on each new request to the server.

### Partner-Dependant identification

The server determines the authentication method to use from the request headers sent by the client software. HTTP clients can log in using any of the authentication methods supported by Gateway. Note that the HTTP server accepts all the connections having a supported identification method.

### HTTP session ID limitation

You can limit the number of simultaneous opened sessions for a user.

A global configuration parameter, <span class="code">sid\_limit</span>, limits the number of sessions a user can have on the server.

Each time a user logs in, the value of this parameter is compared with the number of sessions registered for that user.

If the number of registered sessions is lower than the value of the configuration parameter, the user is allowed to login. Otherwise the login is refused.

You can find the <span class="code">sid\_limit</span> parameter in the Gateway [advanced parameters](../../../configuration_start_here/config_gateway_paras#Advanced_parameters).

This parameter is only taken into account if you have set the HTTP server identification **Method** to *Cookie session id* or *CGI session id* in the configuration menu.

<span id="Directory_listings"></span>

## Directory listings

An HTTP directory listing returns to the client an HTML page containing a list of links to elements (files and subdirectories) contained in the directory. A directory listing is performed when the accessed URL refers to a directory.

The Gateway virtual file system can contain the following elements:

-   **Directories**
-   **Files:** Only available if the directory refers to a real system directory
-   **Transfers:** References to Gateway transfers created in that directory. Only available if the directory is virtual (VFD). When displaying Gateway transfers, the server differentiates the available files in the directory listings as described in the following table:

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>If the Transfer type is:</p>         </th>
<th class="HeadD-Column1-Header1"><p>Then the connected party can:</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>available</p>         </td>
         <td><p>Retrieve the transfer (that is, the file) by clicking the transfer name, which is a hypertext link</p>         </td>
      </tr>
      <tr>
         <td><p>unavailable</p>         </td>
         <td><p>Display transfers in the current directory (similar to FTP). Transfers are displayed for informational purposes only and no hypertext links are required.</p>         </td>
      </tr>
   </tbody>
</table>

To fulfill these requirements, Gateway uses an HTML page to display directory contents. This page is called a listing template and includes elements that adapt the listing to the contents of the listed directory (for example, files, sub-directories, and transfers).

<span id="HTTP_listing_template_files"></span>

## HTTP listing template files

The listing template files contain the HTML formats used to list directories. First, the server must determine which file to use as a pattern. The file path to this pattern is specified in the:

-   CGate selected during login phase.  
    The value can be taken from one of the selected parent CGateGroups.
-   Default template file defined in the HTTP configuration part of Gateway.  
    You can modify this value using the configuration menu.

Once found and loaded, the server stores the patterns in memory and reloads them only when their files were modified. If no file is defined or if the file cannot be loaded, an error is returned to the client.

When the Responder (server) retrieves the listing pattern, it processes the listing in the following sequence:

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p>1</p>         </td>
         <td><p>Substitutes the global symbols (for example "%") in the page with their respective values (refer to <span style="font-style: italic;">Symbol substitution</span> later in this topic for more information)</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Searches for special tags (defined in <span style="font-style: italic;">Using special tags</span> below) and replaces them with each corresponding element of the listed directory</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Returns the dynamically-generated pages to the Initiator (client)</p>         </td>
      </tr>
   </tbody>
</table>

### Using special tags

Gateway recognizes the following special tags that you can use in the template files.

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Tag</p>         </th>
<th class="HeadD-Column1-Header1"><p>Comment</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>&lt;PARENT&gt;  &lt;/PARENT&gt;</p>         </td>
         <td><p>Text between these tags is displayed only if the listed directory is not "/".</p>         </td>
      </tr>
      <tr>
         <td><p>&lt;DIR&gt;  &lt;/DIR&gt;</p>         </td>
         <td><p>Text between these tags is duplicated for each directory in the current directory. The following special names are also replaced:</p>
<ul>
<li>@NAME@: directory name encoded for URL</li>
<li>@name@: directory name</li>
<li>@DATE@: Directory last modification date, per component: @DATE_Y@ (year), @DATE_M@ (month), @DATE_m@ (month as a decimal number), @DATE_D@ (day), @DATE_d@ (day as a decimal number), @DATE_T@: directory last modification time</li>
<li>@CONTENT@: number of files and number of available files from current directory. For example: 43 files (30 available)</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>&lt;REAL_FILE&gt;  &lt;/REAL_FILE&gt;</p>         </td>
         <td><p>Text between these tags is duplicated for each file in the directory. It is only available under <a href="../../../transfers_start_here/virtual_file_directory_start_here#Mounted_directories">mounted directories</a>.</p>
<p>The following special tags are also replaced:</p>
<ul>
<li>@FNAME@: file name encoded for URL</li>
<li>@fname@: file name</li>
<li>@DATE@: Directory last modification date, per component: @DATE_Y@ (year), @DATE_M@ (month), @DATE_m@ (month as a decimal number), @DATE_D@ (day), @DATE_d@ (day as a decimal number), @DATE_T@: directory last modification time</li>
<li>@SIZE@: file size</li>
<li>@ICON@: icon name associated with the directory path and filename, encoded for URL (for more information, refer to <a href="#Configuration_file">Configuration file</a>).</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>&lt;XFER_AVAIL&gt;  &lt;/XFER_AVAIL&gt;</p>         </td>
         <td><p>Text between these tags is duplicated for each available transfer in the current virtual directory. These tags are ignored inside real directories. The following special names are also replaced:</p>
<ul>
<li>@FNAME@: transfer file name encoded for URL</li>
<li>@fname@: transfer file name</li>
<li>@DATE@: Directory last modification date, per component: @DATE_Y@ (year), @DATE_M@ (month), @DATE_m@ (month as a decimal number), @DATE_D@ (day), @DATE_d@ (day as a decimal number), @DATE_T@: directory last modification time</li>
<li>@SIZE@: file size</li>
<li>@LOCAL_ID@: transfer local identifier</li>
<li>@STATE@: transfer status</li>
<li>@ICON@: icon name associated with the directory path and filename, encoded for URL (for more information, refer to <a href="#Configuration_file">Configuration file</a>).</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>&lt;XFER_UNAVAIL&gt;  &lt;/XFER_UNAVAIL&gt;</p>         </td>
         <td><p>Text between these tags is duplicated for each unavailable transfer in the current directory. These tags are ignored inside real directories. Substitutions described above apply here</p>         </td>
      </tr>
   </tbody>
</table>

#### Symbol encoding

As a mechanism for the prevention of XSS (Cross-Site Scripting), <span class="mc-variable suite_variables.GatewayName variable">Gateway</span> offers the possibility to encode HTML entities according to the context in which they are used. Special tags like @NAME@ and @FNAME@ are already encoded for an URI context; however a higher level of control is desirable. For example, the directory or file name can be used in a different context than that of an URI; such as a JavaScript/HTML context. The proper encoding can be done by using a special tag with no default encoding, and suffixing it with an encoding context specifier; e.g. @name@forJsHtml(), @fname@forJsHtml().

The following types of encoding can be used:

-   <span class="code">forUri()</span>  
    URI context
-   <span class="code">forUriComponent()</span>  
    URI component context
-   <span class="code">forCssUri()</span>  
    CSS URI context
-   <span class="code">forCssString()</span>  
    CSS string context
-   <span class="code">forJsSource()</span>  
    JavaScript source context
-   <span class="code">forJsAttribute()</span>  
    JavaScript attribute context
-   <span class="code">forJsBlock()</span>  
    JavaScript block context
-   <span class="code">forJsHtml()</span>  
    JavaScript/HTML context
-   <span class="code">forHtml() </span>  
    HTML context

<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Caution  </strong></span>         </td>
         <td>Make sure every special tag that could be controlled by an attacker is using HTML entity encoding, either explicit or implicit. See the example below, and the sample templates delivered with the product.         </td>
      </tr>
   </tbody>
</table>

> **Note:**
>
> For special tags with implicit encoding (@NAME@, @FNAME@), overwriting by specifying an explicit encoding is not supported.

For more detail regarding XSS (Cross-Site Scripting) and HTML entity encoding, please refer to the OWASP website:

-   <https://www.owasp.org/index.php/Cross-site_Scripting_(XSS)>
-   <https://www.owasp.org/index.php/XSS_(Cross_Site_Scripting)_Prevention_Cheat_Sheet>

(URLs are outside the <span class="mc-variable axway_variables.Company_Name variable">Axway</span> domain, and liable to change without notice).

#### Example

The following is an example of a directory listing template file.


    <HTML>
    <HEAD>
    <TITLE> %u </TITLE>
    </HEAD>
    <BODY>
    <H1> Index of %u </H1>
    <PARENT>
    <A href="">Parent directory (%n)</A> <BR>
    </PARENT>
    <HR> <PRE>
    <DIR>
    @DATE@ <A href="">@name@ .forHtml() /</A>
    </DIR>
    Date    Size    State       Name        Local Ident
    <REAL_FILE>
    @DATE@  @SIZE@             <A href="">@fname@ .forHtml() </A> </REAL_FILE>
    <XFER_AVAIL>
    @DATE@  @SIZE@  @STATE@    <A href="">@fname@ .forHtml() </A>  @LOCAL_IDENT@
    </XFER_AVAIL>
    <XFER_UNAVAIL>
    @DATE@  SIZE@   @STATE@     @fname@ .forHtml()     @LOCAL_IDENT@
    </XFER_AVAIL>
    </PRE> <HR>
    </BODY>
    </HTML>

<span id="Downloading_files"></span>

## Downloading files

To download a file, the client must send a GET (or POST) request with a URL that matches either a [real file](../../../transfers_start_here/virtual_file_directory_start_here#Real_files) or an available transfer.

As different transfers in a directory can have the same file name, you can use a [selection filter](#Restricting_selection__file_filters) to identify a specific transfer.

<span id="Uploading_files"></span>

## Uploading files

To upload a file onto the server, you must send the following elements:

-   Path name (directory in which to receive the transfer)
-   File name
-   File contents
-   Optional transfer parameters

The URL always contains the directory where the transfer is performed. The file name, however, is deduced as follows:

### Attributing file names when uploading

<table>
         
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>HTTP request method</p>         </th>
<th class="HeadE-Column1-Header1"><p>If URL format is</p>         </th>
<th class="HeadD-Column1-Header1"><p>Then the filename is</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>PUT</p>
<p>(not supported by browsers)</p>         </td>
         <td><p>file path (directory + filename)</p>         </td>
         <td><p>The last component of the file path</p>         </td>
      </tr>
      <tr>
         <td><p>directory name</p>         </td>
         <td><p>The value of the CGI parameter <em>filename</em></p>         </td>
      </tr>
      <tr>
         <td><p>POST</p>
<p>(content type must be "multipart/form-data")</p>         </td>
         <td><p>file path (directory + filename)</p>         </td>
         <td><p>The last component of the file path</p>         </td>
      </tr>
      <tr>
         <td><p>directory name</p>         </td>
         <td><p>The value of the CGI parameter <em>filename</em>, if present, or the name of the file sent (extracted from the form field used to send the file)</p>         </td>
      </tr>
   </tbody>
</table>

### Defining Axway MFT specific parameters

If the client is an Axway MFT product, optional parameters are available for more detailed communication. The parameters that you can set in the request include:

-   Application (**P\_APPLI**)
-   Remote destination of the transfer (**P\_DEST**)
-   Origin of the transfer (**P\_ORG**)
-   Message to attach to the transfer (**P\_MSG**)

These optional transfer parameters are sent through CGI parameters, either in the URL or in the request body (POST requests).

The syntax is:

**parameter=value**

Parameters are separated by an ampersand (&).

For examples of requests using the PUT and POST methods, refer to [Using HTTP in client mode - Sending files](http_using_in_client_mode.htm#Sending_files).

**Note:** The server checks and stores these parameters before the file transfer begins. This implies that they must be sent before the file itself. In other words, these parameters must be set either in the URL CGI parameters or in the CGI parameters preceding the file. If the reception results from a form submission, then the **file parameter must be positioned as the last parameter of the form**.

<span id="Restricting_selection__file_filters"></span>

## Restricting selection: File filters

As a virtual directory and a file name are insufficient to describe a Mailbox entry, Gateway provides an advanced file filter feature when downloading and listing requests.

A file filter comprises strings that contain <span class="code" style="font-weight: bold;">field=value</span> pairs. When you use HTTP, these strings are extracted from CGI parameters. Accepted values for the *field* portion of this pair are given in the table below:

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Field</p>         </th>
<th class="HeadD-Column1-Header1"><p>Accepted value</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>name</p>         </td>
         <td><p>Pattern matching paths and protocol filenames</p>         </td>
      </tr>
      <tr>
         <td><p>direction<sup>1</sup></p>         </td>
         <td><p>IN, OUT, or BOTH. Not case-sensitive</p>         </td>
      </tr>
      <tr>
         <td><p>date<sup>2</sup></p>         </td>
         <td><p>Exact date and time of the transfer, expressed in the format: <em>YYYYMMDDhhmmss</em></p>
<ul>
<li>Date fields (year, month, day of month) can be separated by "/" characters.</li>
<li>Time fields (hours, minutes, and seconds) can be separated by ":" characters. You can specify time without a date.</li>
</ul>
<p>Current day is considered the default date.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>end_before</strong> or <strong>endbefore<sup>2</sup></strong></p>         </td>
         <td><p>Date format (Transfers requested or performed earlier than the given date are not selected)</p>         </td>
      </tr>
      <tr>
         <td><p><strong>start_after</strong> or <strong>startafter<sup>2</sup></strong></p>         </td>
         <td><p>Date format (Transfers requested or performed later than the given date are not selected)</p>         </td>
      </tr>
      <tr>
         <td><p><strong>origin</strong> or <strong>org<sup>1</sup></strong></p>         </td>
         <td><p>Origin of the transfer</p>         </td>
      </tr>
      <tr>
         <td><p><strong>destination</strong> or <strong>dest<sup>1</sup></strong></p>         </td>
         <td><p>Destination of the transfer</p>         </td>
      </tr>
      <tr>
         <td><p>state<sup>1</sup></p>         </td>
         <td><p>List of states in Gateway format.</p>
<p>Each selected transfer must have one of the given states.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>mvs_state</strong> or <strong>mvsstate<sup>1</sup></strong></p>         </td>
         <td><p>List of states in MVS format.</p>
<p>Each selected transfer must have one of the given states.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>ftpcs_state</strong> or <strong>ftpcsstate</strong></p>         </td>
         <td><p>List of states in FTPCS format.</p>
<p>Each selected transfer must have one of the given states. The FTPCS state is the concatenation of the state in Gateway format and the state in InterPel MVS format.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>local_ident</strong> or <strong>localident</strong></p>         </td>
         <td><p>Long integer corresponding to the unique transfer local identifier</p>         </td>
      </tr>
      <tr>
         <td><p><strong>xfer_ident</strong> or <strong>xferident</strong></p>         </td>
         <td><p>Long integer corresponding to a transfer identifier</p>         </td>
      </tr>
   </tbody>
</table>

\(1\) For real entries and directories, these fields are ignored.

\(2\) These fields are compared to the last modification date of the file.

#### Example 1: Filtering by date

Downloading:

GET /transfer/out/file1.txt?org=site1&start\_after=20011205

#### Example 2: Filtering by transfer state

Directory listing:

GET /?name=\*.txt&state=IC&org=site1

<span style="font-weight: bold;">Notes:</span> When you retrieve a transfer, if several records match the request, the most recent one is returned.

#### Example 3: Filtering by file type

Requesting an incorrect file type:

GET /transfer/file?state=C

In this example, the user tries to download the most recent entry called **file** and in the state **canceled**. Although this is syntactically correct, Gateway does not allow downloading of canceled files and returns the following response:

404 Not found

<span id="Sort/Ord"></span>

## Sort/Order parameters

There are two parameters for sorting and setting the order of fields:

-   <span class="code">order (order=&lt;order\_field></span>)  
    If negative, the sorting order descends.  
    If positive, sorting order ascends.
-   <span class="code">sort </span>(<span class="code">sort=&lt;sort\_order\_type></span>)  
    Only one field can be chosen from the following:  
    "xfer\_type", "size", "date", "local\_id", "protocol", "rights", "direction", "state", "org", "dest", "remote", "fname", "xfer\_id", "route\_state", "perm", "appli", "msg", "code", "route\_from", "route\_to", "dup\_from", "param1", "param2", "user\_state", "local\_ident", "name", "xfer\_ident"

<span id="Gateway_specific_template_files"></span>

## Gateway specific template files

This section describes the HTML pages returned by the server when:

-   Errors occur
-   Uploads complete successfully
-   Uploads fail

<span id="Error_pages"></span>

### Error pages

Error pages are HTML files returned to the client when an error occurs. The file returned depends on both the type of error and the languages accepted by the connected client.

When Web browsers connect to a server, they typically send an HTTP header field named <span style="font-style: italic;">Accept Language</span> that contains an ordered list of accepted languages. The language used by the HTTP server is the first that matches one of its accepted languages. Use the parameter <span class="code" style="font-weight: bold;">err\_languages</span> to configure the server-accepted languages, whose default values are <span style="font-weight: bold;">en</span> \[English\], and <span style="font-weight: bold;">fr</span> \[French\]. If none of the client languages match, the first default error language is used (en).

Error files are located in the sub-directories of the error directory (parameter <span class="code" style="font-weight: bold;">err\_dir</span> whose default value is <span class="code">&lt;Gateway installation directory>/run\_time/http/pages</span>). The sub-directories must have the same name as the accepted languages. Default directories are:

-   <span class="code">&lt;Gateway installation directory>/run\_time/http/pages/en</span> for English
-   <span class="code">&lt;Gateway installation directory>/run\_time/http/pages/fr</span> for French

The following table lists the files used:

<table>
         
         
         
         
   
   <thead>
      <tr>
<th colspan="3" class="HeadD-Column1-Header1"><p>Error pages displayed by return codes</p>         </th>
      </tr>
      <tr>
<th class="HeadE-Column1-Header1"><p>Filename</p>         </th>
<th class="HeadE-Column1-Header1"><p>Return code</p>         </th>
<th class="HeadD-Column1-Header1"><p>Error description</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>ERR_BAD_REQUEST</p>         </td>
         <td><p>400</p>         </td>
         <td><p>The request contains invalid or missing parameters</p>         </td>
      </tr>
      <tr>
         <td><p>ERR_BAD_VERSION</p>         </td>
         <td><p>505</p>         </td>
         <td><p>Protocol version is not compatible</p>         </td>
      </tr>
      <tr>
         <td><p>ERR_FORBIDDEN</p>         </td>
         <td><p>403</p>         </td>
         <td><p>Requested action is forbidden (read, write, and so on)</p>         </td>
      </tr>
      <tr>
         <td><p>ERR_INTERNAL</p>         </td>
         <td><p>500</p>         </td>
         <td><p>An internal error occurred, for example a memory error, or a real or virtual file system access error</p>         </td>
      </tr>
      <tr>
         <td><p>ERR_NOT_FOUND</p>         </td>
         <td><p>404</p>         </td>
         <td><p>Could not find requested URL</p>         </td>
      </tr>
      <tr>
         <td><p>ERR_SESSIONID</p>         </td>
         <td><p>403</p>         </td>
         <td><p>Could not find received session ID (unknown or expired session)</p>         </td>
      </tr>
      <tr>
         <td><p>ERR_UNAUTHORIZED</p>         </td>
         <td><p>401 (Web auth)</p>         </td>
         <td><p>Invalid credentials</p>         </td>
      </tr>
   </tbody>
</table>

Error pages are loaded in memory the first time you access them. The HTTP server reloads them only when their files are modified. [Symbol substitutions](#Symbol_substitution) apply to these files.

### Upload success and failure pages

The following table summarizes the features of the upload success and failure pages:

<table>
         
         
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Page</p>         </th>
<th class="HeadE-Column1-Header1"><p>Returned when</p>         </th>
<th class="HeadE-Column1-Header1"><p>Associated HTTP return code</p>         </th>
<th class="HeadD-Column1-Header1"><p>Additional symbol substitutions</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Upload success</p>         </td>
         <td><p>File correctly received</p>         </td>
         <td><p>200</p>         </td>
         <td>"%x" replaced by the received and validated request URL, or "/" if the request URL cannot be validated.         </td>
      </tr>
      <tr>
         <td><p>Upload failure</p>         </td>
         <td><p>File incorrectly received</p>         </td>
         <td><p>500</p>         </td>
         <td><p>"%x" replaced by the received and validated request URL, or "/" if the request URL cannot be validated.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="Configuration_file"></span>

## 

> **Note:**
>
> For security reasons, using the CGI parameters success\_url and failure\_url for symbol substitution is no longer supported.

## Configuration file

The configuration file is used to set up all Web server behavior that is based on URLs. The default file is <span class="code">&lt;Gateway installation directory>/run\_time/http/server.ini</span>. The HTTP server automatically reloads the configuration when the file is modified.

Each line of the file must take the form:

command "argument" pattern \[&\]

Empty lines and lines beginning with "#" are ignored. Patterns can match file extensions (<span class="code">".txt"</span>, <span class="code">".htm"</span>), file names (<span class="code">"\*-test-\*.\*"</span>, <span class="code">"\*.tar.gz"</span>) or URLs (<span class="code">"/transfer/\*"</span>).

Configurable elements are:

-   Content types returned to the client for the accessed URL
-   Icons to use with directory listing entries
-   Files for which symbol substitutions must be performed dynamically

### Content types

The content type (also known as media type or MIME type) is a description of the data that the browser uses to determine how to process the received data.

Lines beginning with the <span class="code">AddType</span> command define the **content-type** header field returned to a browser.

<span class="code" style="font-weight: bold;">AddType</span> must be followed by a content type and patterns. If one of the patterns matches the URL, the content type is returned to the client.

#### Example

The following example forces browsers to display all files ending with <span class="code">.htm</span> or <span class="code">.html</span> as Web pages. All other pages must be prompted for downloading:

AddType   "text/html"  \*.htm  \*.html

AddType   "application/octet-stream"  \*

### Icons

When modifying templates for directory listings, you can display an icon for each kind of file present in the directory by using the <span class="code">AddIcon</span> command, followed by the icon URL and patterns. When a pattern matches the URL of a listed element (file or transfer), the symbol *@ICON@* of the listing template is replaced by the URL icon.

#### Example

In the following example, the listing template *@ICON@* symbol is replaced by:

-   <span class="code">/icons/text.gif</span> for file names that end with <span class="code">.txt</span>
-   <span class="code">/icons/binary.gif</span> for file names that end with anything else

AddIcon   "/icons/text.gif"  \*.txt

AddIcon   "/icons/binary.gif" \*

### Substituting symbols in files

The server can apply the same symbol substitution to downloaded files as the one applied to other elements such as error pages and listing templates.

To substitute symbols in files, add a line beginning with <span class="code">AddHandler</span>, followed by the kind of action to perform: *internal*, and then the patterns.

#### Example

In the following example, a symbol substitution is applied to every real file ending with <span class="code">.mhtm</span>.

AddHandler internal  \*.mhtm

<span id="Symbol_substitution"></span>

## Symbol substitution

Symbol substitution consists in replacing symbols (for example, %) read in a file with a value, which is then returned to the client. The substitutions apply to:

-   Directory listing template files
-   Error pages
-   Upload success and failure pages
-   Real files that match an <span class="code" style="font-weight: bold;">AddHandler</span> condition of the server configuration file. [Real files](../../../transfers_start_here/virtual_file_directory_start_here#Real_files) are files located under a [mounted directory](../../../transfers_start_here/virtual_file_directory_start_here#Mounted_directories).

#### Symbol substitution in HTML files

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Symbol</p>         </th>
<th class="HeadD-Column1-Header1"><p>Replaced by</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>%g</p>         </td>
         <td><p>Fragment that follows the marker at the end of a URL</p>         </td>
      </tr>
      <tr>
         <td><p>%G</p>         </td>
         <td><p>URL CGI parameters</p>         </td>
      </tr>
      <tr>
         <td><p>%h</p>         </td>
         <td><p>Returned HTTP code</p>         </td>
      </tr>
      <tr>
         <td><p>%H</p>         </td>
         <td><p>First line of the request</p>         </td>
      </tr>
      <tr>
         <td><p>%i</p>         </td>
         <td><p>CGI identification string (preceded by a "?"):</p>
<ul>
<li>user and password (?user=&amp;&amp;amp;password=)</li>
<li>session ID (?sessionid=)</li>
</ul>
<p>empty for other cases</p>         </td>
      </tr>
      <tr>
         <td><p>%I</p>         </td>
         <td><p>CGI identification string (%i without "?")</p>         </td>
      </tr>
      <tr>
         <td><p>%j</p>         </td>
         <td><p>User login</p>         </td>
      </tr>
      <tr>
         <td><p>%J</p>         </td>
         <td><p>User login encoded for URL</p>         </td>
      </tr>
      <tr>
         <td><p>%k</p>         </td>
         <td><p>User password</p>         </td>
      </tr>
      <tr>
         <td><p>%K</p>         </td>
         <td><p>User password encoded for URL</p>         </td>
      </tr>
      <tr>
         <td><p>%l</p>         </td>
         <td><p>Session ID (if any)</p>         </td>
      </tr>
      <tr>
         <td><p>%L</p>         </td>
         <td><p>Session ID encoded for URL</p>         </td>
      </tr>
      <tr>
         <td><p>%n</p>         </td>
         <td><p>Upload directory path</p>         </td>
      </tr>
      <tr>
         <td><p>%N</p>         </td>
         <td><p>Upload directory path encoded for URL</p>         </td>
      </tr>
      <tr>
         <td><p>%p</p>         </td>
         <td><p>Client HTTP method</p>         </td>
      </tr>
      <tr>
         <td><p>%P</p>         </td>
         <td><p>Client HTTP protocol</p>         </td>
      </tr>
      <tr>
         <td><p>%r</p>         </td>
         <td><p>Error number</p>         </td>
      </tr>
      <tr>
         <td><p>%R</p>         </td>
         <td><p>Error string</p>         </td>
      </tr>
      <tr>
         <td>%s         </td>
         <td>CSRF token (see <a href="#CSRF" class="MCXref xref">Cross-Site Request Forgery prevention</a>)         </td>
      </tr>
      <tr>
         <td>%S         </td>
         <td>CSRF token encoded for URL (see <a href="#CSRF" class="MCXref xref">Cross-Site Request Forgery prevention</a>)         </td>
      </tr>
      <tr>
         <td><p>%t</p>         </td>
         <td><p>Home directory for user</p>         </td>
      </tr>
      <tr>
         <td><p>%T</p>         </td>
         <td><p>Home directory for user encoded for URL</p>         </td>
      </tr>
      <tr>
         <td><p>%u</p>         </td>
         <td><p>URL decoded</p>         </td>
      </tr>
      <tr>
         <td><p>%U</p>         </td>
         <td><p>URL</p>         </td>
      </tr>
      <tr>
         <td><p>%v</p>         </td>
         <td><p>Home page for user</p>         </td>
      </tr>
      <tr>
         <td><p>%V</p>         </td>
         <td><p>Home page for user encoded for URL</p>         </td>
      </tr>
      <tr>
         <td><p>%%</p>         </td>
         <td><p>Character %</p>         </td>
      </tr>
      <tr>
         <td><p>%?</p>         </td>
         <td><p>Character ? -  if identification string is not empty or null</p>         </td>
      </tr>
      <tr>
         <td><p>%&amp;</p>         </td>
         <td><p>Character &amp; - if identification string is not empty or null</p>         </td>
      </tr>
   </tbody>
</table>

<span id="Http"></span>

## HTTP transcoding

In server mode, Gateway stores payloads with Content <span class="code">-Type=text/\*</span> with native line ending. In cases where the header is missing or has another value, the payload is treated as binary and is stored unchanged. The behavior is the same for both PUT and POST HTTP methods (request types). Only text entities using ASCII CR / LF characters as line endings are supported. If transferred text entities are encoded with a multi-byte character set that uses other characters for new lines, the payload will be corrupted.

<span id="Transfer_monitoring_and_log_levels"></span>

## Transfer monitoring and log levels

A monitoring option exists for the virtual file system directories. This option allows you to send and receive files in silent mode in these directories, without creating monitor Transfer Requests.

Disabling the monitoring option in directories where files can be downloaded several times without transfer controls (for example, size and progression indicators) can increase performance.

HTTP uses a log level (<span class="code">http\_log\_level</span>) to determine whether to add a request trace to the log file. This parameter is set in the <span class="code">conffile</span> during configuration or dynamically prior to starting the transfer.

You can set four levels:

-   **0**: no requests are logged
-   **1**: only monitor Transfer Requests are logged
-   **2**: all Transfer Requests are logged (monitored or unmonitored transfers)
-   **3**: (default) all requests are logged (including listings, and invalid requests)

<span id="HTTP_Strict_Transfer_Security"></span>

## HTTP Strict Transfer Security

The HTTP Strict Transfer Security (HSTS) allows Gateway to declare that compliant user agents should only interact with it using secure HTTP connections. Please refer to the RFC 6797 ([<span class="Hyperlink">https://tools.ietf.org/html/rfc6797</span>](https://tools.ietf.org/html/rfc6797)) for more details.

This is communicated by Gateway (acting as a server) via the “Strict-Transport-Security” HTTP response header field. Gateway supports the following directives: max-age and includeSubDomains

### Configuring the HTTP Strict Transfer Security header

The HSTS header can be configured using the following configuration parameters, using the <span class="code">peluconf</span> command:

<table>
   <tbody>
      <tr>
         <td><p>Parameter</p>         </td>
         <td><p>Description</p>         </td>
      </tr>
      <tr>
         <td><p><code>hsts_enabled</code></p>         </td>
         <td><p>Enables the inclusion of the HSTS header field in HTTPS responses.</p>         </td>
      </tr>
      <tr>
         <td><p><code>hsts_max_age</code></p>         </td>
         <td><p>Sets the <code>max-age</code> directive in the HSTS response header field to the specified value (default <em>0</em>).</p>         </td>
      </tr>
      <tr>
         <td><p><code>hsts_include_subdomains</code></p>         </td>
         <td><p>Enables the inclusion of the <code>includeSubDomains</code> directive in the HSTS response header field.</p>         </td>
      </tr>
   </tbody>
</table>

All the configuration parameters are in the <span class="code">ft\_http</span> configuration section. For example, use:

<span class="code">peluconf set -s ft\_http hsts\_enabled 1</span>

to enable the HSTS header field, and

`peluconf set -s ft_http hsts_max_age 86400`

to set the `max-age` directive to 24 hours.

> **Note:**
>
> Setting the hsts\_max\_age parameter to 0 will not disable the inclusion of the HSTS response header field. Instead, the HSTS header field will be sent with a max-age=0 directive. This will effectively remove the Gateway domain from the User Agent’s Known HSTS Hosts cache.

> **Note:**
>
> The HSTS response header field is only sent through HTTPS connections.

<span id="Identification_methods"></span>

## Identification methods

### How the Gateway server identifies the client

Before the Gateway HTTP server can execute an HTTP request and before it checks the URL provided, it must identify the connected party. The Gateway HTTP server retrieves the *user/password* pair and assigns CGate and Site parameters to it.

The Gateway HTTP server can collect identification parameters in various ways, but it can only be configured to use one identification method at a time. The Gateway HTTP server uses **Web** identification by default.

You can change identification parameters (*user*, *password*, and *sessionid*) in the [configuration menu](). This menu also enables you to configure session management (including, for example, the maximum number of created sessions).

Supported identification methods:

-   Web
-   CGI user and password
-   CGI session ID
-   Cookie user and password
-   Cookie session ID

### Web

Web identification, which can be called WWW authorization, is the only standard identification method defined by the HTTP protocol. The other methods presented in this topic are application-level mechanisms.

Summary of the Gateway HTTP server search mechanism and specific actions using the <span style="font-style: italic;">Web</span> identification method:

<table>
         
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Search method (in sequence)</p>         </th>
<th class="HeadE-Column1-Header1"><p>If element found</p>         </th>
<th class="HeadD-Column1-Header1"><p>If login fails</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Searches in the request header for an <span style="font-weight: bold;">Authorization</span> field and identifies the connected party from the parameters found</p>         </td>
         <td><p>Server logs in the user</p>         </td>
         <td><p>Server adds a negative response to the header and returns it with an error page informing the client that the credentials were not valid and prompting the user to try again</p>         </td>
      </tr>
      <tr>
         <td><p>Uses <span style="font-weight: bold;">anonymous</span> to log in</p>         </td>
      </tr>
   </tbody>
</table>

<span style="font-weight: bold;">Note:</span> Browsers typically try to access the requested URL anonymously the first time they connect to a server. If <span style="font-weight: bold;">anonymous</span> is not allowed to log in, the connected user is prompted for a login and password.

### CGI user and password

Clients can send these parameters in either or both of these elements:

-   URL, separated from the path by a question mark ("?")
-   Body of the request (POST requests only)

As the CGI parameters are user-level parameters, standard HTTP clients, such as browsers, do not send them on each request. It is the role of the Gateway server to send parameters to the HTML pages that are requested and to elements such as links and forms.

Summary of the Gateway HTTP server search mechanism and specific actions using the *CGI user and password* identification method:

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Search method (in sequence)</p>         </th>
<th class="HeadD-Column1-Header1"><p>If element found</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>User-level parameters received</p>         </td>
         <td><p>Server logs in the user</p>         </td>
      </tr>
      <tr>
         <td><p>Uses <strong>anonymous</strong> to log in</p>         </td>
      </tr>
   </tbody>
</table>

### CGI session ID

Using CGI session identification, it is the role of the Gateway HTTP server to send the *sessionid* parameter to the returned HTML pages.

Summary of the Gateway HTTP server search mechanism and specific actions using the *CGI session ID* identification method:

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Search method (in sequence)</p>         </th>
<th class="HeadD-Column1-Header1"><p>If found and login correct</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Searches for <em>user</em> and <em>password</em> parameters in the CGI parameters received</p>         </td>
         <td><p>Server uses them as credentials and if login succeeds, creates a session ID</p>         </td>
      </tr>
      <tr>
         <td><p>Searches for the <em>sessionid</em> parameter used to retrieve the <em>user</em> and <em>password</em> provided during session creation</p>         </td>
         <td><p>Server logs in the user</p>         </td>
      </tr>
      <tr>
         <td><p>Uses <strong>anonymous</strong> to log in</p>         </td>
      </tr>
   </tbody>
</table>

### Cookie user and password

Cookies are set for the whole directory tree (everything under path "<span class="code">/</span>"). No expiration dates are attached to them: Web browsers store cookies for the current session and automatically destroy them when the current session is closed.

Summary of the Gateway HTTP server search mechanism and specific actions using the <span style="font-style: italic;">Cookie user and password</span> identification method:

<table>
         
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Search method (in sequence)</p>         </th>
<th class="HeadE-Column1-Header1"><p>If element found</p>         </th>
<th class="HeadD-Column1-Header1"><p>If login fails</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>CGI parameter list</p>         </td>
         <td><p>Sever logs in the user</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>Cookies sent by the client</p>         </td>
         <td><p>Server returns two <strong>Set-Cookie</strong> fields with empty values in order to clear cookies set on the browser side</p>         </td>
      </tr>
      <tr>
         <td><p>Uses <strong>anonymous</strong> to log in</p>         </td>
         <td><p>Server returns two Set-Cookie header fields to the client. These fields request the client to store user and password within its cookies.</p>         </td>
         <td><p> </p>         </td>
      </tr>
   </tbody>
</table>

### Cookie session ID

Summary of the Gateway HTTP server search mechanism and specific actions using the <span style="font-style: italic;">Cookie session ID</span> identification method:

<table>
         
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Search method (in sequence)</p>         </th>
<th class="HeadE-Column1-Header1"><p>If element found and login correct</p>         </th>
<th class="HeadD-Column1-Header1"><p>If login fails</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Searches for user and password in the CGI parameters list</p>         </td>
         <td><p>Server logs in the user and creates a new session</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>Searches for a session ID in the cookies sent by the client</p>         </td>
         <td><p>Server logs in the user with the <em>user</em> and <em>password</em> values saved for this session ID</p>         </td>
         <td><p>Server returns a <span style="font-weight: bold;">Set-Cookie</span> field with an empty value in order to clear the cookie set on the browser side</p>         </td>
      </tr>
   </tbody>
</table>

When the Gateway HTTP server creates a new session, it returns a **Set-Cookie** field to the client. This field requests the client to store *sessionid* in its cookies list. When stored as a cookie, *sessionid* is automatically re-sent on each new request to the server.

### Partner-Dependant identification

The server determines the authentication method to use from the request headers sent by the client software. HTTP clients can log in using any of the authentication methods supported by Gateway. Note that the HTTP server accepts all the connections having a supported identification method.

### HTTP session ID limitation

You can limit the number of simultaneous opened sessions for a user.

A global configuration parameter, <span class="code">sid\_limit</span>, limits the number of sessions a user can have on the server.

Each time a user logs in, the value of this parameter is compared with the number of sessions registered for that user.

If the number of registered sessions is lower than the value of the configuration parameter, the user is allowed to login. Otherwise the login is refused.

You can find the <span class="code">sid\_limit</span> parameter in the Gateway [advanced parameters](../../../configuration_start_here/config_gateway_paras#Advanced_parameters).

This parameter is only taken into account if you have set the HTTP server identification **Method** to *Cookie session id* or *CGI session id* in the configuration menu.

<span id="Directory_listings"></span>

## Directory listings

An HTTP directory listing returns to the client an HTML page containing a list of links to elements (files and subdirectories) contained in the directory. A directory listing is performed when the accessed URL refers to a directory.

The Gateway virtual file system can contain the following elements:

-   **Directories**
-   **Files:** Only available if the directory refers to a real system directory
-   **Transfers:** References to Gateway transfers created in that directory. Only available if the directory is virtual (VFD). When displaying Gateway transfers, the server differentiates the available files in the directory listings as described in the following table:

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>If the Transfer type is:</p>         </th>
<th class="HeadD-Column1-Header1"><p>Then the connected party can:</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>available</p>         </td>
         <td><p>Retrieve the transfer (that is, the file) by clicking the transfer name, which is a hypertext link</p>         </td>
      </tr>
      <tr>
         <td><p>unavailable</p>         </td>
         <td><p>Display transfers in the current directory (similar to FTP). Transfers are displayed for informational purposes only and no hypertext links are required.</p>         </td>
      </tr>
   </tbody>
</table>

To fulfill these requirements, Gateway uses an HTML page to display directory contents. This page is called a listing template and includes elements that adapt the listing to the contents of the listed directory (for example, files, sub-directories, and transfers).

<span id="HTTP_listing_template_files"></span>

## HTTP listing template files

The listing template files contain the HTML formats used to list directories. First, the server must determine which file to use as a pattern. The file path to this pattern is specified in the:

-   CGate selected during login phase.  
    The value can be taken from one of the selected parent CGateGroups.
-   Default template file defined in the HTTP configuration part of Gateway.  
    You can modify this value using the configuration menu.

Once found and loaded, the server stores the patterns in memory and reloads them only when their files were modified. If no file is defined or if the file cannot be loaded, an error is returned to the client.

When the Responder (server) retrieves the listing pattern, it processes the listing in the following sequence:

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p>1</p>         </td>
         <td><p>Substitutes the global symbols (for example "%") in the page with their respective values (refer to <span style="font-style: italic;">Symbol substitution</span> later in this topic for more information)</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Searches for special tags (defined in <span style="font-style: italic;">Using special tags</span> below) and replaces them with each corresponding element of the listed directory</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Returns the dynamically-generated pages to the Initiator (client)</p>         </td>
      </tr>
   </tbody>
</table>

### Using special tags

Gateway recognizes the following special tags that you can use in the template files.

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Tag</p>         </th>
<th class="HeadD-Column1-Header1"><p>Comment</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>&lt;PARENT&gt;  &lt;/PARENT&gt;</p>         </td>
         <td><p>Text between these tags is displayed only if the listed directory is not "/".</p>         </td>
      </tr>
      <tr>
         <td><p>&lt;DIR&gt;  &lt;/DIR&gt;</p>         </td>
         <td><p>Text between these tags is duplicated for each directory in the current directory. The following special names are also replaced:</p>
<ul>
<li>@NAME@: directory name encoded for URL</li>
<li>@name@: directory name</li>
<li>@DATE@: Directory last modification date, per component: @DATE_Y@ (year), @DATE_M@ (month), @DATE_m@ (month as a decimal number), @DATE_D@ (day), @DATE_d@ (day as a decimal number), @DATE_T@: directory last modification time</li>
<li>@CONTENT@: number of files and number of available files from current directory. For example: 43 files (30 available)</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>&lt;REAL_FILE&gt;  &lt;/REAL_FILE&gt;</p>         </td>
         <td><p>Text between these tags is duplicated for each file in the directory. It is only available under <a href="../../../transfers_start_here/virtual_file_directory_start_here#Mounted_directories">mounted directories</a>.</p>
<p>The following special tags are also replaced:</p>
<ul>
<li>@FNAME@: file name encoded for URL</li>
<li>@fname@: file name</li>
<li>@DATE@: Directory last modification date, per component: @DATE_Y@ (year), @DATE_M@ (month), @DATE_m@ (month as a decimal number), @DATE_D@ (day), @DATE_d@ (day as a decimal number), @DATE_T@: directory last modification time</li>
<li>@SIZE@: file size</li>
<li>@ICON@: icon name associated with the directory path and filename, encoded for URL (for more information, refer to <a href="#Configuration_file">Configuration file</a>).</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>&lt;XFER_AVAIL&gt;  &lt;/XFER_AVAIL&gt;</p>         </td>
         <td><p>Text between these tags is duplicated for each available transfer in the current virtual directory. These tags are ignored inside real directories. The following special names are also replaced:</p>
<ul>
<li>@FNAME@: transfer file name encoded for URL</li>
<li>@fname@: transfer file name</li>
<li>@DATE@: Directory last modification date, per component: @DATE_Y@ (year), @DATE_M@ (month), @DATE_m@ (month as a decimal number), @DATE_D@ (day), @DATE_d@ (day as a decimal number), @DATE_T@: directory last modification time</li>
<li>@SIZE@: file size</li>
<li>@LOCAL_ID@: transfer local identifier</li>
<li>@STATE@: transfer status</li>
<li>@ICON@: icon name associated with the directory path and filename, encoded for URL (for more information, refer to <a href="#Configuration_file">Configuration file</a>).</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>&lt;XFER_UNAVAIL&gt;  &lt;/XFER_UNAVAIL&gt;</p>         </td>
         <td><p>Text between these tags is duplicated for each unavailable transfer in the current directory. These tags are ignored inside real directories. Substitutions described above apply here</p>         </td>
      </tr>
   </tbody>
</table>

#### Symbol encoding

As a mechanism for the prevention of XSS (Cross-Site Scripting), <span class="mc-variable suite_variables.GatewayName variable">Gateway</span> offers the possibility to encode HTML entities according to the context in which they are used. Special tags like @NAME@ and @FNAME@ are already encoded for an URI context; however a higher level of control is desirable. For example, the directory or file name can be used in a different context than that of an URI; such as a JavaScript/HTML context. The proper encoding can be done by using a special tag with no default encoding, and suffixing it with an encoding context specifier; e.g. @name@forJsHtml(), @fname@forJsHtml().

The following types of encoding can be used:

-   <span class="code">forUri()</span>  
    URI context
-   <span class="code">forUriComponent()</span>  
    URI component context
-   <span class="code">forCssUri()</span>  
    CSS URI context
-   <span class="code">forCssString()</span>  
    CSS string context
-   <span class="code">forJsSource()</span>  
    JavaScript source context
-   <span class="code">forJsAttribute()</span>  
    JavaScript attribute context
-   <span class="code">forJsBlock()</span>  
    JavaScript block context
-   <span class="code">forJsHtml()</span>  
    JavaScript/HTML context
-   <span class="code">forHtml() </span>  
    HTML context

<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Caution  </strong></span>         </td>
         <td>Make sure every special tag that could be controlled by an attacker is using HTML entity encoding, either explicit or implicit. See the example below, and the sample templates delivered with the product.         </td>
      </tr>
   </tbody>
</table>

> **Note:**
>
> For special tags with implicit encoding (@NAME@, @FNAME@), overwriting by specifying an explicit encoding is not supported.

For more detail regarding XSS (Cross-Site Scripting) and HTML entity encoding, please refer to the OWASP website:

-   <https://www.owasp.org/index.php/Cross-site_Scripting_(XSS)>"
-   <https://www.owasp.org/index.php/XSS_(Cross_Site_Scripting)_Prevention_Cheat_Sheet>"

(URLs are outside the <span class="mc-variable axway_variables.Company_Name variable">Axway</span> domain, and liable to change without notice).

#### Example

The following is an example of a directory listing template file.


    <HTML>
    <HEAD>
    <TITLE> %u </TITLE>
    </HEAD>
    <BODY>
    <H1> Index of %u </H1>
    <PARENT>
    <A href="">Parent directory (%n)</A> <BR>
    </PARENT>
    <HR> <PRE>
    <DIR>
    @DATE@ <A href="">@name@ .forHtml() /</A>
    </DIR>
    Date    Size    State       Name        Local Ident
    <REAL_FILE>
    @DATE@  @SIZE@             <A href="">@fname@ .forHtml() </A> </REAL_FILE>
    <XFER_AVAIL>
    @DATE@  @SIZE@  @STATE@    <A href="">@fname@ .forHtml() </A>  @LOCAL_IDENT@
    </XFER_AVAIL>
    <XFER_UNAVAIL>
    @DATE@  SIZE@   @STATE@     @fname@ .forHtml()     @LOCAL_IDENT@
    </XFER_AVAIL>
    </PRE> <HR>
    </BODY>
    </HTML>

<span id="Downloading_files"></span>

## Downloading files

To download a file, the client must send a GET (or POST) request with a URL that matches either a [real file](../../../transfers_start_here/virtual_file_directory_start_here#Real_files) or an available transfer.

As different transfers in a directory can have the same file name, you can use a [selection filter](#Restricting_selection__file_filters) to identify a specific transfer.

<span id="Uploading_files"></span>

## Uploading files

To upload a file onto the server, you must send the following elements:

-   Path name (directory in which to receive the transfer)
-   File name
-   File contents
-   Optional transfer parameters

The URL always contains the directory where the transfer is performed. The file name, however, is deduced as follows:

### Attributing file names when uploading

<table>
         
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>HTTP request method</p>         </th>
<th class="HeadE-Column1-Header1"><p>If URL format is</p>         </th>
<th class="HeadD-Column1-Header1"><p>Then the filename is</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>PUT</p>
<p>(not supported by browsers)</p>         </td>
         <td><p>file path (directory + filename)</p>         </td>
         <td><p>The last component of the file path</p>         </td>
      </tr>
      <tr>
         <td><p>directory name</p>         </td>
         <td><p>The value of the CGI parameter <em>filename</em></p>         </td>
      </tr>
      <tr>
         <td><p>POST</p>
<p>(content type must be "multipart/form-data")</p>         </td>
         <td><p>file path (directory + filename)</p>         </td>
         <td><p>The last component of the file path</p>         </td>
      </tr>
      <tr>
         <td><p>directory name</p>         </td>
         <td><p>The value of the CGI parameter <em>filename</em>, if present, or the name of the file sent (extracted from the form field used to send the file)</p>         </td>
      </tr>
   </tbody>
</table>

### Defining Axway MFT specific parameters

If the client is an Axway MFT product, optional parameters are available for more detailed communication. The parameters that you can set in the request include:

-   Application (**P\_APPLI**)
-   Remote destination of the transfer (**P\_DEST**)
-   Origin of the transfer (**P\_ORG**)
-   Message to attach to the transfer (**P\_MSG**)
-   URL to use in file substitution if file was correctly received (**success\_url**)
-   URL to use in symbol substitution if the file could not be retrieved (**failure\_url**)

These optional transfer parameters are sent through CGI parameters, either in the URL or in the request body (POST requests).

The syntax is:

**parameter=value**

Parameters are separated by an ampersand (&).

For examples of requests using the PUT and POST methods, refer to [Using HTTP in client mode - Sending files](http_using_in_client_mode.htm#Sending_files).

**Note:** The server checks and stores these parameters before the file transfer begins. This implies that they must be sent before the file itself. In other words, these parameters must be set either in the URL CGI parameters or in the CGI parameters preceding the file. If the reception results from a form submission, then the **file parameter must be positioned as the last parameter of the form**.

<span id="Restricting_selection__file_filters"></span>

## Restricting selection: File filters

As a virtual directory and a file name are insufficient to describe a Mailbox entry, Gateway provides an advanced file filter feature when downloading and listing requests.

A file filter comprises strings that contain <span class="code" style="font-weight: bold;">field=value</span> pairs. When you use HTTP, these strings are extracted from CGI parameters. Accepted values for the *field* portion of this pair are given in the table below:

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Field</p>         </th>
<th class="HeadD-Column1-Header1"><p>Accepted value</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>name</p>         </td>
         <td><p>Pattern matching paths and protocol filenames</p>         </td>
      </tr>
      <tr>
         <td><p>direction<sup>1</sup></p>         </td>
         <td><p>IN, OUT, or BOTH. Not case-sensitive</p>         </td>
      </tr>
      <tr>
         <td><p>date<sup>2</sup></p>         </td>
         <td><p>Exact date and time of the transfer, expressed in the format: <em>YYYYMMDDhhmmss</em></p>
<ul>
<li>Date fields (year, month, day of month) can be separated by "/" characters.</li>
<li>Time fields (hours, minutes, and seconds) can be separated by ":" characters. You can specify time without a date.</li>
</ul>
<p>Current day is considered the default date.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>end_before</strong> or <strong>endbefore<sup>2</sup></strong></p>         </td>
         <td><p>Date format (Transfers requested or performed earlier than the given date are not selected)</p>         </td>
      </tr>
      <tr>
         <td><p><strong>start_after</strong> or <strong>startafter<sup>2</sup></strong></p>         </td>
         <td><p>Date format (Transfers requested or performed later than the given date are not selected)</p>         </td>
      </tr>
      <tr>
         <td><p><strong>origin</strong> or <strong>org<sup>1</sup></strong></p>         </td>
         <td><p>Origin of the transfer</p>         </td>
      </tr>
      <tr>
         <td><p><strong>destination</strong> or <strong>dest<sup>1</sup></strong></p>         </td>
         <td><p>Destination of the transfer</p>         </td>
      </tr>
      <tr>
         <td><p>state<sup>1</sup></p>         </td>
         <td><p>List of states in Gateway format.</p>
<p>Each selected transfer must have one of the given states.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>mvs_state</strong> or <strong>mvsstate<sup>1</sup></strong></p>         </td>
         <td><p>List of states in MVS format.</p>
<p>Each selected transfer must have one of the given states.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>ftpcs_state</strong> or <strong>ftpcsstate</strong></p>         </td>
         <td><p>List of states in FTPCS format.</p>
<p>Each selected transfer must have one of the given states. The FTPCS state is the concatenation of the state in Gateway format and the state in InterPel MVS format.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>local_ident</strong> or <strong>localident</strong></p>         </td>
         <td><p>Long integer corresponding to the unique transfer local identifier</p>         </td>
      </tr>
      <tr>
         <td><p><strong>xfer_ident</strong> or <strong>xferident</strong></p>         </td>
         <td><p>Long integer corresponding to a transfer identifier</p>         </td>
      </tr>
   </tbody>
</table>

\(1\) For real entries and directories, these fields are ignored.

\(2\) These fields are compared to the last modification date of the file.

#### Example 1: Filtering by date

Downloading:

GET /transfer/out/file1.txt?org=site1&start\_after=20011205

#### Example 2: Filtering by transfer state

Directory listing:

GET /?name=\*.txt&state=IC&org=site1

<span style="font-weight: bold;">Notes:</span> When you retrieve a transfer, if several records match the request, the most recent one is returned.

#### Example 3: Filtering by file type

Requesting an incorrect file type:

GET /transfer/file?state=C

In this example, the user tries to download the most recent entry called **file** and in the state **canceled**. Although this is syntactically correct, Gateway does not allow downloading of canceled files and returns the following response:

404 Not found

<span id="Sort/Ord"></span>

## Sort/Order parameters

There are two parameters for sorting and setting the order of fields:

-   <span class="code">order (order=&lt;order\_field></span>)  
    If negative, the sorting order descends.  
    If positive, sorting order ascends.
-   <span class="code">sort </span>(<span class="code">sort=&lt;sort\_order\_type></span>)  
    Only one field can be chosen from the following:  
    "xfer\_type", "size", "date", "local\_id", "protocol", "rights", "direction", "state", "org", "dest", "remote", "fname", "xfer\_id", "route\_state", "perm", "appli", "msg", "code", "route\_from", "route\_to", "dup\_from", "param1", "param2", "user\_state", "local\_ident", "name", "xfer\_ident"

<span id="Gateway_specific_template_files"></span>

## Gateway specific template files

This section describes the HTML pages returned by the server when:

-   Errors occur
-   Uploads complete successfully
-   Uploads fail

<span id="Error_pages"></span>

### Error pages

Error pages are HTML files returned to the client when an error occurs. The file returned depends on both the type of error and the languages accepted by the connected client.

When Web browsers connect to a server, they typically send an HTTP header field named <span style="font-style: italic;">Accept Language</span> that contains an ordered list of accepted languages. The language used by the HTTP server is the first that matches one of its accepted languages. Use the parameter <span class="code" style="font-weight: bold;">err\_languages</span> to configure the server-accepted languages, whose default values are <span style="font-weight: bold;">en</span> \[English\], and <span style="font-weight: bold;">fr</span> \[French\]. If none of the client languages match, the first default error language is used (en).

Error files are located in the sub-directories of the error directory (parameter <span class="code" style="font-weight: bold;">err\_dir</span> whose default value is <span class="code">&lt;Gateway installation directory>/run\_time/http/pages</span>). The sub-directories must have the same name as the accepted languages. Default directories are:

-   <span class="code">&lt;Gateway installation directory>/run\_time/http/pages/en</span> for English
-   <span class="code">&lt;Gateway installation directory>/run\_time/http/pages/fr</span> for French

The following table lists the files used:

<table>
         
         
         
         
   
   <thead>
      <tr>
<th colspan="3" class="HeadD-Column1-Header1"><p>Error pages displayed by return codes</p>         </th>
      </tr>
      <tr>
<th class="HeadE-Column1-Header1"><p>Filename</p>         </th>
<th class="HeadE-Column1-Header1"><p>Return code</p>         </th>
<th class="HeadD-Column1-Header1"><p>Error description</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>ERR_BAD_REQUEST</p>         </td>
         <td><p>400</p>         </td>
         <td><p>The request contains invalid or missing parameters</p>         </td>
      </tr>
      <tr>
         <td><p>ERR_BAD_VERSION</p>         </td>
         <td><p>505</p>         </td>
         <td><p>Protocol version is not compatible</p>         </td>
      </tr>
      <tr>
         <td><p>ERR_FORBIDDEN</p>         </td>
         <td><p>403</p>         </td>
         <td><p>Requested action is forbidden (read, write, and so on)</p>         </td>
      </tr>
      <tr>
         <td><p>ERR_INTERNAL</p>         </td>
         <td><p>500</p>         </td>
         <td><p>An internal error occurred, for example a memory error, or a real or virtual file system access error</p>         </td>
      </tr>
      <tr>
         <td><p>ERR_NOT_FOUND</p>         </td>
         <td><p>404</p>         </td>
         <td><p>Could not find requested URL</p>         </td>
      </tr>
      <tr>
         <td><p>ERR_SESSIONID</p>         </td>
         <td><p>403</p>         </td>
         <td><p>Could not find received session ID (unknown or expired session)</p>         </td>
      </tr>
      <tr>
         <td><p>ERR_UNAUTHORIZED</p>         </td>
         <td><p>401 (Web auth)</p>         </td>
         <td><p>Invalid credentials</p>         </td>
      </tr>
   </tbody>
</table>

Error pages are loaded in memory the first time you access them. The HTTP server reloads them only when their files are modified. [Symbol substitutions](#Symbol_substitution) apply to these files.

### Upload success and failure pages

The following table summarizes the features of the upload success and failure pages:

<table>
         
         
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Page</p>         </th>
<th class="HeadE-Column1-Header1"><p>Returned when</p>         </th>
<th class="HeadE-Column1-Header1"><p>Associated HTTP return code</p>         </th>
<th class="HeadD-Column1-Header1"><p>Additional symbol substitutions</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Upload success</p>         </td>
         <td><p>File correctly received</p>         </td>
         <td><p>200</p>         </td>
         <td><p>"%x" replaced by the received CGI parameter <em>success_url</em>.</p>         </td>
      </tr>
      <tr>
         <td><p>Upload failure</p>         </td>
         <td><p>File incorrectly received</p>         </td>
         <td><p>500</p>         </td>
         <td><p>"%x" replaced by the received CGI parameter <em>failure_url</em>.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="Configuration_file"></span>

## Configuration file

The configuration file is used to set up all Web server behavior that is based on URLs. The default file is <span class="code">&lt;Gateway installation directory>/run\_time/http/server.ini</span>. The HTTP server automatically reloads the configuration when the file is modified.

Each line of the file must take the form:

command "argument" pattern \[&\]

Empty lines and lines beginning with "#" are ignored. Patterns can match file extensions (<span class="code">".txt"</span>, <span class="code">".htm"</span>), file names (<span class="code">"\*-test-\*.\*"</span>, <span class="code">"\*.tar.gz"</span>) or URLs (<span class="code">"/transfer/\*"</span>).

Configurable elements are:

-   Content types returned to the client for the accessed URL
-   Icons to use with directory listing entries
-   Files for which symbol substitutions must be performed dynamically

### Content types

The content type (also known as media type or MIME type) is a description of the data that the browser uses to determine how to process the received data.

Lines beginning with the <span class="code">AddType</span> command define the **content-type** header field returned to a browser.

<span class="code" style="font-weight: bold;">AddType</span> must be followed by a content type and patterns. If one of the patterns matches the URL, the content type is returned to the client.

#### Example

The following example forces browsers to display all files ending with <span class="code">.htm</span> or <span class="code">.html</span> as Web pages. All other pages must be prompted for downloading:

AddType   "text/html"  \*.htm  \*.html

AddType   "application/octet-stream"  \*

### Icons

When modifying templates for directory listings, you can display an icon for each kind of file present in the directory by using the <span class="code">AddIcon</span> command, followed by the icon URL and patterns. When a pattern matches the URL of a listed element (file or transfer), the symbol *@ICON@* of the listing template is replaced by the URL icon.

#### Example

In the following example, the listing template *@ICON@* symbol is replaced by:

-   <span class="code">/icons/text.gif</span> for file names that end with <span class="code">.txt</span>
-   <span class="code">/icons/binary.gif</span> for file names that end with anything else

AddIcon   "/icons/text.gif"  \*.txt

AddIcon   "/icons/binary.gif" \*

### Substituting symbols in files

The server can apply the same symbol substitution to downloaded files as the one applied to other elements such as error pages and listing templates.

To substitute symbols in files, add a line beginning with <span class="code">AddHandler</span>, followed by the kind of action to perform: *internal*, and then the patterns.

#### Example

In the following example, a symbol substitution is applied to every real file ending with <span class="code">.mhtm</span>.

AddHandler internal  \*.mhtm

<span id="CSRF"></span>

## Cross-Site Request Forgery prevention

As a prevention mechanism against Cross-Site Request Forgery (CSRF) attacks, Gateway is using a token-based mitigation approach. This mechanism is activated using the `csrf_token_active `configuration parameter:

`peluconf set -s ft_http csrf_token_active 1`

When activating the CSRF prevention mechanism, the HTTP templates must be updated to include the CSRF token for all state changing requests. The CSRF token itself is generated by Gateway and will be substituted in the HTTP template using a special symbol (`%s` for the non-encoded, and `%S` for the URI-encoded form - see the Symbol Substitution in HTML files section above). For example, an upload form could include the CSRF token as a hidden field:

`<INPUT type=hidden name="token" value="%s" />`

For more detail regarding CSRF (Cross-Site Request Forgery), please refer to the OWASP website:

-   <https://owasp.org/www-community/attacks/csrf>
-   <https://cheatsheetseries.owasp.org/cheatsheets/Cross-Site_Request_Forgery_Prevention_Cheat_Sheet.html>

(URLs are outside the Axway domain, and liable to change without notice).

Related topics

[Configuring protocols: HTTP options](../../../configuration_start_here/config_protocols_about/config_http_options)

[About HTTP](http_about.htm)

[Using HTTP in client mode](http_using_in_client_mode.htm)

[About CGates and CGateGroups](../../../managing_partners_start_here/cgates_start_here)

[About Virtual File Directories](../../../transfers_start_here/virtual_file_directory_start_here)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
