{
    "title": "Integrate Decision Insight",
    "linkTitle": "Integrate Decision Insight",
    "weight": "170"
}<span class="mc-variable suite_variables.DecisionInsightName variable">Decision Insight</span> is a Business Activity Monitoring (BAM) product that collects, aggregates, correlates, and reports events from <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> and other products, applications, and systems throughout your infrastructure. <span class="mc-variable suite_variables.DecisionInsightName variable">Decision Insight</span> is a separate product that you can buy from <span class="mc-variable axway_variables.Company_Name variable">Axway</span> or an authorized partner. Once you license and configure <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> to send file transfer and processing events to Decision Insight, data is collected and displayed on a dashboard.

> **Note:**
>
> Decision Insight does not support Attribute mapping in SecureTransport.

> **Note:**
>
> Decision Insight will not monitor ad hoc activity.

For addition information please refer to the official confluence page [Embedded Analytics for Secure Transport Home](https://techweb.axway.com/public/display/DOCEAST/)

The following topics provide additional for the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> <span class="mc-variable suite_variables.DecisionInsightName variable">Decision Insight</span> integration:

-   <a href="#Event" class="MCXref xref">Event states</a> - Describes the <span class="mc-variable suite_variables.DecisionInsightName variable">Decision Insight</span> event states.
-   <a href="#Tracked" class="MCXref xref">Tracked objects</a> - Lists the attributes of the Tracked Objects used to report <span class="mc-variable axway_variables.Component_Long_Name variable">Axway SecureTransport</span> events to <span class="mc-variable suite_variables.DecisionInsightName variable">Decision Insight</span>.
-   <a href="#XFB" class="MCXref xref">XFB Transfer tracked objects</a> - Describes the XFB transfer tracked objects.
-   <a href="#Configur" class="MCXref xref">Configure SecureTransport to send events to Decision Insight</a> - Provides how-to instructions for configuring <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> to send events to <span class="mc-variable suite_variables.DecisionInsightName variable">Decision Insight</span>.

<span id="Event"></span>

## Event states

An event state specifies the current state of a file transfer. Every event in the same group about one file transfer is identified using the same cycle ID. For Axway Sentinel events information, refer to <a href="../c_st_sentinelintegration/r_st_sentineleventstates" class="MCXref xref">Event states</a>.

The following event states indicate a transfer start and end.

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Direction         </th>
<th class="HeadE-Column1-Header1">Start         </th>
<th class="HeadE-Column1-Header1">Success         </th>
<th class="HeadE-Column1-Header1">Failure         </th>
<th class="HeadD-Column1-Header1">Cancellation         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>Incoming         </td>
         <td><code>RECEIVING</code>         </td>
         <td><code>RECEIVED</code>         </td>
         <td><code>FAILED</code>         </td>
         <td><code>CANCEL</code>         </td>
      </tr>
      <tr>
         <td>Outgoing         </td>
         <td><code>SENDING</code>         </td>
         <td><code>SENT</code>         </td>
         <td><code>FAILED</code>         </td>
         <td><code>CANCEL</code>         </td>
      </tr>
   </tbody>
</table>

The following event states indicate a post processing action.

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Event state         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><code>DECRYPTED</code>         </td>
         <td><span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> has performed a successful PGP decryption.         </td>
      </tr>
      <tr>
         <td><code>DECRYPTING</code>         </td>
         <td><span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> is starting to decrypt a file.         </td>
      </tr>
      <tr>
         <td><code>DELETED</code>         </td>
         <td>A client, post-processing action (PPA), or post client download action has deleted a file.         </td>
      </tr>
      <tr>
         <td><code>ENCRYPTED</code>         </td>
         <td><span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> has performed a successful PGP encryption.         </td>
      </tr>
      <tr>
         <td><code>ENCRYPTING</code>         </td>
         <td><span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> is starting to encrypt a file.         </td>
      </tr>
      <tr>
         <td><code>POST_PROC/ARCHIVED</code>         </td>
         <td>The file has been archived.         </td>
      </tr>
      <tr>
         <td><code>POST_PROC/ICAP_DENIED</code>         </td>
         <td>Access to the file is denied.         </td>
      </tr>
      <tr>
         <td><code>POST_PROC/ICAP_SCANNED</code>         </td>
         <td>The scanning of the file has successfully finished.         </td>
      </tr>
      <tr>
         <td><code>POST_PROC/ICAP_SCANNING</code>         </td>
         <td>The scanning of the file has started.         </td>
      </tr>
      <tr>
         <td><p><code>POST_PROC/ROUTED</code></p>         </td>
         <td>An <span class="mc-variable my_project_variables.Advanced_Routing variable">Advanced Routing</span> application has successfully completed.         </td>
      </tr>
      <tr>
         <td><code>POST_PROC/ROUTING</code>         </td>
         <td><span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> is starting an <span class="mc-variable my_project_variables.Advanced_Routing variable">Advanced Routing</span> application.         </td>
      </tr>
      <tr>
         <td><code>RENAMED</code>         </td>
         <td>A client action, or a post-transmission action (PTA), or post-processing action has renamed a file.         </td>
      </tr>
      <tr>
         <td><code>ROUTED</code>         </td>
         <td>As the intermediate partner in a routed PeSIT transfer, <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> has sent a file to the routing destination.         </td>
      </tr>
   </tbody>
</table>

<span id="Tracked"></span>

## Tracked objects

This topic lists the attributes of the Tracked Objects used to <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> events to <span class="mc-variable suite_variables.DecisionInsightName variable">Decision Insight</span>. For information on all the of standard attributes, refer to <a href="../c_st_sentinelintegration/r_st_sentineltrackedobjects" class="MCXref xref">Axway Sentinel tracked objects</a>.

The attributes that <span class="mc-variable suite_variables.DecisionInsightName variable">Decision Insight</span> uses to build the dashboards are:

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Name         </th>
<th class="HeadE-Column1-Header1">Format         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><code>COREID</code>         </td>
         <td>string         </td>
         <td>File identifier reported with every state         </td>
      </tr>
      <tr>
         <td><code>CYCLEID</code>         </td>
         <td>string         </td>
         <td>ID used to relate events about the same transfer.         </td>
      </tr>
      <tr>
         <td><code>DIRECTION</code>         </td>
         <td>string         </td>
         <td><code>R</code> for receive, <code>S</code> for send         </td>
      </tr>
      <tr>
         <td><code>FINALRECEIVERID</code>         </td>
         <td>string         </td>
         <td>Name of the final receiver of the transfer         </td>
      </tr>
      <tr>
         <td><code>GROUPNAME</code>         </td>
         <td>string         </td>
         <td><span class="mc-variable axway_variables.Component_Long_Name variable">Axway SecureTransport</span> account business unit         </td>
      </tr>
      <tr>
         <td><code>ISALERT</code>         </td>
         <td><code>0</code>/<code>1</code>         </td>
         <td><code>1</code> means permanent error on last entry         </td>
      </tr>
      <tr>
         <td><code>ISEXCEPTION</code>         </td>
         <td><code>0</code>/<code>1</code>         </td>
         <td><code>1</code> means temporary failure         </td>
      </tr>
      <tr>
         <td><code>ORIGINALSENDERID</code>         </td>
         <td>string         </td>
         <td>Name of the original sender of the transfer         </td>
      </tr>
      <tr>
         <td><code>RECEIVERID</code>         </td>
         <td>string         </td>
         <td>Name of the receiving partner         </td>
      </tr>
      <tr>
         <td><code>REQUESTGROUPID</code>         </td>
         <td>string         </td>
         <td>Local identifier of the group to which the requesting user belongs         </td>
      </tr>
      <tr>
         <td><code>REQUESTUSERID</code>         </td>
         <td>string         </td>
         <td>Local identifier of the user who requested the transfer         </td>
      </tr>
      <tr>
         <td><code>SENDERID</code>         </td>
         <td>string         </td>
         <td>Name of the sending partner         </td>
      </tr>
      <tr>
         <td><code>USERID</code>         </td>
         <td>string         </td>
         <td><span class="mc-variable axway_variables.Component_Long_Name variable">Axway SecureTransport</span> Login Name/Account Name or account name of the account the triggered the <span class="mc-variable my_project_variables.Advanced_Routing variable">Advanced Routing</span> feature         </td>
      </tr>
      <tr>
         <td><code>USERPARAMETER1</code>         </td>
         <td>string         </td>
         <td>Account type: <code>E</code> for Partner, <code>I</code> for Internal, <code>N</code> for Unspecified         </td>
      </tr>
   </tbody>
</table>

<span id="XFB"></span>

## XFB Transfer tracked objects

This topic provides the XFB tracked object roles, sender and receivers, production identification, and transfer attributes. For more information, refer to <a href="../c_st_sentinelintegration/r_st_xfb_toattributes" class="MCXref xref">XFB Tracked Object attributes</a>.

<span id="Configur"></span>

## Configure SecureTransport to send events to Decision Insight

Use the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Administration Tool to configure <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> to send events to <span class="mc-variable suite_variables.DecisionInsightName variable">Decision Insight</span>.

The setting applies to all servers in your Enterprise Cluster (EC). Each server must have its own overflow file.

1.  Select **Setup > <span class="mc-variable axway_variables.Company_Name variable" style="mc-tag-and-class: ;">Axway</span> Sentinel/DI** to open the *<span class="mc-variable axway_variables.Company_Name variable">Axway</span> Sentinel/Decision Insights Events* page.

2.  Select the check box for **Send Events to Axway Sentinel or Decision Insight Server**.  
    The rest of the fields on the screen are enabled and <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> sends events to <span class="mc-variable suite_variables.DecisionInsightName variable">Decision Insight</span> as configured.

3.  In the *<span class="mc-variable axway_variables.Company_Name variable" style="mc-tag-and-class: ;">Axway</span> Sentinel/Decision Insight* pane, specify the FQDN or IP address of the <span class="mc-variable suite_variables.DecisionInsightName variable">Decision Insight</span> server in the **Host** field and a valid TCP port on the server to which events will be sent in the **Port** field.

4.  (Optional) Select the check box for **Use Secure Connection** to enable sending the selected event to <span class="mc-variable suite_variables.DecisionInsightName variable">Decision Insight</span> over a secured connection.

5.  (Optional) Select the check box for **Verify Certificate** to enable the SSL certificate verification. The **Verify Certificate** check box is selected by default.

6.  (Optional) Select the check box for **Enable FIPS Transfer Mode** to enable sending events to <span class="mc-variable suite_variables.DecisionInsightName variable">Decision Insight</span> over the secure connection in FIPS transfer mode.  

    > **Note:**
    >
    > Changes to these settings in Step 3 through Step 6 take effect the next time you restart the Transaction Manager.

7.  (Optional) Click the **Test Connection** button. This test indicates whether the port specified on the <span class="mc-variable suite_variables.DecisionInsightName variable">Decision Insight</span> host accepts connections.

8.  In the *Events* pane, select the event states to send to <span class="mc-variable suite_variables.DecisionInsightName variable">Decision Insight</span>.  
    An Event State specifies the current state of a file transfer. If an Event State is not selected to be sent, <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> performs the processing represented by the state, but it does not send the event that reports the state to <span class="mc-variable suite_variables.DecisionInsightName variable">Decision Insight</span>.  

    > **Note:**
    >
    > The Event states that indicate transfer start and end must be enabled to build Decision Insight dashboards. Refer to Event states.

9.  In the *Overflow file* pane, specify information about the file to be used to store <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> event data when there is no connection between <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> and <span class="mc-variable suite_variables.DecisionInsightName variable">Decision Insight</span>. For more information, refer to <a href="../c_st_sentinelintegration/t_st_sentinel" class="MCXref xref">Configure SecureTransport to send events to Axway Sentinel</a>.

10. Click **Save**.
