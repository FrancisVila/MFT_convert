{
    "title": "SWIFTNet (SNET) ",
    "linkTitle": "SWIFTNet (SNET)",
    "weight": "480"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Messages and codes

This topic lists SWIFTNet log messages.

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SNET001E"></span>001</p>         </td>
         <td><p>SNET  E SELOPERR  %1(%2) [%3] select-open error, file %4/%5: %6</p>         </td>
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
         <td><p>Access Point name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Message partner</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local request identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Physical file directory</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Physical file name</p>         </td>
      </tr>
      <tr>
         <td><p>6</p>         </td>
         <td><p>Error description</p>         </td>
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
         <td><p><span id="SNET002E"></span>002</p>         </td>
         <td><p>SNET  E CREOPERR  %1(%2) [%3] create-open error, file %4/%5: %6</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Error on the file creation operations for incoming transmission. The local file system error is returned in parameter %6.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Access Point name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Message partner</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local request identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Physical file directory</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Physical file name</p>         </td>
      </tr>
      <tr>
         <td><p>6</p>         </td>
         <td><p>Error description</p>         </td>
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
         <td><p><span id="SNET003E"></span>003</p>         </td>
         <td><p>SNET  <span style="font-weight: bold;">E CLODSERR  %1(%2) [%3] close-deselect error, file %4/%5: %6</span></p>         </td>
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
         <td><p>Access Point name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Message partner</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local request identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Physical file directory</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Physical file name</p>         </td>
      </tr>
      <tr>
         <td><p>6</p>         </td>
         <td><p>Error description</p>         </td>
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
         <td><p><span id="SNET004E"></span>004</p>         </td>
         <td><p>SNET<span style="font-weight: bold;">  E READ_ERR  %1(%2) [%3] read error, file %4/%5: %6</span></p>         </td>
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
         <td><p>Access Point name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Message partner</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local request identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Physical file directory</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Physical file name</p>         </td>
      </tr>
      <tr>
         <td><p>6</p>         </td>
         <td><p>Error description</p>         </td>
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
         <td><p><span id="SNET005E"></span>005</p>         </td>
         <td><p>SNET <span style="font-weight: bold;"> E WRITEERR  %1(%2) [%3] write error, file %4/%5: %6</span></p>         </td>
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
         <td><p>Access Point name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Message partner</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local request identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Physical file directory</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Physical file name</p>         </td>
      </tr>
      <tr>
         <td><p>6</p>         </td>
         <td><p>Error description</p>         </td>
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
         <td><p><span id="SNET006E"></span>006</p>         </td>
         <td><p>SNET  E CMPF_ERR  %1(%2) [%3] compression error, file %4/%5: %6</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The local file could not be compressed.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Access Point name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Message partner</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local request identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Physical file directory</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Physical file name</p>         </td>
      </tr>
      <tr>
         <td><p>6</p>         </td>
         <td><p>Error description</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Gateway may not have enough free space to achieve the compression. Check the available disk space.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SNET007E"></span>007</p>         </td>
         <td><p>SNET  E UCMPFERR  %1(%2) [%3] decompression error, file %4/%5: %6</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The local file could not be decompressed.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Access Point name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Message partner</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local request identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Physical file directory</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Physical file name</p>         </td>
      </tr>
      <tr>
         <td><p>6</p>         </td>
         <td><p>Error description</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Gateway may not have enough free space to achieve the decompression. Check the available disk space.</p>
<p>The file may not have been compressed properly.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SNET008W"></span>008</p>         </td>
         <td><p>SNET  W QUEUEACQ  %1(%2) queue %3 acquire request rejected</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Warning message indicating that the request for acquiring a queue has been rejected because there is another active output session on it.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Access Point name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Message partner</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>SnF queue name</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Several possible actions:</p>
<ul>
<li>Identify messaging interface already using the queue.</li>
<li>Use another queue.</li>
</ul>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SNET010E"></span>010</p>         </td>
         <td><p>SNET  E ABORTIND  %1(%2)  ABORT received: %3 %4</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Abort received on SWIFTNet session.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Access Point name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Message partner</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Error code</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Error code number (reason for the abort)</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>If the problem is a recurring one, check the Remote and Local Trading Partner definitions. The transfer may have been canceled locally or remotely.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SNET011E"></span>011</p>         </td>
         <td><p>SNET  E ABORTREQ  %1(%2)  ABORT sent: %3 %4</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Abort sent on SWIFTNet session.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Access Point name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Message partner</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Error code</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Error code number (reason for the abort)</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>If the problem is a recurring one, check the Remote and Local Trading Partner definitions. The transfer may have been aborted locally.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p>015</p>         </td>
         <td><p>SNET I SITEACTN %1(%2) site has been %3</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>AA SWIFTNet site state has changed.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Access Point name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Message partner</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>New state:</p>
<ul>
<li>deleted</li>
<li>disconnected</li>
<li>initialized</li>
<li>started</li>
<li>stopped</li>
</ul>         </td>
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
         <td><p>016</p>         </td>
         <td><p>SNET E SITEACTNE %1(%2) site has been %3. Reason: %4</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>A SWIFTNet site state has changed due to a configuration error.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Access Point name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Message partner</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>New state:</p>
<ul>
<li>disabled</li>
</ul>         </td>
      </tr>
      <tr>
         <td>4         </td>
         <td>Error reason         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Contact the Gateway Administrator.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SNET021I"></span>021</p>         </td>
         <td><p>SNET  I XFERRCV1  %1(%2) [%3] begin receiving from %4,%5 file: %6 %7</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Information message indicating the start of reception.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Access Point name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Message partner</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local request identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Alias of the remote partner</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Copied or distributed transfer indicator.</p>
<p>Possible values:</p>
<ul>
<li>"(copied)"</li>
<li>"(distributed)"</li>
<li>""</li>
</ul>
<p>This parameter is empty for normal transfers, which are not copied or distributed.</p>         </td>
      </tr>
      <tr>
         <td><p>6</p>         </td>
         <td><p>Physical file directory</p>         </td>
      </tr>
      <tr>
         <td><p>7</p>         </td>
         <td><p>Physical file name</p>         </td>
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
         <td><p><span id="SNET022I"></span>022</p>         </td>
         <td><p>SNET  I XFERSND1  %1(%2) [%3] begin sending to %4,%5 file: %6 %7</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Information message indicating the start of transmission.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Access Point name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Message partner</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local request identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Alias of the remote partner</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Copied or distributed transfer indicator.</p>
<p>Possible values:</p>
<ul>
<li>"(copied)"</li>
<li>"(distributed)"</li>
<li>""</li>
</ul>
<p>This parameter is empty for normal transfers, which are not copied or distributed.</p>         </td>
      </tr>
      <tr>
         <td><p>6</p>         </td>
         <td><p>Physical file directory</p>         </td>
      </tr>
      <tr>
         <td><p>7</p>         </td>
         <td><p>Physical file name</p>         </td>
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
         <td><p><span id="SNET023I"></span>023</p>         </td>
         <td><p>SNET  I XENDRCV1  %1(%2) [%3] end receiving from %4,%5 file: %6 %7</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Information message indicating the end of reception.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Access Point name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Message partner</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local request identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Alias of the remote partner</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Copied or distributed transfer indicator.</p>
<p>Possible values:</p>
<ul>
<li>"(copied)"</li>
<li>"(distributed)"</li>
<li>""</li>
</ul>
<p>This parameter is empty for normal transfers, which are not copied or distributed.</p>         </td>
      </tr>
      <tr>
         <td><p>6</p>         </td>
         <td><p>Physical file directory</p>         </td>
      </tr>
      <tr>
         <td><p>7</p>         </td>
         <td><p>Physical file name</p>         </td>
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
         <td><p><span id="SNET024I"></span>024</p>         </td>
         <td><p>SNET  I XENDSND1  %1(%2) [%3] end sending to %4,%5 file: %6 %7</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Information message indicating the end of transmission.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Access Point name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Message partner</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local request identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Alias of the remote partner</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Copied or distributed transfer indicator.</p>
<p>Possible values:</p>
<ul>
<li>"(copied)"</li>
<li>"(distributed)"</li>
<li>""</li>
</ul>
<p>This parameter is empty for normal transfers, which are not copied or distributed.</p>         </td>
      </tr>
      <tr>
         <td><p>6</p>         </td>
         <td><p>Physical file directory</p>         </td>
      </tr>
      <tr>
         <td><p>7</p>         </td>
         <td><p>Physical file name</p>         </td>
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
         <td><p><span id="SNET025E"></span>025</p>         </td>
         <td><p>SNET  E XERRRCV1  %1(%2) [%3] error receiving from %4,%5 file: %6 %7</p>         </td>
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
         <td><p>Access Point name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Message partner</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local request identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Alias of the remote partner</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Copied or distributed transfer indicator.</p>
<p>Possible values:</p>
<ul>
<li>"(copied)"</li>
<li>"(distributed)"</li>
<li>""</li>
</ul>
<p>This parameter is empty for normal transfers, which are not copied or distributed.</p>         </td>
      </tr>
      <tr>
         <td><p>6</p>         </td>
         <td><p>Physical file directory</p>         </td>
      </tr>
      <tr>
         <td><p>7</p>         </td>
         <td><p>Physical file name</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check the messages indicating the cause of the problem.</p>
<p>If no solution is found, contact Axway Support.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SNET026E"></span>026</p>         </td>
         <td><p>SNET  E XERRSND1  %1(%2) [%3] error sending to %4,%5 file: %6 %7</p>         </td>
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
         <td><p>Access Point name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Message partner</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local request identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Alias of the remote partner</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Copied or distributed transfer indicator.</p>
<p>Possible values:</p>
<ul>
<li>"(copied)"</li>
<li>"(distributed)"</li>
<li>""</li>
</ul>
<p>This parameter is empty for normal transfers, which are not copied or distributed.</p>         </td>
      </tr>
      <tr>
         <td><p>6</p>         </td>
         <td><p>Physical file directory</p>         </td>
      </tr>
      <tr>
         <td><p>7</p>         </td>
         <td><p>Physical file name</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check the messages indicating the cause of the problem.</p>
<p>If no solution is found, contact Axway Support.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SNET027I"></span>027</p>         </td>
         <td><p>SNET  I MESGSEND  %1(%2) [%3] sending to %4,%5 message: %6 %7</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Information message indicating the transmission of a message.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Access Point name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Message partner</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local request identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Alias of the remote partner</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Copied or distributed transfer indicator.</p>
<p>Possible values:</p>
<ul>
<li>"(copied)"</li>
<li>"(distributed)"</li>
<li>""</li>
</ul>
<p>This parameter is empty for normal transfers, which are not copied or distributed.</p>         </td>
      </tr>
      <tr>
         <td><p>6</p>         </td>
         <td><p>Physical file directory</p>         </td>
      </tr>
      <tr>
         <td><p>7</p>         </td>
         <td><p>Physical file name</p>         </td>
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
         <td><p><span id="SNET028I"></span>028</p>         </td>
         <td><p>SNET  I MESGRECV  %1(%2) [%3] receiving from %4,%5 message: %6 %7</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Information message indicating the reception of a message.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Access Point name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Message partner</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local request identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Alias of the remote partner</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Retrieved message indicator. Copied or distributed transfer indicator.</p>
<p>Possible values:</p>
<ul>
<li>"(copied)"</li>
<li><p>"(retrieved, sent)(copied)” or "(retrieved, received)(copied)"</p></li>
<li>"(distributed)"</li>
<li><p>"(retrieved, sent)(distributed)” or "(retrieved, received)(distributed)"</p></li>
<li>""</li>
<li><p>"(retrieved, sent)” or "(retrieved, received)"</p></li>
</ul>
<p>This parameter is empty for normal transfers, which are not retrieved, copied or distributed.</p>         </td>
      </tr>
      <tr>
         <td><p>6</p>         </td>
         <td><p>Physical file directory</p>         </td>
      </tr>
      <tr>
         <td><p>7</p>         </td>
         <td><p>Physical file name</p>         </td>
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
         <td><p><span id="SNET029E"></span>029</p>         </td>
         <td><p>SNET  E MESGEXCH  %1(%2) [%3] error during message exchange with %4</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Error during message exchange. The recipient may have received the message.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Access Point name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Message partner</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local request identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Alias of the remote partner</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check the messages indicating the cause of the problem.</p>
<p>If no solution is found, contact Axway Support.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SNET030I"></span>030</p>         </td>
         <td><p>SNET  I MESGEXCH  %1(%2) [%3] message exchange with %4 successful</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Information message indicating the success of the message exchange phase.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Access Point name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Message partner</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local request identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Alias of the remote partner</p>         </td>
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
         <td><p><span id="SNET031I"></span>031</p>         </td>
         <td><p>SNET  I QUEUEACQ  %1(%2)  acquired queue %3 session %4</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Information message indicating the acquisition of an SnF queue.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Access Point name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Message partner</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Name of the SnF queue</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>SnF session number</p>         </td>
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
         <td><p><span id="SNET032I"></span>032</p>         </td>
         <td><p>SNET  I QUEUEREL  %1(%2)  released session %3</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Information message indicating the release of a queue identified by its session number.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Access Point name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Message partner</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>SnF session number</p>         </td>
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
         <td><p><span id="SNET033I"></span>033</p>         </td>
         <td><p>SNET  I QUEUEFET  %1(%2) [%3]  fetching file %4 session %5</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Information message indicating an attempt to fetch a file from an SnF queue.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Access Point name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Message partner</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local request identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Local physical file name</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>SnF session number</p>         </td>
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
         <td><p><span id="SNET034I"></span>034</p>         </td>
         <td><p>SNET  I QUEUEACK  %1(%2) [%3]  acknowledge slot session %4</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Information message indicating the acknowledgment of a previously-fetched file.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Access Point name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Message partner</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local request identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>SnF session number</p>         </td>
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
         <td><p><span id="SNET035E"></span>035</p>         </td>
         <td><p>SNET  E QUEUEACQ  %1(%2)  error acquiring queue %3</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>An error occurred during the acquisition of a queue.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Access Point name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Message partner</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Name of the SnF queue</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check that the queue name is correct and the SWIFTNet user has the right to handle the queue.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SNET036E"></span>036</p>         </td>
         <td><p>SNET  E QUEUEREL  %1(%2)  error releasing session %3</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>An error occurred during the release of a queue identified by its session number.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Access Point name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Message partner</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>SnF session number</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>The session may already have been released.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SNET037E"></span>037</p>         </td>
         <td><p>SNET  E QUEUEFET  %1(%2) [%3]  error fetching file %4 session %5</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Error during the attempt to fetch a file from an SnF queue.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Access Point name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Message partner</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local request identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Local physical file name</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>SnF session number</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>The file may already have been fetched by another application.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SNET038E"></span>038</p>         </td>
         <td><p>SNET  E QUEUEACK  %1(%2) [%3]  slot acknowledgment error session %4</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The fetched file cannot be acknowledged.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Access Point name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Message partner</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local request identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>SnF session number</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>None (the transfer will be restarted automatically).</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SNET039I"></span>039</p>         </td>
         <td><p>SNET  I QUEUESTS  %1(%2) SnF session %3 returned status: %4</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Message information indicating the current status of an SnF session received from SWIFT.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Access Point name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Message partner</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>SnF session number</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Session status</p>         </td>
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
         <td><p><span id="SNET040E"></span>040</p>         </td>
         <td><p>SNET  E QUEUESTS  %1(%2) SnF session %3 returned error status: %4</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Error message indicating the current error status of an SnF session received from SWIFT.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Access Point name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Message partner</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>SnF session number</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Session error status</p>         </td>
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
         <td><p><span id="SNET041E"></span>041</p>         </td>
         <td><p>SNET  E APINIERR  %1(%2)  error during access-point initialization: %3</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>An Access Point could not be initialized.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Access Point name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Message partner</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Error description</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check the Remote Site information given in the Access Point name.</p>
<p>Verify the RA and SAG configuration.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SNET042E"></span>042</p>         </td>
         <td><p>SNET  E APCONERR  %1(%2)  access-point configuration error: %3</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Problem with the Access Point configuration.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Access Point name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Message partner</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Error description</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check the Remote Site information given in the Access Point name.</p>
<p>Verify the RA and SAG configuration.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SNET043W"></span>043</p>         </td>
         <td><p>SNET  W APCONWAR  %1(%2)  access-point configuration warning: %3</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Problem encountered when initializing the Access Point.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Access Point name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Message partner</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Error description</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check the Remote Site information given in the Access Point name.</p>
<p>Verify the RA and SAG configuration.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SNET044I"></span>044</p>         </td>
         <td><p>SNET  I SYSMESS %1(%2) %3  system message identified at check-in (looking for Trading Partner)</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Incoming system message.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Access Point name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Message partner</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Type of message</p>         </td>
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
         <td><p><span id="SNET045W"></span>045</p>         </td>
         <td><p>SNET  W QUEUESTS  Swift received %1 (%2) for resource name %3 generated on SNLId %4 at time %5</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Warning message received from SNL indicating that an unsolicited event occurred. Currently there is only a single event, generated when SNL detects that the output session was closed by SWIFT.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Event type</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Event description</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Resource name</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>SNL ID on which the event occurred</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Time when the event occurred</p>         </td>
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
         <td><p><span id="SNET050I"></span>050</p>         </td>
         <td><p>SNET  I SNFDNREQ  %1(%2) [%3] received SnF delivery notification from %4 with status %5</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Information message indicating the receipt of an SnF delivery notification.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Access Point name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Message partner</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local request identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Source of delivery notification (Third Party, Counter Party)</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Status (accepted, rejected, failed)</p>         </td>
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
         <td><p><span id="SNET051I"></span>051</p>         </td>
         <td><p>SNET  I SNFDNUPD  %1(%2) [%3] updating transfer</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Information message indicating the update of a transfer.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Access Point name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Message partner</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
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
         <td><p><span id="SNET052E"></span>052</p>         </td>
         <td><p>SNET  E SNFDNERR  %1(%2) no transfer match for SnF reference %3</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Received SnF delivery notification does not match any existing transfer in the Mailbox. The transfer has been deleted or the Mailbox has been purged.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Access Point name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Message partner</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>SnF reference number</p>         </td>
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
         <td><p><span id="SNET053W"></span>053</p>         </td>
         <td><p>SNET  W SNFDNDPL  %1(%2) [%3] transfer already notified</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Warning message indicating that a transfer notification has already been received (technical duplicate).</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Access Point name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Message partner</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
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
         <td><p><span id="SNET055E"></span>055</p>         </td>
         <td><p>SNET  E XSRVRJCT  %1(%2) [%3] Server rejected the transfer %4</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Incoming transfer rejected by Gateway.</p>
<p>Possible reasons:</p>
<ul>
<li>An unknown partner has sent some unexpected traffic.</li>
<li>The configuration might not be correct.</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Access Point name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Message partner</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local request identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Message ID</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>If this is a configuration issue, review and modify the Trading Partner configuration.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SNET056E"></span>056</p>         </td>
         <td><p>SNET  E XENDRERR  %1(%2) [%3] end reason: %4, end diag: %5, end error: %6</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Generic error message for a transfer that failed.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Access Point name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Message partner</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local request identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Error code number (reason)</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Error code number (diagnostic)</p>         </td>
      </tr>
      <tr>
         <td><p>6</p>         </td>
         <td><p>Error message</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check the messages indicating the cause of the problem.</p>
<p>If no solution is found, contact Axway Support.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SNET060I"></span>060</p>         </td>
         <td><p>SNET  I RCPTSEND  %1(%2) [%3] begin sending to %4, %5 receipt for transfer number [%6]</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>An ack delivery notification request is being sent.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Access Point name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Message partner</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Receipt transfer number</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Remote Trading Partner</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Receipt type (positive/negative)</p>         </td>
      </tr>
      <tr>
         <td><p>6</p>         </td>
         <td><p>Original transfer that is being acknowledged</p>         </td>
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
         <td><p><span id="SNET061I"></span>061</p>         </td>
         <td><p>SNET  I RCPTSNDS  %1(%2) [%3] end sending to %4, %5 receipt for transfer number [%6]</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>An ack delivery notification request has been sent.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Access Point name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Message partner</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Receipt transfer number</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Remote Trading Partner</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Receipt type ( positive/negative)</p>         </td>
      </tr>
      <tr>
         <td><p>6</p>         </td>
         <td><p>Original transfer that is being acknowledged</p>         </td>
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
         <td><p><span id="SNET062E"></span>062</p>         </td>
         <td><p>SNET  E RCPTSNDE  %1(%2) [%3] error sending to %4, %5 receipt for transfer number [%6]</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>An error occurred during the exchange of the ack delivery notification request.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Access Point name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Message partner</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Receipt transfer number</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Remote Trading Partner</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Receipt type (positive/negative)</p>         </td>
      </tr>
      <tr>
         <td><p>6</p>         </td>
         <td><p>Original transfer that is being acknowledged</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>The receipt transfer is automatically retried. If the error persists check traces for more details.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SNET063I"></span>063</p>         </td>
         <td><p>SNET  I RCPTRECV  %1(%2) begin receiving from %3, %4 receipt for transfer reference %5</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>An ack delivery notification request has been received and accepted into the Mailbox.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Access Point name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Message partner</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Receipt transfer number</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Remote Trading Partner</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>SNL transfer reference of the original transfer</p>         </td>
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
         <td><p><span id="SNET064I"></span>064</p>         </td>
         <td><p>SNET  I RCPTRCVS  %1(%2)%3%4%5 end receiving from %6, %7 receipt for transfer number [%8]</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>An ack delivery notification request has been received.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Access Point name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Message partner</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Receipt transfer number, if Trading Partner found</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Receipt transfer number, if Trading Partner found</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Receipt transfer number, if Trading Partner found</p>         </td>
      </tr>
      <tr>
         <td><p>6</p>         </td>
         <td><p>Remote Trading Partner</p>         </td>
      </tr>
      <tr>
         <td><p>7</p>         </td>
         <td><p>Receipt type (positive/negative)</p>         </td>
      </tr>
      <tr>
         <td><p>8</p>         </td>
         <td><p>Original transfer that has been acknowledged</p>         </td>
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
         <td><p><span id="SNET065E"></span>065</p>         </td>
         <td><p>SNET  E RCPTRCVE  %1(%2) error occurred while receiving %3 receipt from %4</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>An error has occurred during the ack delivery notification exchange.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Access Point name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Message partner</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Receipt type (positive/negative)</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Remote Trading Partner</p>         </td>
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
         <td><p><span id="SNET069I"></span>069</p>         </td>
         <td><p>SNET  I RCPTACPT  %1(%2)%3%4%5 %6 receipt from %7 has been %8%9</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>An acknowledgment delivery notification protocol request has been received. Check to see if is accepted in the Mailbox.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Access Point name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Message partner</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Receipt transfer number, if Trading Partner found</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Receipt transfer number, if Trading Partner found</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Receipt transfer number, if Trading Partner found</p>         </td>
      </tr>
      <tr>
         <td><p>6</p>         </td>
         <td><p>Receipt type (positive/negative)</p>         </td>
      </tr>
      <tr>
         <td><p>7</p>         </td>
         <td><p>Remote Trading partner</p>         </td>
      </tr>
      <tr>
         <td><p>8</p>         </td>
         <td><p>Status (accepted/rejected/rejected as duplicated)</p>         </td>
      </tr>
      <tr>
         <td><p>9</p>         </td>
         <td><p>Reason (present if Status is rejected)</p>         </td>
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
         <td><p><span id="SNET070E"></span>070</p>         </td>
         <td><p>SNET E ASPCHKERR %1(%2) [%3] ASP Check to validate outgoing request parameters and to get RMA feature failed. Reason: %4</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Validation of outgoing request parameters against service profile failed or checks if RMA filtering required failed. The reason for the error should be in the log.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Access Point name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Message partner</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local request identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Message containing failure reason</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>If there is an error related to incorrect request parameters usage, correct the problem and try again to initiate the transfer. For other failure reason, contact <span class="mc-variable axway_variables.Company_Name variable">Axway</span> support.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><span id="SNET071I"></span><span class="bold_in_para">071</span>         </td>
         <td><p>SNET I ASPCHKDEF %1(%2) [%3] ASP Check to validate outgoing request parameters and to get RMA feature successful, but the default profile was used %4</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Information message indicating outgoing transfer parameters were successfully checked against the default service profile, including if RMA filtering is required by ASP for current transfer.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Access Point name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Message partner</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local request identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Service profile is requesting RMA filtering or not.</p>
<p>Possible values:</p>
<ul>
<li>RMA check required</li>
<li>RMA check required (in trial period)</li>
<li>RMA check not required</li>
</ul>
<p>This parameter is empty if RMA check is not enabled from SWIFTNet configuration.</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Because the default service profile was used, you must ensure <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> is using an updated ASP package. Meanwhile, it is possible SWIFT may have added the profile for the requested service to a more recent ASP package.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SNET072I"></span>072</p>         </td>
         <td><p>SNET I ASPLDSTS Swift ASP package %1 done. Files: %2, Date: %3, Start: %4, Stop: %5</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Information message indicating ASP package was loaded successfully.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Operation applied to ASP package: load or reload</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Number of service profiles loaded or reloaded</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Date when load or reload operation occurred</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Time when the load or reload operation started</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Time when the load or reload operation ended</p>         </td>
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
         <td><p><span id="SNET073W"></span>073</p>         </td>
         <td><p>SNET W ASPLDSTS Swift ASP package %1 done with warning %2. Files: %3, Date: %4, Start: %5, Stop: %6</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>ASP package was loaded or reloaded, but a warning was raised during the operation.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Operation applied to ASP package: load or reload</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Warning description</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Number of service profiles loaded or reloaded</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td>Date when load or reload operation occurred         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Time when the load or reload operation started</p>         </td>
      </tr>
      <tr>
         <td><p>6</p>         </td>
         <td><p>Time when the load or reload operation ended</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Try to find the cause of the error and correct it.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SNET074E"></span>074</p>         </td>
         <td><p>SNET E ASPLDSTS Swift ASP package %1 failed. Reason: %2, ErrNo: %3, Date: %4, Start: %5, Stop: %6, Previous active load: %7</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>ASP package could not be loaded or reloaded because an error occurred.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Operation applied to ASP package: load or reload</p>         </td>
      </tr>
      <tr>
         <td><p><strong>2</strong></p>         </td>
         <td>Failure reason         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Error code number</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Date when load or reload operation occurred</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Time when the load or reload operation started</p>         </td>
      </tr>
      <tr>
         <td>6         </td>
         <td>Time when the load or reload operation ended         </td>
      </tr>
      <tr>
         <td><p>7</p>         </td>
         <td>Date and time of the last active load         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Try to find the cause of the error and correct it.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SNET075E"></span>075</p>         </td>
         <td><p>SNET E ASPLDINI Swift ASP package %1 initialization failed. Previous active load: %2</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The initialization operation for loading or reloading the ASP package failed.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Operation applied to ASP package: load or reload</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Date and time of the last active load</p>         </td>
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
         <td><p><span id="SNET076I"></span>080</p>         </td>
         <td><p>SNET  I OPOUTCH  %1(%2) opened output channel %3 for queue %4 session %5</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Information message indicating the success of the opening of an output channel.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Access Point name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Message partner</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Output channel name</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Queue name</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>SnF session number</p>         </td>
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
         <td><p><span id="SNET077W"></span>081</p>         </td>
         <td><p>SNET  W OPOUTCHR  %1(%2) output channel %3 opening for queue %4 request rejected</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Warning message indicated that the request for opening an output channel has been rejected because the queue is in exclusive mode and there is an active output session on it.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Access Point name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Message partner</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Output channel name</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Queue name</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Possible actions:</p>
<ul>
<li>Identify messaging interface already using the queue</li>
<li>Change queue sharing mode</li>
<li>Use another queue</li>
</ul>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SNET078E"></span>082</p>         </td>
         <td><p>SNET  E OPOUTCHE  %1(%2) error opening output channel %3 for queue %4</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>An error occurred during the opening of an output channel.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Access Point name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Message partner</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Output channel name</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Queue name</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check that the channel and queue name are correct and the SWIFTNet user has the right to handle them.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SNET079I"></span>083</p>         </td>
         <td><p>SNET  I CLOUTCH  %1(%2) released session %3</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Information message indicating the releasing of a session.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Access Point name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Message partner</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>SnF session number</p>         </td>
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
         <td><p><span id="SNET080E"></span>084</p>         </td>
         <td><p>SNET  E CLOUTCHE  %1(%2) error releasing session %3</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Error message indicating that an error occurred while releasing session.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Access Point name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Message partner</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>SnF session number</p>         </td>
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
         <td><p><span id="SNET081E"></span>085</p>         </td>
         <td><p>SNET  E XERRSND1  %1(%2) [%3] SnFInputTime could not be saved (not received or internal error occurred)</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>SnFInputTime was not received from SWIFT or an internal error occurred while saving it.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Access Point name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Message partner</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local request identifier (number)</p>         </td>
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
         <td><p><span id="SNET082W"></span>086</p>         </td>
         <td><p>SNET  W OVDUETM %1(%2) [%3] Transfer is overdue, due date was: %4</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Overdue transfer warning message.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Access Point name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Message partner</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Transfer ID</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Due time</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>No action required.</p>
<p>SWIFT detected that a file or message was not delivered before the specified due time (OverdueTime specified by the sender).</p>
<p>SWIFT sends this warning message to the sender to inform him that the receiver has not yet received the file or message.</p>
<p>This warning message provides no information as to whether the transfer will or will not be made.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SNET083I"></span>087</p>         </td>
         <td><p>SNET  I XFAUTH  %1(%2) [%3] Transfer is authorised by a third party</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Information message indicating an authorization of the transfer by a third party.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Access Point name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Message partner</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
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
         <td><p><span id="SNET084W"></span>088</p>         </td>
         <td><p>SNET  W XFAUTH  %1(%2) [%3] Transfer is refused by a third party</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Warning message indicating a refusal of the transfer by a third party.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Access Point name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Message partner</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
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
         <td><p><span id="SNET085E"></span>089</p>         </td>
         <td><p>SNET  E SMDNERR  %1(%2) no transfer match for System Message reference %3</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>No transfer found in Mailbox for the incoming System Message. Transfer referenced by the system message could have been deleted or broken routing rules inside the SAG.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Access Point name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Message partner</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td>Original SNL reference         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Verify the SAG routing configuration.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SNET091I"></span>091</p>         </td>
         <td><p>SNET  I OPINCH  %1(%2) opening input channel %3, window=%4, force=%5</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Information message indicating the opening of an input channel.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Access Point name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Message partner</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Input channel name</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Input session suggested window size</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Force opening of input channel</p>         </td>
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
         <td><p><span id="SNET092I"></span>092</p>         </td>
         <td><p>SNET  I OPINCHO  %1(%2) input channel %3 opened, window=%4, nextInputSeq=%5</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Information message indicating the success of the opening of an input channel</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Access Point name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Message partner</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Input channel name</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Input session window size</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Input session first available sequence number</p>         </td>
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
         <td><p><span id="SNET093E"></span>093</p>         </td>
         <td><p>SNET  E OPINCHE  %1(%2) open-error for input channel %3</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Error message indicating a failure while opening an input channel</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Access Point name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Message partner</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Input channel name</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check that the input channel name already exists. If the channel is opened without the force parameter, it might be already opened or locked.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SNET094I"></span>094</p>         </td>
         <td><p>SNET   I CLINCH %1(%2) closing input channel %3, token=%4</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Information message indicating the closure of an input channel.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Access Point name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Message partner</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Input channel name</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Input session token</p>         </td>
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
         <td><p><span id="SNET095I"></span>095</p>         </td>
         <td><p>SNET  I CLINCHO  %1(%2) input channel %3 closed, token=%4</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Information message indicating the success of the closure of an input channel</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Access Point name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Message partner</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Input channel name</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Input session token</p>         </td>
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
         <td><p><span id="SNET096E"></span>096</p>         </td>
         <td><p>SNET  E CLINCHE  %1(%2) close error for input channel %3, token=%4</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Error message indicating a failure while closing an input channel</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Access Point name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Message partner</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Input channel name</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Input session token</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Resolve gaps if any. It might also already have been closed</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SNET097I"></span>097</p>         </td>
         <td><p>SNET  I CRINCHRQ  %1(%2) creating input channel %3</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Input channel was scheduled for creation.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Access Point name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Message partner</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td>Input channel name         </td>
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
         <td><p><span id="SNET098I"></span>098</p>         </td>
         <td><p>SNET   I CRINCHCF  %1(%2) input channel %3 created</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>An input channel was created.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Access Point name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Message partner</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Input channel name</p>         </td>
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
         <td><p><span id="SNET099E"></span>099</p>         </td>
         <td><p>SNET  E CRINCHER  %1(%2) error creating input channel %3: %4</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Creation of an input channel failed.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Access Point name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Message partner</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Input channel name</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Error message</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check whether the channel name is valid and complies with SWIFT specifications. Also, the input channel might already exist.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SNET100E"></span>100</p>         </td>
         <td><p>SNET  E SWERROR  %1(%2) SwGbl:Status Severity=%3, Code=%4, Text=%5</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Display content of SwGbl:Status element received from SWIFT, indicating failure.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Access Point name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Message partner</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Severity of the error</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Error code</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Error description</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check the messages indicating the cause of the problem.</p>
<p>If no solution is found, contact Axway Support.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SNET101I"></span>101</p>         </td>
         <td><p>SNET  I TRACE  %1</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Trace message.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Trace message</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Use this message to trace a SWIFTNet transfer.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SNET102E"></span>102</p>         </td>
         <td><p>SNET  E TRACE  %1</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Trace message.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Trace message</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Use this message to trace a SWIFTNet transfer.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SNET103W"></span>103</p>         </td>
         <td><p>SNET  W TRACE  %1</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Trace message.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Trace message</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Use this message to trace a SWIFTNet transfer.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SNET104E"></span>104</p>         </td>
         <td><p>SNET  E TRACEX  %1(%2) [%3] %4</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Trace message</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Access Point name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Message partner</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local request identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Trace message</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Use this message to trace a SWIFTNet transfer.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SNET110I"></span>110</p>         </td>
         <td><p>SNET  I SYSRECMS  System recovery detection started manually by user</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Information message indicating that the user has started system recovery detection manually.</p>         </td>
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
         <td><p><span id="SNET111I"></span>111</p>         </td>
         <td><p>SNET  I SYSRECMS  System recovery detection started automatically</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Information message indicating that system recovery detection started automatically. This happens every time Gateway opens an output session, after a restart of Gateway, or after a potential SWIFT crash.</p>         </td>
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
         <td><p><span id="SNET112W"></span>112</p>         </td>
         <td><p>SNET  W SYSRECIP  System recovery detection already in progress, new manual request ignored</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Warning message indicating that system recovery detection is already in progress.</p>         </td>
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
         <td><p><span id="SNET113W"></span>113</p>         </td>
         <td><p>SNET  W SYSRECPC  Possible system recovery detected, inconclusive resolution due to insufficient data</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Gateway stores a list of previous SWIFT crashes to help detect a new one. If Gateway is started for the first time, or was offline for a considerable amount of time (weeks, maybe months), it would have no data or the data would be obsolete. This message does not mean there was a SWIFT crash but rather that the detection was inconclusive.</p>         </td>
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
         <td><p><span id="SNET114E"></span>114</p>         </td>
         <td><p>SNET  E SYSRECAG  System recovery detection aborted: no active end-points (sites) found to schedule detection</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>System recovery detection could not be scheduled because no active end-points (Sites) have been found.</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Make sure you have at least one active end-point (Site) to schedule system recovery detection.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SNET115E"></span>115</p>         </td>
         <td><p>SNET  E SYSRECAS  System recovery detection aborted: failed to get system recovery information from Swift</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>An error occurred when Gateway asked SWIFT for previous crash timestamps (last replication time). This might be the result of a problem with SWIFT, SAG, SNL, network etc.</p>         </td>
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
         <td><p><span id="SNET116I"></span>116</p>         </td>
         <td><p>SNET  I SYSRECSN  System recovery detection ended: no action required (no transfer to recover)</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Information message indicating that system recovery detection ended and no action is required (no crash occurred).</p>         </td>
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
         <td><p><span id="SNET117W"></span>117</p>         </td>
         <td><p>SNET  W SYSRECFS  System recovery confirmed, recovery procedure initiated for Store-and-Forward transfers after %1</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Warning message indicating that a system recovery procedure has been initiated for Store-and-Forward transfers that were sent after the last replication timestamp.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Last replication time</p>         </td>
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
         <td><p><span id="SNET118E"></span>118</p>         </td>
         <td><p>SNET  E SYSRECAF  System recovery procedure aborted: no active end-points (sites) found to schedule transfer flagging</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>System recovery procedure was aborted because no active end-points (Sites) were found to schedule transfer flagging (identify transfers that might have been lost in the crash).</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Make sure you have at least one active end-point (Site) to schedule transfer flagging during a system recovery procedure.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SNET119E"></span>119</p>         </td>
         <td><p>SNET  E SYSRECEF  System recovery procedure aborted: internal error or corrupted data files</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>System recovery procedure was aborted because of an internal error or corrupted data files.</p>         </td>
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
         <td><p><span id="SNET120I"></span>120</p>         </td>
         <td><p>SNET  I SYSRECXT  System recovery procedure ended: %1 transfers were marked by system recovery detection</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Message information indicating the ending of the system recovery procedure and the number of transfers marked by the system recovery detection.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Number of transfers</p>         </td>
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
         <td><p><span id="SNET121I"></span>121</p>         </td>
         <td><p>SNET  I MESGSNDS  %1(%2) [%3] sending to %4,%5 message: %6 %7 with sequence number %8</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Information message indicating the transmission of a message through an input channel.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Access Point name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Message partner</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local request identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Alias of the remote partner</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Remote Trading Partner</p>         </td>
      </tr>
      <tr>
         <td><p>6</p>         </td>
         <td><p>Physical file directory</p>         </td>
      </tr>
      <tr>
         <td><p>7</p>         </td>
         <td><p>Physical file name</p>         </td>
      </tr>
      <tr>
         <td><p>8</p>         </td>
         <td><p>Input session sequence number</p>         </td>
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
         <td><p><span id="SNET122W"></span>122</p>         </td>
         <td><p>SNET  W MESGEXGP  %1(%2) [%3] message exchange with %4 successful but located after a gap</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Warning message indicating the success of the message exchange phase although the message is located after a gap.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Access Point name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Message partner</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local request identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Alias of the remote partner</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>This message can be displayed when several messages are handled simultaneously. The gap will be solved by itself. In the case that a transfer has not been accepted by the input channel, the gap will be solved when the transfer is canceled or when the Site or the product is restarted.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SNET123I"></span>123</p>         </td>
         <td><p>SNET   I OPINCH  %1(%2) resolving gap for input channel %3, sequence=%4</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Information message indicating the resolution of a gap</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Access Point name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Message partner</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Input channel name</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Input session sequence number</p>         </td>
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
         <td><p><span id="SNET124I"></span>124</p>         </td>
         <td><p>SNET  I OPINCHO  %1(%2) resolve gap succeeds for input channel %3, sequence=(%4,%5)</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Information message indicating the success of the resolution of a gap</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Access Point name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Message partner</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Input channel name</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>First input session sequence number</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Last input session sequence number</p>         </td>
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
         <td><p><span id="SNET125E"></span>125</p>         </td>
         <td><p>SNET  E OPINCHE  %1(%2) resolve gap fails for input channel %3, sequence=%4</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Error message indicating the failure of the resolution of a gap</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Access Point name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Message partner</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Input channel name</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Input session sequence number</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>The input channel might be closed or the gap might have been already resolved.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SNET126W"></span>126</p>         </td>
         <td><p>SNET  W PDTRDUP  %1(%2) [%3] Duplicated incoming request, with message id "%4", ignored</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Warning message indicating that an incoming request which was detected as being duplicated was ignored because the configuration option <strong>Accept possible duplicate transfers</strong> was disabled.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Access Point name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Message partner</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local request identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Message ID</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>If you want the incoming requests detected as duplicated to be accepted, enable the configuration option <strong>Accept possible duplicate transfers</strong>.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SNET127W"></span>127</p>         </td>
         <td><p>SNET  W PDTRACC  %1(%2) [%3] Duplicated incoming request, with message id "%4", accepted. The configuration option "accept_possible_duplicate" is set</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Warning message indicating that an incoming request which was detected as being duplicated was accepted because the configuration option <strong>Accept possible duplicate transfers</strong> was enabled.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Access Point name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Message partner</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local request identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Message ID</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>If you want the incoming requests detected as duplicated to be ignored, disable the configuration option <strong>Accept possible duplicate transfers</strong>.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SNET128I"></span>128</p>         </td>
         <td><p>SNET  I PDTRNFE  %1(%2) [%3] Duplicated SnF request. No fetch, acknowledging slot session</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Information message indicating that the incoming SWIFT SnF request is duplicated (redelivered message). Therefore no file fetching operation is performed, but the acknowledgment is sent.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Access Point name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Message partner</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
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
         <td><p><span id="SNET129W"></span>129</p>         </td>
         <td><p>SNET  W PDTREID  %1(%2) [%3] Incoming request with empty message id accepted, sender considers it might be a duplicate, but message id is unknown</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Warning message indicating that an incoming request with empty message ID was received and accepted. However, it was considered as being a possible duplicate message on the <em>sender</em> side, which does not have the message ID information.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Access Point name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Message partner</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local request identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Manually check if the incoming transfer is duplicated (file size, timestamp).</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SNET130W"></span>130</p>         </td>
         <td><p>SNET  W SYSMESS  %1(%2) [%3] Transfer authorisation status was already updated</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Warning message indicating that a transfer authorization status was already updated after receiving a (previous) refusal system notification or authorization system notification.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Access Point name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Message partner</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
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
         <td><p><span id="SNET131W"></span>131</p>         </td>
         <td><p>SNET  W TECHDUP  %1(%2) [%3] Duplicated incoming request. Is a Swift redelivered message (technical duplicate), ignored</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Warning message indicating that an incoming SnF request was detected as duplicated but ignored by Gateway because the message was redelivered by SWIFT.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Access Point name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Message partner</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
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
         <td><p><span id="SNET132I"></span>132</p>         </td>
         <td><p>SNET I ASPCHKOK %1(%2) [%3] ASP Check to validate outgoing request parameters and to get RMA feature successful %4</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Information message indicating outgoing transfer parameters were checked successfully against the service profile, including if RMA filtering is required by ASP for current transfer.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Access Point name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Message partner</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local request identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Service profile is requesting RMA filtering or not</p>
<p>Possible values:</p>
<ul>
<li>RMA check required</li>
<li>RMA check required (in trial period)</li>
<li>RMA check not required</li>
</ul>
<p>This parameter is empty if RMA check is not enabled from SWIFTNet configuration.</p>         </td>
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
         <td><p><span id="SNET133I"></span>133</p>         </td>
         <td><p>SNET I ASPRMAOK %1(%2) ASP Check to get RMA feature for incoming request with message id %3 successful %4</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Information message indicating that the ASP check that queries if RMA filtering is required by ASP for current transfer was successful.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Access Point name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Message partner</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Incoming request message ID</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Service profile is requesting RMA filtering or not.</p>
<p>Possible values:</p>
<ul>
<li>RMA check required</li>
<li>RMA check required (in trial period)</li>
<li>RMA check not required</li>
</ul>         </td>
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
         <td><p><span id="SNET134I"></span>134</p>         </td>
         <td><p>SNET I ASPRMADEF %1(%2) ASP Check to get RMA feature for incoming request with message id %3 successful, but the default profile was used %4</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Information message indicating that the ASP check that queries if RMA filtering is required by ASP was successful, but the default profile was used to perform the check.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Access Point name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Message partner</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Incoming request message ID</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Service profile is requesting RMA filtering or not.</p>
<p>Possible values:</p>
<ul>
<li>RMA check required</li>
<li>RMA check required (in trial period)</li>
<li>RMA check not required</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Because the default service profile was used, ensure <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> is using an updated ASP package. Meanwhile, SWIFT may have added the profile for the service in the latest ASP package.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SNET135E"></span>135</p>         </td>
         <td><p>SNET E ASPRMAERR %1(%2) ASP Check to get RMA feature for incoming request with message id %3 failed. Reason: %4</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Error occurred while checking if the service profile requires RMA filtering for incoming request.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Access Point name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Message partner</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Incoming request message ID</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Message containing failure reason</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check the failure reason and try to fix the problem. If not possible, contact <span class="mc-variable axway_variables.Company_Name variable">Axway</span> support.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SNET136W"></span>136</p>         </td>
         <td><p>SNET W ASPNRRERR %1(%2) [%3] ASP Check for non repudiation parameter value used in response failed. Reason: %4</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Warning message indicating validation of the non repudiation value used in response failed, followed by failure reason.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Access Point name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Message partner</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local request identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Message containing failure reason</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>If the error is related to incorrect non repudiation value, contact <span class="mc-variable axway_variables.Company_Name variable">Axway</span> support. <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> is using in response the non repudiation value received in the incoming request, and this normally conforms to service profile.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SNET137I"></span>137</p>         </td>
         <td><p>SNET I ASPNRROK %1(%2) [%3] ASP Check for non repudiation parameter value used in response successful</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Information message indicating the value of non repudiation parameter used in response if conforming to service profile</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Access Point name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Message partner</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
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
         <td><p><span id="SNET138I"></span>138</p>         </td>
         <td><p>SNET I ASPNRRDEF %1(%2) [%3] ASP Check for non repudiation parameter value used in response successful, but the default profile was used</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Information message indicating the value of non repudiation parameter used in response if conforming to default service profile.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Access Point name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Message partner</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local request identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Because the default service profile was used, ensure <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> is using an updated ASP package. Meanwhile, SWIFT may have added the profile for the service in the latest ASP package.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SNET140I"></span>140</p>         </td>
         <td><p>SNET I ASPDSBLD Swift ASP &amp; RMA disabled in global configuration</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The ASP/RMA check is disabled.</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>If you want to enable ASP checking with or without RMA checking, update the SWIFTNet configuration.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SNET141I"></span>141</p>         </td>
         <td><p>SNET I SNFDNRR %1(%2) [%3] received SnF delivery notification from %4 with status %5. Reason: %6</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>A Store-and-Forward delivery notification was received.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Access Point name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Message partner</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local request identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><strong>4</strong>         </td>
         <td><p>Remote partner type:</p>
<ul>
<li>Counter-party</li>
<li>Third-party</li>
<li>Recipient</li>
</ul>         </td>
      </tr>
      <tr>
         <td><strong>5</strong>         </td>
         <td>Delivery notification status         </td>
      </tr>
      <tr>
         <td><strong>6</strong>         </td>
         <td>Delivery notification description         </td>
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
         <td><p><span id="SNET142I"></span>142</p>         </td>
         <td><p>SNET I SUDEVTREP %1(%2) [%3] received Undelivered Traffic Report (xsys.005.001.01) with SnFReference %4. Page number: %5; is last page: %6; execution status: %7</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Information message regarding the receival of an Undelivered Traffic Report system message (xsys.005.001.01)</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Access Point name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Message partner</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local request identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><strong>4</strong>         </td>
         <td>The Store-and-Forward reference of the Undelivered Traffic Request message which generated the Report         </td>
      </tr>
      <tr>
         <td><strong>5</strong>         </td>
         <td>Page number         </td>
      </tr>
      <tr>
         <td><strong>6</strong>         </td>
         <td>True if this is the last page of the report         </td>
      </tr>
      <tr>
         <td><strong>7</strong>         </td>
         <td>Success or Failure         </td>
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
         <td><p><span id="SNET143I"></span>143</p>         </td>
         <td><p>SNET W UUDEVTREP %1(%2) [%3] received Unsolicited Undelivered Traffic Report (xsys.005.002.01) generated after %4. ReportOption: %5; Page number: %6; is last page: %7; execution status: %8</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Information message regarding the receival of an Undelivered Traffic Report system message (xsys.005.001.01)</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Access Point name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Message partner</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local request identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><strong>4</strong>         </td>
         <td>“Cold Start” if ReportOption is “CS”, “unknown event” otherwise         </td>
      </tr>
      <tr>
         <td><strong>5</strong>         </td>
         <td>Report Option (“CS”)         </td>
      </tr>
      <tr>
         <td><strong>6</strong>         </td>
         <td>Page number         </td>
      </tr>
      <tr>
         <td><strong>7</strong>         </td>
         <td>True if this is the last page of the report         </td>
      </tr>
      <tr>
         <td><strong>8</strong>         </td>
         <td>Success or Failure         </td>
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
         <td><p><span id="SNET150E"></span>150</p>         </td>
         <td><p>SNET E RMACFGE RMA userexit configuration error: %1</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Error occurred while loading the RMA user exit configuration file.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Error description</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Make sure the full path and file name of the RMA user exit configuration file is specified, the file exists and the content is valid.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SNET151E"></span>151</p>         </td>
         <td><p>SNET E RMALFAIL RMA userexit library load failed: %1</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Error occurred while loading the RMA user exit library.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Error description</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Make sure the full path and file name of the RMA user exit library file is specified, the library exists and is the correct version.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SNET152E"></span>152</p>         </td>
         <td><p>SNET E RMAIFAIL RMA userexit implementation init failed: %1</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Error occurred while initializing the implementation of RMA user exit library.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Error description</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check the messages indicating the cause of the problem. Contact <span class="mc-variable axway_variables.Company_Name variable">Axway</span> support if no solution is found.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SNET153E"></span>153</p>         </td>
         <td><p>SNET E RMAUFAIL RMA userexit library unload failed: %1</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Error occurred while unloading the RMA user exit library.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Error description</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check the messages indicating the cause of the problem. Contact <span class="mc-variable axway_variables.Company_Name variable">Axway</span> support if no solution is found.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SNET154I"></span>154</p>         </td>
         <td><p>SNET I RMACKOKS %1(%2) Check RMA authorization-to-send for incoming request with message id %3: valid authorization found</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>RMA authorization check was performed by RMA user exit for the incoming request. Valid authorization was found to send.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Access Point name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Message partner</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Incoming request message ID</p>         </td>
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
         <td><p><span id="SNET155I"></span>155</p>         </td>
         <td><p>SNET I RMACKOKR %1(%2) Check RMA authorization-to-receive for incoming request with message id %3: valid authorization found</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>RMA authorization check was performed by RMA user exit for the incoming request. Valid authorization was found to receive.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Access Point name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Message partner</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Incoming request message ID</p>         </td>
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
         <td><p><span id="SNET156E"></span>156</p>         </td>
         <td><p>SNET E RMACKFALS %1(%2) Check failure for RMA authorization-to-send for incoming request with message id %3. Reason: %4 (%5)</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>RMA authorization-to-send check was performed by RMA user exit for the incoming request, but the check failed.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Access Point name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Message partner</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Incoming request message ID</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Error description (reason for the check failure - optional)</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Error code message</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check the messages indicating the cause of the problem. Contact <span class="mc-variable axway_variables.Company_Name variable">Axway</span> support if no solution is found.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SNET157E"></span>157</p>         </td>
         <td><p>SNET E RMACKFALR %1(%2) Check failure for RMA authorization-to-receive for incoming request with message id %3. Reason: %4 (%5)</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>RMA authorization-to-receive check was performed by RMA user exit for the incoming request, but the authorization check failed.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Access Point name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Message partner</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Incoming request message ID</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Error description (reason for the check failure - optional)</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Error code message</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check the messages indicating the cause of the problem. Contact <span class="mc-variable axway_variables.Company_Name variable">Axway</span> support if no solution is found.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SNET158W"></span>158</p>         </td>
         <td><p>SNET W RMAFAILTP %1(%2) RMA authorization validation failed in trial period, but stop unauthorized traffic in trial is not set, for incoming request with message id %3</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>RMA authorization check was performed by RMA user exit in trial period. The check failed, but the configuration option for stopping the unauthorized traffic in trial period was disabled and the transfer was authorized.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Access Point name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Message partner</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Incoming request message ID</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Enable the configuration option for stopping the unauthorized traffic in trial period if you want to reject the transfer requests for which the RMA authorization check failed.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SNET159I"></span>159</p>         </td>
         <td><p>SNET I RMACKOKTS %1(%2) [%3] Check RMA authorization-to-send for outgoing request: valid authorization found</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>RMA authorization check was performed by RMA user exit for the outgoing request. Valid authorization to send was found.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Access Point name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Message partner</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
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
         <td><p><span id="SNET160I"></span>160</p>         </td>
         <td><p>SNET I RMACKOKTR %1(%2) [%3] Check RMA authorization-to-receive for outgoing request: valid authorization found</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>RMA authorization check was performed by RMA user exit for the outgoing request. Valid authorization to receive was found.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Access Point name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Message partner</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
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
         <td><p><span id="SNET161E"></span>161</p>         </td>
         <td><p>SNET E RMACKFLTS %1(%2) [%3] Check failure for RMA authorization-to-send for outgoing request. Reason: %4 (%5)</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>RMA authorization-to-send check was performed by RMA user exit for the outgoing request, but the authorization check failed.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Access Point name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Message partner</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local request identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Error description (reason for the check failure - optional)</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Error code message</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check the messages indicating the cause of the problem. Contact <span class="mc-variable axway_variables.Company_Name variable">Axway</span> support if no solution is found.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SNET162E"></span>162</p>         </td>
         <td><p>SNET E RMACKFLTS %1(%2) [%3] Check failure for RMA authorization-to-receive for outgoing request. Reason: %4 (%5)</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>RMA authorization-to-send check was performed by RMA user exit for the outgoing request, but the authorization check failed.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Access Point name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Message partner</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local request identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Error description (reason for the check failure - optional)</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Error code message</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check the messages indicating the cause of the problem. Contact <span class="mc-variable axway_variables.Company_Name variable">Axway</span> support if no solution is found.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SNET163W"></span>163</p>         </td>
         <td><p>SNET W RMAKOTRT %1(%2) [%3] RMA authorization validation failed in trial period, but stop unauthorized traffic in trial is not set; processing will continue</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>RMA authorization check was performed by RMA user exit in trial period. The check failed, but the configuration option for stopping the unauthorized traffic in trial period was disabled and the transfer request was authorized (default behavior).</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Access Point name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Message partner</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local request identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Enable the configuration option for stopping the unauthorized traffic in trial period if you want to reject the transfer requests for which the RMA authorization check failed.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SNET170I"></span>170</p>         </td>
         <td><p>SNET I DELINCHRQ %1(%2) deleting input channel %3</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Input channel was scheduled for deletion</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Access Point name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Message partner</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Input channel name</p>         </td>
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
         <td><p><span id="SNET171I"></span>171</p>         </td>
         <td><p>SNET I DELINCHCF %1(%2) input channel %3 deleted</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Input channel was deleted.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Access Point name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Message partner</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Input channel name</p>         </td>
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
         <td><p><span id="SNET172E"></span>172</p>         </td>
         <td><p>SNET E DELINCHER %1(%2) error deleting input channel %3 : %4</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Delete of input channel failed.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Access Point name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Message partner</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Input channel name</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Error message</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check whether the channel name is valid and complies with SWIFT specifications. Also, the input channel might be open.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SNET180I"></span>180</p>         </td>
         <td><p>SNET I CREAOCRQ %1(%2) creating output channel %3</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Output channel was scheduled for creation.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Access Point name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Message partner</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Output channel name</p>         </td>
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
         <td><p><span id="SNET181I"></span>181</p>         </td>
         <td><p>SNET I CREAOCOK %1(%2) output channel %3 successfully created</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Output channel was created.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Access Point name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Message partner</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Output channel name</p>         </td>
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
         <td><p><span id="SNET182E"></span>182</p>         </td>
         <td><p>SNET E CREAOCRQF %1(%2) error creating output channel %3. Reason: %4</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Output channel was not created.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Access Point name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Message partner</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Output channel name</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Error message</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check whether the channel name is valid and complies with SWIFT specifications. Also, the output channel might be already created.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SNET183I"></span>183</p>         </td>
         <td><p>SNET I DELOCRQ %1(%2) deleting output channel %3</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Output channel was scheduled for deletion</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Access Point name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Message partner</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Output channel name</p>         </td>
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
         <td><p><span id="SNET184I"></span>184</p>         </td>
         <td><p>SNET I DELOCOK %1(%2) output channel %3 successfully deleted</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Output channel was deleted.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Access Point name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Message partner</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Output channel name</p>         </td>
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
         <td><p><span id="SNET185E"></span>185</p>         </td>
         <td><p>SNET E DELOCFAIL %1(%2) error deleting output channel %3. Reason: %4</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Output channel was scheduled for creation.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Access Point name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Message partner</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Output channel name</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Error message</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check whether the channel name is valid and complies with SWIFT specifications. The output channel might be open or does not exist.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SNET190W"></span>190</p>         </td>
         <td><p>SNET W OPOCDUP %1(%2) Open output channel %3 (queue %4) failed, an output session already exists or broken</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>An open output channel operation failed because an output session already was opened or an error occurred in the output session management mechanism.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Access Point name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Message partner</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Output channel name</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Queue name</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check whether the output channel can be used for Swift communication. Contact <span class="mc-variable axway_variables.Company_Name variable">Axway</span> support if no solution is found.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SNET191W"></span>191</p>         </td>
         <td><p>SNET W CLOCMISS %1(%2) Close output channel %3 (queue %4) failed, an output session does not exist or broken</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>A close output channel operation failed because an output session was not opened previously or an error occurred in the output session management mechanism</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Access Point name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Message partner</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Output channel name</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Queue name</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check whether the output channel is closed. Contact <span class="mc-variable axway_variables.Company_Name variable">Axway</span> support if no solution is found.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SNET192W"></span>192</p>         </td>
         <td><p>SNET W ACQQDUP %1(%2) Acquire queue %3 failed, an output session already exists or broken</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>An acquire queue operation failed because an output session already was opened or an error occurred in the output session management mechanism</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Access Point name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Message partner</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Queue name</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check whether the queue can be used for Swift communication. Contact <span class="mc-variable axway_variables.Company_Name variable">Axway</span> support if no solution is found.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SNET193W"></span>193</p>         </td>
         <td><p>SNET W RELQMISS %1(%2) Release queue %3 failed, an output session does not exist or broken</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>A release queue operation failed because an output session was not opened previously or an error occurred in the output session management mechanism</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Access Point name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Message partner</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Queue name</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check whether the queue is released. Contact <span class="mc-variable axway_variables.Company_Name variable">Axway</span> support if no solution is found.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SNET194E"></span>194</p>         </td>
         <td><p>SNET E MIXQCERR %1(%2) Conflicting declaration for %3. Already declared with %4 at end point %5</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Conflicting situation generated by a double declaration of a queue or output channel.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Access Point name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Message partner</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Queue or output channel declaration</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Conflicting (existing) queue or output channel</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Conflicting (initial) declaration remote site alias</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Remove the duplicated declaration from one of the remote sites involved in conflict.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SNET195E"></span>195</p>         </td>
         <td><p>SNET E DUPQCERR %1(%2) Double %3 declaration for %4. Already declared with %5</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>A queue or output channel was already declared.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Access Point name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Message partner</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Duplication type (empty if there is a simple duplication or <span class="bold_in_para">backup</span> if site is part of a chain of backup sites)</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Queue or output channel</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Conflicting (initial) declaration remote site alias</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Remove the duplicated declaration from one of the remote sites involved in conflict.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SNET196I"></span>196</p>         </td>
         <td><p>SNET I DUPQCNOM %1(%2) Main declaration for %3. Already declared with backup site %4</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>An output session was already declared in a backup site</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Access Point name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Message partner</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Queue or output channel</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Backup site name</p>         </td>
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
         <td><p><span id="SNET197I"></span>197</p>         </td>
         <td><p>SNET I DUPQCBCK %1(%2) Backup declaration for %3. Already declared with nominal site %4</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>An output session was already declared in the nominal site</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Access Point name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Message partner</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Queue or output channel</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Nominal site name</p>         </td>
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
         <td><p><span id="SNET198W"></span>198</p>         </td>
         <td><p>SNET W QRESET %1 (%2) Output session %3 for queue %4 reset from %5 to %6</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The output session status was reset to prevent it remaining in a non-working intermediary state.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Access Point name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Message partner</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>SnF session number</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Queue name</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td>Initial output session state         </td>
      </tr>
      <tr>
         <td><p>6</p>         </td>
         <td>New output session state         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check the new output session state. If the output session was reset to DOWN, re-acquiring the corresponding queue might be necessary for continuing functionality of the product.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SNET199W"></span>199</p>         </td>
         <td><p>SNET W OCRESET %1 (%2) Output session %3 for output channel %4 (queue %5) reset from %6 to %7</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The output session status was reset to prevent it remaining in a non-working intermediary state.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Access Point name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Message partner</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>SnF session number</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Output channel name</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td>Queue name         </td>
      </tr>
      <tr>
         <td><p>6</p>         </td>
         <td>Initial output session state         </td>
      </tr>
      <tr>
         <td>          </td>
         <td><p>7</p>         </td>
         <td>New output session state         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check the new output session state. If the output session was reset to DOWN, re-opening the corresponding output channel might be necessary for continuing functionality of the product.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SNET200I"></span>200</p>         </td>
         <td><p>SNET I ASPLODOK Swift ASP package reload done. Start time %1, end time %2, loaded files %3</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>ASP package was loaded or reloaded on ASP helper process.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Time when the load or reload operation started</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Time when the load or reload operation ended</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Number of service profiles loaded or reloaded</p>         </td>
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
         <td><p><span id="SNET210I"></span>210</p>         </td>
         <td><p>SNET I GETFSCHK %1(%2) [%3] Checking status for pending FileAct transfer</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>A GetFileStatus SWIFTNet query was scheduled for the specified transfer.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Access Point name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Message partner</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>NLocal request identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>None (the transfer status will be updated automatically).
If this message appears often, it might indicate a performance problem.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SNET211I"></span>211</p>         </td>
         <td><p>SNET I GETFSOK %1(%2) [%3] Swift status for pending FileAct transfer is: %4; updating transfer state</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The transfer status will be updated according to its SWIFTNet status.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Access Point name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Message partner</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local request identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Transfer SWIFTNet status</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>None (the transfer status will be updated automatically).</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SNET212E"></span>212</p>         </td>
         <td><p>SNET E GETFSFAIL %1(%2) [%3] Failed to get status for pending FileAct transfer; transfer cancelled</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The GetFileStatus SWIFTNet query failed.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Access Point name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Message partner</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local request identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check the messages indicating the cause of the problem.
If no solution is found, contact Axway Support.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SNET230E"></span>230</p>         </td>
         <td><p>SNET E ACKLFAIL High Availability userexit library load failed: %1</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>An error occurred while loading the SWIFTNet High Availability library.
The reason is specified in parameter %1</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>The library load error reason</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check the messages indicating the cause of the problem. Contact Axway support if no solution is found.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SNET231E"></span>231</p>         </td>
         <td><p>231 SNET E ACKLFAIL High Availability userexit library unload failed: %1</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>An error occurred while loading the SWIFTNet High Availability library.
The reason is specified in parameter %1</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>The library unload error reason</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check the messages indicating the cause of the problem. Contact Axway support if no solution is found.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SNET232E"></span>232</p>         </td>
         <td><p>232 SNET E ACKIFAIL High Availability userexit initialization failed: %1</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>An error occurred while initializing the SWIFTNet High Availability library.
The reason is specified in parameter %1</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>The library initialization error reason</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check the messages indicating the cause of the problem. Contact Axway support if no solution is found.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SNET235E"></span>235</p>         </td>
         <td><p>235 SNET E ACKUEERR %1(%2) [%3] High Availability userexit %4 failed; error: %5</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>A SWIFTNet High Availability operation failed.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Access Point name</p>         </td>
      </tr>
      <tr>
         <td>          </td>
         <td><p>2</p>         </td>
         <td><p>Message Partner</p>         </td>
      </tr>
      <tr>
         <td>          </td>
         <td><p>3</p>         </td>
         <td><p>Local request identifier (number)</p>         </td>
      </tr>
      <tr>
         <td>          </td>
         <td><p>4</p>         </td>
         <td><p>The SWIFTNet High Availability user exit operation which failed</p>         </td>
      </tr>
      <tr>
         <td>          </td>
         <td><p>5</p>         </td>
         <td><p>SWIFTNet HA operation error reason</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check the messages indicating the cause of the problem. Contact Axway support if no solution is found.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SNET236E"></span>236</p>         </td>
         <td><p>236 SNET E ACKUEERR License Key is not valid for SWIFTNet High Availability</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>SWIFTNet High Availability feature is enabled, but the license key does not allow High Availability functionality for SWIFTNet.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td>None         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Set a license key which enables the SWIFTNet High Availability feature.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SNET237E"></span>237</p>         </td>
         <td><p>SNET E ACKUEERR License Key is not valid for Gateway RMA</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Gateway RMA feature is enabled, but the license key does not allow RMA functionality for SWIFTNet.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td>None         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Set a license key which enables the Gateway RMA functionality.</p>         </td>
      </tr>
   </tbody>
</table>

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
