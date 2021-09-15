{
    "title": "PeSIT protocol",
    "linkTitle": "PeSIT protocol",
    "weight": "220"
}This topic describes the XFB tracked object attributes and provides monitoring errors, tracked-event processing, processing cycles, and tracked-event links.

## XFB\_TO system attributes

The XFB tracked objects are monitored and the errors, tracked-event processing, processing cycles, and tracked-event links are passed to Sentinel.

The following topics list errors, tracked-event processing, processing cycles, and tracked-event links are passed to Sentinel:

-   [Monitoring errors](#errors)
-   [Monitoring tracked-event messages](#tracked_event)
-   [Monitoring processing cycles](#processing)
-   [Monitoring tracked-event links](#links)

### <span id="Errors"></span>Monitoring errors

<table cellspacing="0">
   <col/>
   <col/>
   <col/>
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Sentinel
attribute
</th>
         <th>Data type</th>
         <th>Length</th>
         <th>Description</th>
         <th>Name in <span>SecureTransport</span></th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>IsException         </td>
         <td>Integer         </td>
         <td>1         </td>
         <td>
            <p>Indicates a temporary error.</p>
            <p>Values:</p>
            <ul>
               <li><strong>0</strong>: The relevant Tracked-Event Message does not describe an exception.               </li>
               <li><strong>1</strong>: The relevant Tracked-Event Message describes one or more exceptions.               </li>
            </ul>
         </td>
         <td>IsException         </td>
      </tr>
      <tr>
         <td>IsAlert         </td>
         <td>Integer         </td>
         <td>1         </td>
         <td>
            <p>Indicates a permanent (unrecoverable) error.</p>
            <p>Values:</p>
            <ul>
               <li><strong>0</strong>: No alert is associated with the relevant Tracked-Event Message.               </li>
               <li><strong>1</strong>: The relevant Tracked-Event Message is associated with a processing exception that generated an alert.               </li>
            </ul>
         </td>
         <td>IsAlert         </td>
      </tr>
      <tr>
         <td>ReturnCode         </td>
         <td>String         </td>
         <td>20         </td>
         <td>
            <p>Processing details that the relevant tracked application generated. When the value of <em>IsAlert</em> is 1, this attribute often contains an error code.</p>
            <p>The error code corresponds to the exit code of the event.</p>
         </td>
         <td>ReturnCode         </td>
      </tr>
      <tr>
         <td>ReturnMessage         </td>
         <td>String         </td>
         <td>250         </td>
         <td>Processing details that the relevant tracked application generated. In case of successful transfers this message is empty.         </td>
         <td>Stores the details for the transfer error. Corresponds to DXAGENT_EXECUTION_ERROR_MESSAGE.         </td>
      </tr>
   </tbody>
</table>

### <span id="Tracked_event"></span>Monitoring tracked-event messages

<table cellspacing="0">
   <col/>
   <col/>
   <col/>
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Sentinel attribute</th>
         <th>Data type</th>
         <th>Length</th>
         <th>Description</th>
         <th>Name in <span>SecureTransport</span></th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>GMTDiff         </td>
         <td>Integer         </td>
         <td>          </td>
         <td>Positive or negative difference between the Greenwich Mean Time (GMT) and the local time expressed in minutes.         </td>
         <td>GMTDiff         </td>
      </tr>
      <tr>
         <td>ProductName         </td>
         <td>String         </td>
         <td>50         </td>
         <td>The constant SecureTransport.         </td>
         <td>Reports the name of the product.         </td>
      </tr>
      <tr>
         <td>ProductIPAddr         </td>
         <td>String         </td>
         <td>255         </td>
         <td>IP address of the product/application that generated the relevant Tracked Event.         </td>
         <td>Reports the host name assigned to the system.         </td>
      </tr>
      <tr>
         <td>ProductOS         </td>
         <td>String         </td>
         <td>20         </td>
         <td>Operating system of the application that generated the relevant Tracked Event.         </td>
         <td>Java os.name system property.         </td>
      </tr>
      <tr>
         <td>State         </td>
         <td>String         </td>
         <td>29         </td>
         <td>Status of the relevant Tracked Event. The possible values of this attribute depend on the tracked application/product and file transfer protocol used. See List of PeSIT states.         </td>
         <td>State         </td>
      </tr>
   </tbody>
</table>

### <span id="Processing"></span>Monitoring processing cycles

<table cellspacing="0">
   <col/>
   <col/>
   <col/>
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Sentinel attribute</th>
         <th>Data type</th>
         <th>Length</th>
         <th>Description</th>
         <th>Name in <span>SecureTransport</span></th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>CycleId         </td>
         <td>String         </td>
         <td>250         </td>
         <td>CycleId of the relevant Tracked Event.         </td>
         <td>CycleId         </td>
      </tr>
      <tr>
         <td>IsEnd         </td>
         <td>Integer         </td>
         <td>1         </td>
         <td>
            <p>Values:</p>
            <ul>
               <li><strong>0</strong>: The relevant Processing Cycle is not complete.               </li>
               <li><strong>1</strong>: The relevant Processing Cycle is complete.               </li>
            </ul>
         </td>
         <td>IsEnd         </td>
      </tr>
   </tbody>
</table>

### <span id="Links"></span>Monitoring tracked-event links

<table cellspacing="0">
   <col/>
   <col/>
   <col/>
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Sentinel attribute</th>
         <th>Data type</th>
         <th>Length</th>
         <th>Description</th>
         <th>Name in <span>SecureTransport</span></th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>UserParentID         </td>
         <td>String         </td>
         <td>250         </td>
         <td>Unique string that identifies the parent of the relevant Tracked Event         </td>
         <td>Not used         </td>
      </tr>
      <tr>
         <td>UserObjectId         </td>
         <td>String         </td>
         <td>250         </td>
         <td>Unique string that identifies the relevant Tracked Event.         </td>
         <td>Not used         </td>
      </tr>
      <tr>
         <td>UserChildId         </td>
         <td>String         </td>
         <td>250         </td>
         <td>Unique string that identifies a child of the relevant Tracked Event         </td>
         <td>Not used         </td>
      </tr>
   </tbody>
</table>

**Related topics:**

-   [Event states](../r_st_sentineleventstates)
-   [Axway Sentinel tracked objects](../r_st_sentineltrackedobjects)
-   [About XFB Transfer tracked objects](../c_st_aboutxfb_to)
-   [List of PeSIT states](../r_st_listofpesitstates)
-   [XFB Tracked Object attributes](../r_st_xfb_toattributes)
-   [CycleId calculation](../r_st_cycleid)
-   [Axway Sentinel dashboards](r_st_sentineldashboards.htm)
-   [Axway Sentinel requests](../r_st_sentinelrequests)
-   [Configure SecureTransport to send events to Axway Sentinel](../t_st_sentinel)
