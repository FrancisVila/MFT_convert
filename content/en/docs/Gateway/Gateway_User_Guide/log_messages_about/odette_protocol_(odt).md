{
    "title": "OFTP protocol log messages (ODT)",
    "linkTitle": "OFTP Odette (ODT)",
    "weight": "330"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Messages and codes

This topic lists OFTP log messages.

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="ODT100E"></span>100</p>         </td>
         <td><p><span style="font-weight: bold;">ODT E ERROR %1(%2) %3</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>An error condition has been detected. This message is used to report system errors (Input/Output, memory, and network) or errors that cannot be explained by the protocol diagnostic code set.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local number of the transfer (0 if not available)</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Error text</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>For system errors, refer to your platform documentation. For other errors, check protocol or application parameters.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="ODT101I"></span>101</p>         </td>
         <td><p>ODT I TRACE %1</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Use this message to trace OFTP protocol data units sent to the Remote Site. The FPDU can be traced in text mode (field name and value) and/or in dump mode (hexadecimal and ASCII code).</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Protocol Data Unit (PDU)</p>         </td>
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
         <td><p><span id="ODT200I"></span>200</p>         </td>
         <td><p><span style="font-weight: bold;">ODT I CONN_REQ %1(%2) connection established with %3</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The protocol and physical connection on the requester side have been established.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local Site name</p>         </td>
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
         <td><p><span id="ODT201I"></span>201</p>         </td>
         <td><p><span style="font-weight: bold;">ODT I CONN_IND %1(%2) connection established with %3"</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The protocol and physical connection on the requester side have been established.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local Site name</p>         </td>
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
         <td><p><span id="ODT202I"></span>202</p>         </td>
         <td><p><span style="font-weight: bold;">ODT I SEND_REQ %1(%2) [%3] beginning of transmission, file name:%4, date:%5, time:%6</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Indicates on the sender side the beginning of the file transmission. This message comprises two lines.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>OFTP file data set name</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Transfer Request creation date</p>         </td>
      </tr>
      <tr>
         <td><p>6</p>         </td>
         <td><p>Transfer Request creation time</p>         </td>
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
         <td><p><span id="ODT203I"></span>203</p>         </td>
         <td><p><span style="font-weight: bold;">ODT I SEND_REQ %1(%2) [%3] beginning of transmission from %4, file: %5</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Indicates on the sender side the beginning of the file transmission. This message comprises two lines.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>OFTP file data set name</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Local Site name</p>         </td>
      </tr>
      <tr>
         <td><p>6</p>         </td>
         <td><p>File name in file-system</p>         </td>
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
         <td><p><span id="ODT204I"></span>204</p>         </td>
         <td><p><span style="font-weight: bold;">ODT I XEND_SND %1(%2) [%3] end of transmission, file name: %4, date: %5, time: %6</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Indicates on the sender side the end of the file transmission. This message comprises two lines.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>OFTP file data set name</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Transfer Request creation date</p>         </td>
      </tr>
      <tr>
         <td><p>6</p>         </td>
         <td><p>Transfer Request creation time</p>         </td>
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
         <td><p><span id="ODT205I"></span>205</p>         </td>
         <td><p><span style="font-weight: bold;">ODT I XEND_SND %1(%2) [%3] end of transmission from%4, file: %5</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Indicates on the sender side the end of the file transmission. This message comprises two lines.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Local Site name</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>File name in file-system</p>         </td>
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
         <td><p><span id="ODT206W"></span>206</p>         </td>
         <td><p><span style="font-weight: bold;">ODT W XERR_SND %1(%2) [%3] error of transmission, file name: %4, date: %5, time: %6</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Indicates on the requester side an error during the file transmission. This message comprises three lines.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>OFTP file data set name</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Transfer Request creation date</p>         </td>
      </tr>
      <tr>
         <td><p>6</p>         </td>
         <td><p>Transfer Request creation time</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check protocol or application parameters and file-system free space.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="ODT207W"></span>207</p>         </td>
         <td><p><span style="font-weight: bold;">ODT W XERR_SND %1(%2) [%3] error of transmission from %4, file: %5</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Indicates on the requester side an error during the file transmission. This message comprises three lines.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Local Site name</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>File name in file-system</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check protocol or application parameters and file-system free space.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="ODT208W"></span>208</p>         </td>
         <td><p><span style="font-weight: bold;">ODT W XERR_SND %1(%2) [%3] error of transmission [reason=%4]</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Indicates on the requester side an error during the file transmission. This message comprises three lines.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Reason for error in text and decimal code</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check protocol or application parameters and file-system free space.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="ODT209I"></span>209</p>         </td>
         <td><p><span style="font-weight: bold;">ODT I RECV_REQ %1(%2) [%3] begin of reception, file name:%4, date:%5, time:%6</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Indicates on the receiver side the beginning of the file transmission. This message comprises two lines.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>OFTP file data set name</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Transfer Request creation date</p>         </td>
      </tr>
      <tr>
         <td><p>6</p>         </td>
         <td><p>Transfer Request creation time</p>         </td>
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
         <td><p><span id="ODT210I"></span>210</p>         </td>
         <td><p><span style="font-weight: bold;">ODT I RECV_REQ %1(%2) [%3] begin of reception for %4, file: %5</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Indicates on the receiver side the beginning of the file transmission. This message comprises two lines.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Local Site name</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>File name in file-system</p>         </td>
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
         <td><p><span id="ODT211I"></span>211</p>         </td>
         <td><p><span style="font-weight: bold;">ODT I XEND_RCV %1(%2) [%3] end of reception, file name:%4, date:%5, time:%6</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Indicates on the receiver side the end of the file transmission. This message comprises two lines.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>OFTP file data set name</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Transfer Request creation date</p>         </td>
      </tr>
      <tr>
         <td><p>6</p>         </td>
         <td><p>Transfer Request creation time</p>         </td>
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
         <td><p><span id="ODT212I"></span>212</p>         </td>
         <td><p><span style="font-weight: bold;">ODT I XEND_RCV %1(%2) [%3] end of reception for %4, file: %5</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Indicates on the receiver side the end of the file transmission. This message comprises two lines.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Local Site name</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>File name in file-system</p>         </td>
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
         <td><p><span id="ODT213W"></span>213</p>         </td>
         <td><p><span style="font-weight: bold;">ODT W XERR_RCV %1(%2) [%3] error of reception, file name: %4, date:%5, time:%6</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Indicates on the receiver side an error during the file transmission. This message comprises three lines.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>OFTP file data set name</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Transfer Request creation date</p>         </td>
      </tr>
      <tr>
         <td><p>6</p>         </td>
         <td><p>Transfer Request creation time</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check protocol or application parameters and file-system free space.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="ODT214W"></span>214</p>         </td>
         <td><p><span style="font-weight: bold;">ODT W XERR_RCV %1(%2) [%3] error of reception for %4, file: %5</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Indicates on the receiver side an error during the file transmission. This message comprises three lines.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Local Site name</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>File name in file-system</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check protocol or application parameters and file-system free space.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="ODT215W"></span>215</p>         </td>
         <td><p><span style="font-weight: bold;">ODT W XERR_RCV %1(%2) [%3] error of reception [reason="%4"]</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Indicates on the receiver side an error during the file transmission. This message comprises three lines.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Reason for error in text and decimal code</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check protocol or application parameters and file-system free space.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="ODT216I"></span>216</p>         </td>
         <td><p><span style="font-weight: bold;">ODT I DISC_REQ %1(%2) disconnect request send by %3 [reason="%4"]</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The protocol and physical connection on the speaker side have been closed.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local Site name</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Reason for disconnection in text and decimal code</p>         </td>
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
         <td><p><span id="ODT217I"></span>217</p>         </td>
         <td><p><span style="font-weight: bold;">ODT I DISC_IND %1(%2) disconnect request received for %3 [reason="%4"]</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The protocol and physical connection on the listener side have been closed.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local Site name</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Reason for disconnection in text and decimal code</p>         </td>
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
         <td><p><span id="ODT218I"></span>218</p>         </td>
         <td><p><span style="font-weight: bold;">ODT I XACK_REQ %1(%2) [%3] send file acknowledge, file name:%4, date:%5, time:%6</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Indicates on the sender side that an acknowledgment for a previously-received file has been sent. This message comprises two lines.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>OFTP file data set name</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Transfer Request creation date</p>         </td>
      </tr>
      <tr>
         <td><p>6</p>         </td>
         <td><p>Transfer Request creation time</p>         </td>
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
         <td><p><span id="ODT219I"></span>219</p>         </td>
         <td><p><span style="font-weight: bold;">ODT I XACK_REQ %1(%2) [%3] send file acknowledge from %4</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Indicates on the sender side that an acknowledgment for a previously-received file has been sent. This message comprises two lines.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Local Site name</p>         </td>
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
         <td><p><span id="ODT220I"></span>220</p>         </td>
         <td><p><span style="font-weight: bold;">ODT I XACK_IND %1(%2) [%3] receive file acknowledge, file name:%4, date:%5, time:%6</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Indicates on the receiver side that an acknowledgment for a previously sent file has been received. This message comprises two lines.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>OFTP file data set name</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Transfer Request creation date</p>         </td>
      </tr>
      <tr>
         <td><p>6</p>         </td>
         <td><p>Transfer Request creation time</p>         </td>
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
         <td><p><span id="ODT221I"></span>221</p>         </td>
         <td><p><span style="font-weight: bold;">ODT I XACK_IND %1(%2) [%3] receive file acknowledge for %4</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Indicates on the receiver side that an acknowledgment for a previously-sent file has been received. This message comprises two lines.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Local Site name</p>         </td>
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
         <td><p><span id="ODT222I"></span>222</p>         </td>
         <td><p><span style="font-weight: bold;">ODT I CHDR_REQ %1(%2) change direction send by "%3"</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Indicates on the sender side that a Change Direction request has been sent.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local Site name</p>         </td>
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
         <td><p><span id="ODT223I"></span>223</p>         </td>
         <td><p><span style="font-weight: bold;">ODT I CHDR_IND %1(%2) change direction recv for %3</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Indicates on the receiver side that a Change Direction request has been received.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local Site name</p>         </td>
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
         <td><p><span id="ODT224I"></span>224</p>         </td>
         <td><p><span style="font-weight: bold;">ODT I XRSF_REQ %1(%2) [%3] restart of transmission at record:%4</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Indicates the restart record number on the sender side.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Record number</p>         </td>
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
         <td><p><span id="ODT225I"></span>225</p>         </td>
         <td><p><span style="font-weight: bold;">ODT I XRRF_IND %1(%2) [%3] restart of reception at record:%4</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Indicates the restart record number on the receiver side.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Record number</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>None</p>         </td>
      </tr>
   </tbody>
</table>

Related topics

[About messages and codes](../)

[About OFTP](../../protocols_about/oftp_about)

<a href="../../protocols_about/oftp_about/oftp_monitoring_transfer" class="MCXref xref">Monitoring an OFTP transfer</a>

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
