{
    "title": "Using POP3 in Axway Gateway",
    "linkTitle": "Using POP3 in Gateway",
    "weight": "260"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Protocols

[About POP3](#About_POP3)

[Setting up Gateway to work with POP3](#working_with_POP3)

[Retrieving and processing emails](#Retrieving_and_processing_emails)

<span id="About_POP3"></span>

## About POP3

The Gateway implementation of POP3, Post Office Protocol Version 3, is exclusively in client mode and conforms to RFC 1939, incorporating the optional commands.

You can use the POP3 client in Gateway to:

-   Connect to a POP3 server
-   Retrieve email from a POP3 server
-   Process retrieved emails
-   Return acknowledgments

To be compatible, the POP3 server must also conform to RFC 1939 and support the commands USER, PASS and TOP.

<span id="working_with_POP3"></span>

## Setting up Gateway to work with POP3

To retrieve and process email from a POP3 server, you must first configure the POP3 environment by defining the following:

-   Remote Site for each user account on the POP3 server, thus enabling Gateway to connect to the POP3 Site and retrieve email for each specified user.
-   Local Site
-   Application object

You can use the Local Site and Application defined by default in Gateway.

Refer to [Configuring the POP3 environment](../pop3_config).

<span id="Retrieving_and_processing_emails"></span>

## Retrieving and processing emails

When you activate the polling option, Gateway retrieves emails by automatically polling the POP3 server for each defined Remote Site. You do not need to request a transfer.

For each email that it retrieves, Gateway:

-   Identifies the email type by analyzing the MIME header. The following types are recognized:

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p>MIME content-type</p>         </td>
         <td><p>Axway MFT XFER record type</p>         </td>
         <td><p>Description</p>         </td>
      </tr>
      <tr>
         <td><p>Multipart/* : with a single attached file</p>         </td>
         <td><p>TYPE=XFER</p>
<p>FILE_NAME=<em>&lt;file name&gt;</em></p>         </td>
         <td><p>File transfer</p>         </td>
      </tr>
      <tr>
         <td><p>Multipart/alternative text/*</p>         </td>
         <td><p>TYPE=MSG</p>
<p>FILE_NAME=<em>&lt;application name&gt;</em></p>         </td>
         <td><p>Message transfer</p>         </td>
      </tr>
      <tr>
         <td><p>Multipart/report</p>         </td>
         <td><p>TYPE=EERP</p>         </td>
         <td><p>acknowledgment</p>         </td>
      </tr>
      <tr>
         <td><p>All other types</p>         </td>
         <td><p>TYPE=XFER</p>
<p>FILE_NAME=RECOVER |DUPLICATE</p>         </td>
         <td><p>Unknown email format</p>         </td>
      </tr>
   </tbody>
</table>

-   Processes the email according to its identified type:
    -   Receives the whole email as a single received file (XFER)
    -   Acknowledges certain recipients of a transfer (EERP)
    -   Extracts the message of the email (MSG)
    -   Extracts the message and the attachment (XFER)

When you receive acknowledgment requests via POP3, you return the acknowledgment via SMTP.

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
