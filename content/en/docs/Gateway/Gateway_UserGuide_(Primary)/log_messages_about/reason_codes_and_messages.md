{
    "title": "Reason codes and messages",
    "linkTitle": "Reason Codes and Messages",
    "weight": "390"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Messages and codes

This topic lists reason codes and messages.

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;">000</span></p>         </td>
         <td><p>No error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>No error</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>None</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;">005</span></p>         </td>
         <td><p>No space left for an initiator connection</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>A connection attempt in initiator mode is refused due to max number of connections reached.</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Increase max number of connections or wait until connections free.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;">006</span></p>         </td>
         <td><p>No space left for an responder connection</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>A connection attempt in responder mode is refused due to max number of connections reached.</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Increase max number of connections or wait until connections free.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;">007</span></p>         </td>
         <td><p>Initiator mode not allowed</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Site is not configured for initiator mode capabilities.</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Change Site configuration.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;">008</span></p>         </td>
         <td><p>Responder mode not allowed</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Site is not configured for responder mode capabilities.</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Change Site configuration.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;">009</span></p>         </td>
         <td><p>Initiator/sender mode not allowed</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Site is not configured for initiator/sender mode capabilities.</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Change Site configuration.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;">010</span></p>         </td>
         <td><p>Responder/sender mode not allowed</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Site is not configured for responder/sender mode capabilities.</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Change Site configuration.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;">011</span></p>         </td>
         <td><p>Initiator/receiver mode not allowed</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Site is not configured for initiator/receiver mode capabilities.</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Change Site configuration.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;">012</span></p>         </td>
         <td><p>Responder/receiver mode not allowed</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Site is not configured for responder/receiver mode capabilities.</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Change Site configuration.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;">013</span></p>         </td>
         <td><p>Invalid local identifier</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The destination Site declared in the transfer is not accepted by Gateway.</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check configuration (local Sites, CGates, exits).</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;">014</span></p>         </td>
         <td><p>Invalid remote identifier</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The origin Site declared in the transfer is not accepted by Gateway.</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check configuration (Sites, CGates, exits).</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;">017</span></p>         </td>
         <td><p>Data base access error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>An access to a Gateway object has failed.</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Retry operation. Check that object has not been removed from the database.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;">165</span></p>         </td>
         <td><p>Transfer failure</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>A failure occurs during the transfer phase.</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check log for more information.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;">166</span></p>         </td>
         <td><p>Connection failure</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>A connection failure has occurred.</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check log for more information.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;">190</span></p>         </td>
         <td><p>EDI processing error %1</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>An error in EDI processing occurs.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameter</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Text message describing the EDI processing error</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Action depends on displayed text message.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p>191</p>         </td>
         <td><p>EDI process abnormal exit</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Process terminated in error.</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check log for more information.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;">195</span></p>         </td>
         <td><p>TPM connector processing error %1</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>An error in PassPort connector processing has occurred.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameter</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Text message describing the PassPort processing error</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Action depends on displayed text message.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;">196</span></p>         </td>
         <td><strong>Integrity processing error</strong>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td>The transfer was canceled by the data or payload integrity helper         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check log and last_end_diag parameter of the transfer for more information.</p>         </td>
      </tr>
   </tbody>
</table>

 

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
