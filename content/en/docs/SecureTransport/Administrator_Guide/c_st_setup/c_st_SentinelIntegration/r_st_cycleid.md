{
    "title": "CycleId calculation",
    "linkTitle": "CycleId calculation",
    "weight": "250"
}This topic describes the internal CycleId structure for PeSIT and SFTP protocol transfers.

## Internal CycleId structure with PeSIT

The internal CycleId is an XFB Transfer Tracked Object attribute. This field has the following structure for PeSIT transfers:

<table cellspacing="0">
   <col/>
   <col/>
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Offset</th>
         <th>Length</th>
         <th>PI/Value</th>
         <th>Description</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>1         </td>
         <td>4         </td>
         <td>“SUIV”         </td>
         <td>Eye catcher         </td>
      </tr>
      <tr>
         <td rowspan="2">5         </td>
         <td rowspan="2">24         </td>
         <td>PI3 CONNECT         </td>
         <td>For Transmission         </td>
      </tr>
      <tr>
         <td>PI4 CONNECT         </td>
         <td>For Reception         </td>
      </tr>
      <tr>
         <td rowspan="2">29         </td>
         <td rowspan="2">24         </td>
         <td>PI4 CONNECT         </td>
         <td>For Transmission         </td>
      </tr>
      <tr>
         <td>PI3 CONNECT         </td>
         <td>For Reception         </td>
      </tr>
      <tr>
         <td rowspan="3">53         </td>
         <td rowspan="3">5         </td>
         <td>"0   "         </td>
         <td>For File Transfer         </td>
      </tr>
      <tr>
         <td>"65535"         </td>
         <td>For Message Transfer         </td>
      </tr>
      <tr>
         <td>"REPLY"         </td>
         <td>For Acknowledgment         </td>
      </tr>
      <tr>
         <td>58         </td>
         <td>76         </td>
         <td>PI12         </td>
         <td>Logical file name         </td>
      </tr>
      <tr>
         <td>134         </td>
         <td>8         </td>
         <td>PI13         </td>
         <td>Transfer ID         </td>
      </tr>
      <tr>
         <td>142         </td>
         <td>12         </td>
         <td>PI51         </td>
         <td>Only the date is used (YYMMDD), and the time is filled with 6 spaces.         </td>
      </tr>
      <tr>
         <td rowspan="2">154         </td>
         <td rowspan="2">1         </td>
         <td>E         </td>
         <td>For Transmission         </td>
      </tr>
      <tr>
         <td>R         </td>
         <td>For Reception         </td>
      </tr>
   </tbody>
</table>

## Internal CycleId structure with SFTP

The internal CycleId is an XFB Transfer Tracked Object attribute. This field has the following structure for SFTP transfers:

<table cellspacing="0">
   <col/>
   <col/>
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Offset</th>
         <th>Length</th>
         <th>PI/Value</th>
         <th>Comments</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>
            <p> 1</p>
         </td>
         <td>
            <p>4</p>
         </td>
         <td>
            <p>SUIV</p>
            <p>TEMP</p>
         </td>
         <td>
            <p>Eye catcher </p>
         </td>
      </tr>
      <tr>
         <td>
            <p>5</p>
         </td>
         <td>
            <p>24</p>
         </td>
         <td>
            <p>Sender identifier</p>
         </td>
         <td>
            <p>Sender account login na me<br/> SEND: System login of the process that runs the SFTP client<br/> RECV: SFTP login name sends by the client to connect to the SFTP server</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>29</p>
         </td>
         <td>
            <p>24</p>
         </td>
         <td>
            <p>Receiver identifier</p>
         </td>
         <td>
            <p>Receiver login name <br/> SEND: SFTP login name sends by the client to connect to the SFTP server <br/> RECV: System login of the process that runs the SFTP client</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>53</p>
         </td>
         <td>
            <p>5</p>
         </td>
         <td>
            <p>"0"</p>
         </td>
         <td>
            <p>For File Transfer</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>58</p>
         </td>
         <td>
            <p>76</p>
         </td>
         <td>
            <p>Virtual Filename</p>
         </td>
         <td>
            <p>Logical file name, NIDF for CFT</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>134</p>
         </td>
         <td>
            <p>8</p>
         </td>
         <td>
            <p>Sequence number</p>
         </td>
         <td>
            <p>Unique number identifying the transfer sent, NIDT for CFT</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>142</p>
         </td>
         <td>
            <p>12</p>
         </td>
         <td>
            <p>Date YYMMDD </p>
            <p>/padded to 12 with spaces on the right/</p>
         </td>
         <td>
            <p>Only the date is used (YYMMDD), and the time is filled with 6 spaces</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>154</p>
         </td>
         <td>
            <p>1</p>
         </td>
         <td>
            <p>E</p>
         </td>
         <td>
            <p>For Transmission</p>
         </td>
      </tr>
      <tr>
         <td>          </td>
         <td>          </td>
         <td>
            <p>R</p>
         </td>
         <td>
            <p>For Reception</p>
         </td>
      </tr>
   </tbody>
</table>

### Generating common CycleID for end-to-end tracking of SFTP transfers

With transfers occurring across Axway's MFT solutions SecureTransport and Transfer CFT, the CycleID is used for consistent end-to-end reporting to Sentinel. In order to report the common CycleID, you must set the dedicated configuration option: `Ssh.AxwayVendorExtensions.enabled` to `true`. In order to apply this change, you must restart the SSH services and the Transaction Manager (TM) on all Server and Edge instances.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">When this option is enabled, in the case when <span>SecureTransport</span> acts as client and transfer CFT acts as server, make sure to name each of your transfer sites to exactly match the corresponding NIDF name in Transfer CFT. Also, for correct SFTP end-to-end reporting with CFT, make sure to use only capital letters for each SecureTransport user's Account name (Login name).         </td>
      </tr>
</table>

**Related topics:**

-   [Event states](../r_st_sentineleventstates)
-   [Axway Sentinel tracked objects](../r_st_sentineltrackedobjects)
-   [About XFB Transfer tracked objects](../c_st_aboutxfb_to)
-   [PeSIT protocol](../r_st_pesit_protocol)
-   [List of PeSIT states](../r_st_listofpesitstates)
-   [XFB Tracked Object attributes](../r_st_xfb_toattributes)
-   [Axway Sentinel dashboards](r_st_sentineldashboards.htm)
-   [Axway Sentinel requests](../r_st_sentinelrequests)
-   [Configure SecureTransport to send events to Axway Sentinel](../t_st_sentinel)
