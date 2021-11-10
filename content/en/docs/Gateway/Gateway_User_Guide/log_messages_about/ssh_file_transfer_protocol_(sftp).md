{
    "title": "SSH File Transfer Protocol (SFTP)",
    "linkTitle": "SSH File Transfer Protocol (SFTP)",
    "weight": "460"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Messages and codes

This topic lists SFTP log messages.

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SFTP001E"></span>001</p>         </td>
         <td><p><span style="font-weight: bold;">SFTP E SELOPERR %1(%2) [%3] select-open error, file %4/%5: %6</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Error on the file selection or open operations. The local file system error is returned in parameter %6</p>         </td>
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
         <td><p>Local request identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Access path to the file</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>File name</p>         </td>
      </tr>
      <tr>
         <td><p>6</p>         </td>
         <td><p>Local file system diagnostic</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check the parameters of the transfer request and of the Application used for the compatibility of the file characteristics with the file system attributes referenced by the transfer. Check the access security and path to make sure that Gateway can access the file. If a system dependent parameter is requested for file access, you must check that the request contains its description.</p>
<p>Refer to your platform documentation to understand the local file system error.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SFTP002E"></span>002</p>         </td>
         <td><p><span style="font-weight: bold;">SFTP E CREOPERR %1(%2) [%3] create-open error, file %4/%5: %6</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Error on the file creation or open operations for incoming file transmission. The local file system error is returned in parameter %6</p>         </td>
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
         <td><p>Local request identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Access path to the file</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>File name</p>         </td>
      </tr>
      <tr>
         <td><p>6</p>         </td>
         <td><p>Local file system diagnostic</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check the parameters of the Application used and make sure that the file system attributes are consistent. Gateway must have the <span style="font-style: italic;">write</span> privilege in the directory defined (in the Application) for the creation of the files in reception. If a system dependent parameter is requested for file access, you must make sure that it is used. You must have enough space on your disk to receive the file.</p>
<p>Refer to your platform documentation to understand the local file system error.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SFTP003E"></span>003</p>         </td>
         <td><p><span style="font-weight: bold;">SFTP E OPENDERR %1(%2) opendir error, directory %3 : /%4</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Error on the directory opening operation. The local file system error is returned in parameter %4</p>         </td>
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
         <td><p>Directory name</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Local file system diagnostic</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Refer to your platform documentation to understand the local file system error. Check the parameters of the transfer request and of the Application used for the compatibility of the directory characteristics with the file system attributes referenced by the transfer.</p>
<p>Check the access security and path to make sure that Gateway can access the directory. If a system dependent parameter is requested for directory access, you must check that the request contains its description.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SFTP004E"></span>004</p>         </td>
         <td><p><span style="font-weight: bold;">SFTP E CLOSDERR %1(%2) closedir error, directory %3 : %4</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Error on the file closing operation. The local file system error is returned in parameter %4</p>         </td>
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
         <td><p>Directory name</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Local file system diagnostic</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Refer to your platform documentation to understand the local file system error.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SFTP005E"></span>005</p>         </td>
         <td><p><span style="font-weight: bold;">SFTP E CLODSERR %1(%2) [%3] close-deselect error, file %4/%5: %6</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Error on the file closing or de-selection operations. The local file system error is returned in parameter %6</p>         </td>
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
         <td><p>Local request identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Access path to the file</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>File name</p>         </td>
      </tr>
      <tr>
         <td><p>6</p>         </td>
         <td><p>Local file system diagnostic</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Refer to your platform documentation to understand the local file system error.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SFTP006E"></span>006</p>         </td>
         <td><p><span style="font-weight: bold;">SFTP E READ_ERR %1(%2) [%3] read error, file %4/%5: %6</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Read error encountered on the file to send. The local file system error is returned in parameter %6</p>         </td>
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
         <td><p>Local request identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Access path to the file</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>File name</p>         </td>
      </tr>
      <tr>
         <td><p>6</p>         </td>
         <td><p>Local file system diagnostic</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check the parameters of the Application used and make sure that the file system attributes are consistent. Gateway must have the <span style="font-style: italic;">read</span> privilege for the file to send. If a system dependent parameter is requested for file access, you must check that the request contains its description.</p>
<p>Refer to your platform documentation to understand the local file system error.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SFTP007E"></span>007</p>         </td>
         <td><p><span style="font-weight: bold;">SFTP E READDERR %1(%2) [%3] read error, file %4/%5: %6</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Read error encountered on the directory list to send. The local file system error is returned in parameter %6</p>         </td>
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
         <td><p>Local request identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Access path to the file</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>File name</p>         </td>
      </tr>
      <tr>
         <td><p>6</p>         </td>
         <td><p>Local file system diagnostic</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check the parameters of the Application used and make sure that the file system attributes are consistent. Gateway must have the <span style="font-style: italic;">read</span> privilege for the file to send. If a system dependent parameter is requested for file access, you must check that the request contains its description.</p>
<p>Refer to your platform documentation to understand the local file system error.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SFTP008E"></span>008</p>         </td>
         <td><p><span style="font-weight: bold;">SFTP E WRITEERR %1(%2) [%3] write error, file %4/%5: %6</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Write error encountered on the received file. The local file system error is returned in parameter %6</p>         </td>
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
         <td><p>Local request identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Access path to the file</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>File name</p>         </td>
      </tr>
      <tr>
         <td><p>6</p>         </td>
         <td><p>Local file system diagnostic</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check the parameters of the Application used by Gateway for the file reception, and make sure that the file system attributes are consistent. Gateway must have the <span style="font-style: italic;">write</span> privilege in the directory defined (in the Application) for the creation of the files in reception. If a system dependent parameter is requested for file access, you must make sure that it is actually used. There must be enough disk space to receive the file.</p>
<p>Refer to your platform documentation to understand the local file system error.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SFTP009E"></span>009</p>         </td>
         <td><p>SFTP E STAT_ERR %1(%2) [%3] stat error, file %4/%5: %6</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Error reading the info in the indicated file. This message indicates the local file system error.</p>         </td>
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
         <td><p>Local request identifier</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Access path to the file</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>File name</p>         </td>
      </tr>
      <tr>
         <td><p>6</p>         </td>
         <td><p>Local file system diagnostic</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check the message contents for information about the cause of the problem.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SFTP010E"></span>010</p>         </td>
         <td><p><span style="font-weight: bold;">SFTP E ABORTIND %1(%2) ABORT received: %3 %4</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Abort received on SFTP session</p>         </td>
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
         <td><p><span style="font-style: italic;">Type</span> of the error reported</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p><span style="font-style: italic;">Reason</span> for the abort</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>If the problem is a recurring one, check the remote and Local Site definitions. If the abort occurs in data phase, check the transfer parameters used for the Transfer Request.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SFTP011E"></span>011</p>         </td>
         <td><p><span style="font-weight: bold;">SFTP E ABORTREQ %1(%2) ABORT sent : %3 %4</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Abort sent to SFTP session</p>         </td>
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
         <td><p><span style="font-style: italic;">Type</span> of the error reported</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p><span style="font-style: italic;">Reason</span> for the abort</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>If the problem is a recurring one, check the Remote and Local Site definitions. If the abort occurs in data phase, check the transfer parameters used for the Transfer Request.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SFTP016I"></span>016</p>         </td>
         <td><p><span style="font-weight: bold;">SFTP I XFERRCV1 %1(%2) [%3] begin receiving to %4, file: %5 %6</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Information message indicating a start of reception</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Identification of the sender</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Identification of the transfer request</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Identification of the receiver</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Directory path of the file</p>         </td>
      </tr>
      <tr>
         <td><p>6</p>         </td>
         <td><p>Received file name</p>         </td>
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
         <td><p><span id="SFTP017I"></span>017</p>         </td>
         <td><p><span style="font-weight: bold;">SFTP I XFERRCV2 %1(%2) [%3] begin receiving to %4, LIST: %5</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Information message indicating a start of reception</p>         </td>
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
         <td><p>Local identification of the transfer request</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>File type</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Directory name</p>         </td>
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
         <td><p><span id="SFTP018I"></span>018</p>         </td>
         <td><p><span style="font-weight: bold;">SFTP I XFERSND1 %1(%2) [%3] begin sending from %4, file: %5 %6</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Information message indicating a start of transmission</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Identification of the sender</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local identification of the transfer request</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Identification of the receiver</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Directory path of the file</p>         </td>
      </tr>
      <tr>
         <td><p>6</p>         </td>
         <td><p>File name</p>         </td>
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
         <td><p><span id="SFTP019I"></span>019</p>         </td>
         <td><p><span style="font-weight: bold;">SFTP I XFERSND2 %1(%2) [%3] begin sending from %4, LIST: %5</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Information message indicating a start of transmission</p>         </td>
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
         <td><p>Local identification of the transfer request</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>File type</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Directory name</p>         </td>
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
         <td><p><span id="SFTP020I"></span>020</p>         </td>
         <td><p><span style="font-weight: bold;">SFTP I XENDRCV1 %1(%2) [%3] end receiving to %4, file:%5 %6</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Information message indicating an end of reception</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Identification of the sender</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Identification of the transfer request</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Identification of the receiver</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Directory path of the file</p>         </td>
      </tr>
      <tr>
         <td><p>6</p>         </td>
         <td><p>File name</p>         </td>
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
         <td><p><span id="SFTP021I"></span>021</p>         </td>
         <td><p><span style="font-weight: bold;">SFTP I XENDRCV2 %1(%2) [%3] end receiving, %4, LIST:%5</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Information message indicating an end of reception</p>         </td>
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
         <td><p>Local identification of the transfer request</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>File type</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Directory name</p>         </td>
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
         <td><p><span id="SFTP022I"></span>022</p>         </td>
         <td><p><span style="font-weight: bold;">SFTP I XENDSND1 %1(%2) [%3] end sending from %4, file:%5 %6</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Information message indicating an end of transmission</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Identification of the sender</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Identification of the transfer request</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Identification of the receiver</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Directory path of the file</p>         </td>
      </tr>
      <tr>
         <td><p>6</p>         </td>
         <td><p>File name</p>         </td>
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
         <td><p><span id="SFTP023I"></span>023</p>         </td>
         <td><p><span style="font-weight: bold;">SFTP I XENDSND2 %1(%2) [%3] end sending from %4, LIST:%5</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Information message indicating an end of transmission</p>         </td>
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
         <td><p>Local identification of the transfer request</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>File type</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Directory name</p>         </td>
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
         <td><p><span id="SFTP024E"></span>024</p>         </td>
         <td><p><span style="font-weight: bold;">SFTP E XERRRCV1 %1(%2) [%3] error receiving to %4, file: %5 %6</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Reception error</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Identification of the sender</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Identification of the transfer request</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Identification of the receiver</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Directory path of the file</p>         </td>
      </tr>
      <tr>
         <td><p>6</p>         </td>
         <td><p>File name</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check the messages indicating the cause of the problem.</p>
<p>Contact Axway Support if no solution is found.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SFTP025E"></span>025</p>         </td>
         <td><p><span style="font-weight: bold;">SFTP E XERRRCV2 %1(%2) [%3] error receiving to %4, LIST: %5</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Reception error</p>         </td>
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
         <td><p>Local identification of the transfer request</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>File type</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Directory name</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check the messages indicating the cause of the problem.</p>
<p>Contact Axway Support if no solution is found.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SFTP026E"></span>026</p>         </td>
         <td><p><span style="font-weight: bold;">SFTP E XENDSND1 %1(%2) [%3] error sending from %4, file:%5 %6</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Transmission error</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Identification of the sender</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Identification of the transfer request</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Identification of the receiver</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Directory path of the file</p>         </td>
      </tr>
      <tr>
         <td><p>6</p>         </td>
         <td><p>File name</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check the messages indicating the cause of the problem.</p>
<p>Contact Axway Support if no solution is found.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SFTP027E"></span>027</p>         </td>
         <td><p><span style="font-weight: bold;">SFTP E XENDREQ %1(%2) [%3] error sending from %4, LIST:%5</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Transmission error</p>         </td>
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
         <td><p>Identification of the transfer request</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>File type</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Directory name</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check the messages indicating the cause of the problem.</p>
<p>Contact Axway Support if no solution is found.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SFTP028I"></span>028</p>         </td>
         <td><p>SFTP I CONN_ABT %1(%2) [%3] connection interrupted with %4</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Information message indicating a connection abort with no data transfer phase</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Identification of the sender</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Identification of the transfer request</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check the message indicating the reason for the abort.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SFTP029E"></span>029</p>         </td>
         <td><p>SFTP E XERRDATA %1(%2) received data size (%3) exceeds max (%4)</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The size of SFTP requests is too big</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Identification of the sender (Remote Site name)</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Size of received packet (bytes)</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Maximum allowed size of packet (bytes)</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Configure the Remote Partner so that it sends smaller sized packets.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SFTP030E"></span>030</p>         </td>
         <td><p>SFTP E XERRDATA %1(%2) received packet size (%3) exceeds max (%4)</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The amount of data contained in a <span style="font-style: italic;">write</span> request is too big</p>         </td>
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
         <td><p>Size of received packet (bytes)</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Maximum allowed size of packet (bytes)</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Configure the Remote Partner so that it sends smaller sized <span style="font-style: italic;">write</span> requests.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SFTP031E"></span>031</p>         </td>
         <td><p>SFTP E MULTIXFR %1(%2) File : %3, monitored transfer rejected: a transfer is running in this session</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Some SFTP clients try to initiate a transfer even though a monitored transfer is already in progress in the same SSH session. Gateway does not support this.</p>         </td>
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
         <td><p>File name</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Wait until the first transfer has finished. Alternatively, deactivate the multiple transfer option (dependent on client).</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SFTP040I"></span>040</p>         </td>
         <td><p>SFTP I VFD_REMI %1(%2)  removing file: %3</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Removing the file specified in the message</p>         </td>
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
         <td><p>File name</p>         </td>
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
         <td><p><span id="SFTP041I"></span>041</p>         </td>
         <td><p>SFTP I VFD_MKDI %1(%2) creating directory: %3</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Creating the directory specified in the message</p>         </td>
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
         <td><p>Directory name</p>         </td>
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
         <td><p><span id="SFTP042I"></span>042</p>         </td>
         <td><p>SFTP I VFD_RMDI %1(%2) removing directory: %3</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Removing the directory specified in the message.</p>         </td>
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
         <td><p>Directory name</p>         </td>
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
         <td><p><span id="SFTP043I"></span>043</p>         </td>
         <td><p>SFTP I VFD_RENI %1(%2) renaming file: %3 to %4</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Renaming the indicated file with the indicated file name.</p>         </td>
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
         <td><p>Old file name</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>New file name</p>         </td>
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
         <td><p><span id="SFTP044E"></span>044</p>         </td>
         <td><p>SFTP E VFD_REME %1(%2)  error removing file: %3</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Error on deletion of the file specified in the message.</p>         </td>
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
         <td><p>File name</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Verify that the file system attributes are consistent. Gateway must have <span style="font-style: italic;">write</span> privileges in the directory containing the file.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SFTP045E"></span>045</p>         </td>
         <td><p>SFTP E VFD_MKDE %1(%2) error creating directory: %3</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Error when creating the directory specified in the message.</p>         </td>
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
         <td><p>Directory name</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Verify that the file system attributes are consistent. Gateway must have <span style="font-style: italic;">write</span> privileges in the parent directory.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SFTP046E"></span>046</p>         </td>
         <td><p>SFTP E VFD_RMDE %1(%2) error removing directory: %3</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Error in deleting the directory specified in the message</p>         </td>
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
         <td><p>Directory name</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Verify that the file system attributes are consistent. Gateway must have <span style="font-style: italic;">write</span> privileges in the parent directory. The directory must be empty.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SFTP047E"></span>047</p>         </td>
         <td><p>SFTP E VFD_RENE %1(%2) error renaming file: %3 to %4</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Error in the naming of the file specified in the message</p>         </td>
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
         <td><p>Old name</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>New name</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Verify that the file system attributes are consistent. Gateway must have <span style="font-style: italic;">write</span> privileges in the directory containing the file.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SFTP050E"></span>050</p>         </td>
         <td><p>SFTP E TRNFXERR %1(%2) [%3] transcode file to xfer error, file %4/%5: %6</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Error in transcoding the file specified in the message. This message indicates the local file system error.</p>         </td>
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
         <td><p>Local request identifier</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Access path to the file</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>File name</p>         </td>
      </tr>
      <tr>
         <td><p>6</p>         </td>
         <td><p>Local file system diagnostic</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check the message contents for information about the cause of the problem. Check the application parameters to verify that the date code is correct.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SFTP051E"></span>051</p>         </td>
         <td><p>SFTP E TRNXFERR %1(%2) [%3] transcode xfer to file error, file %4/%5: %6</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Error in transcoding the file specified in the message. This message indicates the local file system error.</p>         </td>
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
         <td><p>Local request identifier</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Access path to the file</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>File name</p>         </td>
      </tr>
      <tr>
         <td><p>6</p>         </td>
         <td><p>Local file system diagnostic</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check the message contents for information about the cause of the problem. Check the application parameters to verify that the date code is correct.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SFTP101I"></span>101</p>         </td>
         <td><p><span style="font-weight: bold;">SFTP I TRACE %1</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Use this message to trace SFTP raw data sent to the Remote Site</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Variable area for editing one line of data dump</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Not applicable</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SFTP102I"></span>102</p>         </td>
         <td><p><span style="font-weight: bold;">SFTP I TRACE %1 (%2) ID : %3 %4</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Use this message to trace SFTP protocol data units sent to the Remote Site.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Identification of the sender</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Data unit direction (Incoming/Outgoing)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>SFTP request identifier</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>SFTP packet type</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Not applicable</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SFTP103I"></span>103</p>         </td>
         <td><p><span style="font-weight: bold;">SFTP I TRACE %1 (%2) ID : %3 %4 %5 : %6</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Use this message to trace SFTP protocol data units sent to the Remote Site.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Identification of the sender</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Data unit direction (Incoming/Outgoing)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>SFTP request identifier</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>SFTP packet type</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>SFTP parameter name</p>         </td>
      </tr>
      <tr>
         <td><p>6</p>         </td>
         <td><p>SFTP parameter value</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Not applicable</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SFTP104I"></span>104</p>         </td>
         <td><p><span style="font-weight: bold;">SFTP I TRACE %1 (%2) ID : %3 %4 %5 :%6 %7 : %8</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>This message is used to trace SFTP protocol data units sent to the Remote Site</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Identification of the sender</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Data unit direction (Incoming/Outgoing)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>SFTP request identifier</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>SFTP packet type</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>SFTP parameter name</p>         </td>
      </tr>
      <tr>
         <td><p>6</p>         </td>
         <td><p>SFTP parameter value</p>         </td>
      </tr>
      <tr>
         <td><p>7</p>         </td>
         <td><p>SFTP parameter name</p>         </td>
      </tr>
      <tr>
         <td><p>8</p>         </td>
         <td><p>SFTP parameter value</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Not applicable</p>         </td>
      </tr>
   </tbody>
</table>

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
