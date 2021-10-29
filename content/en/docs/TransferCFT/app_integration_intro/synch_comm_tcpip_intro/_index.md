{
    "title": "About synchronous communication",
    "linkTitle": "About synchronous communication ",
    "weight": "270"
}## Use synchronous communication (TCP/IP)

Synchronous communication provides a real-time response when sending data from a client to the Transfer CFT server. This response indicates that the client command was acknowledged by Transfer CFT and is listed in the catalog. For a transfer request, for example, the response would indicate the date/time stamp and unique identifier associated with the transfer.

An additional benefit of synchronous communication is that you can use it for monitoring purposes, as it returns IDTU information about a transfer.

The alternative to synchronous mode is an asynchronous mode, which places the client data in a communication file where it waits to be picked up by the Transfer CFT server, at which point it is then listed in the catalog.

Another difference between modes is that unlike synchronous mode, asynchronous mode does not require that Transfer CFT be started for the client to send data.

 

![](/Images/TransferCFT/new_synch_comm.png)

## Configuring synchronous communication

There are two steps to set up synchronous communication in Transfer CFT, configure the server and the client.

### Configure the server

Use the CFTCOM command to define the synchronous communication settings. In the Central Governance User Guide, refer to **Transfer request mode &gt; synchronous**.

-   Port: Use the Transfer CFT server port that receives the client commands
-   Maximum connection: Set the number of incoming connections on the Transfer CFT server
-   Session timeout: Set the amount of time after which Transfer CFT disconnects the client connection

**Example**

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>CFTUTIL CFTCOM ID=COMS, TYPE=TCPIP, HOST=localhost, PORT=1765, PROTOCOL=XHTTP, DISCTS=60</p>
            <p>CFTUTIL uconfset id=cft.server.cftcoms.max_connection, value=256</p>         </td>
      </tr>
   </tbody>
</table>

If you manually configure synchronous communication in Transfer CFT, remember to add the COMS identifier in the CFTPARM COM parameter.

Resulting LOG message after a Transfer CFT restart

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>CFTI18I+ TYPE : XHTTP HOST : 127.0.0.1 PORT : 1765         </td>
      </tr>
   </tbody>
</table>

### Configure the client

On the client side perform one of the following configuration procedures, depending on the type of client you are using.

**Example**

#### Simple client configuration using CFTUTIL

Start a CFTUTIL session and perform the following commands.

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>CONFIG TYPE=COM, MEDIACOM=TCPIP, FNAME=XHTTP://localhost:1765</p>
            <p>&lt;execute requests in same session&gt;</p>         </td>
      </tr>
   </tbody>
</table>

Use a configuration file to define the synchronous communication, where the file should contain at least the following elements:

-   # TCP/IP COMMUNICATION
-   TYPE =TCP
-   NAME =xhttp://localhost:1765
-   TIMEOUT = 600

Start a CFTUTIL session and perform the following commands.

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p> CONFIG TYPE=COM, FNAME=&lt;path&gt;&lt;config_file&gt;</p>
            <p>&lt;execute requests in same session&gt;</p>         </td>
      </tr>
   </tbody>
</table>

#### API

The API configuration consists of using a configuration file (the same elements as in a simple client configuration).

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>cftau ("COM",C=&lt;path&gt;&lt;config_file&gt;);</p>         </td>
      </tr>
   </tbody>
</table>

#### JPI

JPI client configuration consists of using a configuration file (the same elements as in a simple client configuration).

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>CFTUTIL uconfset id=copilot.cft.com, value=’C=&lt;path&gt;&lt;config_file&gt;’</p>         </td>
      </tr>
   </tbody>
</table>

#### Web services

When using web services the default media identifier used is the first once declared in the general CFTPARM object. Additionally, you can override this in the web services XML file by adding the desired COM using the format &lt;axw:CFTCOM\_ID>COM0&lt;/axw:CFTCOM\_ID> in the SOAP request.

#### Transfer CFT UI

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>CFTUTIL uconfset id=copilot.cft.com, value=’C=&lt;path&gt;&lt;config_file&gt;’</p>         </td>
      </tr>
   </tbody>
</table>

When using the Transfer CFT UI the first media identifier listed in the server's parameter file (CFTPARM) is used. So for example, if CFTPARM ID = IDPARM0, where COM = (COM0, COM1), the COM0 media is used.

## Using SWAITCAT

For information on the wait period for a catalog value to reach a certain, predefined state (such as T terminated), see [SWAITCAT](define_transfer_wait_period) and the [Request examples](sync_transfer_request_tasks) topics.

## Using password management

For information on controlling remote users that can perform CFTUTIL commands using synchronous communication media, see [Password authentication](control_remote_users_synch_com).

## Troubleshooting

For more information on errors and corrective actions, see [Synchronous communication return codes](../troubleshoot_intro/messages_and_error_codes_start_here/synch_comm_return_codes).
