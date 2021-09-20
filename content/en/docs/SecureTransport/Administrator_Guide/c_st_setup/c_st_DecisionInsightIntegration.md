{
    "title": "Integrate Decision Insight",
    "linkTitle": "Integrate Decision Insight",
    "weight": "180"
}Decision Insight is a Business Activity Monitoring (BAM) product that collects, aggregates, correlates, and reports events from SecureTransport and other products, applications, and systems throughout your infrastructure. Decision Insight is a separate product that you can buy from Axway or an authorized partner. Once you license and configure SecureTransport to send file transfer and processing events to Decision Insight, data is collected and displayed on a dashboard.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">Decision Insight does not support Attribute mapping in <span>SecureTransport</span>.         </td>
      </tr>
</table>

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">Decision Insight will not monitor ad hoc activity.         </td>
      </tr>
</table>

For addition information please refer to the official confluence page [Embedded Analytics for Secure Transport Home](https://techweb.axway.com/public/display/DOCEAST/)

The following topics provide additional for the SecureTransport Decision Insight integration:

-   [Event states](#event) - Describes the Decision Insight event states.
-   [Tracked objects](#tracked) - Lists the attributes of the Tracked Objects used to report Axway SecureTransport events to Decision Insight.
-   [XFB Transfer tracked objects](#xfb) - Describes the XFB transfer tracked objects.
-   [Configure SecureTransport to send events to Decision Insight](#configur) - Provides how-to instructions for configuring SecureTransport to send events to Decision Insight.

## <span id="Event"></span>Event states

An event state specifies the current state of a file transfer. Every event in the same group about one file transfer is identified using the same cycle ID. For Axway Sentinel events information, refer to [Event states](../c_st_sentinelintegration/r_st_sentineleventstates).

The following event states indicate a transfer start and end.

<table cellspacing="0">
   <col/>
   <col/>
   <col/>
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Direction</th>
         <th>Start</th>
         <th>Success</th>
         <th>Failure</th>
         <th>Cancellation</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>Incoming         </td>
         <td><code>RECEIVING</code>
         </td>
         <td><code>RECEIVED</code>
         </td>
         <td><code>FAILED</code>
         </td>
         <td><code>CANCEL</code>
         </td>
      </tr>
      <tr>
         <td>Outgoing         </td>
         <td><code>SENDING</code>
         </td>
         <td><code>SENT</code>
         </td>
         <td><code>FAILED</code>
         </td>
         <td><code>CANCEL</code>
         </td>
      </tr>
   </tbody>
</table>

The following event states indicate a post processing action.

<table cellspacing="0">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Event state</th>
         <th>Description</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><code>DECRYPTED</code>
         </td>
         <td><span>SecureTransport</span> has performed a successful PGP decryption.         </td>
      </tr>
      <tr>
         <td><code>DECRYPTING</code>
         </td>
         <td><span>SecureTransport</span> is starting to decrypt a file.         </td>
      </tr>
      <tr>
         <td><code>DELETED</code>
         </td>
         <td>A client, post-processing action (PPA), or post client download action  has deleted a file.         </td>
      </tr>
      <tr>
         <td><code>ENCRYPTED</code>
         </td>
         <td><span>SecureTransport</span> has performed a successful PGP encryption.         </td>
      </tr>
      <tr>
         <td><code>ENCRYPTING</code>
         </td>
         <td><span>SecureTransport</span> is starting to encrypt a file.         </td>
      </tr>
      <tr>
         <td><code>POST_PROC/ARCHIVED</code>
         </td>
         <td>The file has been archived.         </td>
      </tr>
      <tr>
         <td><code>POST_PROC/ICAP_DENIED</code>
         </td>
         <td>Access to the file is denied.         </td>
      </tr>
      <tr>
         <td><code>POST_PROC/ICAP_SCANNED</code>
         </td>
         <td>The scanning of the file has successfully finished.         </td>
      </tr>
      <tr>
         <td><code>POST_PROC/ICAP_SCANNING</code>
         </td>
         <td>The scanning of the file has started.         </td>
      </tr>
      <tr>
         <td>
            <p><code>POST_PROC/ROUTED</code>
</p>
         </td>
         <td>An <span>Advanced Routing</span> application has successfully completed.         </td>
      </tr>
      <tr>
         <td><code>POST_PROC/ROUTING</code>
         </td>
         <td><span>SecureTransport</span> is starting an <span>Advanced Routing</span> application.         </td>
      </tr>
      <tr>
         <td><code>RENAMED</code>
         </td>
         <td>A client action, or a post-transmission action (PTA), or post-processing action has renamed a file.         </td>
      </tr>
      <tr>
         <td><code>ROUTED</code>
         </td>
         <td>As the intermediate partner in a routed PeSIT transfer, <span>SecureTransport</span> has sent a file to the routing destination.         </td>
      </tr>
   </tbody>
</table>

## <span id="Tracked"></span>Tracked objects

This topic lists the attributes of the Tracked Objects used to SecureTransport events to Decision Insight. For information on all the of standard attributes, refer to [Axway Sentinel tracked objects](../c_st_sentinelintegration/r_st_sentineltrackedobjects).

The attributes that Decision Insight uses to build the dashboards are:

<table cellspacing="0">
   <col/>
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Name</th>
         <th>Format</th>
         <th>Description</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><code>COREID</code>
         </td>
         <td>string         </td>
         <td>File identifier reported with every state         </td>
      </tr>
      <tr>
         <td><code>CYCLEID</code>
         </td>
         <td>string         </td>
         <td>ID used to relate events about the same transfer.         </td>
      </tr>
      <tr>
         <td><code>DIRECTION</code>
         </td>
         <td>string         </td>
         <td><code>R</code> for receive, <code>S</code> for send         </td>
      </tr>
      <tr>
         <td><code>FINALRECEIVERID</code>
         </td>
         <td>string         </td>
         <td>Name of the final receiver of the transfer         </td>
      </tr>
      <tr>
         <td><code>GROUPNAME</code>
         </td>
         <td>string         </td>
         <td><span>Axway SecureTransport</span> account business unit         </td>
      </tr>
      <tr>
         <td><code>ISALERT</code>
         </td>
         <td><code>0</code>/<code>1</code>         </td>
         <td><code>1</code> means permanent error on last entry         </td>
      </tr>
      <tr>
         <td><code>ISEXCEPTION</code>
         </td>
         <td><code>0</code>/<code>1</code>         </td>
         <td><code>1</code> means temporary failure         </td>
      </tr>
      <tr>
         <td><code>ORIGINALSENDERID</code>
         </td>
         <td>string         </td>
         <td>Name of the original sender of the transfer         </td>
      </tr>
      <tr>
         <td><code>RECEIVERID</code>
         </td>
         <td>string         </td>
         <td>Name of the receiving partner         </td>
      </tr>
      <tr>
         <td><code>REQUESTGROUPID</code>
         </td>
         <td>string         </td>
         <td>Local identifier of the group to which the requesting user belongs         </td>
      </tr>
      <tr>
         <td><code>REQUESTUSERID</code>
         </td>
         <td>string         </td>
         <td>Local identifier of the user who requested the transfer         </td>
      </tr>
      <tr>
         <td><code>SENDERID</code>
         </td>
         <td>string         </td>
         <td>Name of the sending partner         </td>
      </tr>
      <tr>
         <td><code>USERID</code>
         </td>
         <td>string         </td>
         <td><span>Axway SecureTransport</span> Login Name/Account Name or account name of the account the triggered the <span>Advanced Routing</span> feature         </td>
      </tr>
      <tr>
         <td><code>USERPARAMETER1</code>
         </td>
         <td>string         </td>
         <td>Account type: <code>E</code> for Partner, <code>I</code> for Internal, <code>N</code> for Unspecified         </td>
      </tr>
   </tbody>
</table>

## <span id="XFB"></span>XFB Transfer tracked objects

This topic provides the XFB tracked object roles, sender and receivers, production identification, and transfer attributes. For more information, refer to [XFB Tracked Object attributes](../c_st_sentinelintegration/r_st_xfb_toattributes).

## <span id="Configur"></span>Configure SecureTransport to send events to Decision Insight

Use the SecureTransport Administration Tool to configure SecureTransport to send events to Decision Insight.

The setting applies to all servers in your Enterprise Cluster (EC). Each server must have its own overflow file.

1.  Select **Setup > Axway Sentinel/DI** to open the *Axway Sentinel/Decision Insights Events* page.

2.  Select the check box for **Send Events to Axway Sentinel or Decision Insight Server**.  
    The rest of the fields on the screen are enabled and SecureTransport sends events to Decision Insight as configured.

3.  In the *Axway Sentinel/Decision Insight* pane, specify the FQDN or IP address of the Decision Insight server in the **Host** field and a valid TCP port on the server to which events will be sent in the **Port** field.

4.  (Optional) Select the check box for **Use Secure Connection** to enable sending the selected event to Decision Insight over a secured connection.

5.  (Optional) Select the check box for **Verify Certificate** to enable the SSL certificate verification. The **Verify Certificate** check box is selected by default.

6.  (Optional) Select the check box for **Enable FIPS Transfer Mode** to enable sending events to Decision Insight over the secure connection in FIPS transfer mode.  
    

    <table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">Changes to these settings in Step 3 through Step 6 take effect the next time you restart the Transaction Manager.         </td>
      </tr>
</table>

7.  (Optional) Click the **Test Connection** button. This test indicates whether the port specified on the Decision Insight host accepts connections.

8.  In the *Events* pane, select the event states to send to Decision Insight.  
    An Event State specifies the current state of a file transfer. If an Event State is not selected to be sent, SecureTransport performs the processing represented by the state, but it does not send the event that reports the state to Decision Insight.  
    

    <table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">The Event states that indicate transfer start and end must be enabled to build <span>Decision Insight</span> dashboards. Refer to <a href="#event">Event states</a>.         </td>
      </tr>
</table>

9.  In the *Overflow file* pane, specify information about the file to be used to store SecureTransport event data when there is no connection between SecureTransport and Decision Insight. For more information, refer to [Configure SecureTransport to send events to Axway Sentinel](../c_st_sentinelintegration/t_st_sentinel).

10. Click **Save**.
