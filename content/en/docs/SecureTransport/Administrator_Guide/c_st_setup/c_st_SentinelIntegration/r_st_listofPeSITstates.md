{
    "title": "List of PeSIT states",
    "linkTitle": "List of PeSIT states",
    "weight": "220"
}This topic describes the roles and states for PeSIT protocol transfers.

-   [Roles of transfer partners](#Roles)
-   [Server/Sender transfer states](#Server_sender)
-   [Server/Receiver transfer states](#Server_receiver)
-   [Requester/Receiver transfer states](#Requester_receiver)
-   [Requester/Sender transfer states](#Requester_sender)

<span id="Roles"></span>

## Roles of transfer partners

Although each transfer occurs between only two transfer partners, each transfer partner plays two roles:

-   **Sender** or **Receiver** (the file is sent or received)
-   **Requester** or **Server** (the transfer request is sent or received)

For a given transfer, only the following combinations of partner roles are possible:

-   **Sender/Requester** and **Receiver/Server** (The partner that sent the file requested the transfer).
-   **Receiver/Requester** and **Sender/Server** (The partner that received the file requested the transfer).

<span id="Server_sender"></span>

## Server/Sender transfer states

{{< SecureTransport/componentshortname  >}} acts as a protocol server.

{{< SecureTransport/componentshortname  >}} sends a file.

Server/Sender corresponds to a CIT Download in {{< SecureTransport/componentshortname  >}} terminology.

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">State         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>SENDING         </td>
         <td>{{< SecureTransport/componentshortname  >}} is sending a file.         </td>
      </tr>
      <tr>
         <td>SENT         </td>
         <td>{{< SecureTransport/componentshortname  >}} has sent a file.         </td>
      </tr>
      <tr>
         <td>ENDED_TO_ACK         </td>
         <td>Indicates that {{< SecureTransport/componentshortname  >}} has received an acknowledgment for the file transfer.         </td>
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

<span id="Server_receiver"></span>

## Server/Receiver transfer states

{{< SecureTransport/componentshortname  >}} acts as a protocol server.

{{< SecureTransport/componentshortname  >}} is receiving a file.

Server/Receiver corresponds to a CIT Upload in {{< SecureTransport/componentshortname  >}} terminology.

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">State         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>RECEIVING         </td>
         <td>{{< SecureTransport/componentshortname  >}} is receiving a file.         </td>
      </tr>
      <tr>
         <td>RECEIVED         </td>
         <td>{{< SecureTransport/componentshortname  >}} has received a file.         </td>
      </tr>
      <tr>
         <td>POST_PPROC         </td>
         <td>Post processing in progress.         </td>
      </tr>
      <tr>
         <td>ACKED         </td>
         <td>Indicates that {{< SecureTransport/componentshortname  >}} has acknowledged the transfer to the partner.         </td>
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

<span id="Requester_receiver"></span>

## Requester/Receiver transfer states

{{< SecureTransport/componentshortname  >}} acts as a protocol client.

{{< SecureTransport/componentshortname  >}} is receiving a file.

This corresponds to SIT Pull in {{< SecureTransport/componentshortname  >}} terminology.

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">State         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>TO_EXECUTE         </td>
         <td>{{< SecureTransport/componentshortname  >}} is about to execute a scheduled job.         </td>
      </tr>
      <tr>
         <td>RECEIVING         </td>
         <td>{{< SecureTransport/componentshortname  >}} is receiving a file.         </td>
      </tr>
      <tr>
         <td>RECEIVED         </td>
         <td>{{< SecureTransport/componentshortname  >}} has received a file.         </td>
      </tr>
      <tr>
         <td>ACKED         </td>
         <td>Indicates that {{< SecureTransport/componentshortname  >}} has acknowledged the transfer to the partner.         </td>
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

<span id="Requester_sender"></span>

## Requester/Sender transfer states

{{< SecureTransport/componentshortname  >}} acts as a protocol client.

{{< SecureTransport/componentshortname  >}} is sending a file.

This corresponds to SIT Push in {{< SecureTransport/componentshortname  >}} terminology.

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">State         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>TO_EXECUTE         </td>
         <td>{{< SecureTransport/componentshortname  >}} is about to execute a scheduled job.         </td>
      </tr>
      <tr>
         <td>SENDING         </td>
         <td>{{< SecureTransport/componentshortname  >}} is sending a file.         </td>
      </tr>
      <tr>
         <td>SENT         </td>
         <td>{{< SecureTransport/componentshortname  >}} has sent a file.         </td>
      </tr>
      <tr>
         <td>ENDED_TO_ACK         </td>
         <td>Indicates that {{< SecureTransport/componentshortname  >}} has received an acknowledgment for the file transfer.         </td>
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
-   [Axway Sentinel dashboards]()
-   [Axway Sentinel requests](../r_st_sentinelrequests)
-   [Configure SecureTransport to send events to Axway Sentinel](../t_st_sentinel)
