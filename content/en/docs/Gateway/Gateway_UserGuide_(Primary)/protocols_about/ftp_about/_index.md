{
    "title": " ",
    "linkTitle": "FTP",
    "weight": "150"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Protocols

# FTP

## About FTP

[FTP](#ftp_intro)

[FTP and Gateway](#FTP_and_Gateway)

<span id="ftp_intro"></span>

### FTP introduction

FTP (File Transfer Protocol), specified in RFC 959 (October 1985), is an end-to-end protocol designed to transfer files or data over a TCP/IP network between two platforms irrespective of the hardware and software architecture of the host computers. FTP includes functions to log on to the network, list directories and copy files. Data is transferred over a data-type connection that is independent of the connection used to submit commands.

#### How does FTP work?

FTP uses two TCP/IP sessions for a transfer:

-   The <span style="font-weight: bold;">control session</span> to send and receive FTP commands
-   The <span style="font-weight: bold;">data session</span> to send and receive file data

The client always initiates the control session. The client submits its identification and then sends the commands that determine the data transfer behavior to implement, as summarized in the following table:

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Data Transfer attribute</p>         </th>
<th class="HeadD-Column1-Header1"><p>Description</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Active or passive role</p>         </td>
         <td><p>The data session is initiated according to the server role defined in the control session:</p>
<ul>
<li>In <span style="font-weight: bold;">active mode</span> the server initiates the data session</li>
<li>In <span style="font-weight: bold;">passive mode</span> the client initiates the data session</li>
</ul>
<p>The mode is independent of the transfer direction.</p>         </td>
      </tr>
      <tr>
         <td><p>Transfer direction</p>         </td>
         <td><p>Send or Receive</p>         </td>
      </tr>
      <tr>
         <td><p>Data format (type)</p>         </td>
         <td><p>ASCII, EBCDIC or Binary</p>         </td>
      </tr>
      <tr>
         <td><p>Data exchange (transmission) mode</p>         </td>
         <td><p>STREAM, BLOCK, or COMPRESSED</p>         </td>
      </tr>
      <tr>
         <td><p>Data structure</p>         </td>
         <td><p>File or Record</p>         </td>
      </tr>
      <tr>
         <td><p>Name of the file to be transferred</p>         </td>
         <td><p>File name</p>         </td>
      </tr>
   </tbody>
</table>

The data connection is used to:

-   Transfer data files (for example, using the <span class="code" style="font-weight: bold;">RETR</span> or <span class="code" style="font-weight: bold;">STOR</span> commands)
-   Send a directory list in response to a <span class="code" style="font-weight: bold;">LIST</span> or <span class="code" style="font-weight: bold;">NLST</span> command

The following diagram gives a simple overview of the two sessions.

![](/Images/Gateway/FTP1_610x350.gif)

#### FTP control and data sessions

To end an FTP session, the client sends an FTP <span class="code" style="font-weight: bold;">QUIT</span> command to the server, which then releases the connection.

<span id="FTP_and_Gateway"></span>

### FTP and Gateway

You can use FTP in Gateway to:

-   Transmit and receive files in client and server mode
-   Compress data using methods including <span style="font-style: italic;">stream</span>, <span style="font-style: italic;">block</span> and <span style="font-style: italic;">compressed</span>
-   Transform data using ASCII, EBCDIC, and IMAGE (Binary) encoding
-   List available files or transfers, via the DIR command
-   Transfer multiple files (MPUT and MGET)

Gateway enables you to implement routing, send pre- and post-transfer commands, and launch user exits when sending or receiving transfers.

Related topics

[Configuring the FTP environment](ftp_config)

[General FTP command attributes](ftp_general_config_attributes)

[Using FTP in Initiator mode](ftp_initiator_mode)

[Using FTP in Responder mode](ftp_responder_mode)

[Using an FTP proxy](ftp_using_proxy)

[Monitoring an FTP Transfer Request](ftp_monitoring_transfer)

[Transferring multiple files with FTP](ftp_multiple_file_transfer) (MPUT and MGET)

[FTP specific user exits](ftp_exits)

[Executing a basic FTP transfer](../../transfer_examples/transfer_example_ftp)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
