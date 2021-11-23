{
    "title": "Using HTTP in client mode",
    "linkTitle": "Using HTTP in client mode",
    "weight": "210"
}{{< Gateway/componentlongname  >}}: Protocols

[About the HTTP client](#About_the_HTTP_client)

[Client login: Identification methods](#Client_login)

[Sending files](#Sending_files)

[Retrieving files](#Retrieving_files)

[Retrieving a directory listing](#Retrieving_a_directory_listing)

<span id="About_the_HTTP_client"></span>

## About the HTTP client

The HTTP client is used to perform transfers where Gateway is the connection Initiator. This includes the following tasks:

-   Sending a file to a server
-   Retrieving a file from a server
-   Retrieving a directory listing from a server

<span id="Client_login"></span>

## Client login: Identification methods

You must set the login parameters for the [Remote Site](../../../managing_partners_start_here/sites_start_here/managing_remote_sites) to be used to connect to the HTTP server.

For information on configuration, refer to [Configuring protocols: HTTP options](../../../configuration_start_here/config_protocols_about/config_http_options).

Supported identification methods are described in the following table:

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Identification method</p>         </th>
<th class="HeadE-Column1-Header1"><p>Elements sent in Transfer Request</p>         </th>
<th class="HeadD-Column1-Header1"><p>Comment</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Anonymous</p>         </td>
         <td><p>ID and password (set in the Remote Site) are not sent.</p>         </td>
         <td><p>–</p>         </td>
      </tr>
      <tr>
         <td><p>CGI</p>         </td>
         <td><p>ID and password values are sent using the CGI parameters <em>user</em> and <em>password</em>.</p>         </td>
         <td><p>Parameter names (<em>user</em> and <em>password</em>) are the same as those used by the HTTP server. You can modify these parameter names in the Gateway configuration menu.</p>         </td>
      </tr>
      <tr>
         <td><p>Web</p>         </td>
         <td><p>ID and password values are sent using the standard HTTP identification header field (Authorization).</p>         </td>
         <td><p>–</p>         </td>
      </tr>
      <tr>
         <td><p>Cookies</p>         </td>
         <td><p>If a login request is sent, the cookies returned with the login response are sent back to the server with each Transfer Request, on condition that the HTTP session is not closed.</p>         </td>
         <td><p>Received cookies are stored with their directory settings. They are only sent back if the Transfer Request is performed under the defined directory. Expiration dates are not taken into account.</p>         </td>
      </tr>
      <tr>
         <td>NTLM         </td>
         <td>NTLM authentication is used to connect to the HTTP server.         </td>
         <td>see section <em>NTLM and NTLMv2 authentication</em> below.         </td>
      </tr>
   </tbody>
</table>

### NTLM and NTLMv2 authentication

NTLM and NTLMv2 authentication is supported in HTTP client mode.

<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Caution  </strong></span>         </td>
         <td>Only the authentication feature of NTLM is supported. Other NTLM features like session security are not supported; also, LM and LM2 authentication packages are not used. Depending on the Security Policies of the HTTP server, it is possible to require NTLM features not supported by Gateway; in this case, the NTLM authentication could <strong>fail</strong> or become <strong>unstable</strong>.         </td>
      </tr>
   </tbody>
</table>

The NTLM version (NTLM or NTLMv2) cannot be negotiated between the client (Gateway) and the remote HTTP server; instead, it must be configured at both ends. With Gateway, this is done using the command line, for example:

`peladm update_site -a REMOTE_SITE -ntlm_version NTLM2`

By default, NTLMv2 is used.

### Login request

An optional login request is performed the first time Gateway initiates an HTTP connection with a Remote Site. Login applies to both incoming and outgoing transfers.

The login request is performed under two conditions:

-   **Cookies** client identification method must be in use
-   Login path must not be empty (otherwise login is not performed, which is equivalent to performing the transfer anonymously)

Login requests are used with server CGI scripts that return a cookie to the Gateway client. For each transfer performed after the login phase, this cookie is sent back to the server. As a result, the login path must be the URL path to the server CGI script that identifies Gateway and returns the cookie, for example, "<span class="code">/cgi-bin/login.php</span>". You can also configure the HTTP method to use, either GET or POST.

On login, the *ID* and *password* parameters that you set in the <span style="font-weight: bold;">ID/Password to send</span> field of the Remote Site are sent using the CGI parameters *user* and *password*. You can add optional CGI parameters to the login request.

If login succeeds, the cookies returned by the server are stored in memory and sent with each Transfer Request. Once Gateway no longer needs to perform any more transfers with the server, the connection is closed and the cookies are deleted.

#### Example

Configuration for SERVER1 as a Remote Site

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Site parameter</p>         </th>
<th class="HeadD-Column1-Header1"><p>Value</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>IP address or machine name</p>         </td>
         <td><p>webserver1</p>         </td>
      </tr>
      <tr>
         <td><p>ID to send</p>         </td>
         <td><p>login_1</p>         </td>
      </tr>
      <tr>
         <td><p>password to send</p>         </td>
         <td><p>password_1</p>         </td>
      </tr>
      <tr>
         <td><p>identification method</p>         </td>
         <td><p>Cookies</p>         </td>
      </tr>
      <tr>
         <td><p>login path</p>         </td>
         <td><p>/cgi-bin/login.php</p>         </td>
      </tr>
      <tr>
         <td><p>HTTP method</p>         </td>
         <td><p>POST</p>         </td>
      </tr>
      <tr>
         <td><p>login CGI parameters</p>         </td>
         <td><p>client=Gateway&amp;site=SERVER1</p>         </td>
      </tr>
   </tbody>
</table>

A file transfer with SERVER1 will trigger a login request formatted as follows:


    POST /cgi-bin/login.php HTTP/1.0
    Content-Length: 64
    Host: webserver1
    Content-Type: application/x-www-form-urlencoded
    User-Agent: Gateway/680
    Connection: Keep-alive
     
    user=login_1&password=password_1&client=Gateway&site=SERVER1

<span id="Sending_files"></span>

## Sending files

When you use the HTTP protocol to send a file as Initiator, Gateway sends the following parameters from the Remote Site representing the Responder:

-   Connection parameters (including <span class="code">dest\_address</span>, and <span class="code">comm\_type</span>)
-   Identification method to use and all its related parameters (including <span class="code">login\_type</span>, <span class="code">login\_ident</span> and <span class="code">login\_password</span>).
-   <span class="mc-variable axway_variables.Company_Name variable">Axway</span> MFT specific transfer attributes, if the remote server is an <span class="mc-variable axway_variables.Company_Name variable">Axway</span> MFT product (<span class="code">is\_monitor</span>)

Gateway can also send additional CGI parameters specified in the Remote Site <span class="code">snd\_msg</span> parameter.

### Axway MFT specific transfer attributes

The table below describes the Transfer Request parameters required by Gateway:

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Parameter</p>         </th>
<th class="HeadD-Column1-Header1"><p>Description</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>(file_component)</p>         </td>
         <td><p>Local file attributes including file name and path</p>         </td>
      </tr>
      <tr>
         <td><p>(dir_name/file_name)</p>         </td>
         <td><p>URL path to send:</p>
<ul>
<li>directory name (POST)</li>
<li>directory name plus the file name (PUT)</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>(request_method)</p>         </td>
         <td><p>HTTP method to use: POST or PUT</p>
<p>The request method to use depends on the remote server configuration.</p>         </td>
      </tr>
      <tr>
         <td><p>P_ORG (org)</p>         </td>
         <td><p>Transfer parameters</p>
<p>When available, these parameters are sent if the Remote Site is configured as an Axway MFT product (<span class="code">is_monitor</span>).</p>         </td>
      </tr>
      <tr>
         <td><p>P_DEST (dest)</p>         </td>
      </tr>
      <tr>
         <td><p>P_APPLI (appli)</p>         </td>
      </tr>
      <tr>
         <td><p>P_MSG (snd_msg)</p>         </td>
      </tr>
      <tr>
         <td><p>(ftp_command)</p>         </td>
         <td><p>Additional CGI parameters to send</p>         </td>
      </tr>
   </tbody>
</table>

### Examples of sending a file using the POST method

#### Example 1: CGI login type

The following example creates a Remote Site representing the server and:

-   Defines the remote partner as an Axway MFT product
-   Defines the login type as CGI
-   Sends a file with the POST command


    peladm create_site  -a LOOP_HTTP1  -pr HTTP  -check_login_ident LOOP_HTTP1  
    -partner_loc_alias LOC_SITE  -dest_address localhost/8080  -is_monitor Y  
    -login_ident user  -login_password passwd  -login_type CGI  
    -snd_msg "site=loop_http1"
     
    peltrans  -da LOOP_HTTP1  -dest AxwayGW  -appli FTP_B  -dir O  -mode I  
    -file_name "machine.txt"  -fc ./machine  -snd_msg "message 1"  
    -ftp_command "fc=machine"  -request_method POST

This command sends the following request:

POST / HTTP/1.0

Content-Length: 1397

Host: localhost:8080

Content-Type: multipart/form-data;

boundary=-----LOC\_SITE-AxwayGW-20020304160043-883517092697405393766851741526

User-Agent: Gateway/680

Connection: Keep-alive

#### Example 2: Cookies login type

The following example creates a Remote Site representing the server and:

-   Defines the login path for the login request (*login\_url*)
-   Selects the login type *Cookies*
-   Selects the GET login method for the login request
-   Selects the POST request method for the transfer


    peladm create_site  -a LOOP_HTTP1  -pr HTTP  -check_login_ident LOOP_HTTP1  
    -partner_loc_alias LOC_SITE  -dest_address localhost/8080  -is_monitor N  
    -login_ident user  -login_password passwd  -login_type Cookies  
    -login_url "/cgi-bin/login.php"  -login_method GET  
    -snd_msg "site=loop_http1"
     
    peltrans  -da LOOP_HTTP1  -dest AxwayGW  -appli FTP_B  -dir O  -mode I  
    -request_method POST -file_name "machine.txt"  -fc ./machine  
    -snd_msg "message 1"  -ftp_command "fc=machine"

This command sends the following requests:

GET /cgi-bin/login.php?user=user&password=passwd HTTP/1.0

Host: localhost:8080

User-Agent: Gateway/680

Connection: Keep-alive

and

POST / HTTP/1.0

Content-Length: 641

Cookie: sessionid=Synchrony3C839199A725636418

Host: localhost:8080

Content-Type: multipart/form-data;

     boundary=-----LOC\_SITE-AxwayGW-20020304161231-134212818461445708661152709889

User-Agent: Gateway/680

Connection: Keep-alive

### Examples of sending a file using the PUT method

#### Example 1: CGI login type

The following example creates a Remote Site representing the server and:

-   Defines the remote partner as an Axway MFT product
-   Defines the login type as CGI
-   Sends a file with the PUT command


    peladm create_site
     -a LOOP_HTTP1 -pr HTTP -check_login_ident LOOP_HTTP1
     -partner_loc_alias LOC_SITE -dest_address localhost/8080
     -is_monitor Y -login_ident user -login_password passwd 
    -login_type CGI  -snd_msg "site=loop_http1"
     
    peltrans
     -da LOOP_HTTP1 -dest AxwayGW -appli FTP_B -dir O -mode I
     -file_name "machine.txt" -fc ./machine -snd_msg "message 1"
     -ftp_command "fc=machine" -request_method PUT

This command sends the following request:

PUT /machine.txt?user=user&password=passwd&P\_DEST=AxwayGW&P\_ORG=LOC\_SITE&

     P\_APPLI=FTP\_B&P\_MSG=message%201&fc=machine&site=loop\_http1 HTTP/1.0

Content-Length: 4

Host: localhost:8080

User-Agent: Gateway/680

Connection: Keep-alive

#### Example 2: Cookies login type

The following example creates a Remote Site representing the server and:

-   Defines the login path for the login request (*login\_url*)
-   Selects the login type *Cookies*
-   Selects the POST login method for the login request
-   Selects the PUT request method for the transfer


    peladm create_site
     -a LOOP_HTTP1 -pr HTTP -check_login_ident LOOP_HTTP1
     -partner_loc_alias LOC_SITE -dest_address localhost/8080
     -is_monitor N -login_ident user -login_password passwd
     -login_type Cookies -login_url "/cgi-bin/login.php" -login_method POST 
    -snd_msg "site=loop_http1"
     
    peltrans
     -da LOOP_HTTP1 -dest AxwayGW -appli FTP_B -dir O -mode I
     -file_name "machine.txt" -fc ./machine -snd_msg "message 1"
     -ftp_command "fc=machine" -request_method PUT

This command sends the following request:

POST /cgi-bin/login.php HTTP/1.0

Content-Length: 25

Host: localhost:8080

Content-Type: application/x-www-form-urlencoded

User-Agent: Gateway/680

Connection: Keep-alive

user=user&password=passwd

and

PUT /machine.txt?fc=machine&site=loop\_http1 HTTP/1.0

Content-Length: 4

Cookie: sessionid=Synchrony3C8399622152645421

Host: localhost:8080

User-Agent: Gateway/680

Connection: Keep-alive

<span id="Retrieving_files"></span>

## Retrieving files

When you use the HTTP protocol to retrieve a file from a server, Gateway extracts the following parameters from the Remote Site:

-   Connection parameters (<span class="code">dest\_address</span>, <span class="code">comm\_type</span>)
-   Identification method to use and all its related parameters (<span class="code">login\_type</span>, <span class="code">login\_ident</span>, <span class="code">login\_password</span>)
-   Additional CGI parameters in Remote Site (<span class="code">snd\_msg</span>)

Gateway extracts the parameters from each Transfer Request as described in the Axway MFT specific transfer attributes table.

### Examples of retrieving a file using the POST method

#### Example 1: CGI login type

The following example creates a Remote Site representing the server and:

-   Defines the login type as CGI
-   Retrieves a file with the POST command


    peladm create_site
     -a LOOP_HTTP1 -pr HTTP -dest_address localhost/8080
     -check_login_ident LOOP_HTTP1 -login_ident user -login_password passwd
     -login_type CGI  -snd_msg "site=loop_http1"
     
    peltrans
     -da LOOP_HTTP1 -dest AxwayGW -appli FTP_B -dir I -mode I
     -file_name "dispo.txt" -fc retrieve.txt dir_name /dispo -request_method POST

This command sends the following request:

POST /dispo/dispo.txt HTTP/1.0

Content-Length: 41

Host: localhost:8080

Content-Type: application/x-www-form-urlencoded

User-Agent: Gateway/680

Connection: Keep-alive

user=user&password=passwd&site=loop\_http1

#### Example 2: Cookies login type

The following example creates a Remote Site representing the server and:

-   Defines the login path for the login request (*login\_url*)
-   Selects the login type *Cookies*
-   Selects the GET login method for the login request
-   Selects the POST request method for the Transfer Request


    peladm create_site
     -a LOOP_HTTP1 -pr HTTP -dest_address localhost/8080
     -check_login_ident LOOP_HTTP1 -login_ident user -login_password passwd
     -login_type Cookies -login_url "/cgi-bin/login.php" -login_method GET  
    -snd_msg "site=loop_http1"
     
    peltrans
     -oa LOOP_HTTP1 -dest AxwayGW -appli FTP_B -dir I -mode I
     -file_name "dispo.txt" -fc retrieve.txt dir_name /dispo
     -request_method POST

This command sends the following requests:

GET /cgi-bin/login.php?user=user&password=passwd HTTP/1.0

Host: localhost:8080

User-Agent: Gateway/680

Connection: Keep-alive

and

POST /dispo/dispo.txt HTTP/1.0

Content-Length: 15

Cookie: sessionid=Synchrony3C84FA4244304328

Host: localhost:8080

Content-Type: application/x-www-form-urlencoded

User-Agent: Gateway/680

Connection: Keep-alive

### Examples of retrieving a file using the GET method

#### Example 1: CGI login type

The following example creates a Remote Site representing the server and:

-   Defines the login type as CGI
-   Retrieves a file with the GET command


    peladm create_site
     -a LOOP_HTTP1 -pr HTTP -dest_address localhost/8080
     -check_login_ident LOOP_HTTP1 -login_ident user -login_password passwd
     -login_type CGI  -snd_msg "site=loop_http1"
     
    peltrans
     -oa LOOP_HTTP1 -dest AxwayGW -appli FTP_B -dir I -mode I
     -file_name "dispo.txt" -fc retrieve.txt dir_name /dispo
     -request_method GET

This command sends the following request:

GET /dispo/dispo.txt?user=user&password=passwd&site=loop\_http1 HTTP/1.0

Host: localhost:8080

User-Agent: Gateway/680

Connection: Keep-alive

#### Example 2: Cookies login type

The following example:

-   Creates a Remote Site representing the server
-   Defines the login path for the login request (*login\_url*)
-   Selects the login type *Cookies*
-   Selects the POST login method for the login request
-   Selects the GET request method for the Transfer Request


    peladm create_site
     -a LOOP_HTTP1 -pr HTTP -dest_address localhost/8080
     -check_login_ident LOOP_HTTP1 -login_ident user -login_password passwd
     -login_type Cookies -login_url "/cgi-bin/login.php" -login_method POST  
    -snd_msg "site=loop_http1"
     
    peltrans
     -oa LOOP_HTTP1 -dest AxwayGW -appli FTP_B -dir I -mode I
     -file_name "dispo.txt" -fc retrieve.txt dir_name /dispo
     -request_method GET

This command sends the following requests:

POST /cgi-bin/login.php HTTP/1.0

Content-Length: 25

Host: localhost:8080

Content-Type: application/x-www-form-urlencoded

User-Agent: Gateway/680

Connection: Keep-alive

user=user&password=passwd

and

GET /dispo/dispo.txt?site=loop\_http1 HTTP/1.0

Cookie: sessionid=Synchrony3C85E636C6730196

Host: localhost:8080

User-Agent: Gateway/680

Connection: Keep-alive

<span id="Retrieving_a_directory_listing"></span>

## Retrieving a directory listing

When you use the HTTP protocol to retrieve a directory listing from a server, the <span class="code" style="font-weight: bold;">peltrans</span> parameter <span class="code" style="font-weight: bold;">type</span> must be set to <span class="code" style="font-weight: bold;">dir</span>.

#### Example of retrieving a directory listing

The following example:

-   Creates a Remote Site representing the server
-   Defines the login type as CGI
-   Retrieves a directory listing with the GET command


    peladm create_site
     -a LOOP_HTTP1 -pr HTTP -dest_address localhost/8080
     -check_login_ident LOOP_HTTP1 -login_ident user -login_password passwd
     -login_type CGI  -snd_msg "site=loop_http1"
     
    peltrans
     -oa LOOP_HTTP1 -dest AxwayGW -appli FTP_B -dir I -mode I
     type dir dir_name /dispo -request_method GET

This command sends the following request:

GET /dispo/dispo.txt?user=user&password=passwd&site=loop\_http1 HTTP/1.0

Host: localhost:8080

User-Agent: Gateway/680

Connection: Keep-alive

Related topics

[About HTTP](http_about.htm)

[Configuring the HTTP environment](http_config.htm)

[Working with Remote Sites](../../../managing_partners_start_here/sites_start_here/managing_remote_sites)

[Configuring protocols: HTTP options](../../../configuration_start_here/config_protocols_about/config_http_options)

[Using HTTP in server mode](http_using_in_server_mode.htm)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
