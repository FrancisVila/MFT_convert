{
    "title": "X.400 (X420) log messages",
    "linkTitle": "X.400 (X420)",
    "weight": "560"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Messages and codes

This topic lists X.400 log messages.

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="X420001S"></span>001</p>         </td>
         <td><p>X420  S TRACE  TRACE from %1: %2</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Success</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Generic trace.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Location in the program</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Trace message</p>         </td>
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
         <td><p><span id="X420002I"></span>002</p>         </td>
         <td><p>X420  I INITING  X420 initializing (Port=%1, Host=%2, Password=%3)</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Information message indicating the connection of the X.420 message transfer connector to the local X.420 UA.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>TCP port</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>TCP address</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Password</p>         </td>
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
         <td><p><span id="X420003I"></span>003</p>         </td>
         <td><p>X420  I INITOK  X420 initialization OK</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Information message indicating the successful initialization of the X.420 connector.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>None</p>         </td>
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
         <td><p><span id="X420011I"></span>011</p>         </td>
         <td><p>X420  I MSGRCVD  MSG received - originator_alias=%1 recipient_alias=%2 content_id=%3 ipm_urid=%4 ua_rn_id=%5</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Information message indicating the reception of a message from the local UA.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Originator</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Recipient</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Message content identifier</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>IPM User ID</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>UA receipt notification</p>         </td>
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
         <td><p><span id="X420012I"></span>012</p>         </td>
         <td><p>X420  I MSGSNDING  Sending MSG - originator_alias=%1 recipient_alias=%2 content_id=%3 ipm_urid=%4</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Information message indicating the transmission of a message to the local UA.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Originator</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Recipient</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Message content identifier</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>IPM User ID</p>         </td>
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
         <td><p><span id="X420014I"></span>014</p>         </td>
         <td><p>X420  I MSGSENT  MSG sent - content_id=%1 size=%2 total time=%3</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Information message indicating the of transmission of a message to the local UA.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Message content identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Number of byte transferred</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Total transfer time in hundreds of seconds</p>         </td>
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
         <td><p><span id="X420015I"></span>015</p>         </td>
         <td><p>X420  I DNRCVD  DN received - recipient_alias=%1 content_id=%2</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Information message indicating the reception of a delivery notification.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Recipient</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Message content identifier</p>         </td>
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
         <td><p><span id="X420016I"></span>016</p>         </td>
         <td><p>X420  I NDNRCVD  NDN received - recipient_alias=%1 content_id=%2</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Information message indicating the reception of a non-delivery notification.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Recipient</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Message content identifier</p>         </td>
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
         <td><p><span id="X420017I"></span>017</p>         </td>
         <td><p>X420  I RNRCVD  RN received - originator_alias=%1 recipient_alias=%2 ipm_urid=%3</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Information message indicating the reception of a receipt notification.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Originator</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Recipient</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>IPM User ID</p>         </td>
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
         <td><p><span id="X420018I"></span>018</p>         </td>
         <td><p>X420  I NRNRCVD  NRN received - originator_alias=%1 recipient_alias=%2 ipm_urid=%3</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Information message indicating the reception of a non-receipt notification.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Originator</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Recipient</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>IPM User ID</p>         </td>
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
         <td><p><span id="X420019I"></span>019</p>         </td>
         <td><p>X420  I RNSNDING  Sending RN - content_id=%1 ua_rn_id=%2</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Information message indicating the transmission of a receipt notification.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Message content identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>UA receipt notification ID</p>         </td>
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
         <td><p><span id="X420020I"></span>020</p>         </td>
         <td><p>X420  I NRNSNDING  Sending NRN - content_id=%1 ua_rn_id=%2</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Information message indicating the transmission of a non-receipt notification.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Message content identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>UA receipt notification ID</p>         </td>
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
         <td><p><span id="X420021I"></span>021</p>         </td>
         <td><p>X420  I NORSNDING  Sending NOR - ua_rn_id=%1</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Information message indicating the transmission of no receipt notification.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>UA receipt notification ID</p>         </td>
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
         <td><p><span id="X420051I"></span>051</p>         </td>
         <td><p>X420  I XFERCREA  %2 [%1] Inbound transfer created - destination=%3 file=%4</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Information message indicating the creation of an incoming transfer.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Local request identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Identification of the sender</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Identification of the receiver</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Local file name</p>         </td>
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
         <td><p><span id="X420052I"></span>052</p>         </td>
         <td><p>X420  I XFERSTART  %2 [%1] Outbound transfer starting - originator=%3 file=%4</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Information message indicating the creation of an outgoing transfer.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Local request identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Identification of the receiver</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Identification of the sender</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Local file name</p>         </td>
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
         <td><p><span id="X420054I"></span>054</p>         </td>
         <td><p>X420  I XFERSENT  %2 [%1] Outbound transfer sent - originator=%3 file=%4</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Information message indicating the successful end of an outgoing transfer</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Local request identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Identification of the receiver</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Identification of the sender</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Local file name</p>         </td>
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
         <td><p><span id="X420057I"></span>057</p>         </td>
         <td><p>X420  I XRNCREA  %2 [%1] Inbound RN created - destination=%3</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Information message indicating the creation of an incoming receipt notification.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Local request identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Identification of the sender</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Identification of the receiver</p>         </td>
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
         <td><p><span id="X420058I"></span>058</p>         </td>
         <td><p>X420  I XNRNCREA  %2 [%1] Inbound NRN created - destination=%3</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Information message indicating the creation of an incoming non-receipt notification.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Local request identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Identification of the sender</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Identification of the receiver</p>         </td>
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
         <td><p><span id="X420059I"></span>059</p>         </td>
         <td><p>X420  I XRNSTART  %2 [%1] Outbound RN starting - originator=%3</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Information message indicating the creation of an outgoing receipt notification.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Local request identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Identification of the receiver</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Identification of the sender</p>         </td>
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
         <td><p><span id="X420060I"></span>060</p>         </td>
         <td><p>X420  I XNRNSTART  %2 [%1] Outbound NRN starting - originator=%3</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Information message indicating the creation of an outgoing non-receipt notification.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Local request identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Identification of the receiver</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Identification of the sender</p>         </td>
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
         <td><p><span id="X420061I"></span>061</p>         </td>
         <td><p>X420  I XNORSTART  %2 [%1] Outbound NORN starting - originator=%3</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Information message indicating the creation of an outgoing no receipt notification.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Local request identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Identification of the receiver</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Identification of the sender</p>         </td>
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
         <td><p><span id="X420062I"></span>062</p>         </td>
         <td><p>X420  I XRNSENT  %2 [%1] Outbound RN sent - originator=%3</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Information message indicating the successful end of an outgoing receipt notification.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Local request identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Identification of the receiver</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Identification of the sender</p>         </td>
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
         <td><p><span id="X420063I"></span>063</p>         </td>
         <td><p>X420  I XNRNSENT  %2 [%1] Outbound NRN sent - originator=%3</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Information message indicating the successful end of an outgoing non-receipt notification.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Local request identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Identification of the receiver</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Identification of the sender</p>         </td>
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
         <td><p><span id="X420101E"></span>101</p>         </td>
         <td><p>X420  E ERROR  ERROR from %1: %2</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Generic error message.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Location in the program</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Error message</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>The error message, further log message and trace should hint about the issue.</p>
<p>If you cannot resolve the problem, contact Axway Support and provide them with the information from the log message.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="X420102E"></span>102</p>         </td>
         <td><p>X420  E INITFAIL  X420 initialization failed</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The X.420 connector failed to initialize.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>None</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check associated log messages, traces and configuration.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="X420201S"></span>201</p>         </td>
         <td><p>X400  S TRACE     TRACE from %1: %2</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Success</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Generic product trace.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Location in the program</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Trace message</p>         </td>
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
         <td><p><span id="X420202I"></span>202</p>         </td>
         <td><p>X400  I INITING  X400 Configuration Updater initializing...</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The configuration update process is being initialized.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>None</p>         </td>
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
         <td><p><span id="X420203I"></span>203</p>         </td>
         <td><p>X400  I INITOK  X400 Configuration Updater initialization OK</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The configuration update process has been initialized.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>None</p>         </td>
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
         <td><p><span id="X420204S"></span>204</p>         </td>
         <td><p>X400  S CNFGENER  X400 Configuration generation success to file : %1</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Success</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>A specific configuration file has been generated successfully.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Local configuration file</p>         </td>
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
         <td><p><span id="X420205I"></span>205</p>         </td>
         <td><p>X400  I CNFGENER  X400 Configuration generation success</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>A new configuration has been generated successfully.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>None</p>         </td>
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
         <td><p><span id="X420302E"></span>302</p>         </td>
         <td><p>X400  E INITFAIL  X400 Configuration Updater initialization failed</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The configuration update process failed to initialize.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>None</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check associated log messages, traces and configuration.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="X420303W"></span>303</p>         </td>
         <td><p>X400  W CNFMSIGN  [%1] %2 : Ignored, pointed by no local user</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The MSP7 entry is pointed to by no local user. Therefore it is ignored.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Item type: MSP7</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Item name</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Create or update a local user entry to point to that item. Delete the MSP7 entry if it is not used.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="X420304E"></span>304</p>         </td>
         <td><p>X400  E CNFGEERR  X400 Configuration generation failed to file : %1</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>An X.400 configuration file could not be generated.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Local configuration file</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check file permissions.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="X420305W"></span>305</p>         </td>
         <td><p>X400  W CNFUSMTA  [%1] %2 : Pointing to non existing MTA %3</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The MTA entry set in the remote user definition does not exist.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Item type: Remote User</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Item name</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>MTA name</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Change the MTA value in the remote user settings or create an MTA entry whose name matches the setting.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="X420306E"></span>306</p>         </td>
         <td><p>X400  E CNFUSMS7  [%1] %2 : Pointing to non existing MSP7 %3</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The MSP7 entry set in the local user definition does not exist.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Item type : Remote User</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Item name</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>MSP7 name</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Change the MSP7 value in the local user settings or create an MSP7 entry whose name matches the setting.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="X420307E"></span>307</p>         </td>
         <td><p>X400  E CNFCLMTA  [%1] %2 : Local MTA is not configured</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The local MTA is not set in the configuration.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Item type: Configuration</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Item name</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Configure the local MTA.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="X420308E"></span>308</p>         </td>
         <td><p>X400  E CNFCDMTA  [%1] %2 : Invalid DEFAULT_MTA_NAME = %3</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The default MTA value located in the configuration does not point to an existing MTA.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Item type: Configuration</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Item name</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>MTA name</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Change the default MTA value in the configuration or create an MTA entry whose name matches the setting.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="X420309E"></span>309</p>         </td>
         <td><p>X400  E CNFUSLOC [%1] %2 : No local X420 user defined</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>No local X.420 user has been found.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Item type: User</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Item name</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Create an X.420 local user or turn a remote user into local.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="X420311E"></span>311</p>         </td>
         <td><p>X400  E CHKINVEN [%1] %2 : Check failed. Invalid entry %3 = %4</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>An item contains an entry which value has been checked as not being valid.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Item type: Configuration, MTA, MSP7 or User</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Item name</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Entry</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Entry value</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Fix the specific value.</p>         </td>
      </tr>
   </tbody>
</table>

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
