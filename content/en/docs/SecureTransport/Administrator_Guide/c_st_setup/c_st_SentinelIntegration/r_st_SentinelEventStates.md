{
    "title": "Event states",
    "linkTitle": "Event states",
    "weight": "180"
}An *event state* specifies the current state of a file transfer. You choose the information {{< SecureTransport/componentshortname  >}} sends to Sentinel by selecting the event states to report. For details, see <a href="../t_st_sentinel#top" class="MCXref xref">Configure SecureTransport to send events to Axway Sentinel</a>.

{{< SecureTransport/componentshortname  >}} uses three pre-defined Sentinel Tracked Objects to report events:

-   **XFBTransfer** – to report states that occur during file transfers.
-   **ST\_VAS** (Value-Added Services) – to report states that occur during process other than file transfers.
-   **Heartbeat** – to indicate to Sentinel that {{< SecureTransport/componentshortname >}} is running and connected.

Every event in the same group about one file transfer is identified using the same *cycle ID*. Sentinel uses the cycle ID to associate the event information in its display.

The following table describes the available event states:

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Event state         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>ACKED†         </td>
         <td>{{< SecureTransport/componentshortname  >}} has sent an acknowledgment for a transfer.         </td>
      </tr>
      <tr>
         <td>AVAILABLE (ST_VAS)         </td>
         <td>{{< SecureTransport/componentshortname  >}} application has completed successfully.         </td>
      </tr>
      <tr>
         <td>AVAILABLE (XFBTransfer)*†         </td>
         <td>{{< SecureTransport/componentshortname  >}} has published a file in a target folder using Publish To Account step.         </td>
      </tr>
      <tr>
         <td>CANCELED*†         </td>
         <td>An application, agent, or user has canceled a file transfer.         </td>
      </tr>
      <tr>
         <td>DECRYPTED         </td>
         <td>{{< SecureTransport/componentshortname  >}} has performed a successful PGP decryption.         </td>
      </tr>
      <tr>
         <td>DECRYPTING         </td>
         <td>{{< SecureTransport/componentshortname  >}} is starting to decrypt a file.         </td>
      </tr>
      <tr>
         <td>DELETED         </td>
         <td>A client, post-processing action (PPA), or post client download action has deleted a file.         </td>
      </tr>
      <tr>
         <td>ENCRYPTED         </td>
         <td>{{< SecureTransport/componentshortname  >}} has performed a successful PGP encryption.         </td>
      </tr>
      <tr>
         <td>ENCRYPTING         </td>
         <td>{{< SecureTransport/componentshortname  >}} is starting to encrypt a file.         </td>
      </tr>
      <tr>
         <td>ENDED_TO_ACK†         </td>
         <td>{{< SecureTransport/componentshortname  >}} has received an acknowledgment for a transfer.         </td>
      </tr>
      <tr>
         <td>ERROR         </td>
         <td>An error has occurred during file deletion, renaming, transformation, or routing.         </td>
      </tr>
      <tr>
         <td>FAILED*†         </td>
         <td>An error has occurred during a file transfer, {{< SecureTransport/advancedrouting  >}} execution, or while an agent was running.         </td>
      </tr>
      <tr>
         <td>FORWARDED         </td>
         <td>A routing application (such as Standard Router) has completed successfully.         </td>
      </tr>
      <tr>
         <td>FORWARDING         </td>
         <td>{{< SecureTransport/componentshortname  >}} is starting a routing application (such as Standard Router).         </td>
      </tr>
      <tr>
         <td>INTERRUPTED†         </td>
         <td>A remote PeSIT server paused a transfer it initiated.         </td>
      </tr>
      <tr>
         <td>POST_PROC/ICAP_DENIED         </td>
         <td>Access to the file is denied.         </td>
      </tr>
      <tr>
         <td>POST_PROC/ICAP_SCANNED         </td>
         <td>The scanning of the file has successfully finished.         </td>
      </tr>
      <tr>
         <td>POST_PROC/ICAP_SCANNING         </td>
         <td>The scanning of the file has started.         </td>
      </tr>
      <tr>
         <td>POST_PROC/ROUTED†         </td>
         <td>An {{< SecureTransport/advancedrouting  >}} application has successfully completed.         </td>
      </tr>
      <tr>
         <td>POST_PROC/ROUTING†         </td>
         <td>{{< SecureTransport/componentshortname  >}} is starting an {{< SecureTransport/advancedrouting  >}} application.         </td>
      </tr>
      <tr>
         <td>PRESERVED         </td>
         <td>The original file was not deleted after an decryption or encryption.         </td>
      </tr>
      <tr>
         <td>RECEIVED*†         </td>
         <td>{{< SecureTransport/componentshortname  >}} has successfully received a file by server-initiated pull or client-initiated push.         </td>
      </tr>
      <tr>
         <td>RECEIVING†         </td>
         <td>{{< SecureTransport/componentshortname  >}} is starting to receive a file by server-initiated pull or client-initiated push.         </td>
      </tr>
      <tr>
         <td>RENAMED         </td>
         <td>A client action, or a post-transmission action (PTA), or post-processing action has renamed a file.         </td>
      </tr>
      <tr>
         <td>ROUTED†         </td>
         <td>As the intermediate partner in a routed PeSIT transfer, {{< SecureTransport/componentshortname  >}} has sent a file to the routing destination.         </td>
      </tr>
      <tr>
         <td>SENDING†         </td>
         <td>{{< SecureTransport/componentshortname  >}} is starting to send a file by server-initiated push or client-initiated pull.         </td>
      </tr>
      <tr>
         <td>SENT*†         </td>
         <td>{{< SecureTransport/componentshortname  >}} has successfully sent a file by server-initiated push or client-initiated pull.         </td>
      </tr>
      <tr>
         <td>SUBMITTED†         </td>
         <td>{{< SecureTransport/componentshortname  >}} has sent a wild card pattern for a server-initiated pull.         </td>
      </tr>
      <tr>
         <td>TO_EXECUTE†         </td>
         <td>{{< SecureTransport/componentshortname  >}} is ready to start a server-initiated transfer.         </td>
      </tr>
   </tbody>
</table>

\* Event state that is always monitored by Sentinel.

† Event state reported using the XFBTransfer Tracked Object and selected by default to be sent to Sentinel. The other event states are reported using ST\_VAS.

The following event states are *in-process* states: DECRYPTING, ENCRYPTING, FORWARDING, POST\_PROC/ICAP\_SCANNING, POST\_PROC/ROUTING, RECEIVING, SENDING, and TO\_EXECUTE. All other event states are *processed* states that report the successful or unsuccessful completion of processing.

> **Note:**
>
> Added data transformations and other SecureTransport customizations can add additional event states to be sent to Sentinel.

**Related topics:**

-   <a href="../r_st_sentineltrackedobjects" class="MCXref xref">Axway Sentinel tracked objects</a>
-   <a href="../c_st_aboutxfb_to" class="MCXref xref">About XFB Transfer tracked objects</a>
-   <a href="../r_st_pesit_protocol" class="MCXref xref">PeSIT protocol</a>
-   <a href="../r_st_listofpesitstates" class="MCXref xref">List of PeSIT states</a>
-   <a href="../r_st_xfb_toattributes" class="MCXref xref">XFB Tracked Object attributes</a>
-   <a href="../r_st_cycleid" class="MCXref xref">CycleId calculation</a>
-   <a href="" class="MCXref xref">Axway Sentinel dashboards</a>
-   <a href="../r_st_sentinelrequests" class="MCXref xref">Axway Sentinel requests</a>
-   <a href="../t_st_sentinel" class="MCXref xref">Configure SecureTransport to send events to Axway Sentinel</a>
