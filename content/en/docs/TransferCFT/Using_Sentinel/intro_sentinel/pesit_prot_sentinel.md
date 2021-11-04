{
    "title": "XFBTransfer system attributes",
    "linkTitle": "XFBTransfer system attributes",
    "weight": "220"
}This section provides information on the following attributes:

-   <a href="#Monitori" class="MCXref xref">Monitoring errors</a>
-   <a href="#Monitori2" class="MCXref xref">Monitoring tracked-event messages</a>
-   <a href="#Monitori3" class="MCXref xref">Monitoring processing cycles</a>
-   <a href="#List" class="MCXref xref">List of Sentinel states</a>

<span id="Monitori"></span>

## Monitoring errors

<table>
   <th>
      <tr>
<th><p>Sentinel</p>
<p>attribute</p>         </th>
<th><p>Data type</p>         </th>
<th><p>Length</p>         </th>
<th><p>Description</p>         </th>
<th><p>Name in</p>
<p><span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span></p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>IsException</p>
<p> </p>         </td>
         <td><p>Integer</p>
<p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>Values:</p>
<ul>
<li>0: The relevant Tracked-Event Message does not describe an exception.</li>
<li>1: The relevant Tracked-Event Message describes one or more exceptions.</li>
</ul>         </td>
         <td><p>Not used</p>         </td>
      </tr>
      <tr>
         <td><p>IsAlert</p>
<p> </p>         </td>
         <td><p>Integer</p>
<p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>Values:</p>
<ul>
<li>0: No alert is associated with the relevant Tracked-Event Message.</li>
<li>1: The relevant Tracked-Event Message is associated with a processing exception that generated an alert.</li>
</ul>         </td>
         <td><p>IsAlert</p>         </td>
      </tr>
      <tr>
         <td><p>ReturnCode</p>         </td>
         <td><p>String</p>         </td>
         <td><p>20</p>         </td>
         <td><p>Processing details that the relevant tracked application generated. When the value of IsAlert is 1, this attribute often contains an error code.</p>         </td>
         <td><p>DIAGI + DIAGP</p>         </td>
      </tr>
      <tr>
         <td><p>ReturnMessage</p>         </td>
         <td><p>String</p>         </td>
         <td><p>250</p>         </td>
         <td><p>Processing details that the relevant tracked application generated</p>         </td>
         <td><p>DIAGC</p>         </td>
      </tr>
   </tbody>
</table>

<span id="Monitori2"></span>

## Monitoring tracked-event messages

<table>
   <th>
      <tr>
<th><p>Sentinel</p>
<p>attribute</p>         </th>
<th><p>Data type</p>         </th>
<th><p>Length</p>         </th>
<th><p>Description</p>         </th>
<th><p>Name in <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span></p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>GMTDiff</p>         </td>
         <td><p>Int.</p>         </td>
         <td><p> </p>         </td>
         <td><p>Positive or negative difference between the GMT (Greenwich Mean Time) and the local time, expressed in minutes.</p>         </td>
         <td><p>uconf:sentinel.trkgmtdiff</p>         </td>
      </tr>
      <tr>
         <td><p>ProductName</p>         </td>
         <td><p>String</p>         </td>
         <td><p>50</p>         </td>
         <td><p>Name of the product that generated the relevant Tracked-Event. For customer applications this name is defined via the Universal Agent.</p>         </td>
         <td><p>uconf: sentinel.trkproductname</p>         </td>
      </tr>
      <tr>
         <td><p>ProductIPAddr</p>         </td>
         <td><p>String</p>         </td>
         <td><p>20</p>         </td>
         <td><p>Domain Name Server (DNS) of the product/application that generated the relevant Tracked Event.</p>         </td>
         <td><p>uconf: sentinel.trkproductipaddr</p>         </td>
      </tr>
      <tr>
         <td><p>ProductOS</p>         </td>
         <td><p>String.</p>         </td>
         <td><p>20</p>         </td>
         <td><p>Operating system of the application that generated the relevant Tracked Event.</p>         </td>
         <td><p><span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> target</p>         </td>
      </tr>
      <tr>
         <td><p>State</p>         </td>
         <td><p>String</p>         </td>
         <td><p>29</p>         </td>
         <td><p>Status of the relevant Tracked Event. The possible values of this attribute depend on the tracked application/product and file transfer protocol used. See <a href="#List" class="MCXref xref">List of Sentinel states</a> .</p>         </td>
         <td><p>PHASE/PHASESTEP combination</p>         </td>
      </tr>
   </tbody>
</table>

<span id="Monitori3"></span>

## Monitoring processing cycles

<table>
   <th>
      <tr>
<th><p>Sentinel</p>
<p>attribute</p>         </th>
<th><p>Data Type</p>         </th>
<th><p>Length</p>         </th>
<th><p>Description</p>         </th>
<th><p>Name in</p>
<p><span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span></p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>CycleId</p>         </td>
         <td><p>String</p>         </td>
         <td><p>250</p>         </td>
         <td><p>CycleId of the relevant Tracked Event.</p>         </td>
         <td><p>TRKR</p>         </td>
      </tr>
      <tr>
         <td><p>IsEnd</p>         </td>
         <td><p>Int.</p>         </td>
         <td><p> </p>         </td>
         <td><p>Values:</p>
<ul>
<li>0: The relevant Processing Cycle is not complete.</li>
<li>1 : The relevant Processing Cycle is complete.</li>
</ul>         </td>
         <td><p>IsEnd set to 1 when PHASE=X</p>         </td>
      </tr>
   </tbody>
</table>

<span id="List"></span>

## List of Sentinel states

### Roles of transfer partners

Although each transfer occurs between only two transfer partners, each transfer partner plays two roles:

-   Sender or Receiver  (the file is sent or received)
-   Requester or Server (the transfer request is sent or received)

For a given transfer, only the following combinations of partner roles are possible:

-   Sender/Requester and Receiver/Server (the partner that sent the file requested the transfer)
-   Receiver/Requester and Sender/Server the partner that received the file requested the transfer)

In the XFBTransfer Tracked Object, the Attributes ‘Direction” and “IsServer” reflect these roles (see below).

Receiver/Server transfer states

<table>
   <th>
      <tr>
<th><p>State</p>         </th>
<th><p>Compatible Sentinel State</p>         </th>
<th><p>IsEnd</p>         </th>
<th><p>IsAlert</p>         </th>
<th><p>IsException</p>         </th>
<th><p>Description</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>RECEIVING</p>         </td>
         <td><p>RECEIVING</p>         </td>
         <td><p>0</p>         </td>
         <td><p>0</p>         </td>
         <td><p>0</p>         </td>
         <td><p>File data transmission in progress</p>         </td>
      </tr>
      <tr>
         <td><p>CANCELED</p>         </td>
         <td><p>CANCELED</p>         </td>
         <td><p>0</p>         </td>
         <td><p>1</p>         </td>
         <td><p>1</p>         </td>
         <td><p>File data transmission locally canceled (KEEP command)</p>         </td>
      </tr>
      <tr>
         <td><p>SUSPENDED</p>         </td>
         <td><p>SUSPENDED</p>         </td>
         <td><p>0</p>         </td>
         <td><p>0</p>         </td>
         <td><p>1</p>         </td>
         <td><p>File data transmission locally suspended (HALT command)</p>         </td>
      </tr>
      <tr>
         <td><p>INTERRUPTED</p>         </td>
         <td><p>INTERRUPTED</p>         </td>
         <td><p>0</p>         </td>
         <td><p>1</p>         </td>
         <td><p>1</p>         </td>
         <td><p>File data transmission remotely suspended</p>         </td>
      </tr>
      <tr>
         <td><p>RECEIVED</p>         </td>
         <td><p>RECEIVED</p>         </td>
         <td><p>0</p>         </td>
         <td><p>0</p>         </td>
         <td><p>0</p>         </td>
         <td><p>File data transmission ended</p>         </td>
      </tr>
      <tr>
         <td><p>TO_ROUTE</p>         </td>
         <td><p>TO_ROUTE</p>         </td>
         <td><p>0</p>         </td>
         <td><p>0</p>         </td>
         <td><p>0</p>         </td>
         <td><p>Received file to be routed (only on the relay site in store and forward mode)</p>         </td>
      </tr>
      <tr>
         <td><p>POST_PROC</p>         </td>
         <td><p>RECEIVED</p>         </td>
         <td><p>0</p>         </td>
         <td><p>0</p>         </td>
         <td><p>0</p>         </td>
         <td><p>Post processing in progress</p>         </td>
      </tr>
      <tr>
         <td><p>POST_PROC_ABORT</p>         </td>
         <td><p>RECEIVED</p>         </td>
         <td><p>0</p>         </td>
         <td><p>1</p>         </td>
         <td><p>1</p>         </td>
         <td><p><span class="span_1">Post processing aborted by the application (KEEP command)</span></p>         </td>
      </tr>
      <tr>
         <td><p>ACK_EXPECTED</p>         </td>
         <td><p>RECEIVED</p>         </td>
         <td><p>0</p>         </td>
         <td><p>0</p>         </td>
         <td><p>0</p>         </td>
         <td><p>Waiting for a local acknowledgement</p>         </td>
      </tr>
      <tr>
         <td><p>ACKED</p>         </td>
         <td><p>ACKED</p>         </td>
         <td><p>1</p>         </td>
         <td><p>0</p>         </td>
         <td><p>0</p>         </td>
         <td><p>Transfer locally acknowledged by the application</p>         </td>
      </tr>
      <tr>
         <td><p>POST_PROC_ACK_ABORT</p>         </td>
         <td><p>RECEIVED/ACKED/NACKED</p>         </td>
         <td><p>0</p>         </td>
         <td><p>1</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Post processing of the Acknowledgement phase aborted by the application (KEEP command)</p>         </td>
      </tr>
      <tr>
         <td><p>COMPLETED</p>         </td>
         <td><p>CONSUMED</p>         </td>
         <td><p>1</p>         </td>
         <td><p>0</p>         </td>
         <td><p>0</p>         </td>
         <td><p>Transfer completed (this state is replaced by ROUTED on the relay site in store and forward mode)</p>         </td>
      </tr>
      <tr>
         <td><p>ROUTED</p>         </td>
         <td><p>ROUTED</p>         </td>
         <td><p>1</p>         </td>
         <td><p>0</p>         </td>
         <td><p>0</p>         </td>
         <td><p>File successfully routed (only on the relay site in store and forward mode)</p>         </td>
      </tr>
   </tbody>
</table>

Sender/Server transfer states

<table>
   <th>
      <tr>
<th><p>State</p>         </th>
<th><p>Compatible Sentinel State</p>         </th>
<th><p>IsEnd</p>         </th>
<th><p>IsAlert</p>         </th>
<th><p>IsException</p>         </th>
<th><p>Description</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>AVAILABLE</p>         </td>
         <td><p>AVAILABLE</p>         </td>
         <td><p>0</p>         </td>
         <td><p>0</p>         </td>
         <td><p>0</p>         </td>
         <td><p>Transfer available</p>         </td>
      </tr>
      <tr>
         <td><p>SENDING</p>         </td>
         <td><p>SENDING</p>         </td>
         <td><p>0</p>         </td>
         <td><p>0</p>         </td>
         <td><p>0</p>         </td>
         <td><p>File data transmission in progress</p>         </td>
      </tr>
      <tr>
         <td><p>CANCELED</p>         </td>
         <td><p>CANCELED</p>         </td>
         <td><p>0</p>         </td>
         <td><p>1</p>         </td>
         <td><p>1</p>         </td>
         <td><p>File data transmission locally canceled (KEEP command)</p>         </td>
      </tr>
      <tr>
         <td><p>SUSPENDED</p>         </td>
         <td><p>SUSPENDED</p>         </td>
         <td><p>0</p>         </td>
         <td><p>0</p>         </td>
         <td><p>1</p>         </td>
         <td><p><span class="span_1">File data transmission locally suspended (HALT command)</span></p>         </td>
      </tr>
      <tr>
         <td><p>INTERRUPTED</p>         </td>
         <td><p>INTERRUPTED</p>         </td>
         <td><p>0</p>         </td>
         <td><p>1</p>         </td>
         <td><p>1</p>         </td>
         <td><p>File data transmission remotely suspended</p>         </td>
      </tr>
      <tr>
         <td><p>SENT</p>         </td>
         <td><p>SENT</p>         </td>
         <td><p>0</p>         </td>
         <td><p>0</p>         </td>
         <td><p>0</p>         </td>
         <td><p>File data transmission ended</p>         </td>
      </tr>
      <tr>
         <td><p>POST_PROC</p>         </td>
         <td><p>SENT</p>         </td>
         <td><p>0</p>         </td>
         <td><p>0</p>         </td>
         <td><p>0</p>         </td>
         <td><p>Post processing in progress</p>         </td>
      </tr>
      <tr>
         <td><p>POST_PROC_ABORT</p>         </td>
         <td><p>SENT</p>         </td>
         <td><p>1</p>         </td>
         <td><p>1</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Post processing aborted by the application (KEEP command)</p>         </td>
      </tr>
      <tr>
         <td><p>ACK_EXPECTED</p>         </td>
         <td><p>SENT</p>         </td>
         <td><p>0</p>         </td>
         <td><p>0</p>         </td>
         <td><p>0</p>         </td>
         <td><p>Waiting for a remote acknowledgement</p>         </td>
      </tr>
      <tr>
         <td><p>ENDED_TO_ACK</p>         </td>
         <td><p>ENDED_TO_ACK</p>         </td>
         <td><p>0 (ack expected)/1</p>         </td>
         <td><p>0</p>         </td>
         <td><p>0</p>         </td>
         <td><p>Transfer remotely acknowledged</p>         </td>
      </tr>
      <tr>
         <td><p>POST_PROC_ACK_ABORT</p>         </td>
         <td><p>SENT/ENDED_TO_ACK/ENDED_TO_NACK</p>         </td>
         <td><p>0</p>         </td>
         <td><p>1</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Post processing of the Acknowledgement phase aborted by the application (KEEP command)</p>         </td>
      </tr>
      <tr>
         <td><p>COMPLETED</p>         </td>
         <td><p>CONSUMED</p>         </td>
         <td><p>1</p>         </td>
         <td><p>0</p>         </td>
         <td><p>0</p>         </td>
         <td><p>Transfer completed</p>         </td>
      </tr>
   </tbody>
</table>

Receiver/Requester transfer states

<table>
   <th>
      <tr>
<th><p>State</p>         </th>
<th><p>Compatible Sentinel State</p>         </th>
<th><p>IsEnd</p>         </th>
<th><p>IsAlert</p>         </th>
<th><p>IsException</p>         </th>
<th><p>Description</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>TO_EXECUTE</p>         </td>
         <td><p>TO_EXECUTE</p>         </td>
         <td><p>0</p>         </td>
         <td><p>0</p>         </td>
         <td><p>0</p>         </td>
         <td><p>Transfer to execute (delayed or to restart)</p>         </td>
      </tr>
      <tr>
         <td><p>RECEIVING</p>         </td>
         <td><p>RECEIVING</p>         </td>
         <td><p>0</p>         </td>
         <td><p>0</p>         </td>
         <td><p>0</p>         </td>
         <td><p>File data transmission in progress</p>         </td>
      </tr>
      <tr>
         <td><p>CANCELED</p>         </td>
         <td><p>CANCELED</p>         </td>
         <td><p>0</p>         </td>
         <td><p>1</p>         </td>
         <td><p>1</p>         </td>
         <td><p>File data transmission locally canceled (KEEP command)</p>         </td>
      </tr>
      <tr>
         <td><p>SUSPENDED</p>         </td>
         <td><p>SUSPENDED</p>         </td>
         <td><p>0</p>         </td>
         <td><p>0</p>         </td>
         <td><p>1</p>         </td>
         <td><p>File data transmission locally suspended (HALT command)</p>         </td>
      </tr>
      <tr>
         <td><p>INTERRUPTED</p>         </td>
         <td><p>INTERRUPTED</p>         </td>
         <td><p>0</p>         </td>
         <td><p>1</p>         </td>
         <td><p>1</p>         </td>
         <td><p>File data transmission remotely suspended</p>         </td>
      </tr>
      <tr>
         <td><p>RECEIVED</p>         </td>
         <td><p>RECEIVED</p>         </td>
         <td><p>0</p>         </td>
         <td><p>0</p>         </td>
         <td><p>0</p>         </td>
         <td><p>File data transmission ended</p>         </td>
      </tr>
      <tr>
         <td><p>POST_PROC</p>         </td>
         <td><p>RECEIVED</p>         </td>
         <td><p>0</p>         </td>
         <td><p>0</p>         </td>
         <td><p>0</p>         </td>
         <td><p>Post processing in progress</p>         </td>
      </tr>
      <tr>
         <td><p>POST_PROC_ABORT</p>         </td>
         <td><p>RECEIVED</p>         </td>
         <td><p>0</p>         </td>
         <td><p>1</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Post processing aborted by the application (KEEP command)</p>         </td>
      </tr>
      <tr>
         <td><p>ACK_EXPECTED</p>         </td>
         <td><p>RECEIVED</p>         </td>
         <td><p>0</p>         </td>
         <td><p>0</p>         </td>
         <td><p>0</p>         </td>
         <td><p>Waiting for a local acknowledgement</p>         </td>
      </tr>
      <tr>
         <td><p>ACKED</p>         </td>
         <td><p>ACKED</p>         </td>
         <td><p>1</p>         </td>
         <td><p>0</p>         </td>
         <td><p>0</p>         </td>
         <td><p>Transfer locally acknowledged by the application</p>         </td>
      </tr>
      <tr>
         <td><p>POST_PROC_ACK_ABORT</p>         </td>
         <td><p>RECEIVED/ACKED/NACKED</p>         </td>
         <td><p>0</p>         </td>
         <td><p>1</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Post processing of the Acknowledgement phase aborted by the application (KEEP command)</p>         </td>
      </tr>
      <tr>
         <td><p>COMPLETED</p>         </td>
         <td><p>CONSUMED</p>         </td>
         <td><p>1</p>         </td>
         <td><p>0</p>         </td>
         <td><p>0</p>         </td>
         <td><p>Transfer completed</p>         </td>
      </tr>
   </tbody>
</table>

Sender/Requester transfer states

<table>
   <th>
      <tr>
<th><p>State</p>         </th>
<th><p>Compatible Sentinel State</p>         </th>
<th><p>IsEnd</p>         </th>
<th><p>IsAlert</p>         </th>
<th><p>IsException</p>         </th>
<th><p>Description</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>PRE_PROC</p>         </td>
         <td><p>AVAILABLE/TO_EXECUTE</p>         </td>
         <td><p>0</p>         </td>
         <td><p>0</p>         </td>
         <td><p>0</p>         </td>
         <td><p>Pre-processing in progress</p>         </td>
      </tr>
      <tr>
         <td><p>PRE_PROC_ABORT</p>         </td>
         <td><p>CANCELED</p>         </td>
         <td><p>0</p>         </td>
         <td><p>1</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Pre-processing aborted by the application (KEEP command)</p>         </td>
      </tr>
      <tr>
         <td><p>TO_EXECUTE</p>         </td>
         <td><p>TO_EXECUTE</p>         </td>
         <td><p>0</p>         </td>
         <td><p>0</p>         </td>
         <td><p>0</p>         </td>
         <td><p>Transfer to execute (delayed or to restart)</p>         </td>
      </tr>
      <tr>
         <td><p>SENDING</p>         </td>
         <td><p>SENDING</p>         </td>
         <td><p>0</p>         </td>
         <td><p>0</p>         </td>
         <td><p>0</p>         </td>
         <td><p>File data transmission in progress</p>         </td>
      </tr>
      <tr>
         <td><p>CANCELED</p>         </td>
         <td><p>CANCELED</p>         </td>
         <td><p>0</p>         </td>
         <td><p>1</p>         </td>
         <td><p>1</p>         </td>
         <td><p>File data transmission locally canceled (KEEP command)</p>         </td>
      </tr>
      <tr>
         <td><p>SUSPENDED</p>         </td>
         <td><p>SUSPENDED</p>         </td>
         <td><p>0</p>         </td>
         <td><p>0</p>         </td>
         <td><p>1</p>         </td>
         <td><p>File data transmission locally suspended (HALT command)</p>         </td>
      </tr>
      <tr>
         <td><p>INTERRUPTED</p>         </td>
         <td><p>INTERRUPTED</p>         </td>
         <td><p>0</p>         </td>
         <td><p>1</p>         </td>
         <td><p>1</p>         </td>
         <td><p>File data transmission remotely suspended</p>         </td>
      </tr>
      <tr>
         <td><p>SENT</p>         </td>
         <td><p>SENT</p>         </td>
         <td><p>0</p>         </td>
         <td><p>0</p>         </td>
         <td><p>0</p>         </td>
         <td><p>File data transmission ended</p>         </td>
      </tr>
      <tr>
         <td><p>POST_PROC</p>         </td>
         <td><p>SENT</p>         </td>
         <td><p>0</p>         </td>
         <td><p>0</p>         </td>
         <td><p>0</p>         </td>
         <td><p>Post-processing in progress</p>         </td>
      </tr>
      <tr>
         <td><p>POST_PROC_ABORT</p>         </td>
         <td><p>SENT</p>         </td>
         <td><p>0</p>         </td>
         <td><p>1</p>         </td>
         <td><p>1</p>         </td>
         <td><p><span class="span_1">Post-processing aborted by the application (KEEP command)</span></p>         </td>
      </tr>
      <tr>
         <td><p>ACK_EXPECTED</p>         </td>
         <td><p>SENT</p>         </td>
         <td><p>0</p>         </td>
         <td><p>0</p>         </td>
         <td><p>0</p>         </td>
         <td><p>Waiting for a remote acknowledgement</p>         </td>
      </tr>
      <tr>
         <td><p>ENDED_TO_ACK</p>         </td>
         <td><p>ENDED_TO_ACK</p>         </td>
         <td><p>0 (ack expected)/1</p>         </td>
         <td><p>0</p>         </td>
         <td><p>0</p>         </td>
         <td><p>Transfer remotely acknowledged</p>         </td>
      </tr>
      <tr>
         <td><p>POST_PROC_ACK_ABORT</p>         </td>
         <td><p>SENT/ENDED_TO_ACK/ENDED_TO_NACK</p>         </td>
         <td><p>0</p>         </td>
         <td><p>1</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Post-processing of the Acknowledgement phase aborted by the application (KEEP command)</p>         </td>
      </tr>
      <tr>
         <td><p>COMPLETED</p>         </td>
         <td><p>CONSUMED</p>         </td>
         <td><p>1</p>         </td>
         <td><p>0</p>         </td>
         <td><p>0</p>         </td>
         <td><p>Transfer completed</p>         </td>
      </tr>
   </tbody>
</table>
