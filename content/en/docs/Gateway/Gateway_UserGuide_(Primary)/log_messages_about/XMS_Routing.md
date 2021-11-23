{
    "title": "Axway Messaging connector routing (XMSC)",
    "linkTitle": "Messaging connector routing (XMSC)",
    "weight": "290"
}{{< Gateway/componentlongname  >}}: Messages and codes

This topic lists the log messages for the Axway Messaging connector routing. The general format for these messages is a text message.

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="XMSC001E"></span>001</p>         </td>
         <td><p>XMSC  E PROP  list properties selected, name:%1 not found</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Property List was not found in the Rule Table.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Property List name</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check that the Property List name entered in the Rule Table exists.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="XMSC002E"></span>002</p>         </td>
         <td><p>XMSC  E CONN  error of connection to XMS:%1 %2</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Error connecting to Axway Messaging.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Error code</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Error message</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check that Axway Messaging is started.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="XMSC003I"></span>003</p>         </td>
         <td><p>XMSC  I CONN  connection to XMS established</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>A connection to Axway Messaging was established.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>None</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="XMSC004E"></span>004</p>         </td>
         <td><p>XMSC  E CONN  error of disconnection to XMS:%1 %2</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Error disconnecting from Axway Messaging.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Error code</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Error message</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check that the Axway Messaging has not stopped.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="XMSC005I"></span>005</p>         </td>
         <td><p>XMSC  I CONN  connection to XMS finished</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Connection to Axway Messaging is successfully completed.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>None</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="XMSC006E"></span>006</p>         </td>
         <td><p>XMSC  E MSG  error to get XMS message:%1 %2</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Error retrieving an Axway Messaging message.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Code error</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Error message</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check the following error message sent by Axway Messaging.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="XMSC007E"></span>007</p>         </td>
         <td><p>XMSC  E MSG  error: the type of XMS message (%1) is not XMS_DATA_TYPE</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The type of message recuperated is not the XMS_DATA_TYPE</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Message ID</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check to see why a message of a different type arrived in the queue to be processed by the Axway Messaging connector.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="XMSC008E"></span>008</p>         </td>
         <td><p>XMSC  E ALLOC  allocation error for: %1</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Memory allocation error occurred</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Allocation field name</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="XMSC009E"></span>009</p>         </td>
         <td><p>XMSC  E FILE  file already exist: %1</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>File already exists</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>File name</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Delete or move the file in the receiving directory.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="XMSC010E"></span>010</p>         </td>
         <td><p>XMSC  E FILE  can't create file: %1</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Impossible to create a file</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>File name</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check the <em>write</em> rights or check for adequate disc space.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="XMSC011E"></span>011</p>         </td>
         <td><p>XMSC  E PROP  error property "%1" not found in XMS message(%2 %3)</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Message property not found</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Name of property</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Code error</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Error message</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check that the application that is sending the message is informed of the missing property.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="XMSC012E"></span>012</p>         </td>
         <td><p>XMSC  E PROP  error type of property "%1"</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Property type is incorrect</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Property type</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>You must either modify the property type in the Property List declaration, or modify the type in the sent message.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="XMSC013E"></span>013</p>         </td>
         <td><p>XMSC  E FUNCT  error in function: %1</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>A function error occurred</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Name of the function</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="XMSC014E"></span>014</p>         </td>
         <td><p>XMSC  E CONN  can't connect to Gateway</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Impossible to connect to Gateway</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>None</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check that Gateway is started.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="XMSC015I"></span>015</p>         </td>
         <td><p>XMSC  I CONN  connected to Gateway</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The connection to Gateway was successful</p>         </td>
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
         <td><p><span id="XMSC016E"></span>016</p>         </td>
         <td><p>XMSC  E TRANS  error to put a transfer: %1 %2</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Error occurred while attempting to complete a transfer</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Error code</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Message error</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Action in accordance with the error message.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="XMSC017I"></span>017</p>         </td>
         <td><p>XMSC  I TRANS  deposit of transfer %1</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Transfer send was successful</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Local identifier for transfer</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="XMSC018E"></span>018</p>         </td>
         <td><p>XMSC  E MSG  error to commit XMS message %1: %2 %3</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Impossible to commit the Axway Messaging session.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Message ID</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Error code</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Error message</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Action in accordance with the error message.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="XMSC019E"></span>019</p>         </td>
         <td><p>XMSC  E TRANS  XferGet(%1) error: %2[%3]</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>An error occurred recuperating a transfer</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Transfer ID</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Error code</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Error message</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Action in accordance with the error message.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="XMSC020E"></span>020</p>         </td>
         <td><p>XMSC  E TRANS  XferUpdate failed: id(%1), state(%2), rc(%3) [%4]</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Error updating a transfer</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Transfer ID</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Transfer status</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Error code</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Error message</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check that the transfer with this ID is still in the Gateway Mailbox.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="XMSC021I"></span>021</p>         </td>
         <td><p>XMSC  I TRANS  XferUpdate: id(%1), state(%2)</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Transfer update successful</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Transfer ID</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Transfer status</p>         </td>
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
         <td><p><span id="XMSC022E"></span>022</p>         </td>
         <td><p>XMSC  E MSG  send message %1 failed: %2 %3</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Error sending an Axway Messaging message.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Message ID</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Error code</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Error message</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Action in accordance with the error message.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="XMSC023E"></span>023</p>         </td>
         <td><p>XMSC  E RULE  RuleTable with XmsCtor name "%1" not found</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Rule Table with this connector name was not found.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Axway Messaging connector name</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check that a Rule Table with this connector name exists.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="XMSC024E"></span>024</p>         </td>
         <td><p>XMSC  E RULE  they are too many RuleTables with XmsCtor name "%1"</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>There are several (more than one) Rule Tables with this connector name.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Axway Messaging connector name</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Delete or modify the Rule Table so that there is only one with this name.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="XMSC025E"></span>025</p>         </td>
         <td><p>XMSC  E MSG  error to put a message error : %1 %2</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Error depositing message</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Error code</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Message code</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Action in accordance with the error message.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="XMSC026E"></span>026</p>         </td>
         <td><p>XMSC  E MSG  error, Xms messageID null</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="XMSC027E"></span>027</p>         </td>
         <td><p>XMSC  E MSG  put the message %1 in backup file "%2"</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Put the message in queue</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Message ID</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Queue name</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="XMSC028E"></span>028</p>         </td>
         <td><p>XMSC  E MSG  error to put the backup message %1 in "%2": %3 %4</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Error occurred putting message in queue.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Message ID</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Queue name</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Error code</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Message code</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Action in accordance with the error message.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="XMSC029I"></span>029</p>         </td>
         <td><p>XMSC  I CONN  connect to queue :%1</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Gateway has connected to Axway Messaging queue.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Axway Messaging queue name</p>         </td>
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
         <td><p><span id="XMSC030E"></span>030</p>         </td>
         <td><p>XMSC  E MSG  can't sent an error message because the replyToQmgr field in the header is empty</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The <em>replyToQmgr</em> field in the header of the message to be processed is empty.</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Configure the message headers.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="XMSC031E"></span>031</p>         </td>
         <td><p>XMSC  E MSG  can't sent an error message because the replyToQueue field in the header is empty</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The <em>replyToQmgr</em> field in the header of the message to be processed is empty.</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Configure the message headers.</p>         </td>
      </tr>
   </tbody>
</table>

 

Links to documentation set for Axway Gateway {{< Gateway/releasenumber  >}}:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
