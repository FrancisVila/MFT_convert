{
    "title": "PeSIT HS protocol (FPSIT)",
    "linkTitle": "PeSIT HS (FPSIT)",
    "weight": "360"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Messages and codes

This topic lists PeSIT HS log messages.

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="FPSIT001E"></span>001</p>         </td>
         <td><p><span style="font-weight: bold;">FPSIT E SEL_ERR %1(%2) [%3] select error, file %4 %5: %6</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Error on the file selection operation</p>         </td>
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
         <td><p>Check the access security and path to make sure that Gateway can access the file. If a system dependent parameter is requested for file access, you must check that the request contains its description.</p>
<p>Refer to your platform documentation to understand the local file system error.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="FPSIT002E"></span>002</p>         </td>
         <td><p><span style="font-weight: bold;">FPSIT E SELOP_ERR %1(%2) [%3] select-open error, file %4 %5: %6</span></p>         </td>
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
         <td><p>Check the parameters of the Transfer Request and of the Application used for the compatibility of the file characteristics with the file system attributes referenced by the transfer.</p>
<p>Check the access security and path to make sure that Gateway can access the file. If a system dependent parameter is requested for file access, you must check that the request contains its description.</p>
<p>Refer to your platform documentation to understand the local file system error.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="FPSIT003E"></span>003</p>         </td>
         <td><p><span style="font-weight: bold;">FPSIT E CRE_ERR %1(%2) [%3] create error, file %4 %5: %6</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Error on the file creation operations for incoming transmission. The local file system error is returned in parameter %6</p>         </td>
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
         <td><p><span id="FPSIT004E"></span>004</p>         </td>
         <td><p><span style="font-weight: bold;">FPSIT E CREOP_ERR %1(%2) [%3] create-open error, file %4 %5: %6</span></p>         </td>
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
         <td><p><span id="FPSIT005E"></span>005</p>         </td>
         <td><p><span style="font-weight: bold;">FPSIT E DESEL_ERR %1(%2) [%3] deselect error, file %4 %5: %6</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Error on the file de-selection operation. The local file system error is returned in parameter %6</p>         </td>
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
         <td><p>Refer to your platform documentation to understand the local file system error</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="FPSIT006E"></span>006</p>         </td>
         <td><p><span style="font-weight: bold;">FPSIT E OPEN_ERR %1(%2) [%3] open error, file %4 %5: %6</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Error on the file opening operation. The local file system error is returned in parameter %6</p>         </td>
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
         <td><p>Refer to your platform documentation to understand the local file system error.</p>
<p>Check the parameters of the Transfer Request and of the Application used for the compatibility of the file characteristics with the file system attributes referenced by the transfer.</p>
<p>Check the access security and path to make sure that Gateway can access the file. If a system dependent parameter is requested for file access, you must check that the request contains its description.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="FPSIT007E"></span>007</p>         </td>
         <td><p><span style="font-weight: bold;">FPSIT E CLOSE_ERR %1(%2) [%3] close error, file %4 %5: %6</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Error on the file closing operation. The local file system error is returned in parameter %6</p>         </td>
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
         <td><p>Refer to your platform documentation to understand the local file system error</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="FPSIT008E"></span>008</p>         </td>
         <td><p><span style="font-weight: bold;">FPSIT E CLODS_ERR %1(%2) [%3] close-deselect error, file %4 %5: %6</span></p>         </td>
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
         <td><p>Refer to your platform documentation to understand the local file system error</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="FPSIT009E"></span>009</p>         </td>
         <td><p><span style="font-weight: bold;">FPSIT E READ_ERR %1(%2) [%3] read error, file %4 %5: %6</span></p>         </td>
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
         <td><p><span id="FPSIT010E"></span>010</p>         </td>
         <td><p><span style="font-weight: bold;">FPSIT E WRITE_ERR %1(%2) [%3] write error, file %4 %5: %6</span></p>         </td>
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
         <td><p><span id="FPSIT011E"></span>011</p>         </td>
         <td><p><span style="font-weight: bold;">FPSIT E UREAD_ERR %1(%2) [%3] previous record read error, file %4 %5: %6</span></p>         </td>
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
         <td><p><span id="FPSIT012E"></span>012</p>         </td>
         <td><p><span style="font-weight: bold;">FPSIT E SEEK_ERR %1(%2) [%3] position error, file %4 %5: %6</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>File positioning error encountered on the file to send. The local file system error is returned in parameter %6</p>         </td>
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
         <td><p>Check the parameters of the Application used and make sure that the file system attributes are consistent. If a system dependent parameter is requested for file access, you must check that the Transfer Request contains their description.</p>
<p>Refer to your platform documentation to understand the local file system error.</p>
<p>Contact Axway Support if the problem persists.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="FPSIT013E"></span>013</p>         </td>
         <td><p><span style="font-weight: bold;">FPSIT E FLUSH_ERR %1(%2) [%3] forced write error, file %4 %5: %6</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Forced writing failed on the received file. The local file system error is returned in parameter %6</p>         </td>
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
         <td><p>Refer to your platform documentation to understand the local file system error.</p>
<p>Contact Axway Support if the problem persists.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="FPSIT014W"></span>014</p>         </td>
         <td><p><span style="font-weight: bold;">FPSIT W COMP_ERR %1(%2) [%3] received data incorrectly compressed, file %4 %5</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The Local Site cannot uncompress the received data</p>         </td>
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
         <td><p>Check that the data transmitted on the network by the Remote Site is compressed according to PeSIT normalized rules. The same compression mode must be used on both emission and reception sides.</p>
<p>Contact Axway Support if the problem persists.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="FPSIT015I"></span>015</p>         </td>
         <td><p><span style="font-weight: bold;">FPSIT I TRACE %1</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>This message is used to trace PeSIT protocol data units sent to the Remote Site</p>         </td>
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
         <td><p><span id="FPSIT020E"></span>020</p>         </td>
         <td><p><span style="font-weight: bold;">FPSIT E ABORT_IND %1(%2) [%3] ABORT received: %4 %5</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Abort received on PeSIT session</p>         </td>
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
         <td><p><em>Type</em> of error reported</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p><em>Reason</em> for the abort</p>         </td>
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
         <td><p><span id="FPSIT021E"></span>021</p>         </td>
         <td><p><span style="font-weight: bold;">FPSIT E ABORT_REQ %1(%2) [%3] ABORT sent : %4 %5</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Abort sent to PeSIT session</p>         </td>
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
         <td><p><em>Type</em> of error reported</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Reason for the abort</p>         </td>
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
         <td><p><span id="FPSIT022E"></span>022</p>         </td>
         <td><p><span style="font-weight: bold;">FPSIT E IDT_IND %1(%2) [%3] IDT received D:%4 %5, R:%6, N=%7</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>IDT received/sent on PeSIT session</p>         </td>
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
         <td><p><em>Type</em> of error reported</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>PeSIT diagnostic code</p>         </td>
      </tr>
      <tr>
         <td><p>6</p>         </td>
         <td><p>Reason for the abort</p>         </td>
      </tr>
      <tr>
         <td><p>7</p>         </td>
         <td><p>File name</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Parameters 4, 5, 6 and 7 are described in the PeSIT protocol specifications.</p>
<p>For more information, contact Axway Support.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="FPSIT023E"></span>023</p>         </td>
         <td><p><span style="font-weight: bold;">FPSIT E IDT_IND %1(%2) [%3] IDT received D:%4 %5, R:%6, N=%7</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>IDT received/sent on PeSIT session</p>         </td>
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
         <td><p><em>Type</em> of error reported</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Reason for the abort</p>         </td>
      </tr>
      <tr>
         <td><p>6</p>         </td>
         <td><p>File name</p>         </td>
      </tr>
      <tr>
         <td><p>7</p>         </td>
         <td><p>Internal use</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Parameters 4, 5 and 6 are described in the PeSIT protocol specifications.</p>
<p>For more information, contact Axway Support.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="FPSIT024I"></span>024</p>         </td>
         <td><p><span style="font-weight: bold;">FPSIT I CONN_IND %1(%2) [%3] connection request received for %</span><span style="font-weight: bold;">4</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Information message meaning that a PeSIT connection indication has been received</p>         </td>
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
         <td><p><span id="FPSIT025I"></span>025</p>         </td>
         <td><p><span style="font-weight: bold;">FPSIT I CONN_REQ %1(%2) [%3] connection request sent by %4</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Information message meaning that a PeSIT connection indication has been sent</p>         </td>
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
         <td><p><span id="FPSIT026I"></span>026</p>         </td>
         <td><p><span style="font-weight: bold;">FPSIT I XFER_RCV1 %1(%2) [%3] begin receiving to %4, file:%5 %6</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Information message indicating start of reception</p>         </td>
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
         <td><p><span id="FPSIT027I"></span>027</p>         </td>
         <td><p><span style="font-weight: bold;">FPSIT I XFER_RCV2 %1(%2) [%3] begin receiving, TYPE:%4, ID:%5, N:%6</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Information message indicating start of reception</p>         </td>
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
         <td><p>Protocol file name</p>         </td>
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
         <td><p><span id="FPSIT028I"></span>028</p>         </td>
         <td><p><span style="font-weight: bold;">FPSIT I XFER_SND1 %1(%2) [%3] begin sending from %4, file:%5 %6</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Information message indicating a beginning of transmission</p>         </td>
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
         <td><p><span id="FPSIT029I"></span>029</p>         </td>
         <td><p><span style="font-weight: bold;">FPSIT I XFER_SND2 %1(%2) [%3] begin sending from %4, file:%5 %6</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Information message indicating a beginning of transmission</p>         </td>
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
         <td><p>Protocol file name</p>         </td>
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
         <td><p><span id="FPSIT030I"></span>030</p>         </td>
         <td><p><span style="font-weight: bold;">FPSIT I XEND_RCV1 %1(%2) [%3] end receiving to %4, file:%5 %6</span></p>         </td>
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
         <td><p><span id="FPSIT031I"></span>031</p>         </td>
         <td><p><span style="font-weight: bold;">FPSIT I XEND_RCV2 %1(%2) [%3] end receiving, TYPE:%4, ID:%5, N:%6</span></p>         </td>
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
         <td><p>Protocol file name</p>         </td>
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
         <td><p><span id="FPSIT032I"></span>032</p>         </td>
         <td><p><span style="font-weight: bold;">FPSIT I XEND_SND1 %1(%2) [%3] end sending from %4, file:%5 %6</span></p>         </td>
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
         <td><p><span id="FPSIT033I"></span>033</p>         </td>
         <td><p><span style="font-weight: bold;">FPSIT I XEND_SND2 %1(%2) [%3] end sending, TYPE: %4, ID:%5, N:%6</span></p>         </td>
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
         <td><p>Protocol file name</p>         </td>
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
         <td><p><span id="FPSIT034E"></span>034</p>         </td>
         <td><p><span style="font-weight: bold;">FPSIT E XERR_IND %1(%2) [%3] error receiving to %4, file: %5 %6</span></p>         </td>
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
         <td><p>Check the messages indicating the cause of the problem.</p>
<p>Contact Axway Support if no solution is found.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="FPSIT035E"></span>035</p>         </td>
         <td><p><span style="font-weight: bold;">FPSIT E XERR_IND %1(%2) [%3] error receiving, TYPE:%4, ID:%5, N:%6</span></p>         </td>
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
         <td><p>Protocol file name</p>         </td>
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
         <td><p><span id="FPSIT036E"></span>036</p>         </td>
         <td><p><span style="font-weight: bold;">FPSIT E XERR_REQ %1(%2) [%3] error sending from %4, file: %5 %6</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Error sending a file</p>         </td>
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
         <td><p>Check the messages indicating the cause of the problem.</p>
<p>Contact Axway Support if no solution is found.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="FPSIT037E"></span>037</p>         </td>
         <td><p><span style="font-weight: bold;">FPSIT E XERR_REQ %1(%2) [%3] error sending, TYPE: %4, ID:%5 %6</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Error sending a file</p>         </td>
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
         <td><p>Protocol file name</p>         </td>
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
         <td><p><span id="FPSIT038I"></span>038</p>         </td>
         <td><p><span style="font-weight: bold;">FPSIT I RSTR_IND %1(%2) [%3] resume, sync:%4, record:%5, bytes:%6</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Information message indicating that a restart indication has been received in PeSIT protocol</p>         </td>
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
         <td><p>Check point number</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Record number</p>         </td>
      </tr>
      <tr>
         <td><p>6</p>         </td>
         <td><p>Byte offset</p>         </td>
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
         <td><p><span id="FPSIT039I"></span>039</p>         </td>
         <td><p><span style="font-weight: bold;">FPSIT I CONN_ABT %1(%2) [%3] connection interrupted with <span style="font-weight: bold;">%</span></span><span style="font-weight: bold;">4</span></p>         </td>
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
         <td><p>Identification of the Transfer Request</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check the message indicating the reason for the abort</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="FPSIT040I"></span>040</p>         </td>
         <td><p><span style="font-weight: bold;">FPSIT I SELECT_E1 %1(%2) [%3] SELECT fails: TYPE:%4, ID:%5, N:%6</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Information message indicating a file selection request failure</p>         </td>
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
         <td><p>Protocol file type</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Protocol connection ID</p>         </td>
      </tr>
      <tr>
         <td><p>6</p>         </td>
         <td><p>Protocol file name</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>See notes in the following message</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="FPSIT041I"></span>041</p>         </td>
         <td><p><span style="font-weight: bold;">FPSIT I SELECT_E2 %1(%2) [%3] SELECT fails: %4</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Information message indicating a file selection request failure</p>         </td>
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
         <td><p>Diagnostic code and reason of the failure</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>If the diagnostic code is "205:file not found", no particular action is required. Otherwise, check PeSIT protocol documentation for an explanation of the protocol error encountered.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="FPSIT042I"></span>042</p>         </td>
         <td><p><span style="font-weight: bold;">FPSIT I CREATE_E1 %1(%2) [%3] CREATE fails: TYPE:%4, ID:%5, N:%6</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Information message indicating a file creation failure</p>         </td>
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
         <td><p>Protocol file type</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Protocol connection ID</p>         </td>
      </tr>
      <tr>
         <td><p>6</p>         </td>
         <td><p>Protocol file name</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>See notes in the following message</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="FPSIT043I"></span>043</p>         </td>
         <td><p><span style="font-weight: bold;">FPSIT I CREATE_E2 %1(%2) [%3] CREATE fails: %4</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Information message indicating a file creation failure</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Identification of the sender</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Internal context number associated with the transfer</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Identification of the Transfer Request</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Diagnostic code and reason of the failure</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check PeSIT protocol documentation for an explanation of the protocol error encountered</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="FPSIT051I"></span>051</p>         </td>
         <td><p><span style="font-weight: bold;">FPSIT I MSG_SND2 %1(%2) [%3] begin sending %4, TYPE:%5, ID:%6, N:%7</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Information message indicating a file creation failure</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Internal context number associated with the transfer</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local identification of the Transfer Request</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>MSG/REPLY</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>File type</p>         </td>
      </tr>
      <tr>
         <td><p>6</p>         </td>
         <td><p>Transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>7</p>         </td>
         <td><p>Protocol file name</p>         </td>
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
         <td><p><span id="FPSIT052I"></span>052</p>         </td>
         <td><p><span style="font-weight: bold;">FPSIT I MEND_SND2 %1(%2) [%3] end sending %4, TYPE:%5, ID:%6, N:%7</span></p>         </td>
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
         <td><p>Internal context number associated with the transfer</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local identification of the Transfer Request</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>MSG/REPLY</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>File type</p>         </td>
      </tr>
      <tr>
         <td><p>6</p>         </td>
         <td><p>Transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>7</p>         </td>
         <td><p>Protocol file name</p>         </td>
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
         <td><p><span id="FPSIT053I"></span>053</p>         </td>
         <td><p><span style="font-weight: bold;">FPSIT I MSG_RCV2 %1(%2) [%3] begin receiving %4, TYPE:%5, ID:%6, N:%7</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Information message indicating a start of message reception</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Internal context number associated with the transfer</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local identification of the Transfer Request</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>MSG/REPLY</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>File type</p>         </td>
      </tr>
      <tr>
         <td><p>6</p>         </td>
         <td><p>Transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>7</p>         </td>
         <td><p>Protocol file name</p>         </td>
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
         <td><p><span id="FPSIT054I"></span>054</p>         </td>
         <td><p><span style="font-weight: bold;">FPSIT I MEND_RCV2 %1(%2) [%3] end receiving %4, TYPE:%5, ID:%6, N:%7</span></p>         </td>
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
         <td><p>Internal context number associated with the transfer</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local identification of the Transfer Request</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>MSG/REPLY</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>File type</p>         </td>
      </tr>
      <tr>
         <td><p>6</p>         </td>
         <td><p>Transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>7</p>         </td>
         <td><p>Protocol file name</p>         </td>
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
         <td><p><span id="FPSIT055I"></span>055</p>         </td>
         <td><p><span style="font-weight: bold;">FPSIT I CONN_NACK %1(%2) [%3] invalid connection request: unsupported option %4</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>An incoming connection request was refused because it asked for an unsupported option</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Internal context number associated with the transfer</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local identification of the Transfer Request</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>The unsupported option in question: it can either be negative acknowledgment or Change Direction for PeSIT protocol</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Configure these options via the Remote Site definition</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="FPSIT101I"></span>101</p>         </td>
         <td><p><span style="font-weight: bold;">FPSIT I TRACE %1</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>This message is used to trace PeSIT protocol data units sent to the Remote Site</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
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
         <td><p><span id="FPSIT102I"></span>102</p>         </td>
         <td><p>FPSIT I CDI_SND   %1(%2) [%3] Change of direction sent. Heartbeat interval: %4</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Information message indicating that a change of direction request has been sent</p>         </td>
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
         <td><p>Request number</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Heartbeat message time interval (in seconds)</p>         </td>
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
         <td><p><span id="FPSIT103I"></span>103</p>         </td>
         <td><p>FPSIT I CDI_RCV   %1(%2) [%3] Change of direction received. Heartbeat interval: %4</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Information message indicating that a change of direction request has been received</p>         </td>
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
         <td><p>Request number</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Heartbeat message time interval (in seconds)</p>         </td>
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
         <td><p><span id="FPSIT104I"></span>104</p>         </td>
         <td><p>FPSIT I ACDI_SND  %1(%2) [%3] Change of direction accepted. Heartbeat interval: %4</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Information message indicating that a change of direction request has been accepted</p>         </td>
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
         <td><p>Request number</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Heartbeat message time interval (in seconds)</p>         </td>
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
         <td><p><span id="FPSIT105I"></span>105</p>         </td>
         <td><p>PSIT I ACDI_RCV  %1(%2) [%3] Change of direction confirmed. Heartbeat interval: %4</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Information message confirming change of direction</p>         </td>
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
         <td><p>Request number</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Heartbeat message time interval (in seconds)</p>         </td>
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
         <td><p><span id="FPSIT106E"></span>106</p>         </td>
         <td><p>FPSIT E ABORT_REQ %1(%2) [%3] ABORT sent : %4 %5</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>PeSIT error triggers Gateway ABORT request</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Connector ID</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Request number</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>PeSIT error code</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Internal error code</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>The corrective action depends on the returned error code:</p>
<ul>
<li>To interpret PeSIT error codes, refer to the PeSIT topics in this documentation, or alternatively, refer to PeSIT standards documentation.</li>
<li>To correct errors referenced by internal error codes, contact Axway Support.</li>
</ul>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="FPSIT107E"></span>107</p>         </td>
         <td><p>FPSIT E ABORT_IND %1(%2) [%3] ABORT received : %4 %5</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>ABORT request received following error</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Connector ID</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Request number</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>PeSIT error code</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Internal error code</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>The corrective action depends on the returned error code:</p>
<ul>
<li>To interpret PeSIT error codes refer to the PeSIT topics in this documentation, or alternatively, refer to PeSIT standards documentation.</li>
<li>To correct errors referenced by internal error codes, contact Axway Support.</li>
</ul>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p>110</p>         </td>
         <td><p>FPSIT W HA_DUP %1(%2) Transfer is a duplicate (PI3: %3 PI4: %4 PI12: %5 PI13: %6 PI51: %7)</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>A duplicate incoming transfer was detected.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Connector ID</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>PI3 (originator)</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>PI4 (destination)</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>PI12 (file name)</p>         </td>
      </tr>
      <tr>
         <td><p>6</p>         </td>
         <td><p>PI13 (transfer identifier)</p>         </td>
      </tr>
      <tr>
         <td><p>7</p>         </td>
         <td><p>PI51 (file creation date)</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p>111</p>         </td>
         <td><p>FPSIT E HA_ERROR %1 Reason: %2</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>An error occurred during a PeSIT Duplicate Checking in the context of High Availability operation.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Error message</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Error reason</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p>112</p>         </td>
         <td><p>FPSIT E HA_DCERR %1(%2) Duplicate check failed (PI3: %3 PI4: %4 PI12: %5 PI13: %6 PI51: %7). Reason: %8</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The duplicate check failed for an incoming transfer. The transfer will continue.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Error message</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Error reason</p>         </td>
      </tr>
      <tr>
         <td>          </td>
         <td><p>3</p>         </td>
         <td><p>PI3 (originator)</p>         </td>
      </tr>
      <tr>
         <td>          </td>
         <td><p>4</p>         </td>
         <td><p>PI4 (destination)</p>         </td>
      </tr>
      <tr>
         <td>          </td>
         <td><p>5</p>         </td>
         <td><p>PI12 (file name)</p>         </td>
      </tr>
      <tr>
         <td>          </td>
         <td><p>6</p>         </td>
         <td><p>PI13 (transfer identifier)</p>         </td>
      </tr>
      <tr>
         <td>          </td>
         <td><p>7</p>         </td>
         <td><p>PI51 (file creation date)</p>         </td>
      </tr>
      <tr>
         <td>          </td>
         <td><p>8</p>         </td>
         <td><p>Error reason</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p>113</p>         </td>
         <td><p>FPSIT E HA_STERR %1(%2) Transfer DB store failed, duplicate check will not be available (PI3: %3 PI4: %4 PI12: %5 PI13: %6 PI51: %7). Reason: %8</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Storing the transfer parameters in the High Availability database failed. Duplicate check will not be available for this transfer.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Connector ID</p>         </td>
      </tr>
      <tr>
         <td>          </td>
         <td><p>3</p>         </td>
         <td><p>PI3 (originator)</p>         </td>
      </tr>
      <tr>
         <td>          </td>
         <td><p>4</p>         </td>
         <td><p>PI4 (destination)</p>         </td>
      </tr>
      <tr>
         <td>          </td>
         <td><p>5</p>         </td>
         <td><p>PI12 (file name)</p>         </td>
      </tr>
      <tr>
         <td>          </td>
         <td><p>6</p>         </td>
         <td><p>PI13 (transfer identifier)</p>         </td>
      </tr>
      <tr>
         <td>          </td>
         <td><p>7</p>         </td>
         <td><p>PI51 (file creation date)</p>         </td>
      </tr>
      <tr>
         <td>          </td>
         <td><p>8</p>         </td>
         <td><p>Error reason</p>         </td>
      </tr>
   </tbody>
</table>

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
