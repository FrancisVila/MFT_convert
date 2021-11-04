{
    "title": "Configuring the SMTP environment",
    "linkTitle": "Configuring SMTP",
    "weight": "230"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Protocols

[About SMTP configuration](#About_SMTP_configuration)

[Defining a Local Site (-local\_agent)](#Defining_Local_Site)

[Defining a Remote Site (-remote\_agent)](#Defining_Remote_Site)

[Defining an Application](#Defining_an_Application)

[Configuring SMTP defaults](#Configuring_SMTP_defaults)

[Requesting an acknowledgment](#Requesting_an_acknowledgement)

[Transfer identifiers](#Transfer_identifiers)

[Limitations for SMTP parameters](#Limitations_for_SMTP_parameters)

<span id="About_SMTP_configuration"></span>

## About SMTP configuration

Before submitting a file transfer, you must configure the SMTP environment by defining the following Gateway objects to be used, if they do not already exist:

-   <span style="font-weight: bold;">Local Site</span>  
    On installation, you must create a Local Site corresponding to the <span class="code">local\_site\_alias</span> and <span class="code">local\_site\_proto\_ident</span> parameters in the configuration file <span class="code">&lt;Gateway installation directory>/run\_time/etc/conffile</span>. This is the default Local Site for all protocols supplied by the product, including SMTP. You can create a specific SMTP Local Site if necessary.
-   <span style="font-weight: bold;">Remote Site</span>  
    Define communication attributes (such as SMTP server address, login and password) in Remote Site objects. The Remote Site represents an SMTP server to contact. At least one Remote Site must be defined for each remote SMTP server and user that Gateway uses to send email. The SMTP Remote Site is always Responder/Receiver.
-   <span style="font-weight: bold;">Application</span>  
    The default Application is MAIL.

You can use either the GUI or the <span class="codeBold_in_para">peladm</span> online command (as in the examples used here) to create these objects.

<span id="Defining_Local_Site"></span>

## Defining a Local Site (-local\_agent)

The Local Site is the object that represents Gateway when connecting to an SMTP server. It provides the:

-   Client identifier to the server via the EHLO command (or HELO if the server does not recognize extensions)
-   Return email address to use by default if no address is provided when a transfer is submitted from this Site (From)

<span id="Defining_Remote_Site"></span>

## Defining a Remote Site (-remote\_agent)

The Remote Site is used to:

-   Connect to the server (Network address of the SMTP server)
-   Establish a secure session with TLS
-   Select the method to use for the identification phase with the server, and information relative to this method (user name and password for the login method)
-   Obtain the destination email address to use by default if it was not specified when the transfer was submitted to this Site

You can define SMTP Remote Sites by creating either:

-   One Remote Site that represents the SMTP server and identify the email recipients in the Transfer Request
-   Several SMTP Remote Sites that reference the same SMTP server but have different default recipient addresses (the **To** field)

<span style="font-weight: bold;">Note:</span> Remote Site templates are not used in SMTP, because Gateway is always the Initiator in this protocol (no incoming transfers).

For the specific SMTP parameters to complete, refer to [Remote Site: SMTP tab](../../../managing_partners_start_here/sites_start_here/managing_remote_sites/remote_site_smtp_tab).

<span id="Defining_an_Application"></span>

## Defining an Application

An Application is a set of parameters describing the structure of a file in terms of local storage and transfer format. In addition, the Application associated with a transfer indicates to Gateway whether it must create an email for the transfer or not.

<span id="Configuring_SMTP_defaults"></span>

## Configuring SMTP defaults

You can configure default values for SMTP parameters in the Gateway [configuration menu.](../../../configuration_start_here/config_protocols_about/config_protocols#olh_connectivity_internet_mail_smtp)

<span id="Requesting_an_acknowledgement"></span>

## Requesting an acknowledgment

Gateway only sends an acknowledgment request if, in the Transfer Request, you set the <span style="font-weight: bold;">Ack option</span> (<span class="code">acknowledgment\_option</span>) parameter to <span style="font-weight: bold;">To ack</span> (<span class="code">TO\_ACK</span>).

There are two types of acknowledgment in SMTP:

-   DSN – (Delivery Status Notification) network (or protocol) acknowledgment
-   MDN – (Mail Disposition Notification) application acknowledgment

The following table shows the type of acknowledgment request that Gateway sends for specific file types.

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>File type</p>         </th>
<th class="HeadD-Column1-Header1"><p>acknowledgment request applicable</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p><strong>Attach file</strong> (<span class="code">attach_extract_file</span>) parameter is set to <em>Yes</em></p>         </td>
         <td><p>MDN and DSN</p>         </td>
      </tr>
      <tr>
         <td><p>Formatted email</p>         </td>
         <td><p>DSN only</p>         </td>
      </tr>
   </tbody>
</table>

SMTP acknowledgments have the following characteristics in Gateway:

-   <span style="font-weight: bold;">Initiation:</span> The sender requests acknowledgments in a transfer
-   <span style="font-weight: bold;">Interaction with POP3:</span> acknowledgment requests sent in SMTP result in acknowledgments received in POP3. Inversely, reception of an acknowledgment request received via POP3 results in an acknowledgment sent in SMTP.
-   <span style="font-weight: bold;">Multiple recipients:</span> If an email is sent to several recipients, network and application acknowledgments can be returned for each.
-   <span style="font-weight: bold;">acknowledgment status:</span> If you are sending an email to multiple recipients, and DSN is acknowledged in error for at least one of the recipients, then the global SMTP acknowledgment status for a DSN is *negative acknowledgment*. It is *undefined* in all other cases.
-   <span style="font-weight: bold;">Errors:</span> In case of error, both the DSN and the MDN are equally valid. However, only a positive MDN acknowledgment is considered a certain acknowledgment.

<span id="Transfer_identifiers"></span>

## Transfer identifiers

A DSN acknowledgment carries a transfer identifier (ENVID) created by the SMTP client and relayed by the intermediary SMTP servers. When the final SMTP server receives an email it creates the acknowledgment file containing the transfer identifier and returns it to the sender (**From**).

On creation of an SMTP transfer, the transfer identifier (<span class="code">xfer\_ident</span>) used will have the format<span class="code"> &lt;from\_user.date\_creation.local\_ident@from\_domain></span> where:

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Parameter</p>         </th>
<th class="HeadD-Column1-Header1"><p>Meaning</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>from_user</p>         </td>
         <td><p>User portion of the return address (<strong>From</strong>)</p>         </td>
      </tr>
      <tr>
         <td><p>date_creation</p>         </td>
         <td><p>Whole number representing the transfer creation date</p>         </td>
      </tr>
      <tr>
         <td><p>local_ident</p>         </td>
         <td><p>Transfer number (local identifier)</p>         </td>
      </tr>
      <tr>
         <td><p>from_domain</p>         </td>
         <td><p>Domain portion of the return address (<strong>From</strong>)</p>         </td>
      </tr>
   </tbody>
</table>

If Gateway creates the email, the SMTP transfer identifier <span class="code">xfer\_ident</span> is:

-   Equivalent to the MIME **Message-Id**
-   Used as the ENVID parameter of the protocol acknowledgment request (DSN)

<span id="Limitations_for_SMTP_parameters"></span>

## Limitations for SMTP parameters

The following table summarizes SMTP parameter restrictions:

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Parameter</p>         </th>
<th class="HeadD-Column1-Header1"><p>Limits</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>User name</p>         </td>
         <td><p>64 characters</p>         </td>
      </tr>
      <tr>
         <td><p>Domain</p>         </td>
         <td><p>64 characters</p>         </td>
      </tr>
      <tr>
         <td><p>Path</p>         </td>
         <td><p>256 characters, including all separators and punctuation</p>         </td>
      </tr>
      <tr>
         <td><p>Command line</p>         </td>
         <td><p>512 characters, including the command itself and the end-of-line &lt;CRLF&gt; characters.</p>
<p>This maximum size is increased depending on the extensions implemented by the server.</p>         </td>
      </tr>
      <tr>
         <td><p>Response string</p>         </td>
         <td><p>512 characters, including the end-of-line characters &lt;CRLF&gt;</p>         </td>
      </tr>
      <tr>
         <td><p>Text line (DATA)</p>         </td>
         <td><p>1000 characters, including end-of-line characters (excluding the full stop copied at the beginning of a line)</p>         </td>
      </tr>
      <tr>
         <td><p>Recipients</p>         </td>
         <td><p>100 per transaction</p>         </td>
      </tr>
      <tr>
         <td><p>Data</p>         </td>
         <td><p>The SMTP server must be able to accept at least 64 KB of data</p>         </td>
      </tr>
   </tbody>
</table>

Related topics

[Working with Local Sites](../../../managing_partners_start_here/sites_start_here/managing_local_sites)

[Working with Local Sites (command line)](../../../managing_partners_start_here/sites_start_here/managing_local_sites_cli)

[Working with Remote Sites](../../../managing_partners_start_here/sites_start_here/managing_remote_sites)

[Remote Site: SMTP tab](../../../managing_partners_start_here/sites_start_here/managing_remote_sites/remote_site_smtp_tab)

[Working with Remote Sites (command line)](../../../managing_partners_start_here/sites_start_here/managing_local_sites_cli/managing_remote_sites_cli)

[Working with Applications](../../../transfers_start_here/parameters_start_here/applications_start_here/working_with_applications_(gui))

[Working with Applications (command line)](../../../transfers_start_here/parameters_start_here/applications_start_here/working_with_applications_cli)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
