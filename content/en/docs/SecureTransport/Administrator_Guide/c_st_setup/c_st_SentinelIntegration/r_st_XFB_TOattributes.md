{
    "title": "XFB Tracked Object attributes",
    "linkTitle": "XFB Tracked Object attributes",
    "weight": "230"
}This topic provides the XFB tracked object roles, sender and receivers, production identification, and transfer attributes.

> **Note:**
>
> Depending on the type of transfer some Sentinel attributes may not be reported in SENDING or RECEIVING state, but are correspondingly available for SENT or RECEIVED.

The following sections list the XFB tracked object roles, sender and receivers, production identification, and transfer attributes:

-   [Tracked object roles](#Tracked_roles)
-   [Tracked object sender and receivers](#Tracked_sender_receivers)
-   [Tracked object product identification](#Tracked_prod_id)
-   [Tracked object transfer users](#Tracked_transfer_user)
-   [Tracked object transfer identification](#Tracked_transfer_id)
-   [Tracked object transfer dates and times](#Tracked_date_time)
-   [Tracked object transfer protocols](#Tracked_protocol)
-   [Tracked object transfer options](#Tracked_options)
-   [Tracked object transfer size](#Tracked_size)
-   [Tracked object transfer structure and content](#Tracked_structure)
-   [Tracked object other attributes](#Tracked_other)

<span id="Tracked_roles"></span>

## Tracked object roles

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Sentinel attribute         </th>
<th class="HeadE-Column1-Header1">Length         </th>
<th class="HeadE-Column1-Header1">Description         </th>
<th class="HeadE-Column1-Header1">Applicable states         </th>
<th class="HeadD-Column1-Header1">Name in Secure<br />
Transport         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Direction</p>
<p><em>integer</em></p>         </td>
         <td>1         </td>
         <td><p>One of the following:</p>
<ul>
<li><strong>S</strong>: The file is sent (Sender).</li>
<li><strong>R</strong>: The file is received (Receiver).</li>
</ul>         </td>
         <td>All         </td>
         <td><p>Direction</p>
<p>Corresponds to the DXAGENT_TRANSFER_DIRECTION {{< SecureTransport/componentshortname  >}} event environment variable.</p>         </td>
      </tr>
      <tr>
         <td><p>IsServer</p>
<p><em>integer</em></p>         </td>
         <td>1         </td>
         <td><p>One of the following:</p>
<ul>
<li><strong>1</strong>: The Sender or the Receiver acts as a Server.</li>
<li><strong>0</strong>: The Sender or the Receiver is a Requester.</li>
</ul>         </td>
         <td>All         </td>
         <td>Action By         </td>
      </tr>
   </tbody>
</table>

<span id="Tracked_sender_receivers"></span>

## Tracked object sender and receivers

<table>
         
         
         
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Sentinel <br />
attribute         </th>
<th class="HeadE-Column1-Header1">Length         </th>
<th class="HeadE-Column1-Header1">Description         </th>
<th class="HeadE-Column1-Header1">Applicable states         </th>
<th class="HeadD-Column1-Header1">Name in Secure<br />
Transport         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>ReceiverId</p>
<p><em>string</em></p>         </td>
         <td>80         </td>
         <td><p>Receiver Login Name</p>         </td>
         <td><p>SENDING</p>
<p>RECEIVING</p>
<p>SENT</p>
<p>RECEIVED</p>
<p>ACKED</p>
<p>ENDED_TO_ACK</p>
<p>INTERRUPTED</p>
<p>SUSPENDED</p>
<p>ROUTED</p>         </td>
         <td><p>For PeSIT transfers, corresponds to PeSIT PI4.</p>
<ul>
<li>In case of {{< SecureTransport/componentshortname  >}} receiving a file from CFT, the PI4 value is the login name of the {{< SecureTransport/componentshortname  >}} account that receives the file.</li>
<li>In case of {{< SecureTransport/componentshortname  >}} uploading a file to a CFT partner, the PI4 value corresponds to the transfer site name that identifies the partner.</li>
</ul>
<p>For non-PeSIT transfers, the value of this attribute is the <code>ip:port</code> of the remote partner, the hostname, or the {{< SecureTransport/componentshortname  >}} login name.</p>
<p>For ADHOC transfers:</p>
<ul>
<li>In case of an incoming ADHOC transfer, the value of this attribute is the account email.</li>
<li>In case of an outgoing ADHOC transfer, the value of this attribute is the recipient email.</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>SenderId</p>
<p><em>string</em></p>         </td>
         <td>80         </td>
         <td><p>Sender Login Name</p>         </td>
         <td><p>SENDING</p>
<p>RECEIVING</p>
<p>SENT</p>
<p>RECEIVED</p>
<p>ACKED</p>
<p>ENDED_TO_ACK</p>
<p>INTERRUPTED</p>
<p>SUSPENDED</p>
<p>ROUTED</p>         </td>
         <td><p>For PeSIT transfers, corresponds to PeSIT PI3.</p>
<ul>
<li>In case of {{< SecureTransport/componentshortname  >}} receiving a file from CFT, the PI3 parameter value is the name of the transfer site that identifies the partner.</li>
<li>In case of {{< SecureTransport/componentshortname  >}} uploading a file to a CFT partner, the PI3 parameter value corresponds to the {{< SecureTransport/componentshortname  >}} account name that’s doing the transfer.</li>
</ul>
<p>For non-PeSIT transfers, reports the {{< SecureTransport/componentshortname  >}} login name of the transfer site owner, the hostname, or the <code>ip:port</code> of the remote partner where {{< SecureTransport/securetransportname  >}} pulled the file from.</p>
<p>For ADHOC transfers:</p>
<ul>
<li>In case of an incoming ADHOC transfer, the value of this attribute is the email of the sender.</li>
<li>In case of an outgoing ADHOC transfer, the value of this attribute is the account email.</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>FinalReceiverId</p>
<p><em>string</em></p>         </td>
         <td>80         </td>
         <td><p>The Login Name of the final Receiver in case of Store and Forward</p>         </td>
         <td><p>All</p>         </td>
         <td><p><span id="Pesit_Store&amp;Forward_PI62"></span>For PeSIT transfers, corresponds to PeSIT PI62 or PI4.</p>
<ul>
<li>If PI62 is not present, PI4 is used in both Sentinel and PeSIT.</li>
<li>In case of {{< SecureTransport/componentshortname  >}} initiating a new Store and Forward transfer, the PI62 value corresponds either to the <a href="#Pesit_Store&amp;Forward_PI62">Final Destination</a> property of the PeSIT transfer site or to the <a href="../../../c_st_advanced_routing/c_st_route_steps/t_st_send_to_partner#AR_SP_Final_Destination">Final Destination</a> property of the Send To Partner step. If both properties are left blank, PI62 is not populated.</li>
<li>In the PRESERVE store and forward mode, PI preserves the PI62 value.</li>
</ul>
<p>For non-PeSIT transfers, the value of this attribute is the ReceiverId. In case the ReceiverId value is not present, the value of the FinalReceiverId is the <code>ip:port</code> of the Remote Partner or the hostname.</p>         </td>
      </tr>
      <tr>
         <td><p>OriginalSenderId</p>
<p><em>string</em></p>         </td>
         <td>80         </td>
         <td><p> </p>
<p>The Login Name of the original Sender in case of Store and Forward</p>         </td>
         <td><p>All</p>         </td>
         <td><p>For PeSIT transfers, corresponds to PeSIT PI61.</p>
<ul>
<li>In case of {{< SecureTransport/componentshortname  >}} initiating a new Store and Forward transfer, the PI61 value corresponds either to the <a href="#Pesit_Store&amp;Forward_PI61">Originator</a> property, <span id="Pesit_Store&amp;Forward_PI61"></span>specified in the PeSIT transfer site settings, or the <a href="../../../c_st_advanced_routing/c_st_route_steps/t_st_send_to_partner#AR_SP_Originator">Originator</a> property in the Send To Partner step settings. If both properties are left blank, PI61 is not populated.</li>
<li>In the PRESERVE store and forward mode, PI preserves the PI61 value.</li>
</ul>
<p>For non-PeSIT transfers, the value of this attribute is the login name of the {{< SecureTransport/securetransportname  >}} account which received/sent the file from a Remote Partner. If login name is not present, the value is SenderID or UserID.</p>         </td>
      </tr>
      <tr>
         <td><p>UserID</p>
<p><em>string</em></p>         </td>
         <td>80         </td>
         <td>Transfer site
owner         </td>
         <td>All         </td>
         <td><p>For non-PeSIT transfers, reports the transfer site owner. If no transfer site is used, reports the account name of the user who initiated the transfer. When an account template is used, the login name is reported. If no values are present for the account name and the transfer site, <strong>N3</strong> is reported.</p>         </td>
      </tr>
      <tr>
         <td><p>Site</p>
<p><em>string</em></p>         </td>
         <td>80         </td>
         <td>Transfer site name         </td>
         <td>All         </td>
         <td><p>For non-PeSIT transfers, reports the transfer site name. If no value is present for the transfer site name, <strong>N2</strong> is reported.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="Tracked_prod_id"></span>

## Tracked object product identification

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Sentinel attribute         </th>
<th class="HeadE-Column1-Header1">Length         </th>
<th class="HeadE-Column1-Header1">Description         </th>
<th class="HeadE-Column1-Header1">Applicable states         </th>
<th class="HeadD-Column1-Header1">Name in Secure<br />
Transport         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>MonitorVersion</p>
<p><em>string</em></p>         </td>
         <td>25         </td>
         <td>Version of {{< SecureTransport/componentshortname  >}} in the X.Y.Z format e.g. 5.3.0 or 5.2.1         </td>
         <td>All         </td>
         <td>MonitorVersion         </td>
      </tr>
      <tr>
         <td><p>ProductName</p>
<p><em>string</em></p>         </td>
         <td>50         </td>
         <td>The constant “{{< SecureTransport/componentshortname  >}}”         </td>
         <td>All         </td>
         <td>ProductName         </td>
      </tr>
      <tr>
         <td><p>ProductIPAddr</p>
<p><em>string</em></p>         </td>
         <td>255         </td>
         <td>IP address assigned to the server hosting the {{< SecureTransport/componentshortname  >}} application         </td>
         <td>All         </td>
         <td>java.net.InetAddress.<br />
getLocalHost()         </td>
      </tr>
      <tr>
         <td><p>ProductOS</p>
<p><em>string</em></p>         </td>
         <td>20         </td>
         <td>Operating system name as returned by os.name Java system property         </td>
         <td>All         </td>
         <td>os.name Java system property.         </td>
      </tr>
      <tr>
         <td><p>EnvironmentID</p>
<p><em>integer</em></p>         </td>
         <td>          </td>
         <td>Environment ID as defined in Server Config         </td>
         <td>All         </td>
         <td>EnvironmentID         </td>
      </tr>
   </tbody>
</table>

<span id="Tracked_transfer_user"></span>

## Tracked object transfer users

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Sentinel attribute         </th>
<th class="HeadE-Column1-Header1">Length         </th>
<th class="HeadE-Column1-Header1">Description         </th>
<th class="HeadE-Column1-Header1">Applicable states         </th>
<th class="HeadD-Column1-Header1">Name in Secure<br />
Transport         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>GroupId</p>
<p><em>string</em></p>         </td>
         <td>80         </td>
         <td>The name of the {{< SecureTransport/componentshortname  >}} account         </td>
         <td>All         </td>
         <td>Account name         </td>
      </tr>
   </tbody>
</table>

<span id="Tracked_transfer_id"></span>

## Tracked object transfer identification

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Sentinel attribute         </th>
<th class="HeadE-Column1-Header1">Length         </th>
<th class="HeadE-Column1-Header1">Description         </th>
<th class="HeadE-Column1-Header1">Applicable states         </th>
<th class="HeadD-Column1-Header1">Name in Secure<br />
Transport         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Application</p>
<p><em>string</em></p>         </td>
         <td>80         </td>
         <td>Application name.         </td>
         <td>All         </td>
         <td>{{< SecureTransport/componentshortname  >}} application name.         </td>
      </tr>
      <tr>
         <td><p>CoreId</p>
<p><em>string</em></p>         </td>
         <td>100         </td>
         <td>File identifier. Preserved during all types of processing.         </td>
         <td>All         </td>
         <td>Corresponds to <code>DXAGENT_CORE_ID</code> environment variable         </td>
      </tr>
      <tr>
         <td><p>EventTimeStamp</p>
<p><em>string</em></p>         </td>
         <td>100         </td>
         <td>Event time stamp.         </td>
         <td>All         </td>
         <td>          </td>
      </tr>
      <tr>
         <td><p>FileName</p>
<p><em>string</em></p>         </td>
         <td>512         </td>
         <td><p>If the value of the CommandType attribute is:</p>
<ul>
<li>File and the value of the Direction attribute is <strong>E</strong> (Sender), this attribute identifies the file from which the Sender retrieved the transfer data (full path).</li>
<li>File and the value of the Direction attribute is <strong>R</strong> (Receiver), this attribute identifies the file in which the Receiver recorded the transfer data (full path).</li>
</ul>         </td>
         <td>All         </td>
         <td><p>Fullpath of the filename.</p>
<p>Corresponds to the DXAGENT_FULLTARGET {{< SecureTransport/componentshortname  >}} event environment variable.</p>         </td>
      </tr>
      <tr>
         <td><p>LocalId</p>
<p><em>string</em></p>         </td>
         <td>36         </td>
         <td>Stores the file tracking transfer ID.         </td>
         <td><p>SENDING</p>
<p>RECEIVING</p>
<p>SENT</p>
<p>RECEIVED</p>
<p>ACKED</p>
<p>ENDED_TO_ACK</p>
<p>INTERRUPTED</p>
<p>SUSPENDED</p>
<p>ROUTED</p>         </td>
         <td>Transfer ID.<br />
Corresponds to the TRANSFER_STATUS_ID {{< SecureTransport/componentshortname  >}} event environment variable.         </td>
      </tr>
      <tr>
         <td><p>ProtocolFile<br />
Name</p>
<p><em>string</em></p>         </td>
         <td>512         </td>
         <td><p>Corresponds to the PeSIT PI12.</p>
<p>Reports the new name of a file that has been renamed using the "Send File As" functionality of an internal or pluggable transfer site.</p>         </td>
         <td><p>SENDING</p>
<p>RECEIVING</p>
<p>SENT</p>
<p>RECEIVED</p>
<p>ACKED</p>
<p>ENDED_TO_ACK</p>
<p>INTERRUPTED</p>
<p>SUSPENDED</p>
<p>ROUTED</p>         </td>
         <td>File.<br />
Corresponds to the <code>DXAGENT_TARGET</code> {{< SecureTransport/componentshortname  >}} event environment variable.         </td>
      </tr>
      <tr>
         <td><p>ProtocolFile<br />
Label</p>
<p><em>string</em></p>         </td>
         <td>80         </td>
         <td><p>Corresponds to the PeSIT PI37 – file label.</p>
<p>Reports the remote file path and the new name of a file that has been renamed using the "Send File As" functionality.</p>         </td>
         <td><p>SENDING</p>
<p>RECEIVING</p>
<p>SENT</p>
<p>RECEIVED</p>
<p>ACKED</p>
<p>ENDED_TO_ACK</p>
<p>INTERRUPTED</p>
<p>SUSPENDED</p>
<p>ROUTED</p>         </td>
         <td>When {{< SecureTransport/componentshortname  >}} is a sender, this is configured in the Transfer Profile.
When {{< SecureTransport/componentshortname  >}} is a receiver, this value is configured and supplied by the sender.         </td>
      </tr>
      <tr>
         <td><p>ProtocolId</p>
<p><em>string</em></p>         </td>
         <td>80         </td>
         <td>Corresponds to the PeSIT PI13 – Transfer ID.         </td>
         <td><p>SENDING</p>
<p>RECEIVING</p>
<p>SENT</p>
<p>RECEIVED</p>
<p>ACKED</p>
<p>ENDED_TO_ACK</p>
<p>INTERRUPTED</p>
<p>SUSPENDED</p>
<p>ROUTED</p>         </td>
         <td>Transfer ID         </td>
      </tr>
      <tr>
         <td><p>Protocol<br />
Message</p>
<p><em>string</em></p>         </td>
         <td>4000         </td>
         <td><p>If the value of the CommandType attribute is:</p>
<ul>
<li><strong>A</strong>: the value of this attribute is the content of the message sent as part of the acknowledgment.</li>
<li><strong>F</strong>: this attribute is empty.</li>
</ul>         </td>
         <td><p>ACKED</p>
<p>ENDED_TO_ACK</p>         </td>
         <td>Corresponds to the DXAGENT_TRANSFER_ACK_MESSAGE {{< SecureTransport/componentshortname  >}} event environment variable.         </td>
      </tr>
      <tr>
         <td><p>Protocol<br />
Parameter</p>
<p><em>string</em></p>         </td>
         <td>512         </td>
         <td><p>Corresponds to PI99. (ServiceParam or User message);</p>
<p>For FTP server-initiated transfers, reports the upload command used in the FTP transfer site.</p>         </td>
         <td><p>SENDING</p>
<p>RECEIVING</p>
<p>SENT</p>
<p>RECEIVED</p>
<p>ACKED</p>
<p>ENDED_TO_ACK</p>
<p>INTERRUPTED</p>
<p>SUSPENDED</p>
<p>ROUTED</p>         </td>
         <td><p>User message</p>
<p>Upload command in FTP transfer sites</p>         </td>
      </tr>
      <tr>
         <td><p>User<br />
Parameter1</p>
<p><em>string</em></p>         </td>
         <td>255         </td>
         <td><p>Contains information whether the transfer is with an Internal partner, External partner or Unknown.</p>
<ul>
<li>For transfer with an Internal partner <strong>I</strong> is reported.</li>
<li>For transfer with an External partner <strong>E</strong> is reported.</li>
<li>If the Administrator has not specified Internal or External – <strong>N</strong> is reported.</li>
</ul>         </td>
         <td>All         </td>
         <td><p>TransferType in account or site name.</p>
<p> </p>
<p> </p>         </td>
      </tr>
      <tr>
         <td><p>User<br />
Parameter2</p>
<p><em>string</em></p>         </td>
         <td>255         </td>
         <td><p>Reports the account type:</p>
<ul>
<li><strong>User</strong> (meaning that account has been specified in {{< SecureTransport/componentshortname  >}}’s database).</li>
<li><strong>Template</strong> (meaning that this is a template).</li>
<li><strong>Service</strong> (Service account).</li>
</ul>         </td>
         <td>All         </td>
         <td>Account Type         </td>
      </tr>
      <tr>
         <td><p>ParentCycleID</p>
<p><em>integer</em></p>         </td>
         <td>          </td>
         <td>ID of the parent processing cycle.         </td>
         <td>TO_EXECUTE, SENDING, SENT         </td>
         <td>ParentCycleID         </td>
      </tr>
   </tbody>
</table>

<span id="Tracked_date_time"></span>

## Tracked object transfer dates and times

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Sentinel attribute         </th>
<th class="HeadE-Column1-Header1">Length         </th>
<th class="HeadE-Column1-Header1">Description         </th>
<th class="HeadE-Column1-Header1">Applicable states         </th>
<th class="HeadD-Column1-Header1">Name in Secure<br />
Transport         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>StartDate</p>
<p><em>date</em></p>         </td>
         <td>          </td>
         <td><p>If the value of the State attribute is:</p>
<ul>
<li><strong>SENT</strong>, the value of this attribute is the date on which the Sender began sending the transfer.</li>
<li><strong>RECEIVED</strong>, the value of this attribute is the date on which the Receiver began receiving the transfer.</li>
</ul>
<p>These dates are expressed in dd.mm.yyyy format.</p>         </td>
         <td><p>SENDING</p>
<p>RECEIVING</p>
<p>SENT</p>
<p>RECEIVED</p>
<p>ACKED</p>
<p>ENDED_TO_ACK</p>
<p>INTERRUPTED</p>
<p>SUSPENDED</p>
<p>ROUTED</p>         </td>
         <td>          </td>
      </tr>
      <tr>
         <td><p>StartTime</p>
<p><em>time</em></p>         </td>
         <td>         </td>
         <td><p>If the value of the State attribute is:</p>
<ul>
<li><strong>SENT</strong>, the value of this attribute is the local time at which the Sender began sending the transfer.</li>
<li><strong>RECEIVED</strong>, the value of this attribute is the local time at which the Receiver began receiving the transfer.</li>
</ul>
<p>These times are expressed in hh:mn:ss format.</p>         </td>
         <td><p>SENDING</p>
<p>RECEIVING</p>
<p>SENT</p>
<p>RECEIVED</p>
<p>ACKED</p>
<p>ENDED_TO_ACK</p>
<p>INTERRUPTED</p>
<p>SUSPENDED</p>
<p>ROUTED</p>         </td>
         <td>          </td>
      </tr>
      <tr>
         <td><p>EndDate</p>
<p><em>date</em></p>         </td>
         <td>          </td>
         <td><p>If the value of the State attribute is:</p>
<ul>
<li><strong>SENT</strong>, the value of this attribute is the date on which the Sender stopped sending the transfer.</li>
<li><strong>RECEIVED</strong>, the value of this attribute is the date on which the Receiver stopped receiving the transfer.</li>
</ul>
<p>These dates are expressed in dd.mm.yyyy format.</p>         </td>
         <td><p>SENT</p>
<p>RECEIVED</p>
<p>ACKED</p>
<p>ENDED_TO_ACK</p>
<p>INTERRUPTED</p>
<p>SUSPENDED</p>
<p>ROUTED</p>         </td>
         <td>          </td>
      </tr>
      <tr>
         <td><p>EndTime</p>
<p><em>time</em></p>         </td>
         <td>          </td>
         <td><p>If the value of the State attribute is:</p>
<ul>
<li><strong>SENT</strong>, the value of this attribute is the local time at which the Sender stopped sending the transfer.</li>
<li><strong>RECEIVED</strong>, the value of this attribute is the local time at which the Receiver stopped receiving the transfer.</li>
</ul>
<p>These times are expressed in hh:mn:ss format.</p>         </td>
         <td><p>SENT</p>
<p>RECEIVED</p>
<p>ACKED</p>
<p>ENDED_TO_ACK</p>
<p>INTERRUPTED</p>
<p>SUSPENDED</p>
<p>ROUTED</p>         </td>
         <td>          </td>
      </tr>
      <tr>
         <td><p>Transmission<br />
Duration</p>
<p><em>integer</em></p>         </td>
         <td>          </td>
         <td>Transfer duration (expressed in seconds).         </td>
         <td><p>SENT</p>
<p>RECEIVED</p>
<p>INTERRUPTED</p>
<p>SUSPENDED</p>
<p>ACKED</p>
<p>ENDED_TO_ACK</p>
<p>ROUTED</p>         </td>
         <td>Duration         </td>
      </tr>
   </tbody>
</table>

<span id="Tracked_protocol"></span>

## Tracked object transfer protocols

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Sentinel attribute         </th>
<th class="HeadE-Column1-Header1">Length         </th>
<th class="HeadE-Column1-Header1">Description         </th>
<th class="HeadE-Column1-Header1">Applicable states         </th>
<th class="HeadD-Column1-Header1">Name in Secure<br />
Transport         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p><code>ServerName</code></p>
<p><em>string</em></p>         </td>
         <td>250         </td>
         <td>Name of the server that processed the transfer. Applicable when the Sender or the Receiver is a Requester, except for the ENDED_TO_ACK state, where the attribute is set <code>no matter</code>.         </td>
         <td><p>RECEIVING,</p>
<p>RECEIVED,</p>
<p>SENDING,</p>
<p>SENT,</p>
<p>INTERRUPTED,</p>
<p>CANCELED,</p>
<p>FAILED,</p>
<p>RENAMED,</p>
<p>DELETED,</p>
<p>ACKED,</p>
<p>ENDED_TO_ACK</p>         </td>
         <td>Corresponds to <code>DXAGENT_SERVERNAME </code>{{< SecureTransport/componentshortname  >}} event environment variable.         </td>
      </tr>
      <tr>
         <td><p>Protocol</p>
<p><em>string</em></p>         </td>
         <td>25         </td>
         <td><p>The following:</p>
<ul>
<li><strong>PSIT_HS_E</strong></li>
</ul>         </td>
         <td>All         </td>
         <td><p>Protocol.</p>
<p>Corresponds to the DXAGENT_PROTOCOL {{< SecureTransport/componentshortname  >}} event environment variable.</p>         </td>
      </tr>
      <tr>
         <td><p>IsSSL</p>
<p><em>string</em></p>         </td>
         <td>1         </td>
         <td><p>One of the following:</p>
<ul>
<li><strong>1</strong>: SSL/TLS used for the transfer.</li>
<li><strong>0</strong>: SSL/TLS not used for the transfer.</li>
</ul>         </td>
         <td><p>SENDING</p>
<p>RECEIVING</p>
<p>SENT</p>
<p>RECEIVED</p>
<p>ACKED</p>
<p>ENDED_TO_ACK</p>
<p>INTERRUPTED</p>
<p>SUSPENDED</p>
<p>ROUTED</p>         </td>
         <td>Use TLS/SSL in transfer site.         </td>
      </tr>
      <tr>
         <td><p>SSLAuth</p>
<p><em>string</em></p>         </td>
         <td>1         </td>
         <td><p>One of the following:</p>
<ul>
<li><strong>S</strong>: The Server sent X.509 certificates to the Requester. For SSH sessions, the value of SSLAuth will be always <strong>S</strong> if the Requester does not present a key.</li>
<li><strong>B</strong>: Both the Server and the Requester sent X.509 certificates to each other.</li>
<li><strong>N</strong>: Neither the Server nor the Requester sent X.509 certificates.</li>
</ul>         </td>
         <td><p>SENDING</p>
<p>RECEIVING</p>
<p>SENT</p>
<p>RECEIVED</p>
<p>ACKED</p>
<p>ENDED_TO_ACK</p>
<p>INTERRUPTED</p>
<p>SUSPENDED</p>
<p>ROUTED</p>         </td>
         <td>DXAGENT_SSLAUTH         </td>
      </tr>
      <tr>
         <td><p>SSLCypher</p>
<p><em>integer</em></p>         </td>
         <td>          </td>
         <td><p>One of the following:</p>
<ul>
<li>the <strong>RFC code</strong> of the cipher suite that the Server and the Requester used during the SSL/TLS session. The cipher suite identifies the authentication method, the encryption algorithm, and the hash algorithm for MAC calculation.</li>
<li><strong>0</strong> for all SSH sessions.</li>
</ul>         </td>
         <td>All         </td>
         <td>DXAGENT_SESSION_SSL_CYPHER         </td>
      </tr>
   </tbody>
</table>

<span id="Tracked_options"></span>

## Tracked object transfer options

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Sentinel
attribute         </th>
<th class="HeadE-Column1-Header1">Length         </th>
<th class="HeadE-Column1-Header1">Description         </th>
<th class="HeadE-Column1-Header1">Applicable states         </th>
<th class="HeadD-Column1-Header1">Name in Secure<br />
Transport         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Compression</p>
<p><em>string</em></p>         </td>
         <td>1         </td>
         <td><p>One of the following:</p>
<ul>
<li><strong>0</strong>: Undefined</li>
<li><strong>1</strong>: Horizontal</li>
<li><strong>2</strong>: Vertical</li>
<li><strong>3</strong>: Both horizontal and vertical</li>
<li><strong>4</strong>: Not compressed</li>
</ul>
<p>Corresponds to PI21.</p>         </td>
         <td><p>SENDING</p>
<p>RECEIVING</p>
<p>SENT</p>
<p>RECEIVED</p>
<p>ACKED</p>
<p>ENDED_TO_ACK</p>
<p>INTERRUPTED</p>
<p>SUSPENDED</p>
<p>ROUTED</p>         </td>
         <td>Compression in transfer site.         </td>
      </tr>
      <tr>
         <td><p>RetryMax<br />
Number</p>
<p><em>integer</em></p>         </td>
         <td>          </td>
         <td>Maximum number of times that the Sender can attempt to send transfers.         </td>
         <td><p>SENDING</p>
<p>RECEIVING</p>
<p>SENT</p>
<p>RECEIVED</p>
<p>ACKED</p>
<p>ENDED_TO_ACK</p>
<p>INTERRUPTED</p>
<p>SUSPENDED</p>
<p>ROUTED</p>         </td>
         <td><code>EventQueue.maxRetryCount</code> on <em>Server Configuration</em> page.         </td>
      </tr>
      <tr>
         <td><p>Retry<br />
Number</p>
<p><em>integer</em></p>         </td>
         <td>          </td>
         <td>Number of times that the Sender attempted to send the transfer. Each time the Sender established a connection with the Receiver, the Sender counted one attempt.         </td>
         <td><p>SENDING</p>
<p>RECEIVING</p>
<p>SENT</p>
<p>RECEIVED</p>
<p>ACKED</p>
<p>ENDED_TO_ACK</p>
<p>INTERRUPTED</p>
<p>SUSPENDED</p>
<p>ROUTED</p>         </td>
         <td>Corresponds to the DXAGENT_PERSISTED_EVENT_RETRY_COUNT {{< SecureTransport/componentshortname  >}} event environment variable.         </td>
      </tr>
      <tr>
         <td><p>Request<br />
Type</p>
<p><em>string</em></p>         </td>
         <td>1         </td>
         <td><p>One of the following:</p>
<ul>
<li><strong>S</strong>: The Sender sent a single transfer to a single Receiver. This corresponds to a normal file transfer.</li>
<li><strong>F</strong>: The Sender sent a group of transfers to a single Receiver. For each transfer in the group, the product generated one Processing Cycle. This corresponds to multiselect PeSIT option.</li>
<li><strong>D</strong>: The Sender sent a single transfer to a group of Receivers (diffusion). For each Receiver in the group, the product generated one Processing Cycle. This corresponds to send to multiple transfer sites SecureTransport configuration.</li>
</ul>         </td>
         <td><p>SENDING</p>
<p>RECEIVING</p>
<p>SENT</p>
<p>RECEIVED</p>
<p>ACKED</p>
<p>ENDED_TO_ACK</p>
<p>INTERRUPTED</p>
<p>SUSPENDED</p>
<p>ROUTED</p>         </td>
         <td>{{< SecureTransport/componentshortname  >}} always reports as value for RequestType.         </td>
      </tr>
      <tr>
         <td><p>Transfer<br />
Type</p>
<p><em>string</em></p>         </td>
         <td>1         </td>
         <td><p>One of the following:</p>
<ul>
<li><strong>S</strong>: The Sender sent a single transfer to a single Receiver. This corresponds to a normal file transfer.</li>
<li><strong>F</strong>: The transfer belongs to a group of transfers that the Sender sent to a single Receiver. For each transfer in the group, the product generated one Processing Cycle. This corresponds to multiselect PeSIT option.</li>
<li><strong>D</strong>: The Receiver belongs to a group of Receivers to whom the Sender sent the transfer (diffusion). For each Receiver in the group, the product generated one Processing Cycle. This corresponds to send to multiple transfer sites SecureTransport configuration.</li>
</ul>         </td>
         <td><p>SENDING</p>
<p>RECEIVING</p>
<p>SENT</p>
<p>RECEIVED</p>
<p>ACKED</p>
<p>ENDED_TO_ACK</p>
<p>INTERRUPTED</p>
<p>SUSPENDED</p>
<p>ROUTED</p>         </td>
         <td>{{< SecureTransport/componentshortname  >}} always reports as value for RequestType         </td>
      </tr>
   </tbody>
</table>

<span id="Tracked_size"></span>

## Tracked object transfer size

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Sentinel
attribute         </th>
<th class="HeadE-Column1-Header1">Length         </th>
<th class="HeadE-Column1-Header1">Description         </th>
<th class="HeadE-Column1-Header1">Applicable states         </th>
<th class="HeadD-Column1-Header1">Name in Secure<br />
Transport         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>FileSize</p>
<p><em>integer</em></p>         </td>
         <td><p> </p>         </td>
         <td><p>An estimation of the file size given at the beginning of the transfer and updated upon completion of the transfer with the real value checked by ST using the file system.</p>
<p>Corresponds to PI42.</p>         </td>
         <td><p>SENDING</p>
<p>RECEIVING</p>
<p>SENT</p>
<p>RECEIVED</p>
<p>ACKED</p>
<p>ENDED_TO_ACK</p>
<p>INTERRUPTED</p>
<p>SUSPENDED</p>
<p>ROUTED</p>         </td>
         <td>          </td>
      </tr>
      <tr>
         <td><p>TransmittedBytes</p>
<p><em>integer</em></p>         </td>
         <td>          </td>
         <td><p>Number of bytes transferred, after decompression, to transfer the file. This size is expressed in bytes.</p>
<p>Corresponds to PI27.</p>
<p><strong>Note</strong>: For PeSIT, this value sent is crosschecked by both the sender and receiver.</p>         </td>
         <td><p>SENDING</p>
<p>RECEIVING</p>
<p>SENT</p>
<p>RECEIVED</p>
<p>ACKED</p>
<p>ENDED_TO_ACK</p>
<p>INTERRUPTED</p>
<p>SUSPENDED</p>
<p>ROUTED</p>         </td>
         <td>Corresponds to the DXAGENT_TRANSFERRED_BYTES {{< SecureTransport/componentshortname  >}} event environment variable.         </td>
      </tr>
   </tbody>
</table>

<span id="Tracked_structure"></span>

## Tracked object transfer structure and content

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Sentinel
attribute         </th>
<th class="HeadE-Column1-Header1">Length         </th>
<th class="HeadE-Column1-Header1">Description         </th>
<th class="HeadE-Column1-Header1">Applicable states         </th>
<th class="HeadD-Column1-Header1">Name in Secure<br />
Transport         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>CommandType</p>
<p><em>string</em></p>         </td>
         <td>1         </td>
         <td><p>One of the following:</p>
<ul>
<li><strong>F</strong>: File transfer</li>
<li><strong>A</strong>: Acknowledgment</li>
</ul>         </td>
         <td><p>SENDING</p>
<p>RECEIVING</p>
<p>SENT</p>
<p>RECEIVED</p>
<p>ACKED</p>
<p>ENDED_TO_ACK</p>
<p>INTERRUPTED</p>
<p>SUSPENDED</p>
<p>ROUTED</p>         </td>
         <td>          </td>
      </tr>
      <tr>
         <td><p>FileType</p>
<p><em>string</em></p>         </td>
         <td>60         </td>
         <td><p>One of the following:</p>
<ul>
<li><strong>B</strong>: the transferred file is a Binary file.</li>
<li><strong>T</strong>: the transferred file is a Text file.</li>
</ul>         </td>
         <td><p>SENDING</p>
<p>RECEIVING</p>
<p>SENT</p>
<p>RECEIVED</p>
<p>ACKED</p>
<p>ENDED_TO_ACK</p>
<p>INTERRUPTED</p>
<p>SUSPENDED</p>
<p>ROUTED</p>         </td>
         <td>Transfer Mode in Transfer Profile or
Data Encoding in Send To Partner step.         </td>
      </tr>
      <tr>
         <td><p>RecordNumber</p>
<p><em>integer</em></p>         </td>
         <td>         </td>
         <td><p>Number of record in the file. This size is expressed in bytes.</p>
<p><strong>Note</strong>: For PeSIT, this value sent is crosschecked by both the sender and receiver.</p>
<p>Corresponds to PeSIT PI28.</p>         </td>
         <td><p>SENDING</p>
<p>RECEIVING</p>
<p>SENT</p>
<p>RECEIVED</p>
<p>ACKED</p>
<p>ENDED_TO_ACK</p>
<p>INTERRUPTED</p>
<p>SUSPENDED</p>
<p>ROUTED</p>         </td>
         <td>          </td>
      </tr>
      <tr>
         <td><p>RecordFormat</p>
<p><em>string</em></p>         </td>
         <td>64         </td>
         <td><p>One of the following:</p>
<ul>
<li><strong>F</strong>: <strong>fixed</strong>: The transferred data contains fixed-length records.</li>
<li><strong>V</strong>: <strong>variable</strong>: The transferred data contains variable-length records.</li>
</ul>
<p>Corresponds to PeSIT PI31.</p>         </td>
         <td><p>SENDING</p>
<p>RECEIVING</p>
<p>SENT</p>
<p>RECEIVED</p>
<p>ACKED</p>
<p>ENDED_TO_ACK</p>
<p>INTERRUPTED</p>
<p>SUSPENDED</p>
<p>ROUTED</p>         </td>
         <td>Record Format in Transfer Profile or in Send To Partner step.         </td>
      </tr>
      <tr>
         <td><p>RecordSize</p>
<p><em>integer</em></p>         </td>
         <td>          </td>
         <td><p>One of the following:</p>
<ul>
<li>If the value of RecordFormat attribute is <strong>fixed</strong>, the value of this attribute is the size of all records in the transferred file, expressed in bytes.</li>
<li>If the value of RecordFormat is <strong>variable</strong> or <strong>undefined</strong>, the value of this attribute is the size of the largest record in the transferred file, expressed in bytes.</li>
</ul>
<p>Corresponds to PeSIT PI32.</p>         </td>
         <td><p>SENDING</p>
<p>RECEIVING</p>
<p>SENT</p>
<p>RECEIVED</p>
<p>ACKED</p>
<p>ENDED_TO_ACK</p>
<p>INTERRUPTED</p>
<p>SUSPENDED</p>
<p>ROUTED</p>         </td>
         <td>Record Length in Transfer Profile or in Send To Partner step.         </td>
      </tr>
      <tr>
         <td><p>Transcoding</p>
<p><em>integer</em></p>         </td>
         <td>          </td>
         <td><p>Character code of the transferred data:</p>
<ul>
<li><strong>A</strong>: ASCII</li>
<li><strong>B</strong>: Binary</li>
<li><strong>E</strong>: EBCDIC</li>
</ul>
<p>From PI16.</p>         </td>
         <td><p>SENDING</p>
<p>RECEIVING</p>
<p>SENT</p>
<p>RECEIVED</p>
<p>ACKED</p>
<p>ENDED_TO_ACK</p>
<p>INTERRUPTED</p>
<p>SUSPENDED</p>
<p>ROUTED</p>         </td>
         <td>Transfer Mode in Transfer Profile or
Data Encoding in Send To Partner step.         </td>
      </tr>
   </tbody>
</table>

<span id="Tracked_other"></span>

## Tracked object other attributes

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Sentinel
attribute         </th>
<th class="HeadE-Column1-Header1">Length         </th>
<th class="HeadE-Column1-Header1">Description         </th>
<th class="HeadE-Column1-Header1">Applicable states         </th>
<th class="HeadD-Column1-Header1">Name in Secure<br />
Transport         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>VirtualDirName</p>
<p><em>string</em></p>         </td>
         <td>255         </td>
         <td>The current folder relative to the home folder.         </td>
         <td>All         </td>
         <td><p>DXAGENT_TARGET_PATH</p>         </td>
      </tr>
      <tr>
         <td><p>GroupName</p>
<p><em>string</em></p>         </td>
         <td>80         </td>
         <td>Business Unit name         </td>
         <td>All         </td>
         <td><p>DXAGENT_BUSINESS_UNIT_NAME</p>         </td>
      </tr>
      <tr>
         <td><p>IdAppl</p>
<p><em>string</em></p>         </td>
         <td>255         </td>
         <td>The ID of the route template package that is executed         </td>
         <td>POST_PROC/ROUTED, POST_PROC/ROUTING, FAILED         </td>
         <td><p>DXAGENT_ROUTE_EXECUTION_ID</p>         </td>
      </tr>
      <tr>
         <td><p>SessionTag</p>
<p><em>string</em></p>         </td>
         <td>255         </td>
         <td>Represents {{< SecureTransport/componentshortname  >}} session ID.
The Session ID could be used to query the server log for a particular session.         </td>
         <td>All         </td>
         <td><p>Session ID</p>         </td>
      </tr>
      <tr>
         <td><p>TransferTag</p>
<p><em>string</em></p>         </td>
         <td>50         </td>
         <td><p>Represents {{< SecureTransport/componentshortname  >}} transfer status operationIndex.</p>
<p>Transfer ID could be used to query the file tracking log for a particular transfer</p>         </td>
         <td>All         </td>
         <td>          </td>
      </tr>
      <tr>
         <td><p>RemoteAddr</p>
<p><em>string</em></p>         </td>
         <td>255         </td>
         <td>Partner remote address (IPv4 and IPv6).         </td>
         <td><p>SENDING</p>
<p>RECEIVING</p>
<p>SENT</p>
<p>RECEIVED</p>
<p>ACKED</p>
<p>ENDED_TO_ACK</p>
<p>INTERRUPTED</p>
<p>SUSPENDED</p>
<p>ROUTED</p>         </td>
         <td>          </td>
      </tr>
      <tr>
         <td><p>RemoteSAP</p>
<p><em>integer</em></p>         </td>
         <td>          </td>
         <td>Partner remote port number.         </td>
         <td><p>SENDING</p>
<p>RECEIVING</p>
<p>SENT</p>
<p>RECEIVED</p>
<p>ACKED</p>
<p>ENDED_TO_ACK</p>
<p>INTERRUPTED</p>
<p>SUSPENDED</p>         </td>
         <td>Not reported by {{< SecureTransport/componentshortname  >}}.         </td>
      </tr>
   </tbody>
</table>

 

**Related topics:**

-   [Event states](../r_st_sentineleventstates)
-   [Axway Sentinel tracked objects](../r_st_sentineltrackedobjects)
-   [About XFB Transfer tracked objects](../c_st_aboutxfb_to)
-   [PeSIT protocol](../r_st_pesit_protocol)
-   [List of PeSIT states](../r_st_listofpesitstates)
-   [CycleId calculation](../r_st_cycleid)
-   [Axway Sentinel dashboards]()
-   [Axway Sentinel requests](../r_st_sentinelrequests)
-   [Configure SecureTransport to send events to Axway Sentinel](../t_st_sentinel)
