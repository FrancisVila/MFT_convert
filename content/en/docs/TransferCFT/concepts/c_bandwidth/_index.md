{
    "title": "Manage bandwidth control",
    "linkTitle": "Managing bandwidth",
    "weight": "200"
}The bandwidth control feature aides in controlling the network bandwidth used for incoming and outgoing data. This feature is based on the notion of class-of-service.

Class-of-service defines a common set of parameters for all network session established under it, such as :

-   Weight: An integer value used to compute the global bandwidth rate that this class of service can use (for details, see 'Nominal data rate').
-   Rate: The global bandwidth rate that this class of service can use. The value is computed by the product from the 'weights' configured for the class of services.
-   Max-rate: The maximum bandwidth rate that this class of service can use when borrowing
-   Session-rate: The maximum bandwidth rate that a network session can use under that class of service

All rates, either configured as rates or computed from weights, represent a number of Kbytes per second.

> **Note:**
>
> In Central Governance see the Bandwidth Allocation section on the product configuration page, and Bandwidth Allocation in the Transfer Properties of the flow definition, for supported bandwidth features and details.

## Parameters

All class-of-service parameters can be updated dynamically. Use CFTUTIL RECONFIG TYPE=UCONF to update these parameters.

### Assign a class-of-service to transfers

Transfers are assigned to a specific class of bandwidth through the **COS** field:

-   Transfer parameter (SEND, RECV)
-   Transfer profile parameters (CFTSEND, CFTRECV)
-   Partner (CFTPART)
-   Protocol (CFTPROT)

### Class-of-service parameters

<table>
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Parameter         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Default         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>uconf:cft.server.bandwidth.cos.&lt;cos-num&gt;.weight_in         </td>
         <td>unlimited         </td>
         <td>This value is used to compute the nominal rate of incoming data for this class of service. **         </td>
      </tr>
      <tr>
         <td>uconf:cft.server.bandwidth.cos.&lt;cos-num&gt;.weight_out         </td>
         <td>unlimited         </td>
         <td>This value is used to compute the nominal rate of outgoing data for this class of service. **         </td>
      </tr>
      <tr>
         <td><p>** Do not configure the parameters <strong>weight_in</strong> and <strong>weight_out</strong> for the class-of-service 0, as they cannot be used in this context. See <a href="#Concepts">Concepts.</a></p>         </td>
      </tr>
      <tr>
         <td>uconf:cft.server.bandwidth.cos.&lt;cos-num&gt;.max_rate_out         </td>
         <td>unlimited         </td>
         <td>Maximum rate of incoming data for that class-of-service         </td>
      </tr>
      <tr>
         <td>uconf:cft.server.bandwidth.cos.&lt;cos-num&gt;.max_rate_out         </td>
         <td>unlimited         </td>
         <td>Maximum rate of outgoing data for that class-of-service         </td>
      </tr>
      <tr>
         <td>uconf:cft.server.bandwidth.cos.&lt;cos-num&gt;.session_rate_in         </td>
         <td>unlimited         </td>
         <td>Maximum rate of incoming data for sessions under that class-of-service         </td>
      </tr>
      <tr>
         <td>uconf:cft.server.bandwidth.cos.&lt;cos-num&gt;.session_rate_out         </td>
         <td>unlimited         </td>
         <td>Maximum rate of outgoing data for sessions under that class-of-service         </td>
      </tr>
      <tr>
         <td>uconf:cft.server.bandwidth.cos.&lt;cos-num&gt;.parent         </td>
         <td>0         </td>
         <td>Parent class-of-service         </td>
      </tr>
      <tr>
         <td>uconf:cft.server.bandwidth.cos.&lt;cos-num&gt;.comment         </td>
         <td>“”         </td>
         <td>User comment that describes the class-of-service         </td>
      </tr>
      <tr>
         <td>uconf:cft.server.bandwidth.cos         </td>
         <td>1         </td>
         <td>Total number of class-of-services including the
class number zero.         </td>
      </tr>
   </tbody>
</table>

### Global parameters

<table>
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Parameter         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Default         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>uconf:cft.server.bandwidth.enable         </td>
         <td>No         </td>
         <td>Enable bandwidth control feature         </td>
      </tr>
      <tr>
         <td>uconf:cft.server.bandwidth.cos_server_default         </td>
         <td>0         </td>
         <td>Set default class-of-service in server mode         </td>
      </tr>
      <tr>
         <td>uconf:cft.server.bandwidth.cos_requester_default         </td>
         <td>0         </td>
         <td>Set default class-of-service in requester mode         </td>
      </tr>
   </tbody>
</table>

### Expert level global parameters

<table>
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Parameter         </th>
<th style="text-align: center;" class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Default         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>uconf:cft.server.bandwidth.delay         </td>
         <td>1s         </td>
         <td>Bandwidth control granularity (this value is expressed in microseconds, so for example 1s = 1000000 ms).         </td>
      </tr>
      <tr>
         <td>uconf:cft.server.bandwidth.smoothing_factor         </td>
         <td>3         </td>
         <td>The bandwidth smoothing parameter optimizes resources to flatten, or smooth, bandwidth usage. Values range from 1 to 10, where 1 is the smoothest and 10 may result in irregular bandwidth usage.         </td>
      </tr>
   </tbody>
</table>

<span id="Concepts"></span>

## Class-of-service concepts

-   The class of service “0” is directly or indirectly the parent of all others.
-   A rate (max\_rate, ...) or weight (weight\_in, weight\_out) that is not configured or set to -1 indicates an unlimited rate.

<!-- -->

-   The class-of-service used by default is:
    -   uconf:cft.server.bandwidth.cos\_requester\_default for connection in requester mode
    -   uconf:cft.server.bandwidth.cos\_server\_default for connection in server mode
-   The class-of-service rate is decreased to max\_rate if needed.
-   The class-of-service rate when there are no siblings is set to the max\_rate.

### Borrowing bandwidth from other class-of-service

Typically a class-of-service does not use more than its own rate. However when a class-of-service is not used (has no active sessions), class-of-service siblings can borrow available bandwidth up to their own max-rate. This is referred to as passive borrowing. The bandwidth is obtained proportionally to its own rate against siblings:

-   Rate-borrowed = (sum(sibling-rate) - sum(active-sibling-rate)) \*rate/sum(active-sibling-rate) + rate

## Class-of-service prioritization

Bandwidth prioritization can be obtained provided some requirements:

-   The bandwidth configured is supposed to be reachable.
-   The class-of-service with the highest priority is defined with the highest bandwidth.
-   Reduce DISCTD/DISCTS to allow aggressive passive borrowing.

While technically you can assign a class-of-service that has children to file transfers, we recommend against implementing this configuration. In this case the total rate of the class-of-service value is available to both the transfers using this class as well as to the transfers using the child classes. As such, you cannot guarantee the nominal data rate for both the transfers using the parent class and those using the child classes.

When defining a class-of-service it is recommended that you configure as follows for a class "leaf" that has no children.

-   Server mode: the configured default class-of-service is a "leaf"
-   Requester mode: the configured default class-of-service is a "leaf"
-   File transfers: a "leaf" class-of-service is used

### Nominal data rate

For each direction of data, the maximum rate configured for class 0 and the corresponding configured weights for other classes are used to compute a nominal data rate for all classes, as follows:

-   The nominal data rate of class 0 is set to the configured maximum rate.
-   Each class different from class 0 is given a nominal data rate proportional to its configured weight.
-   The nominal data rate of any class is equal to the sum of the nominal data of its child classes.

Note that:

-   Weights that are not configured (unlimited) are not taken into account in the computation of nominal data rates.

<!-- -->

-   If a class has an unlimited nominal data rate for a given data direction, the corresponding data rate of its child classes are also unlimited, regardless any configured weight value for these child classes.

For each direction, the nominal data rates represent guaranteed data rates, so long that the corresponding maximum data rate configured for class 0 is available to the product.

#### Recommendations

While technically you can assign a class-of-service that has children to file transfers, we recommend against implementing this configuration. In this configuration the total rate of the class-of-service value is available to both the transfers using this class, as well as to the transfers using the child classes. This means that you cannot guarantee the nominal data rate for both the transfers using the parent class and those using the child classes.

When defining a class-of-service it is recommended that you configure as follows for a class "leaf" that has no children.

-   Server mode: the configured default class-of-service is a "leaf"
-   Requester mode: the configured default class-of-service is a "leaf"
-   File transfers: a "leaf" class-of-service is used

Related topics

-   [Managing bandwidth](t_bandwidth)
-   [Bandwidth control use cases](r_use_cases_bandwidth)
