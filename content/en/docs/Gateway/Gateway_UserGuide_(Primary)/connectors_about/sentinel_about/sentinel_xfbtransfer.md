{
    "title": "Sentinel: XFBTransfer Tracked Object",
    "linkTitle": "XFBTransfer",
    "weight": "220"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Connectors

[About XFBTransfer](#About_XFBTransfer)

[XFBTransfer: Attributes](#Attributes)

[XFBTransfer: Predefined Requests](#Requests)

<span id="About_XFBTransfer"></span>

## About XFBTransfer

When you configure Sentinel to monitor Gateway, you can import the <span style="font-style: italic;">XFBTransfer</span> Tracked Object. XFBTransfer stores and describes Tracked Instances of Gateway transfers. Each Tracked Instance describes a single step of a single transfer process. Taken together, the Tracked Instances in each Processing Cycle describe the transfer of a file or, alternatively, a message between two Gateway applications.

In this documentation, a Gateway file transfer is referred to as a <span style="font-style: italic;">transfer</span>.

<span id="Attributes"></span>

## XFBTransfer Attributes

XFBTransfer includes attributes that you can use to identify:

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><ul>
<li><a href="#State">Each step in the transfer process</a></li>
<li><a href="#roles">The roles of transfer partners</a></li>
<li><a href="#Senders_and_Receivers">Senders and Receivers</a></li>
<li><a href="#Transfer_monitors">Transfer monitors</a></li>
<li><a href="#Transfer_users">Transfer users</a></li>
<li><a href="#Transfers">Transfers</a></li>
<li><a href="#Validity_periods">Transfer validity periods</a></li>
</ul>         </td>
         <td><ul>
<li><a href="#Dates_and_times">Transfer dates and times</a></li>
<li><a href="#protocols">Transfer protocols</a></li>
<li><a href="#Transfer_options">Transfer options</a></li>
<li><a href="#Transfer_size">The size of transfers</a></li>
<li><a href="#Transfer_data">The structure and content of transfers</a></li>
<li><a href="#smtp_pop3">Details about SMTP/POP3 transfers</a></li>
<li><a href="#swiftnet">Details about SWIFTNet transfers</a></li>
</ul>         </td>
      </tr>
   </tbody>
</table>

<span id="State"></span>

### Identifying each step in the transfer process

For each step of each Gateway transfer, Gateway generates one Tracked Instance. In each Tracked Instance, the <span style="font-weight: bold;">State</span> attribute identifies the relevant step of the transfer process. The following table lists and describes the possible values of the <span style="font-weight: bold;">State</span> attribute for the Tracked Instances of a single Gateway transfer.

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>State</p>         </th>
<th class="HeadD-Column1-Header1"><p>Details</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Created</p>         </td>
         <td><p>The <span style="font-weight: bold;">Requester</span> prepared a Transfer Request and updated the transfer catalog or, alternatively the transfer Mailbox.</p>         </td>
      </tr>
      <tr>
         <td><p>To_Execute</p>         </td>
         <td><p>The <span style="font-weight: bold;">Requester</span> sent the Transfer Request to the <span style="font-weight: bold;">Server</span>.</p>         </td>
      </tr>
      <tr>
         <td><p>Sending</p>         </td>
         <td><p>The <span style="font-weight: bold;">Sender</span> is sending data.</p>         </td>
      </tr>
      <tr>
         <td><p>Receiving</p>         </td>
         <td><p>The <span style="font-weight: bold;">Receiver</span> is receiving data.</p>         </td>
      </tr>
      <tr>
         <td><p>Sent</p>         </td>
         <td><p>The <span style="font-weight: bold;">Sender</span> sent all of the transfer data.</p>         </td>
      </tr>
      <tr>
         <td><p>Received</p>         </td>
         <td><p>The <span style="font-weight: bold;">Receiver</span> received all of the transfer data.</p>         </td>
      </tr>
      <tr>
         <td><p>Terminated</p>         </td>
         <td><p>The <span style="font-weight: bold;">Sender</span> sent all of the transfer data, and the <span style="font-weight: bold;">Receiver</span> received all of the transfer data. Both partners successfully completed the transfer.</p>         </td>
      </tr>
   </tbody>
</table>

Taken together, the set of Tracked Instances that concern a single Gateway transfer are referred to as a <span style="font-style: italic;">Processing Cycle</span>. To identify the Tracked Instances that belong to the same Processing Cycle, use the <span style="font-weight: bold;">CycleId</span> attribute.

<span style="font-weight: bold;">Note:</span> Not all States in Gateway have equivalent States in Axway Sentinel.

<span id="roles"></span>

### Identifying the roles of transfer partners

Although each Gateway transfer occurs between only two transfer partners, each transfer partner plays two roles:

-   <span style="font-weight: bold;">Sender</span> or <span style="font-weight: bold;">Receiver</span>
-   <span style="font-weight: bold;">Requester</span> or <span style="font-weight: bold;">Server</span>

The [preceding table](#State) underscores these roles. Note that transfer partners are referred to as Requesters, Senders, and Receivers.

For a given transfer, only the following combinations of partner roles are possible:

-   <span style="font-weight: bold;">Sender/Requester</span> and <span style="font-weight: bold;">Receiver/Server</span>  
    The partner that <span style="font-weight: bold;">sent</span> the transfer <span style="font-weight: bold;">requested</span> the transfer.  
    The partner that <span style="font-weight: bold;">received</span> the transfer <span style="font-weight: bold;">listened</span> for the Transfer Request.
-   <span style="font-weight: bold;">Receiver/Requester</span> and <span style="font-weight: bold;">Sender/Server</span>  
    The partner that <span style="font-weight: bold;">received</span> the transfer <span style="font-weight: bold;">requested</span> the transfer.  
    The partner that <span style="font-weight: bold;">sent</span> the transfer <span style="font-weight: bold;">listened</span> for the Transfer Request.

In each Tracked Instance, the following attributes identify the roles of the transfer partner that generated the Tracked Instance.

<table>
         
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Attribute</p>         </th>
<th class="HeadE-Column1-Header1"><p>Data Type</p>         </th>
<th class="HeadD-Column1-Header1"><p>Value</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p><span id="Direction"></span>Direction</p>         </td>
         <td><p>String</p>         </td>
         <td><p>One of:</p>
<ul>
<li><span style="font-weight: bold;">E</span>: The <span style="font-weight: bold;">Sender</span> generated the Tracked Instance. Equivalent to Output (O) on Gateway.</li>
<li><span style="font-weight: bold;">R</span>: The <span style="font-weight: bold;">Receiver</span> generated the Tracked Instance. Equivalent to Input (I) on Gateway.</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span id="IsServer"></span>IsServer</p>         </td>
         <td><p>String</p>         </td>
         <td><p>One of:</p>
<ul>
<li><span style="font-weight: bold;">1</span>: The Sender or, alternatively the Receiver is a <span style="font-weight: bold;">Server</span>.</li>
<li><span style="font-weight: bold;">0</span>: The Sender or, alternatively the Receiver is a <span style="font-weight: bold;">Requester</span>.</li>
</ul>         </td>
      </tr>
   </tbody>
</table>

#### Examples

When a transfer occurs between a <span style="font-weight: bold;">Sender/Requester</span> and a <span style="font-weight: bold;">Receiver/Server</span>, Sentinel receives the following Tracked Instances.

<table>
         
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>State</p>         </th>
<th class="HeadE-Column1-Header1"><p>Direction</p>         </th>
<th class="HeadD-Column1-Header1"><p>IsServer</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Created</p>         </td>
         <td><p><span style="font-weight: bold;">E</span><span style="font-style: italic;">(Sender)</span></p>         </td>
         <td><p><span style="font-weight: bold;">0</span><span style="font-style: italic;">(Requester)</span></p>         </td>
      </tr>
      <tr>
         <td><p>To_Execute</p>         </td>
         <td><p><span style="font-weight: bold;">E</span><span style="font-style: italic;">(Sender)</span></p>         </td>
         <td><p><span style="font-weight: bold;">0</span><span style="font-style: italic;">(Requester)</span></p>         </td>
      </tr>
      <tr>
         <td><p>Sending</p>         </td>
         <td><p><span style="font-weight: bold;">E</span><span style="font-style: italic;">(Sender)</span></p>         </td>
         <td><p><span style="font-weight: bold;">0</span><span style="font-style: italic;">(Requester)</span></p>         </td>
      </tr>
      <tr>
         <td><p>Receiving</p>         </td>
         <td><p><span style="font-weight: bold;">R</span><span style="font-style: italic;">(Receiver)</span></p>         </td>
         <td><p><span style="font-weight: bold;">1</span><span style="font-style: italic;">(Server)</span></p>         </td>
      </tr>
      <tr>
         <td><p>Sent</p>         </td>
         <td><p><span style="font-weight: bold;">E</span><span style="font-style: italic;">(Sender)</span></p>         </td>
         <td><p><span style="font-weight: bold;">0</span><span style="font-style: italic;">(Requester)</span></p>         </td>
      </tr>
      <tr>
         <td><p>Received</p>         </td>
         <td><p><span style="font-weight: bold;">R</span><span style="font-style: italic;">(Receiver)</span></p>         </td>
         <td><p><span style="font-weight: bold;">1</span><span style="font-style: italic;">(Server)</span></p>         </td>
      </tr>
   </tbody>
</table>

However, when a transfer occurs between a <span style="font-weight: bold;">Receiver/Requester</span> and a <span style="font-weight: bold;">Sender/Server</span>, Sentinel receives the following Tracked Instances.

<table>
         
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>State</p>         </th>
<th class="HeadE-Column1-Header1"><p>Direction</p>         </th>
<th class="HeadD-Column1-Header1"><p>IsServer</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Created</p>         </td>
         <td><p><span style="font-weight: bold;">R</span><span style="font-style: italic;">(Receiver)</span></p>         </td>
         <td><p><span style="font-weight: bold;">0</span><span style="font-style: italic;">(Requester)</span></p>         </td>
      </tr>
      <tr>
         <td><p>To_Execute</p>         </td>
         <td><p><span style="font-weight: bold;">R</span><span style="font-style: italic;">(Receiver)</span></p>         </td>
         <td><p><span style="font-weight: bold;">0</span><span style="font-style: italic;">(Requester)</span></p>         </td>
      </tr>
      <tr>
         <td><p>Sending</p>         </td>
         <td><p><span style="font-weight: bold;">E</span><span style="font-style: italic;">(Sender)</span></p>         </td>
         <td><p><span style="font-weight: bold;">1</span><span style="font-style: italic;">(Server)</span></p>         </td>
      </tr>
      <tr>
         <td><p>Receiving</p>         </td>
         <td><p><span style="font-weight: bold;">R</span><span style="font-style: italic;">(Receiver)</span></p>         </td>
         <td><p><span style="font-weight: bold;">0</span><span style="font-style: italic;">(Requester)</span></p>         </td>
      </tr>
      <tr>
         <td><p>Sent</p>         </td>
         <td><p><span style="font-weight: bold;">E</span><span style="font-style: italic;">(Sender)</span></p>         </td>
         <td><p><span style="font-weight: bold;">1</span><span style="font-style: italic;">(Server)</span></p>         </td>
      </tr>
      <tr>
         <td><p>Received</p>         </td>
         <td><p><span style="font-weight: bold;">R</span><span style="font-style: italic;">(Receiver)</span></p>         </td>
         <td><p><span style="font-weight: bold;">0</span><span style="font-style: italic;">(Requester)</span></p>         </td>
      </tr>
   </tbody>
</table>

<span id="Senders_and_Receivers"></span>

### Identifying Senders and Receivers

Together, the [Direction](#Direction) and [IsServer](#IsServer) attributes identify the [role](#roles) of a transfer partner in the transfer process. However, they do not explicitly identify partners. To explicitly identify transfer partners, use the following attributes:

<table>
         
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Attribute</p>         </th>
<th class="HeadE-Column1-Header1"><p>Data Type</p>         </th>
<th class="HeadD-Column1-Header1"><p>Value</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Site</p>         </td>
         <td><p>String</p>         </td>
         <td><p>Partner alias that the local partner uses to identify the parameter settings for the remote partner. When the value of the <a href="#Direction">Direction</a> attribute is:</p>
<ul>
<li><span style="font-weight: bold;">R</span> (Receiver), the Receiver is the local partner. The Receiver used the value of this attribute to identify the parameter settings for the Sender.</li>
<li><span style="font-weight: bold;">E</span> (Sender), the Sender is the local partner. The Sender used the value of this attribute to identify the parameter settings for the Receiver.</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>ReceiverId</p>         </td>
         <td><p>String</p>         </td>
         <td><p>Network identifier of the Receiver</p>         </td>
      </tr>
      <tr>
         <td><p>SenderId</p>         </td>
         <td><p>String</p>         </td>
         <td><p>Network identifier of the Sender</p>         </td>
      </tr>
      <tr>
         <td><p>RAppl</p>         </td>
         <td><p>String</p>         </td>
         <td><p>Network identifier of the Receiver application</p>         </td>
      </tr>
      <tr>
         <td><p>SAppl</p>         </td>
         <td><p>String</p>         </td>
         <td><p>Network identifier of the Sender application</p>         </td>
      </tr>
      <tr>
         <td><p>FinalReceiverId</p>         </td>
         <td><p>String</p>         </td>
         <td><p>If the Processing Cycle:</p>
<ul>
<li>Describes a stored and forwarded transfer, the value of this attribute is the Network Identifier of the final Receiver of the transfer</li>
<li>Does not describe a stored and forwarded transfer, the value of this attribute is empty</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>OriginalSenderId</p>         </td>
         <td><p>String</p>         </td>
         <td><p>If the Processing Cycle:</p>
<ul>
<li>Describes a stored and forwarded transfer, the value of this attribute is the Network Identifier of the initial Sender of the transfer</li>
<li>Does not describe a stored and forwarded transfer, the value of this attribute is empty</li>
</ul>         </td>
      </tr>
   </tbody>
</table>

<span id="Transfer_monitors"></span>

### Identifying transfer monitors

Each Sender and Receiver is a logical entity that operates from a physical machine. Each machine is referred to as a <span style="font-style: italic;">transfer monitor</span>. To identify details about transfer monitors, use the attributes that are listed in the following table. If the value of the [Direction](#Direction) attribute is:

-   <span style="font-weight: bold;">E</span> (Sender), these attributes identify the Sender's transfer monitor
-   <span style="font-weight: bold;">R</span> (Receiver), these attributes identify the Receiver's transfer monitor

<table>
         
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Attribute</p>         </th>
<th class="HeadE-Column1-Header1"><p>Data Type</p>         </th>
<th class="HeadD-Column1-Header1"><p>Value</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Location</p>         </td>
         <td><p>String</p>         </td>
         <td><p>Unique and logical identifier of the transfer monitor.</p>         </td>
      </tr>
      <tr>
         <td><p>Machine</p>         </td>
         <td><p>String</p>         </td>
         <td><p>Name of the Gateway application and platform that run on the transfer monitor.</p>         </td>
      </tr>
      <tr>
         <td><p><span id="Monitor"></span>Monitor</p>         </td>
         <td><p>String</p>         </td>
         <td><p>Application name: "GTW"</p>         </td>
      </tr>
      <tr>
         <td><p>MonitorVersion</p>         </td>
         <td><p>String</p>         </td>
         <td><p>Version of the Gateway application that runs on the transfer monitor.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="Transfer_users"></span>

### Identifying transfer users

Although Senders and Receivers perform all actions in the transfer process, they do not initiate these actions. Transfer users initiate transfer actions. Transfer users include both people and software applications. To monitor details about transfer users, use the following attributes.

<table>
         
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Attribute</p>         </th>
<th class="HeadE-Column1-Header1"><p>Data Type</p>         </th>
<th class="HeadD-Column1-Header1"><p>Value</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>UserId</p>         </td>
         <td><p>String</p>         </td>
         <td><p>Local identifier of the user who owns the transferred file or message</p>         </td>
      </tr>
      <tr>
         <td><p>GroupId</p>         </td>
         <td><p>String</p>         </td>
         <td><p>Local identifier of the group to which the transfer owner belongs</p>         </td>
      </tr>
      <tr>
         <td><p><span id="RequestUserId"></span>RequestUserId</p>         </td>
         <td><p>String</p>         </td>
         <td><p>Local identifier of the user who requested the transfer. If the user is:</p>
<ul>
<li>also the transfer owner, the values of <span style="font-weight: bold;">UserId</span> and <span style="font-weight: bold;">RequestUserId</span> match</li>
<li>not the transfer owner, the values of <span style="font-weight: bold;">UserId</span> and <span style="font-weight: bold;">RequestUserId</span> do not match</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>RequestGroupId</p>         </td>
         <td><p>String</p>         </td>
         <td><p>Local identifier of the group to which the requesting user belongs</p>         </td>
      </tr>
      <tr>
         <td><p>Trustee</p>         </td>
         <td><p>String</p>         </td>
         <td><p>If User Access Control is:</p>
<ul>
<li>activated for the transfer, the value of this attribute is the local identifier of the transfer owner (<span style="font-weight: bold;">UserId</span>)</li>
<li>not activated for the transfer, the value of this attribute is the network identifier of the user who requested the transfer (<span style="font-weight: bold;">RequestUserId</span>)</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>RUser</p>         </td>
         <td><p>String</p>         </td>
         <td><p>Local identifier of the user who received the transfer</p>         </td>
      </tr>
      <tr>
         <td><p><span id="SUser"></span>SUser</p>         </td>
         <td><p>String</p>         </td>
         <td><p>Local identifier of the user who sent the transfer</p>         </td>
      </tr>
   </tbody>
</table>

<span id="Transfers"></span>

### Identifying transfers

To identify a transfer, use the following attributes.

<table>
         
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Attribute</p>         </th>
<th class="HeadE-Column1-Header1"><p>Data Type</p>         </th>
<th class="HeadD-Column1-Header1"><p>Value</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>IdAppl</p>         </td>
         <td><p>String</p>         </td>
         <td><p>If the value of the <a href="#IsServer">IsServer</a> attribute is:</p>
<ul>
<li><span style="font-weight: bold;">0</span>, the value of this attribute is the local identifier of the Requester</li>
<li><span style="font-weight: bold;">1</span>, the value of this attribute is empty</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Application</p>         </td>
         <td><p>String</p>         </td>
         <td><p>Local Application.</p>         </td>
      </tr>
      <tr>
         <td><p>FileName</p>         </td>
         <td><p>String</p>         </td>
         <td><p>If the value of the <a href="#CommandType">CommandType</a> attribute is:</p>
<ul>
<li><span style="font-weight: bold;">Message</span>, this attribute is empty</li>
<li><span style="font-weight: bold;">File</span> and the value of the <a href="#Direction">Direction</a> attribute is <span style="font-weight: bold;">E</span> (Sender), this attribute identifies the file from which the Sender retrieved the transfer data</li>
<li><span style="font-weight: bold;">File</span> and the value of the <a href="#Direction">Direction</a> attribute is <span style="font-weight: bold;">R</span> (Receiver), this attribute identifies the file in which the Receiver recorded the transfer data</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>LocalId</p>         </td>
         <td><p>String</p>         </td>
         <td><p>If the value of the <a href="#Direction">Direction</a> attribute is:</p>
<ul>
<li><span style="font-weight: bold;">E</span> (Sender), the value of this attribute is the local transfer identifier for the Sender</li>
<li><span style="font-weight: bold;">R</span> (Receiver), the value of this attribute is the local transfer identifier for the Receiver</li>
</ul>
<p>Senders and Receivers use local transfer identifiers to manage transfers (cancel, delete, and so on).</p>         </td>
      </tr>
      <tr>
         <td><p>ProtocolFileName</p>         </td>
         <td><p>String</p>         </td>
         <td><p>Network transfer identifier. The Sender sent this identifier to the Receiver.</p>         </td>
      </tr>
      <tr>
         <td><p>ProtocolFileLabel</p>         </td>
         <td><p>String</p>         </td>
         <td><p>Network transfer name. The Sender sent this name to the Receiver. The Receiver can use this name to locally name the transfer.</p>         </td>
      </tr>
      <tr>
         <td><p>ProtocolId</p>         </td>
         <td><p>String</p>         </td>
         <td><p>Network transfer identifier. The Sender generated this identifier. The Receiver acknowledged this identifier.</p>         </td>
      </tr>
      <tr>
         <td><p>ProtocolMessage</p>         </td>
         <td><p>String</p>         </td>
         <td><p>If the value of the <a href="#CommandType">CommandType</a> attribute is:</p>
<ul>
<li><span style="font-weight: bold;">Message</span>, the value of this attribute is the content of the transferred message</li>
</ul>
<ul>
<li><span style="font-weight: bold;">File</span>, this attribute is empty</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>PositionNumber</p>         </td>
         <td><p>Integer</p>         </td>
         <td><p>Catalog transfer identifier. If the value of the <a href="#Direction">Direction</a> attribute is:</p>
<ul>
<li><span style="font-weight: bold;">E</span> (Sender), the value of this attribute identifies the transfer in the Sender's transfer catalog or transfer Mailbox</li>
<li><span style="font-weight: bold;">R</span> (Receiver), the value of this attribute identifies the transfer in the Receiver's transfer catalog or transfer Mailbox</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>ProtocolParameter</p>         </td>
         <td><p>String</p>         </td>
         <td><p>Network transfer description. The Sender sent this description to the Receiver.</p>         </td>
      </tr>
      <tr>
         <td><p>UserParameter</p>         </td>
         <td><p>String</p>         </td>
         <td><p>Local transfer description. When the Requester recorded the transfer in the transfer catalog or transfer Mailbox, the Requester generated this description.</p>
<p>The value of this attribute includes two parts:</p>
<ul>
<li>The first part contains the first forty characters of the description</li>
<li>The second part contains the remaining characters of the description</li>
</ul>         </td>
      </tr>
   </tbody>
</table>

<span id="Validity_periods"></span>

### Identifying transfer validity periods

Senders and Receivers can perform specific transfers only during the specified validity periods. To monitor the validity periods for transfers, use the following attributes.

<table>
         
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Attribute</p>         </th>
<th class="HeadE-Column1-Header1"><p>Data Type</p>         </th>
<th class="HeadD-Column1-Header1"><p>Value</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>EarliestDate</p>         </td>
         <td><p>Date</p>         </td>
         <td><p>Date on which the validity period begins</p>         </td>
      </tr>
      <tr>
         <td><p>EarliestTime</p>         </td>
         <td><p>String</p>         </td>
         <td><p>Time at which the validity period begins</p>         </td>
      </tr>
      <tr>
         <td><p>LatestDate</p>         </td>
         <td><p>Date</p>         </td>
         <td><p>Date on which the validity period ends</p>         </td>
      </tr>
      <tr>
         <td><p>LatestTime</p>         </td>
         <td><p>String</p>         </td>
         <td><p>Time at which the validity period ends</p>         </td>
      </tr>
   </tbody>
</table>

<span id="Dates_and_times"></span>

### Identifying transfer dates and times

During the transfer process, Senders and Receivers record the time and date of certain actions that they perform. To monitor these details, use the following attributes.

<table>
         
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Attribute</p>         </th>
<th class="HeadE-Column1-Header1"><p>Date Type</p>         </th>
<th class="HeadD-Column1-Header1"><p>Value</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>CreationDate</p>         </td>
         <td><p>Date</p>         </td>
         <td><p>By default, the system date on which the Sender sent the transfer. The Sender can set this date. The Receiver can filter transfers based on this date.</p>         </td>
      </tr>
      <tr>
         <td><p>CreationTime</p>         </td>
         <td><p>String</p>         </td>
         <td><p>By default, the system time at which the Sender sent the transfer. The Sender can set this time. The Receiver can filter transfers based on this time.</p>         </td>
      </tr>
      <tr>
         <td><p>SendDate</p>         </td>
         <td><p>Date</p>         </td>
         <td><p>If the value of the <a href="#Direction">Direction</a> attribute is:</p>
<ul>
<li><span style="font-weight: bold;">E</span> (Sender), the value of this attribute is the date on which the Sender recorded the transfer in the transfer catalog or transfer Mailbox</li>
<li><span style="font-weight: bold;">R</span> (Receiver), the value of this attribute is the date on which the Receiver recorded the transfer in the transfer catalog or transfer Mailbox</li>
</ul>
<p>The Sender and the Receiver record each transfer only once.</p>         </td>
      </tr>
      <tr>
         <td><p>SendTime</p>         </td>
         <td><p>String</p>         </td>
         <td><p>If the value of the <a href="#Direction">Direction</a> attribute is:</p>
<ul>
<li><span style="font-weight: bold;">E</span> (Sender), the value of this attribute is the local time at which the Sender recorded the transfer in the transfer catalog or transfer Mailbox</li>
<li><span style="font-weight: bold;">R</span> (Receiver), the value of this attribute is the local time at which the Receiver recorded the transfer in the transfer catalog or transfer Mailbox</li>
</ul>
<p>The Sender and the Receiver record each transfer only once.</p>         </td>
      </tr>
      <tr>
         <td><p>AckDate</p>         </td>
         <td><p>Date</p>         </td>
         <td><p>Date on which the Receiver acknowledged the transfer. If the Receiver did not acknowledge the transfer, this attribute is empty.</p>         </td>
      </tr>
      <tr>
         <td><p>AckTime</p>         </td>
         <td><p>String</p>         </td>
         <td><p>Time at which the Receiver acknowledged the transfer. If the Receiver did not acknowledge the transfer, this attribute is empty.</p>         </td>
      </tr>
      <tr>
         <td><p>StartDate</p>         </td>
         <td><p>Date</p>         </td>
         <td><p>If the value of the <a href="#State">State</a> attribute is:</p>
<ul>
<li><span style="font-weight: bold;">SENT</span>, the value of this attribute is the date on which the Sender began sending the transfer</li>
<li><span style="font-weight: bold;">RECEIVED</span>, the value of this attribute is the date on which the Receiver began receiving the transfer</li>
</ul>
<p>These dates are expressed in <span style="font-style: italic;">dd.mm.yyyy</span> format.</p>         </td>
      </tr>
      <tr>
         <td><p>StartTime</p>         </td>
         <td><p>String</p>         </td>
         <td><p>If the value of the <a href="#State">State</a> attribute is:</p>
<ul>
<li><span style="font-weight: bold;">SENT</span>, the value of this attribute is the local time at which the Sender began sending the transfer</li>
<li><span style="font-weight: bold;">RECEIVED</span>, the value of this attribute is the local time at which the Receiver began receiving the transfer</li>
</ul>
<p>These times are expressed in <span style="font-style: italic;">hh:mn:ss</span> format.</p>         </td>
      </tr>
      <tr>
         <td><p>EndDate</p>         </td>
         <td><p>Date</p>         </td>
         <td><p>If the value of the <a href="#State">State</a> attribute is:</p>
<ul>
<li><span style="font-weight: bold;">SENT</span>, the value of this attribute is the date on which the Sender stopped sending the transfer</li>
<li><span style="font-weight: bold;">RECEIVED</span>, the value of this attribute is the date on which the Receiver stopped receiving the transfer</li>
</ul>
<p>These dates are expressed in <span style="font-style: italic;">dd.mm.yyyy</span> format.</p>         </td>
      </tr>
      <tr>
         <td><p>EndTime</p>         </td>
         <td><p>String</p>         </td>
         <td><p>If the value of the <a href="#State">State</a> attribute is:</p>
<ul>
<li><span style="font-weight: bold;">SENT</span>, the value of this attribute is the local time at which the Sender stopped sending the transfer</li>
<li><span style="font-weight: bold;">RECEIVED</span>, the value of this attribute is the local time at which the Receiver stopped receiving the transfer</li>
</ul>
<p>These times are expressed in <span style="font-style: italic;">hh:mn:ss</span> format.</p>         </td>
      </tr>
      <tr>
         <td><p>TransmissionDuration</p>         </td>
         <td><p>String</p>         </td>
         <td><p>If the value of the <a href="#State">State</a> attribute is:</p>
<ul>
<li><span style="font-weight: bold;">SENT</span>, the value of this attribute is the time that was required to send the transfer</li>
<li><span style="font-weight: bold;">RECEIVED</span>, the value of this attribute is the time that was required to receive the transfer</li>
</ul>
<p>These times are expressed in seconds.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="protocols"></span>

### Identifying transfer protocols

Most transfers are associated with three protocol layers:

-   Network Layer: rules that manage transfer media
-   SSL/TLS Layer (Security Sockets Layer / Transport Layer Security): rules that manage transfer security
-   Protocol Layer: rules that manage transfer communication

To monitor details about the Protocol and SSL/TLS Layers, use the following attributes:

<table>
         
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Attribute</p>         </th>
<th class="HeadE-Column1-Header1"><p>Data Type</p>         </th>
<th class="HeadD-Column1-Header1"><p>Value</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Protocol</p>         </td>
         <td><p>String</p>         </td>
         <td><p>Name of the protocol that operates at the Protocol Layer of the transfer. Possible values:</p>
<ul>
<li><span style="font-weight: bold;">PSIT_HS_E</span><span style="font-style: italic;">(PESIT, version E)</span></li>
<li><span style="font-weight: bold;">PSIT_HS_D</span><span style="font-style: italic;">(PESIT, version D)</span></li>
<li><span style="font-weight: bold;">PEL</span></li>
<li><span style="font-weight: bold;">ODT</span><span style="font-style: italic;">(Odette File Transfer Protocol)</span></li>
<li><span style="font-weight: bold;">FTP</span></li>
<li><span style="font-weight: bold;">HTTP</span></li>
<li>FTP_HTTP</li>
<li>SFTP</li>
<li>POP3</li>
<li>SMTP</li>
<li>AS1</li>
<li>AS2</li>
<li>AS3</li>
<li>RN_POP3</li>
<li>RN_SMTP</li>
<li>RN_HTTP</li>
<li>SWIFTNET</li>
<li>JMS</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>IsSSL</p>         </td>
         <td><p>String</p>         </td>
         <td><p>One of:</p>
<ul>
<li><span style="font-weight: bold;">1</span>: SSL/TLS protected the transfer.</li>
<li><span style="font-weight: bold;">0</span>: SSL/TLS did not protect the transfer.</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>SSLAuth</p>         </td>
         <td><p>String</p>         </td>
         <td><p>One of:</p>
<ul>
<li><span style="font-weight: bold;">S</span>: The <a href="#roles">Server</a> sent X.509 certificates to the <a href="#roles">Requester</a>.</li>
<li><span style="font-weight: bold;">B</span>: <span style="font-style: italic;">Both</span> the Server and the Requester sent X.509 certificates to each other.</li>
<li><span style="font-weight: bold;">N</span>: <span style="font-style: italic;">Neither</span> the Server nor the Requester sent X.509 certificates.</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>SSLCypher</p>         </td>
         <td><p>String</p>         </td>
         <td><p>The cipher suite that <a href="#roles">the Server and the Requester</a> used during the SSL/TLS session. The cipher suite identifies the following:</p>
<ul>
<li>Authentication method</li>
<li>Encryption algorithm</li>
<li>Hash algorithm for MAC calculation</li>
</ul>         </td>
      </tr>
   </tbody>
</table>

<span id="Transfer_options"></span>

### Identifying transfer options

To monitor transfer options, use the following attributes.

<table>
         
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Attribute</p>         </th>
<th class="HeadE-Column1-Header1"><p>Data Type</p>         </th>
<th class="HeadD-Column1-Header1"><p>Value</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Compression</p>         </td>
         <td><p>String</p>         </td>
         <td><p>One of the following compression options:</p>
<ul>
<li><span style="font-weight: bold;">0</span>: Undefined</li>
<li><span style="font-weight: bold;">1</span>: Horizontal</li>
<li><span style="font-weight: bold;">2</span>: Vertical</li>
<li><span style="font-weight: bold;">3</span>: Both horizontal and vertical</li>
<li><span style="font-weight: bold;">4</span>: Not compressed</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>EOTProcedure</p>         </td>
         <td><p>String</p>         </td>
         <td><p>When the value of the <a href="#State">State</a> attribute is:</p>
<ul>
<li><span style="font-weight: bold;">SENT</span>, the value of this attribute is the name of the EOT (End of Transfer Procedure) that the Sender executed</li>
<li><span style="font-weight: bold;">RECEIVED</span>, the value of this attribute is the name of the EOT (End of Transfer Procedure) that the Receiver executed</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Priority</p>         </td>
         <td><p>Integer</p>         </td>
         <td><p>Transfer priority. Receivers process transfers in the order of their priority. The range of possible values for this attribute is zero to 255. The lowest priority is zero. The highest priority is 255.</p>         </td>
      </tr>
      <tr>
         <td><p>RetryMaxNumber</p>         </td>
         <td><p>Integer</p>         </td>
         <td><p>Maximum number of times that the Sender can attempt to send transfers.</p>         </td>
      </tr>
      <tr>
         <td><p>RetryNumber</p>         </td>
         <td><p>Integer</p>         </td>
         <td><p>Number of times that the Sender attempted to send the transfer. Each time the Sender established a connection with the Receiver, the Sender counted one attempt.</p>         </td>
      </tr>
      <tr>
         <td><p>RequestType</p>         </td>
         <td><p>String</p>         </td>
         <td><p>One of:</p>
<ul>
<li><span style="font-weight: bold;">S</span>: The Sender sent a <span style="font-style: italic;">single</span> transfer to a single Receiver.</li>
<li><span style="font-weight: bold;">G</span>: The Sender sent a <span style="font-style: italic;">group</span> of transfers to a single Receiver. For each transfer in the group, Gateway generated one Processing Cycle.</li>
<li><span style="font-weight: bold;">D</span>: The Sender sent a single transfer to a group of Receivers (<span style="font-style: italic;">diffusion</span>). For each Receiver in the group, Gateway generated one Processing Cycle.</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>TransferType</p>         </td>
         <td><p>String</p>         </td>
         <td><p>One of:</p>
<ul>
<li><span style="font-weight: bold;">G</span>: The transfer belongs to a <span style="font-style: italic;">group</span> of transfers that the Sender sent to a single Receiver. For each transfer in the group, Gateway generated one Processing Cycle.</li>
<li><span style="font-weight: bold;">D</span>: The Receiver belongs to a group of Receivers to whom the Sender sent the transfer (<span style="font-style: italic;">diffusion</span>). For each Receiver in the group, Gateway generated one Processing Cycle.</li>
</ul>         </td>
      </tr>
   </tbody>
</table>

<span id="Transfer_size"></span>

### Identifying the size of transfers

To monitor the size of transferred files and messages, use the following attributes:

<table>
         
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Attribute</p>         </th>
<th class="HeadE-Column1-Header1"><p>Data Type</p>         </th>
<th class="HeadD-Column1-Header1"><p>Value</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>FileSize</p>         </td>
         <td><p>Integer</p>         </td>
         <td><p>Size of the transferred file or message on the Sender's monitor, before compression. This size is expressed in bytes.</p>         </td>
      </tr>
      <tr>
         <td><p>TransmittedBytes</p>         </td>
         <td><p>Integer</p>         </td>
         <td><p>Size of the transferred file or message on the Receiver's monitor, after decompression. This size is expressed in bytes.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="Transfer_data"></span>

### Identifying the structure and content of transfers

To monitor the structure and content of transfers, use the following attributes:

<table>
         
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Attribute</p>         </th>
<th class="HeadE-Column1-Header1"><p>Data Type</p>         </th>
<th class="HeadD-Column1-Header1"><p>Value</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p><span id="CommandType"></span>CommandType</p>         </td>
         <td><p>String</p>         </td>
         <td><p>One of:</p>
<ul>
<li><span style="font-weight: bold;">Message (M)</span>: The transferred data is a message. Denotes InterAct for SWIFTNet transfers.</li>
<li><span style="font-weight: bold;">File (F)</span>: The transferred data is a file. Denotes FileAct for SWIFTNet transfers.</li>
<li>Receipt (R)</li>
<li><span style="font-weight: bold;">Directory (D)</span>: FTP list.</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>BlockSize</p>         </td>
         <td><p>Integer</p>         </td>
         <td><p>If the value of the <a href="#CommandType">CommandType</a> attribute is:</p>
<ul>
<li><span style="font-weight: bold;">Message</span>, this attribute is empty</li>
<li><span style="font-weight: bold;">File</span> and the Receiver's monitor is a main frame, the value of this attribute identifies where the Receiver stores the transferred data</li>
<li><span style="font-weight: bold;">File</span> and the Receiver's monitor is not a main frame, this attribute is empty</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>FileOrganization</p>         </td>
         <td><p>String</p>         </td>
         <td><p>If the value of the <a href="#CommandType">CommandType</a> attribute is:</p>
<ul>
<li><span style="font-weight: bold;">Message</span>, the value of this attribute is <span style="font-weight: bold;">org_undefined</span></li>
<li><span style="font-weight: bold;">File</span>, the value of this attribute is one of the following:
<ul>
<li><span style="font-weight: bold;">org_sequential</span>: The transferred data is not indexed.</li>
<li><span style="font-weight: bold;">indexed</span>: The transferred data is indexed.</li>
<li><span style="font-weight: bold;">direct</span>: The transferred data is assigned relative access.</li>
</ul></li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span id="FileType"></span>FileType</p>         </td>
         <td><p>String</p>         </td>
         <td><p>If the value of the <a href="#CommandType">CommandType</a> attribute is:</p>
<ul>
<li><span style="font-weight: bold;">Message</span>, this attribute is empty</li>
<li><span style="font-weight: bold;">File</span>, the value of this attribute is one of the following:
<ul>
<li><span style="font-weight: bold;">fixed</span>: The transferred data contains <span style="font-style: italic;">fixed-length</span> records.</li>
<li><span style="font-weight: bold;">variable</span>: The transferred data contains <span style="font-style: italic;">variable-length</span> records.</li>
<li><span style="font-weight: bold;">undefined</span>: The structure of the transferred data is unknown.</li>
</ul></li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>RecordNumber</p>         </td>
         <td><p>Integer</p>         </td>
         <td><p>If the value of the <a href="#CommandType">CommandType</a> attribute is:</p>
<ul>
<li><span style="font-weight: bold;">Message</span>, this attribute is empty</li>
<li><span style="font-weight: bold;">File</span>, the value of this attribute is the number of records in the transferred file</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>RecordSize</p>         </td>
         <td><p>Integer</p>         </td>
         <td><p>If the value of the <a href="#CommandType">CommandType</a> attribute is:</p>
<ul>
<li><span style="font-weight: bold;">Message</span>, this attribute is empty</li>
<li><span style="font-weight: bold;">File</span> and the value of the <a href="#FileType">FileType</a> attribute is <span style="font-weight: bold;">fixed</span>, the value of this attribute is the size of all records in the transferred file, expressed in bytes</li>
<li><span style="font-weight: bold;">File</span> and the value of the <a href="#FileType">FileType</a> attribute is <span style="font-weight: bold;">variable</span> or <span style="font-weight: bold;">undefined</span>, the value of this attribute is the size of the largest record in the transferred file, expressed in bytes</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Transcoding</p>         </td>
         <td><p>String</p>         </td>
         <td><p>Character code of the transferred data:</p>
<ul>
<li><span style="font-weight: bold;">A</span>: ASCII</li>
<li><span style="font-weight: bold;">B</span>: Binary</li>
<li><span style="font-weight: bold;">E</span>: EBCDIC</li>
<li><span style="font-weight: bold;">T</span>: A transcoding table modified the character code of the transfer</li>
<li><span style="font-weight: bold;">U</span>: Undefined</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>TranslationTableId</p>         </td>
         <td><p>String</p>         </td>
         <td><p>Translation table identifier. When a transfer partner uses a translation table that is delivered with Gateway, the value of this parameter is <span style="font-weight: bold;">INTERNAL</span>.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="smtp_pop3"></span>

### Identifying details about SMTP/POP3 transfers

To identify details about the emails that Gateway transfers, use the following attributes.

<table>
         
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Attribute</p>         </th>
<th class="HeadE-Column1-Header1"><p>Data Type</p>         </th>
<th class="HeadD-Column1-Header1"><p>Value</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>SmtpFrom</p>         </td>
         <td><p>String</p>         </td>
         <td><p>Email address in the <span style="font-style: italic;">From</span> field (Sender)</p>         </td>
      </tr>
      <tr>
         <td><p>SmtpTo</p>         </td>
         <td><p>String</p>         </td>
         <td><p>Email addresses in the <span style="font-style: italic;">To</span> field (Receiver)</p>         </td>
      </tr>
      <tr>
         <td><p>SmtpCc</p>         </td>
         <td><p>String</p>         </td>
         <td><p>Email addresses in the <span style="font-style: italic;">CC</span> field (Copy)</p>         </td>
      </tr>
      <tr>
         <td><p>SmtpBcc</p>         </td>
         <td><p>String</p>         </td>
         <td><p>Email addresses in the <span style="font-style: italic;">BCC</span> field (Blind copy)</p>         </td>
      </tr>
      <tr>
         <td><p>SmtpSubject</p>         </td>
         <td><p>String</p>         </td>
         <td><p>Contents of the <span style="font-style: italic;">Subject</span> field</p>         </td>
      </tr>
      <tr>
         <td><p>SmtpAckTo</p>         </td>
         <td><p>String</p>         </td>
         <td><p>Contents of the <span style="font-style: italic;">Ack</span> field</p>         </td>
      </tr>
      <tr>
         <td><p>SmtpAef</p>         </td>
         <td><p>String</p>         </td>
         <td><p>One of the following:</p>
<ul>
<li><span style="font-weight: bold;">0</span>: If Gateway:
<ul>
<li>sent the relevant transfer to an SMTP server, Gateway did not format the associated email. The transfer was already formatted as an email. However, Gateway attached all related files.</li>
<li>received the relevant transfer from a POP3 server, Gateway did not decode the associated email. However, Gateway extracted all file attachments</li>
</ul></li>
<li><span style="font-weight: bold;">1</span>: If Gateway:
<ul>
<li>sent the relevant transfer to an SMTP server, Gateway formatted the associated email and attached all related files</li>
<li>received the relevant transfer from a POP3 server, Gateway decoded the associated email and extracted all file attachments</li>
</ul></li>
</ul>         </td>
      </tr>
   </tbody>
</table>

<span id="swiftnet"></span>

### Identifying details about SWIFTNet transfers

To identify details about SWIFTNet transfers, use the following attributes.

<table>
         
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Attribute</p>         </th>
<th class="HeadE-Column1-Header1"><p>Data Type</p>         </th>
<th class="HeadD-Column1-Header1"><p>Value</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>TradeCompressing</p>         </td>
         <td><p>String</p>         </td>
         <td><ul>
<li>Y</li>
<li>N</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>TradeCompressionAlgo</p>         </td>
         <td><p>String</p>         </td>
         <td><p>Example values:</p>
<ul>
<li>ZIP</li>
<li>ZLIB</li>
<li>GZIP</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>TradeDeliveryMode</p>         </td>
         <td><p>String</p>         </td>
         <td><ul>
<li><span style="font-weight: bold;">RT</span> (RealTime)</li>
<li><span style="font-weight: bold;">SNF</span> (Store-and-Forward)</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>TradeDestination</p>         </td>
         <td><p>String</p>         </td>
         <td><p>Distinguished Name of the Originator of the Transfer.</p>
<p>For example, ou=Paris, o=Bank, o=swift.</p>         </td>
      </tr>
      <tr>
         <td><p>TradeDestinationAlias</p>         </td>
         <td><p>String</p>         </td>
         <td><p>Gateway Trading Partner name.</p>
<p>For example, SWIFT_REAL.</p>         </td>
      </tr>
      <tr>
         <td><p>TradeDestinationRemote</p>         </td>
         <td><p>String</p>         </td>
         <td><ul>
<li>Y</li>
<li>N</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>TradeEncrypting</p>         </td>
         <td><p>String</p>         </td>
         <td><ul>
<li>Y</li>
<li>N</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>TradeFileEncoded</p>         </td>
         <td><p>String</p>         </td>
         <td><ul>
<li>Y</li>
<li>N</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>TradeFormat</p>         </td>
         <td><p>String</p>         </td>
         <td><ul>
<li>"SWIFTNET"<br />
(for SWIFTNet Protocol).</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>TradeKeyEncryptionAlgo</p>         </td>
         <td><p>String</p>         </td>
         <td><ul>
<li>RSA</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>TradeMessageId</p>         </td>
         <td><p>String</p>         </td>
         <td><p>SNL-defined (incoming) or Gateway-defined (outgoing) technical transfer ID.</p>         </td>
      </tr>
      <tr>
         <td><p>TradeNonRepudiation</p>         </td>
         <td><p>String</p>         </td>
         <td><ul>
<li>Y</li>
<li>N</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>TradeOriginator</p>         </td>
         <td><p>String</p>         </td>
         <td><p>Distinguished Name of the Originator of the Transfer.</p>
<p>For example, ou=Lyon, o=Bank, o=swift.</p>         </td>
      </tr>
      <tr>
         <td><p>TradeOriginatorAlias</p>         </td>
         <td><p>String</p>         </td>
         <td><p>Gateway Trading Partner name.</p>
<p>For example, SWIFT_REAL_LOCAL.</p>         </td>
      </tr>
      <tr>
         <td><p>TradeReceiptMicAlgo</p>         </td>
         <td><p>String</p>         </td>
         <td><p>Example values:</p>
<ul>
<li>ZIP</li>
<li>ZLIB</li>
<li>GZIP</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>TradeRequestType</p>         </td>
         <td><p>String</p>         </td>
         <td><p>SWIFTNet RequestType. This is related to the name of Message Structure used.</p>
<p>For example, "camt.006.001.03" refers to the "ReturnTransaction" message, as defined in ISO20022.</p>         </td>
      </tr>
      <tr>
         <td><p>TradeService</p>         </td>
         <td><p>String</p>         </td>
         <td><p>SWIFTNet service used.</p>
<p>For example, "swift.generic.fa".</p>         </td>
      </tr>
      <tr>
         <td><p>TradeSigning</p>         </td>
         <td><p>String</p>         </td>
         <td><ul>
<li>Y</li>
<li>N</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>TradeSigningAlgo</p>         </td>
         <td><p>String</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>TradeState</p>         </td>
         <td><p>String</p>         </td>
         <td><ul>
<li>ACKED</li>
<li>TERMINATED</li>
<li>CANCELED</li>
<li>ROUTED</li>
<li>TO_EXECUTE</li>
<li>SENT</li>
<li>ENDED_TO_ACK</li>
<li>AVAILABLE</li>
</ul>         </td>
      </tr>
   </tbody>
</table>

The following attributes have specific values for SWIFTNet:

<table>
         
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Attribute</p>         </th>
<th class="HeadE-Column1-Header1"><p>Data Type</p>         </th>
<th class="HeadD-Column1-Header1"><p>Value</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Protocol</p>         </td>
         <td><p>String</p>         </td>
         <td><ul>
<li>SWIFTNET</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>CommandType</p>         </td>
         <td><p>String</p>         </td>
         <td><ul>
<li><span style="font-weight: bold;">F</span> (FileAct)</li>
<li><span style="font-weight: bold;">M</span> (Interact/Message)</li>
<li><span style="font-weight: bold;">R</span> (Receipt)</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>ProtocolId</p>         </td>
         <td><p>String</p>         </td>
         <td><p>Value of the SWIFTNet Protocol Sw:MsgId.</p>
<p><span style="font-weight: bold;">Note:</span> You can use the<span class="code" style="font-weight: bold;"> peltrans -sw_message_id</span> command to modify this value.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="Requests"></span>

## XFBTransfer Predefined Requests

When you configure Sentinel, you can import a set of predefined XFBTransfer Requests into the Monitoring Interface. The following table describes these Requests. All of these Requests retrieve Tracked Instances from the Current Table of XFBTransfer.

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>This Request</p>         </th>
<th class="HeadD-Column1-Header1"><p>Retrieves...</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>CurrentTransfers</p>         </td>
         <td><p>All Tracked Instances from the Current Table of XFBTransfer.</p>         </td>
      </tr>
      <tr>
         <td><p>CurrentTransfersToday</p>         </td>
         <td><p>Tracked Instances from the Current Table of XFBTransfer that correspond to the current date.</p>         </td>
      </tr>
      <tr>
         <td><p>CurrentTransfersAlert</p>         </td>
         <td><p>Tracked Instances from the Current Table of XFBTransfer that correspond to an Alert.</p>         </td>
      </tr>
   </tbody>
</table>

Related topics

[XFBTransfer Sentinel/Gateway correspondence](../sentinel_xfbtransfer_correspondence)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
