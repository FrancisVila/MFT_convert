{
    "title": "SMTP/POP3",
    "linkTitle": "SMTP/POP3",
    "weight": "210"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Protocols

[SMTP/POP3](#smtp_pop3_intro)

[Using SMTP in Gateway](#using_smtp_in_gateway)

<span id="smtp_pop3_intro"></span>

## SMTP/POP3 Introduction

SMTP and POP3 message transfer protocols are integrated in Gateway as file transfer processes. You can use Gateway to:

-   Transfer email
-   Send files as email attachments
-   Send user messages in an email format
-   Receive email-formatted files \[s29\]

SMTP and POP3 are implemented in Gateway exclusively in client mode. This means that sending and receiving email occurs in a single direction for each protocol. In SMTP, the client (Initiator of the connection) can only <span style="font-style: italic;">send</span> email. In POP3, the client can only <span style="font-style: italic;">receive</span> email.

Gateway does not include SMTP and POP3 server functions. <span style="font-weight: bold;">You must use Gateway in conjunction with both an SMTP and POP3 server.</span>

### Examples of SMTP/POP3 email processing

#### Email Transfer

Gateway can relay files received in PeSIT HS E to an electronic mailbox, as illustrated below:

 

<img src="/Images/Gateway/SMTP.png" class="mediumWidth" />

 

#### Email Distribution

Gateway can make files received in an electronic mailbox available to HTTP and FTP clients.

<span id="using_smtp_in_gateway"></span>

## Using SMTP in Gateway

SMTP is used to send email when Gateway is installed behind an SMTP server.

You can send the following types of email with Gateway:

-   File transferred as an attachment (a maximum of one attached file is allowed) with or without a user message
-   acknowledgment (of a transfer received in POP3)
-   File already formatted as an email, unaltered by Gateway. This type of email "black box" can contain several attachments.
-   User message (as in PeSIT)

Related topics

[Configuring the SMTP environment](smtp_config)

[Configuring security for SMTP](smtp_configuring_security)

[SMTP/POP3: sending an email](smtp_pop3_sending_mail)

[Using POP3 in <span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>](pop3_using)

[Configuring the POP3 environment](pop3_config)

[Processing email after retrieval](smtp_pop3_processing_mail)

[Diagnostics and Troubleshooting](smtp_pop3_troubleshooting)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
