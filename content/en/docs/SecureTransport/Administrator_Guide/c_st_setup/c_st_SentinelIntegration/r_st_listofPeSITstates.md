{
    "title": "List of PeSIT states",
    "linkTitle": "List of PeSIT states",
    "weight": "220"
}This topic describes the roles and states for PeSIT protocol transfers.

-   <a href="#Roles" class="MCXref xref">Roles of transfer partners</a>
-   <a href="#Server_sender" class="MCXref xref">Server/Sender transfer states</a>
-   <a href="#Server_receiver" class="MCXref xref">Server/Receiver transfer states</a>
-   <a href="#Requester_receiver" class="MCXref xref">Requester/Receiver transfer states</a>
-   <a href="#Requester_sender" class="MCXref xref">Requester/Sender transfer states</a>

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

-   <a href="../r_st_sentineleventstates" class="MCXref xref">Event states</a>
-   <a href="../r_st_sentineltrackedobjects" class="MCXref xref">Axway Sentinel tracked objects</a>
-   <a href="../c_st_aboutxfb_to" class="MCXref xref">About XFB Transfer tracked objects</a>
-   <a href="../r_st_pesit_protocol" class="MCXref xref">PeSIT protocol</a>
-   <a href="../r_st_xfb_toattributes" class="MCXref xref">XFB Tracked Object attributes</a>
-   <a href="../r_st_cycleid" class="MCXref xref">CycleId calculation</a>
-   <a href="" class="MCXref xref">Axway Sentinel dashboards</a>
-   <a href="../r_st_sentinelrequests" class="MCXref xref">Axway Sentinel requests</a>
-   <a href="../t_st_sentinel" class="MCXref xref">Configure SecureTransport to send events to Axway Sentinel</a>
