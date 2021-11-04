{
    "title": "PEL protocol (PEL)",
    "linkTitle": "PEL",
    "weight": "340"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Messages and codes

This topic lists PEL log messages.

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="PEL001E"></span>001</p>         </td>
         <td><p><span style="font-weight: bold;">PEL E SELOP_ERR %1(%2) [%3] select-open error, file %4/%5: %6</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Error on the file selection or open operations. The local file system error is returned in parameter %6.</p>         </td>
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
         <td><p>Check the parameters of the Transfer Request and of the Application used for the compatibility of the file characteristics with the file system attributes referenced in the transfer. Check the access security and make sure that Gateway has the open-read privilege for the file. If a system-dependent parameter is requested for file access, check that the request contains its description.</p>
<p>Refer to your platform documentation to understand the local file system error.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="PEL002E"></span>002</p>         </td>
         <td><p><span style="font-weight: bold;">PEL E CREOP_ERR %1(%2) [%3] create-open error, file %4/%5: %6</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Error on the file creation or open operations for incoming file transmission. The local file system error is returned in parameter %6.</p>         </td>
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
         <td><p>Check the parameters of the Application used and make sure that the file system attributes are consistent. Gateway must have the "write" privilege in the directory defined (in the Application) for the creation of the files in reception. If a system-dependent parameter is requested for file access, make sure that it is used. There must be enough disk space to receive the file.</p>
<p>Refer to your platform documentation to understand the local file system error.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="PEL003E"></span>003</p>         </td>
         <td><p><span style="font-weight: bold;">PEL E CLODS_ERR %1(%2) [%3] close-deselect error, file %4/%5: %6</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Error on the file closing or de-selection operations. The local file system error is returned in parameter %6.</p>         </td>
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
         <td><p>Check the parameters of the Application used and make sure that the file system attributes are consistent.</p>
<p>Refer to your platform documentation to understand the local file system error.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="PEL004E"></span>004</p>         </td>
         <td><p><span style="font-weight: bold;">PEL E READ_ERR %1(%2) [%3] read error, file %4/%5: %6</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Read error encountered on the file to send. The local file system error is returned in parameter %6.</p>         </td>
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
         <td><p>Check the parameters of the Application used and make sure that the file system attributes are consistent. Gateway must have the "read" privilege for the file to send. If a system dependent parameter is requested for file access, you must check that the request contains its description.</p>
<p>Refer to your platform documentation to understand the local file system error.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="PEL005E"></span>005</p>         </td>
         <td><p><span style="font-weight: bold;">PEL E WRITE_ERR %1(%2) [%3] write error, file %4/%5: %6</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Write error encountered on the received file. The local file system error is returned in parameter %6.</p>         </td>
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
         <td><p>Check the parameters of the Application used by Gateway for the file reception, and make sure that the file system attributes are consistent. Gateway must have the "write" privilege in the directory defined (in the Application) for the creation of the files in reception. If a systems dependent parameter is requested for file access, you must make sure that it is actually used. There must be enough disk space to receive the file.</p>
<p>Refer to your platform documentation to understand the local file system error.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="PEL006E"></span>006</p>         </td>
         <td><p><span style="font-weight: bold;">PEL E UREAD_ERR %1(%2) [%3] previous record read error, file %4/%5: %6</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Read error encountered on the file to send. The local file system error is returned in parameter %6.</p>         </td>
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
         <td><p>Check the parameters of the Application used and make sure that the file system attributes are consistent. Gateway must have the "read" privilege for the file to send. If a system dependent parameter is requested for file access, you must check that the request contains its description.</p>
<p>Refer to your platform documentation to understand the local file system error.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="PEL007E"></span>007</p>         </td>
         <td><p><span style="font-weight: bold;">PEL E SEEK_ERR %1(%2) [%3] position error, file %4/%5: %6</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>File positioning error encountered on the file to send. The local file system error is returned in parameter %6.</p>         </td>
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
         <td><p>Check the parameters of the Application used and make sure that the file system attributes are consistent. If a systems dependent parameter is requested for file access, you must check that the Transfer Request contains their description.</p>
<p>Refer to your platform documentation to understand the local file system error.</p>
<p>Contact Axway Support if the problem persists.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="PEL010E"></span>010</p>         </td>
         <td><p><span style="font-weight: bold;">PEL E TRN_FILE_XFER %1(%2) [%3] send format conv. error %4/%5: %6</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Character set conversion or formatting error on the file to send. The local file system error is returned in parameter %6.</p>         </td>
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
         <td><p>Check the attributes used by character set conversion and formatting modules in the parameters of the Application or the Transfer Request. The corresponding character set conversion table must exist.</p>
<p>Refer to your platform documentation to understand the local file system error.</p>
<p>Contact Axway Support if the problem persists.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="PEL011E"></span>011</p>         </td>
         <td><p><span style="font-weight: bold;">PEL E TRN_XFER_FILE %1(%2) [%3] receive format conv. error %4/%5: %6</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Character set conversion or formatting error on the received file. The local file system error is returned in parameter %6.</p>         </td>
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
         <td><p>Check the attributes used by character set conversion and formatting modules in the parameters of the Application or the Transfer Request. The corresponding character set conversion table must exist.</p>
<p>Refer to your platform documentation to understand the local file system error.</p>
<p>Contact Axway Support if the problem persists.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="PEL020E"></span>020</p>         </td>
         <td><p><span style="font-weight: bold;">PEL E DECOMP %1(%2) [%3] receive data not respecting compression rules, file %4/%5</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The Local Site cannot uncompress the received data.</p>         </td>
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
         <td><p>Action</p>         </td>
         <td><p>Contact Axway Support if the problem persists.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="PEL021I"></span>021</p>         </td>
         <td><p><span style="font-weight: bold;">PEL I SENT %1(%2) [%3] %4</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>This message is used to trace PEL protocol data units sent to the Remote Site.</p>         </td>
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
         <td><p>Protocol data unit</p>         </td>
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
         <td><p><span id="PEL022I"></span>022</p>         </td>
         <td><p><span style="font-weight: bold;">PEL I RECEIVED %1(%2) [%3] %4</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>This message is used to trace PEL protocol data units received from the Remote Site.</p>         </td>
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
         <td><p>Protocol data unit</p>         </td>
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
         <td><p><span id="PEL100I"></span>100</p>         </td>
         <td><p><span style="font-weight: bold;">PEL I TRACE %1</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>General format for PEL protocol data unit dump.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Field for one line of dump</p>         </td>
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
         <td><p><span id="PEL131I"></span>131</p>         </td>
         <td><p><span style="font-weight: bold;">PEL I CONN_REQ %1(%2) [%3] connection established %4</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>PEL session established in Initiator mode.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Number of the internal context associated with the session</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Identification of the Transfer Request</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Local request identifier (number)</p>         </td>
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
         <td><p><span id="PEL132I"></span>132</p>         </td>
         <td><p><span style="font-weight: bold;">PEL I CONN_IND %1(%2) [%3] connection established %4</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>PEL session established in server mode.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Number of the internal context associated with the session</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Identification of the Transfer Request</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Local request identifier (number)</p>         </td>
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
         <td><p><span id="PEL134I"></span>134</p>         </td>
         <td><p><span style="font-weight: bold;">PEL I CNAK_REQ %1(%2) [%3] connection refused by %4. reason=%5</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>PEL session by the Local Site.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Number of the internal context associated with the session</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Identification of the Transfer Request</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Local request identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Refusal reason</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check the reason.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="PEL135I"></span>135</p>         </td>
         <td><p><span style="font-weight: bold;">PEL I CNAK_IND %1(%2) [%3] connection refused to %4. reason=%5</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>PEL session to the Local Site.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Number of the internal context associated with the session</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Identification of the Transfer Request</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Local request identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Refusal reason</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check the reason.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="PEL136I"></span>136</p>         </td>
         <td><p><span style="font-weight: bold;">PEL I SEND_REQ %1(%2) [%3] beginning of transmission from %4 to %5</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Information message indicating a beginning of transmission.</p>         </td>
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
         <td><p>Identification of the Transfer Request</p>         </td>
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
         <td><p><span id="PEL137I"></span>137</p>         </td>
         <td><p><span style="font-weight: bold;">PEL I SEND_REQ %1(%2) [%3] beginning of transmission, appli:%4, file: %5 %</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Information message indicating beginning of transmission.</p>         </td>
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
         <td><p>Identification of the Transfer Request</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>File type</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Transfer identifier</p>         </td>
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
         <td><p><span id="PEL138I"></span>138</p>         </td>
         <td><p><span style="font-weight: bold;">PEL I RECV_REQ %1(%2) [%3] beginning of reception from %4 to %5</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Information message indicating beginning of transmission.</p>         </td>
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
         <td><p>Identification of the Transfer Request</p>         </td>
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
         <td><p><span id="PEL139I"></span>139</p>         </td>
         <td><p><span style="font-weight: bold;">PEL I RECV_REQ %1(%2) [%3] beginning of reception, appli:%4, file: %5 %6</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Information message indicating beginning of transmission.</p>         </td>
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
         <td><p>Identification of the Transfer Request</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>File type</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Transfer identifier</p>         </td>
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
         <td><p><span id="PEL141I"></span>141</p>         </td>
         <td><p><span style="font-weight: bold;">PEL I XEND_SND %1(%2) [%3] end of transmission from %4 to %5</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Information message indicating an end of transmission.</p>         </td>
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
         <td><p>Identification of the Transfer Request</p>         </td>
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
         <td><p><span id="PEL142I"></span>142</p>         </td>
         <td><p><span style="font-weight: bold;">PEL I XEND_SND %1(%2) [%3] end of transmission, appli:%4, file: %5 %6</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Information message indicating an end of transmission.</p>         </td>
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
         <td><p>Local identification of the Transfer Request</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>File type</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Transfer identifier</p>         </td>
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
         <td><p><span id="PEL143I"></span>143</p>         </td>
         <td><p><span style="font-weight: bold;">PEL I XEND_RCV %1(%2) [%3] end of reception from %4 to %5</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Information message indicating an end of reception.</p>         </td>
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
         <td><p>Identification of the Transfer Request</p>         </td>
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
         <td><p><span id="PEL144I"></span>144</p>         </td>
         <td><p><span style="font-weight: bold;">PEL I XEND_RCV %1(%2) [%3] end of reception, appli:%4, file: %5 %6</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Information message indicating an end of reception.</p>         </td>
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
         <td><p>Local identification of the Transfer Request</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>File type</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Transfer identifier</p>         </td>
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
         <td><p><span id="PEL145E"></span>145</p>         </td>
         <td><p><span style="font-weight: bold;">PEL E DIAG_REQ %1(%2) [%3] DIAG. sent:%4</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Error diagnostic sent to a Remote Site.</p>         </td>
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
         <td><p>Identification of the transfer context</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Error diagnostic</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check the diagnostic value.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="PEL146E"></span>146</p>         </td>
         <td><p><span style="font-weight: bold;">PEL E DIAG_IND %1(%2) [%3] DIAG. received:%4</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Error diagnostic received from a Remote Site.</p>         </td>
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
         <td><p>Identification of the transfer context</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Error diagnostic</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check the diagnostic value.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="PEL147E"></span>147</p>         </td>
         <td><p><span style="font-weight: bold;">PEL E DIAG_REQ %1(%2) [%3] DIAG. sent:%4</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Timeout reached while expecting a response from the Remote Site.</p>         </td>
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
         <td><p>Identification of the transfer context</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Contact Axway Support.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="PEL148I"></span>148</p>         </td>
         <td><p>PEL I XRDL_REQ %1(%2) [%3] restart, record:%4</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Transfer restarted by Local Site.</p>         </td>
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
         <td><p>Identification of the transfer context</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Record number to restart from</p>         </td>
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
         <td><p><span id="PEL149I"></span>149</p>         </td>
         <td><p>PEL I XRDL_IND %1(%2) [%3] restart, record:%4</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Transfer restarted by Remote Site.</p>         </td>
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
         <td><p>Identification of the transfer context</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Record number to restart from</p>         </td>
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
         <td><p><span id="PEL153I"></span>153</p>         </td>
         <td><p><span style="font-weight: bold;">PEL  I LOTS_REQ  %1(%2) [%3] request for file sent from %4</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>PEL LOTS command sent to an adjacent Site.</p>         </td>
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
         <td><p>Identification of the transfer context</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Local request identifier (number)</p>         </td>
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
         <td><p><span id="PEL154I"></span>154</p>         </td>
         <td><p><span style="font-weight: bold;">PEL  I LOTS_IND  %1(%2) [%3] request for file received on %4</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>PEL LOTS command received from an adjacent Site.</p>         </td>
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
         <td><p>Identification of the transfer context</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Local request identifier (number)</p>         </td>
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
         <td><p><span id="PEL155I"></span>155</p>         </td>
         <td><p>PEL  I LOTS_END  %1(%2) [%3] end of file-list for %4</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>PEL LL command successfully recorded.</p>         </td>
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
         <td><p>Identification of the transfer context</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Local request identifier (number)</p>         </td>
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
         <td><p><span id="PEL156E"></span>156</p>         </td>
         <td><p><span style="font-weight: bold;">PEL E XERR_SND %1(%2) [%3] error of transmission from %4 to %5, reason=%6</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Transmission error detected.</p>         </td>
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
         <td><p>Local identification of the Transfer Request</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Identification of the sender (Site name)</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Identification of the receiver (Site name)</p>         </td>
      </tr>
      <tr>
         <td><p>6</p>         </td>
         <td><p>Reason on end of transmission (0 is successful)</p>         </td>
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
         <td><p><span id="PEL157E"></span>157</p>         </td>
         <td><p><span style="font-weight: bold;">PEL E XERR_SND %1(%2) [%3] error of transmission, appli:%4, file: %5 %6</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Transmission error detected.</p>         </td>
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
         <td><p>Local identification of the Transfer Request</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>File type</p>         </td>
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
         <td><p><span id="PEL158E"></span>158</p>         </td>
         <td><p><span style="font-weight: bold;">PEL E XERR_RCV %1(%2) [%3] error of reception from %4 to %5, reason=%6</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Reception error detected.</p>         </td>
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
         <td><p>Identification of the Transfer Request</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Identification of the receiver (Site name)</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Identification of the receiver (Site name)</p>         </td>
      </tr>
      <tr>
         <td><p>6</p>         </td>
         <td><p>Reason on end of transmission (0 is successful)</p>         </td>
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
         <td><p><span id="PEL159E"></span>159</p>         </td>
         <td><p><span style="font-weight: bold;">PEL E XERR_RCV %1(%2) [%3] error of reception, appli:%4, file: %5 %6</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Reception error detected.</p>         </td>
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
         <td><p>Identification of the Transfer Request</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>File type</p>         </td>
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

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
