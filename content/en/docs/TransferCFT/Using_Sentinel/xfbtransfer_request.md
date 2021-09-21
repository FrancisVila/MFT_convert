{
    "title": "XFBTransfer predefined requests",
    "linkTitle": "XFBTransfer predefined requests",
    "weight": "240"
}## XFBTransfer requests

When you configure Sentinel, you can import a set of predefined XFBTransfer
requests into the Monitoring interface. The following table describes
these Requests. All of these Requests retrieve Tracked Instances
from XFBTransfer.

<table cellspacing="0">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Request</th>
         <th>Retrieves...</th>
      </tr>
   </thead>
      <tr>
         <td valign="top" width="40%">
            <p>CurrentTransfers</p>
         </td>
         <td valign="top" width="60%">
            <p>All Tracked Instances from the Current Table 
 of XFBTransfer.</p>
         </td>
      </tr>
      <tr>
         <td valign="top" width="40%">
            <p>CurrentTransfersToday</p>
         </td>
         <td valign="top" width="60%">
            <p>Tracked Instances from the Current Table 
 of XFBTransfer that correspond to the current date.</p>
         </td>
      </tr>
      <tr>
         <td valign="top" width="40%">
            <p>CurrentTransfersAlert</p>
         </td>
         <td valign="top" width="60%">
            <p>Tracked Instances from the Current Table of XFBTransfer 
 that correspond to an Alert.</p>
         </td>
      </tr>
</table>

## XFBLog request

When you configure Sentinel with Transfer CFT, you can import
a predefined request for XFBTransfer TransferLog.
This Request retrieves Tracked Instances that describe the contents of
a Transfer CFT log.

Related topics

-   [XFBLog Tracked Object](../xfblog)