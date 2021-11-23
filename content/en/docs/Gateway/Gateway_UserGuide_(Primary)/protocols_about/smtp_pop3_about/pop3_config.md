{
    "title": "Configuring the POP3 environment",
    "linkTitle": "Configuring POP3",
    "weight": "280"
}{{< Gateway/componentlongname  >}}: Protocols

[About POP3 configuration](#About_the_POP3_configuration)

[Connecting to POP3 server](#Connecting_to_POP3_server)

[Retrieving emails](#Retrieving_emails)

[POP3 specific user exits](#exit_routines)

[Types of email recognized by Gateway](#email_types)

<span id="About_the_POP3_configuration"></span>

## About POP3 configuration

You must create the following Gateway objects if they do not already exist:

-   Remote Site
-   Application

You can use either the GUI or the `peladm` online command to create these objects.

### Defining a Remote Site

The Remote Site represents the POP3 server to contact. You must define one Remote Site for each email account on the POP3 server.

<span id="Defining_an_Application"></span>

### Defining an Application

An Application is a set of parameters that describes the structure of a file in terms of local storage and transfer format.

In addition to defining the formats you can use to receive a file, the Application associated with a transfer indicates to Gateway if it must extract a file from the email or not.

<span id="Connecting_to_POP3_server"></span>

## Connecting to POP3 server

<span id="Automatic_Polling"></span>

### Automatic Polling

Gateway retrieves emails by polling the POP3 server at defined intervals. To activate this polling mechanism, set the Polling Options in the [Remote Site POP3 tab](../../../managing_partners_start_here/sites_start_here/managing_remote_sites/remote_site_pop3_tab).

<span id="Dynamically_managing_a_polling_cycle"></span>

### Dynamically managing a polling cycle

While Gateway is running, it polls the POP3 server at the interval that you set in the Remote Site (**`polling_interval`** parameter).If necessary you can suspend polling for server maintenance, troubleshooting, or diagnostics purposes.

To suspend or resume the polling activity on a Remote Site, use the `pelctl` commands:

**Note:** These commands do not affect transfers that are already initiated or in progress.

-   To suspend polling, use<span class="code" style="font-weight: bold;"> pelctl stop\_site  –a pop3\_&lt;site\_name>  –pm</span>
-   To resume polling, use<span class="code" style="font-weight: bold;"> pelctl start\_site  –a pop3\_&lt;site\_name>  –pm</span>

The change to the polling status is confirmed in the log file.

<span id="Retrieving_emails"></span>

## Retrieving emails

The principal elements of email retrieval in Gateway are:

-   Authentication mechanism:
    -   AUTO
    -   BASIC
    -   APOP \[RFC1939\]
    -   CRAM
-   Automatic and periodic polling of POP servers to retrieve email
-   Capacity to suspend and resume an email retrieval session
-   Automatic deletion of email from the server after a POP3 session

### How Gateway retrieves email

Gateway examines the MIME header of an incoming email and, if identified, creates the Transfer Request.

For every type of email received, except acknowledgment requests (DSN/MDN), a Transfer Request (of the Initiator/Receiver type) is created for possible monitoring or routing.

Otherwise Gateway processes the retrieved email according to the email type identified from the MIME header.

### Rejecting the Transfer Request

If there is an error in parsing the MIME header, or a duplicate email is detected during the retrieval process, Gateway rejects the Transfer Request (if already created) and marks it as *CANCELED*. The status of the email is determined by the value of the ERROR\_MAIL\_DISPOSAL parameter for the Site in question.

The table below describes how Gateway handles the *CANCELED* Transfer Request.

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">ERROR_MAIL_DISPOSAL value         </th>
<th class="HeadD-Column1-Header1">Action         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>LEAVE</p>         </td>
         <td><p>The email is ignored and left on the POP3 server</p>         </td>
      </tr>
      <tr>
         <td><p>DELETE</p>         </td>
         <td><p>The email is deleted from the POP3 server</p>         </td>
      </tr>
      <tr>
         <td><p>RECOVER</p>         </td>
         <td><p>A new Transfer Request is created with the <span class="code">extract_file</span> parameter set to <em>No.</em> The email (header and body) is retrieved (still encoded) with the identifying parameters:</p>
<ul>
<li>PROTOCOL=POP3</li>
<li>ORIGINATOR=POP3 Site identifier</li>
<li>DESTINATION=login user identification</li>
<li>FILE_NAME=RECOVER | DUPLICATE</li>
<li>FILE_TYPE=DATA</li>
<li>XFER_ID=XFER ident.local_ident</li>
</ul>         </td>
      </tr>
   </tbody>
</table>

<span id="extract_file_parameter"></span>

#### extract\_file parameter

If Gateway accepts the Transfer Request, it uses the <span class="code" style="font-weight: bold;">extract\_file</span> parameter to determine how to process the email. The value of this parameter is read from the objects below in the following order of priority:

-   Application: returned by the exit function <span style="font-weight: bold;">ExitPop3GetAppli</span>
-   Remote Site: for the POP3 server in progress

<span id="exit_routines"></span>

## POP3 specific user exits

Gateway supplies the specific exit routine <span style="font-weight: bold;">[ExitPop3GetAppli()](../../../customizing_gw_about/user_exits_about/user_exits_internal#ExitPop3GetAppli)</span> for the POP3 protocol.

This exit allows you to select an Application to apply to the current transfer. Input and output parameters are described in the following table:

<table>
         
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Parameter         </th>
<th class="HeadE-Column1-Header1">Name         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Input</p>         </td>
         <td><p>xfer.proto.originator</p>         </td>
         <td><p>Protocol originator</p>         </td>
      </tr>
      <tr>
         <td><p>xfer.proto.destination</p>         </td>
         <td><p>Protocol destination</p>         </td>
      </tr>
      <tr>
         <td><p>xfer.proto.from</p>         </td>
         <td><p>Email From field</p>         </td>
      </tr>
      <tr>
         <td><p>xfer.proto.to</p>         </td>
         <td><p>Email To field</p>         </td>
      </tr>
      <tr>
         <td><p>xfer.proto.xfer_ident</p>         </td>
         <td><p>Message_id</p>         </td>
      </tr>
      <tr>
         <td><p>xfer.sup.mail_subject</p>         </td>
         <td><p>Email subject</p>         </td>
      </tr>
      <tr>
         <td><p>Output</p>         </td>
         <td><p>xfer.sup.application</p>         </td>
         <td><p>Application to use</p>         </td>
      </tr>
      <tr>
         <td><p>return code = 1</p>         </td>
         <td><p>No Application is selected, use the default defined in the Site</p>         </td>
      </tr>
      <tr>
         <td><p>return code = 0</p>         </td>
         <td><p>Use the Application in the return parameter</p>         </td>
      </tr>
   </tbody>
</table>

<span id="email_types"></span>

## Types of email recognized by Gateway

Parsing the contents of the MIME header of the email, Gateway can identify four kinds of email:

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Email type         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>XFER (<span class="code">extract_file</span>=yes: single file attached)</p>         </td>
         <td><p><span style="font-weight: bold;">Envelope for a file transfer</span>: a multi-part email with an attachment. The body of the message (optional), up to 254 characters, is considered a transfer user message. The first attachment<sup>*</sup> is considered to be the transferred file.</p>         </td>
      </tr>
      <tr>
         <td><p>MSG (<span class="code">extract_file</span>=yes: no file attached)</p>         </td>
         <td><p><span style="font-weight: bold;">User Message</span>: a one-part email without an attachment. The body of the message is considered to be the transferred message.</p>         </td>
      </tr>
      <tr>
         <td><p>XFER (<span class="code">attach_extract_file</span>=no)</p>         </td>
         <td><p>Formatted email</p>         </td>
      </tr>
      <tr>
         <td><p>DNS/MDN</p>         </td>
         <td><p><span style="font-weight: bold;">acknowledgment</span>: Delivery Status Notification (DSN)/ /Mail Disposition Notification (MDN).</p>         </td>
      </tr>
   </tbody>
</table>

<span style="font-weight: bold;">(\*)</span> Gateway does not accept emails with more than one attachment.

Related topics

[About Site objects](../../../managing_partners_start_here/sites_start_here)

[Remote Site POP3 tab](../../../managing_partners_start_here/sites_start_here/managing_remote_sites/remote_site_pop3_tab)

[About Applications](../../../transfers_start_here/parameters_start_here/applications_start_here)

[Internal user exits](../../../customizing_gw_about/user_exits_about/user_exits_internal)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
