{
    "title": "XFBTransfer predefined requests",
    "linkTitle": "XFBTransfer predefined requests",
    "weight": "230"
}## XFBTransfer requests

When you configure Sentinel, you can import a set of predefined XFBTransfer
requests into the Monitoring interface. The following table describes
these Requests. All of these Requests retrieve Tracked Instances
from XFBTransfer.

<table>
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Request         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1">Retrieves...         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>CurrentTransfers</p>         </td>
         <td><p>All Tracked Instances from the Current Table
of XFBTransfer.</p>         </td>
      </tr>
      <tr>
         <td><p>CurrentTransfersToday</p>         </td>
         <td><p>Tracked Instances from the Current Table
of XFBTransfer that correspond to the current date.</p>         </td>
      </tr>
      <tr>
         <td><p>CurrentTransfersAlert</p>         </td>
         <td><p>Tracked Instances from the Current Table of XFBTransfer
that correspond to an Alert.</p>         </td>
      </tr>
   </tbody>
</table>

## XFBLog request

When you configure Sentinel with Transfer CFT, you can import
a predefined request for XFBTransfer <span style="font-style: italic;">TransferLog</span>.
This Request retrieves Tracked Instances that describe the contents of
a <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> log.

Related topics

-   [XFBLog Tracked Object](../xfblog)
