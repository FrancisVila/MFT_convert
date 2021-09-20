{
    "title": "List of PeSIT states",
    "linkTitle": "List of PeSIT states",
    "weight": "230"
}This topic describes the roles and states for PeSIT protocol transfers.

-   [Roles of transfer partners](#roles)
-   [Server/Sender transfer states](#server_sender)
-   [Server/Receiver transfer states](#server_receiver)
-   [Requester/Receiver transfer states](#requester_receiver)
-   [Requester/Sender transfer states](#requester_sender)

## <span id="Roles"></span>Roles of transfer partners

Although each transfer occurs between only two transfer partners, each transfer partner plays two roles:

-   **Sender** or **Receiver** (the file is sent or received)
-   **Requester** or **Server** (the transfer request is sent or received)

For a given transfer, only the following combinations of partner roles are possible:

-   **Sender/Requester** and **Receiver/Server** (The partner that sent the file requested the transfer).
-   **Receiver/Requester** and **Sender/Server** (The partner that received the file requested the transfer).

## <span id="Server_sender"></span>Server/Sender transfer states

SecureTransport acts as a protocol server.

SecureTransport sends a file.

Server/Sender corresponds to a CIT Download in SecureTransport terminology.

<table cellspacing="0">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>State</th>
         <th>Description</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>SENDING         </td>
         <td><span>SecureTransport</span> is sending a file.         </td>
      </tr>
      <tr>
         <td>SENT         </td>
         <td><span>SecureTransport</span> has sent a file.         </td>
      </tr>
      <tr>
         <td>ENDED_TO_ACK         </td>
         <td>Indicates that <span>SecureTransport</span> has received an acknowledgment for the file transfer.         </td>
      </tr>
      <tr>
         <td>CANCELED         </td>
         <td>File transfer has been canceled by the client.         </td>
      </tr>
      <tr>
         <td>INTERRUPTED         </td>
         <td>The file transfer has been locally suspended.         </td>
      </tr>
      <tr>
         <td>SUSPENDED         </td>
         <td>The file transfer has been remotely suspended.         </td>
      </tr>
   </tbody>
</table>

## <span id="Server_receiver"></span>Server/Receiver transfer states

SecureTransport acts as a protocol server.

SecureTransport is receiving a file.

Server/Receiver corresponds to a CIT Upload in SecureTransport terminology.

<table cellspacing="0">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>State</th>
         <th>Description</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>RECEIVING         </td>
         <td><span>SecureTransport</span> is receiving a file.         </td>
      </tr>
      <tr>
         <td>RECEIVED         </td>
         <td><span>SecureTransport</span> has received a file.         </td>
      </tr>
      <tr>
         <td>POST_PPROC         </td>
         <td>Post processing in progress.         </td>
      </tr>
      <tr>
         <td>ACKED         </td>
         <td>Indicates that <span>SecureTransport</span> has acknowledged the transfer to the partner.         </td>
      </tr>
      <tr>
         <td>CANCELED         </td>
         <td>File transfer has been canceled by the client.         </td>
      </tr>
      <tr>
         <td>INTERRUPTED         </td>
         <td>The file transfer has been locally suspended.         </td>
      </tr>
      <tr>
         <td>SUSPENDED         </td>
         <td>The file transfer has been remotely suspended.         </td>
      </tr>
      <tr>
         <td>ROUTED         </td>
         <td>File transfer has been successfully routed (only on the relay site in store and forward mode).         </td>
      </tr>
   </tbody>
</table>

## <span id="Requester_receiver"></span>Requester/Receiver transfer states

SecureTransport acts as a protocol client.

SecureTransport is receiving a file.

This corresponds to SIT Pull in SecureTransport terminology.

<table cellspacing="0">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>State</th>
         <th>Description</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>TO_EXECUTE         </td>
         <td><span>SecureTransport</span> is about to execute a scheduled job.         </td>
      </tr>
      <tr>
         <td>RECEIVING         </td>
         <td><span>SecureTransport</span> is receiving a file.         </td>
      </tr>
      <tr>
         <td>RECEIVED         </td>
         <td><span>SecureTransport</span> has received a file.         </td>
      </tr>
      <tr>
         <td>ACKED         </td>
         <td>Indicates that <span>SecureTransport</span> has acknowledged the transfer to the partner.         </td>
      </tr>
      <tr>
         <td>INTERRUPTED         </td>
         <td>The file transfer has been locally suspended.         </td>
      </tr>
      <tr>
         <td>SUSPENDED         </td>
         <td>The file transfer has been remotely suspended.         </td>
      </tr>
      <tr>
         <td>POST_PROC         </td>
         <td>Post processing in progress.         </td>
      </tr>
   </tbody>
</table>

## <span id="Requester_sender"></span>Requester/Sender transfer states

SecureTransport acts as a protocol client.

SecureTransport is sending a file.

This corresponds to SIT Push in SecureTransport terminology.

<table cellspacing="0">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>State</th>
         <th>Description</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>TO_EXECUTE         </td>
         <td><span>SecureTransport</span> is about to execute a scheduled job.         </td>
      </tr>
      <tr>
         <td>SENDING         </td>
         <td><span>SecureTransport</span> is sending a file.         </td>
      </tr>
      <tr>
         <td>SENT         </td>
         <td><span>SecureTransport</span> has sent a file.         </td>
      </tr>
      <tr>
         <td>ENDED_TO_ACK         </td>
         <td>Indicates that <span>SecureTransport</span> has received an acknowledgment for the file transfer.         </td>
      </tr>
      <tr>
         <td>CANCELED         </td>
         <td>File transfer has been canceled by the client.         </td>
      </tr>
      <tr>
         <td>INTERRUPTED         </td>
         <td>The file transfer has been locally suspended.         </td>
      </tr>
      <tr>
         <td>SUSPENDED         </td>
         <td>The file transfer has been remotely suspended.         </td>
      </tr>
      <tr>
         <td>POST_PROC         </td>
         <td>Post processing in progress.         </td>
      </tr>
      <tr>
         <td>ROUTED         </td>
         <td>File transfer has been successfully routed (only on the relay site in store and forward mode).         </td>
      </tr>
   </tbody>
</table>

 

**Related topics:**

-   [Event states](../r_st_sentineleventstates)
-   [Axway Sentinel tracked objects](../r_st_sentineltrackedobjects)
-   [About XFB Transfer tracked objects](../c_st_aboutxfb_to)
-   [PeSIT protocol](../r_st_pesit_protocol)
-   [XFB Tracked Object attributes](../r_st_xfb_toattributes)
-   [CycleId calculation](../r_st_cycleid)
-   [Axway Sentinel dashboards](r_st_sentineldashboards.htm)
-   [Axway Sentinel requests](../r_st_sentinelrequests)
-   [Configure SecureTransport to send events to Axway Sentinel](../t_st_sentinel)
