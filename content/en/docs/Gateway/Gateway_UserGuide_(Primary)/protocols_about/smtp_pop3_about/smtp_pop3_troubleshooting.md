{
    "title": "Diagnostics and Troubleshooting SMTP/POP3",
    "linkTitle": "Diagnostics and Troubleshooting",
    "weight": "290"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Protocols

[About diagnostics and troubleshooting](#About_diagnostics_and_troubleshooting)

[Mailbox content](#Mailbox_content)

[Protocol Trace](#Protocol_Trace)

[Sample POP3 commands](#Sample_POP3_commands)

<span id="About_diagnostics_and_troubleshooting"></span>

## About diagnostics and troubleshooting

During a file transfer you can record messages, exchanges between Gateway and a POP3 server, relating to the transfer activities in the log file.

<span id="Mailbox_content"></span>

## Mailbox content

To monitor SMTP/POP3, the Mailbox stores the following information for each transfer:

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p>Field</p>         </td>
         <td><p>Comment</p>         </td>
      </tr>
      <tr>
         <td><p>&lt;Subject&gt;</p>         </td>
         <td><p>After removal of any specific Gateway parameters such as <strong>appli</strong>, <strong>dest</strong> and <strong>org</strong></p>         </td>
      </tr>
      <tr>
         <td><p>appli</p>         </td>
         <td><p>These parameters are saved in the fields <strong>Application</strong>, <strong>Destination</strong> and <strong>Origin</strong> of the Mailbox record</p>         </td>
      </tr>
      <tr>
         <td><p>dest</p>         </td>
      </tr>
      <tr>
         <td><p>org</p>         </td>
      </tr>
      <tr>
         <td><p>&lt;From&gt;</p>         </td>
         <td><p>Taken from the MIME Header field</p>         </td>
      </tr>
      <tr>
         <td><p><em>&lt;To&gt;</em>, <em>&lt;Cc&gt;</em> and <em>&lt;Bcc&gt;</em></p>         </td>
         <td><p>If there is more than one email recipient, these lists are saved in the overflow zone of the Mailbox.</p>
<p>The overflow blocks strings in the form:<br />
To: (options) "description" &lt;address@email&gt;, \0 Cc:  \0 Bcc:  \0 \0</p>
<p>For each recipient, the <em>options</em> field will contain the complementary information (such as acknowledgement status).</p>         </td>
      </tr>
      <tr>
         <td><p>xfer_ident</p>         </td>
         <td><p>Corresponds to the <strong>Message-ID</strong> field of the MIME header, and is used to detect duplication of received messages. If this field is not found in the header, a hash of the MIME header (Date, From, To, Cc, Bcc, Subject) replaces it.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="Protocol_Trace"></span>

## Protocol Trace

Activate the protocol trace for more detailed diagnostics when an unexpected error occurs.

The protocol trace is an optional feature that you define for transfer activity for a given Site.

You can enable or disable trace printing for a Site object at either of the following stages by setting the Remote Site parameter <span class="code" style="font-weight: bold;">-trace\_mode (-tm)</span> to Y (*yes*) or N (*no*):

-   During Site creation
-   On modifying attributes of an existing Site
-   During Gateway processing (dynamically)

Enabling or disabling protocol tracing using this method is only valid for the current session. The update is lost when you stop Gateway.

<span id="Sample_POP3_commands"></span>

## Sample POP3 commands

Use the following online commands to manage and launch POP3 in Gateway:

-   <span class="code" style="font-weight: bold;">peladm</span> to create and update POP3 Sites and Applications
-   <span class="code" style="font-weight: bold;">pelctl</span> to control the polling status of a Site
-   <span class="code" style="font-weight: bold;">peldsp status\_site</span> to view the status of the polling activity of a Remote Site

<span style="font-weight: bold;">Note:</span> The <span class="code" style="font-weight: bold;">peltrans</span> command is not used for the POP3 protocol, which operates by polling the POP3 Sites.

To create an SMTP/POP3 loop (to send an email in SMTP and receive it in POP3), you must create a Remote Site to represent each server partner, in this case the SMTP server and the POP3 server. You only need to create a transfer in SMTP.

### Example: Creating an SMTP/POP3 Loop

#### Create an SMTP Remote Site, as follows:

peladm create\_site  -a site\_smtp  -pr SMTP  -aef N  -smtp\_auth\_method none

                    -l\_id user1  -l\_pswd user1  -ct tcpip  -pi smtp\_attach\_no

This command creates an SMTP Remote Site named **site\_smtp** with the following parameters:

-   **Attach file / Extract file** set to *No* (sends a formatted email)
-   Authentication method: none (id to server with login and password)
-   Protocol identifier: *smtp\_attach\_no*

#### Create a POP3 Remote Site, as follows:

peladm create\_site  -a site\_pop3  -pr POP3  -aef N  -pop3\_auth\_method basic

                    -l\_id user1  -l\_pswd user1  -ct tcpip  -pi site\_pop3  -pm Y

                    -pollint 1  -dp /dir1/dir2/  -routing N

This command creates a POP3 Remote Site named **site\_pop3** with the following parameters:

-   Polling mode: enabled
-   Polling interval: 1 minute
-   Storage directory: */dir1/dir2/*
-   Protocol identifier: *site\_pop3*

#### Send an SMTP transfer, as follows:

peltrans  -appli MAIL  -fc /dir1/dir2/SMTP\_POP3/file.txt  -da site\_smtp  -mode I

          -oa GW1  -smtp\_from user2@xxx.yy.zz  -to user1@xxx.yy.zz

This Transfer Request sends an email from user2@xxx.yy.zz to user1@xxx.yy.zz.

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
