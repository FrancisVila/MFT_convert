{
    "title": "File Transfers and Transfer Requests",
    "linkTitle": "File Transfers and Transfer Requests",
    "weight": "70"
}{{< Gateway/componentlongname  >}}: Overview

As described in the [previous topic](../ov_network_archi), Gateway facilitates the exchange of files between diverse platforms and applications, over local networks and across the Internet.

## File Transfers

Most of the tasks you execute with Gateway involve configuring and executing *file transfers*. File transfer is the process of displacing a file from one computer platform to another.

In any file exchange, one computer is the sender, another is the receiver. The two computers are linked together by a network, either TCP/IP or SNA. An inter-platform file transfer also requires the use of a high-level file transfer protocol, independent of the supporting network type and the hardware and software architecture of the host computers.

### Supported protocols

Gateway enables automatic and secured file transfers over the following supporting protocols:

-   FTP
-   HTTP
-   OFTP (Odette)
-   PEL
-   PeSIT HS D
-   PeSIT HS E
-   SFTP (SSH-FTP)
-   SMTP
-   POP3
-   EDIINT
-   RosettaNet
-   SWIFTNet
-   JMS
-   X.400

## Transfer Requests

A file transfer consists of sending:

-   The file itself
-   Technical parameters associated with the file. For example: connected partners, local file storage format, and so on.

### Transfer Request object

The *Transfer Request object* contains the complete set of information required to trigger a Gateway file transfer:

-   Name of file to transfer
-   Physical file attributes
-   Protocol used for the transfer
-   Compression or encryption options
-   Behavior in case of transfer failure
-   Transfer scheduling, restarting and routing

### Mailbox

Gateway stores all data related to each Transfer Request in a permanent file, named the *Mailbox*. During the transfer process, Gateway updates the Transfer Request status and information in the Mailbox. This information allows transfer restart upon failure or transfer completion.

### Transfer acknowledgments

Depending on the protocol used for a file transfer, Gateway can handle both positive and negative acknowledgments.

A *positive acknowledgment* informs the sender that the recipient correctly received or processed the file. The following protocols support positive acknowledgments:

-   PeSIT HS E
-   OFTP (Odette)
-   SMTP
-   POP3
-   FTP (via a proprietary mechanism, only when communicating with another Gateway)

A *negative acknowledgment* indicates that errors occurred during the processing of a received file, or that file transfer failed during routing. The following protocols support negative acknowledgments:

-   PeSIT HS E (via the proprietary `nack_option` parameter)
-   SMTP
-   POP3

## Transfer-related objects

The **Transfer Request** object and the <span style="font-weight: bold;">[Site](../ov_transfer_sites)</span> object together usually contain all data required to process transfers. Additionally, some transfers require an <span style="font-weight: bold;">[Application](../ov_applications#application_object)</span> object or a <span style="font-weight: bold;">[Trading Partner](../ov_trading_partners)</span> object.

[Next topic](../ov_transfer_sites)

Related topics

[Managing Transfers](../../transfers_start_here)

[About <span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span> protocols](../../protocols_about)

[Viewing and managing Mailbox contents](../../transfers_start_here/monitoring_transfers_start_here/viewing_and_managing_mailbox_contents_(gui))

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
