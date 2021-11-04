{
    "title": "New Transfer Request: General tab",
    "linkTitle": "General tab",
    "weight": "140"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Managing Transfers

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Field         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>General information</p>         </td>
      </tr>
      <tr>
         <td><p>Model</p>         </td>
         <td><p>Optional</p>
<p>To accelerate the creation of Transfer Requests, you can use a Model. The Model object groups a set of reusable parameters for submitting Transfer Requests. When setting parameters, note that the Transfer Request parameters override the Model parameters.</p>
<p>Enter the name of the Model to use.<br />
Maximum: 25 alphanumeric characters.</p>
<p>Alternatively, select an existing Model from the drop-down list.</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Select the type of transfer:</p>
<ul>
<li><span style="font-weight: bold;">TRANS</span>: Submit Transfer Request.</li>
<li><span style="font-weight: bold;">LOT</span> <span style="font-style: italic;">PEL protocol only</span>: After polling the Remote Site, Gateway creates the Transfer on the Local Site in <span style="font-style: italic;">frozen</span> state.</li>
<li><span style="font-weight: bold;">POLL</span> <span style="font-style: italic;">PEL protocol only</span>: After polling the Remote Site, Gateway creates the Transfer on the Local Site in <span style="font-style: italic;">To Begin</span> state.</li>
<li><span style="font-weight: bold;">LIST</span>: Submit a Diffusion List type Transfer.</li>
<li><span style="font-weight: bold;">DIR</span> <span style="font-style: italic;">FTP, SFTP and HTTP Initiator mode only</span>: Gateway retrieves the contents of a given directory and saves the result in the file that you specify in the <span style="font-weight: bold;">File component</span> field.</li>
<li><span style="font-weight: bold;">MULTI</span> <span style="font-style: italic;">FTP and SFTP multiple transfers only</span>: Upload and download multiple files with a single request. This is an MGET or MPUT transfer (the distinction between the two is indicated by the <span style="font-weight: bold;">Direction</span> parameter).</li>
<li><span style="font-weight: bold;">INTERACT</span> <span style="font-style: italic;">SWIFTNet only</span>: Submit a SWIFTNet InterAct Transfer (equivalent to MSG Transfer type when using online commands).</li>
<li><span style="font-weight: bold;">(Empty)</span>: Gateway takes the Transfer type definition from the Application object first, and if undefined, from the Model object.</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Mode</p>         </td>
         <td><p>Select the Transfer connection mode:</p>
<ul>
<li><span style="font-weight: bold;">Initiator</span></li>
<li><span style="font-weight: bold;">Responder</span></li>
<li><span style="font-weight: bold;">(Empty)</span></li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Direction</p>         </td>
         <td><p>Select the Transfer direction:</p>
<ul>
<li><span style="font-weight: bold;">Send</span></li>
<li><span style="font-weight: bold;">Receive</span></li>
<li><span style="font-weight: bold;">(Empty)</span></li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Application</p>         </td>
         <td><p>Optional</p>
<p>Select an existing Application. The Application defines file attributes to apply to the transferred file. Keep in mind that the Application that you select must belong to the same group as the Site that you specify in the <span style="font-weight: bold;">Destination alias</span> field.</p>
<p>If you do not select an Application:</p>
<ul>
<li>The Transfer takes the parameters that you explicitly specify in the Request</li>
<li>You must specify the <span style="font-weight: bold;">Record format</span> and the <span style="font-weight: bold;">Record length</span> (in the <span style="font-weight: bold;"><a href="../transfer_request_attributes_tab">Attributes</a></span> tab)</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Ack option</p>         </td>
         <td><p>OFTP, PeSIT, SMTP and SWIFTNet only</p>
<p>Use this option to specify acknowledgment behavior for the Transfer.</p>
<p>Select one of the following acknowledgment options:</p>
<ul>
<li><span style="font-weight: bold;">Undefined</span> (acknowledgment behavior undefined)</li>
<li><span style="font-weight: bold;">Not to ack</span> (do not wait for acknowledgment)</li>
<li><span style="font-weight: bold;">To ack</span> (wait for acknowledgment)</li>
</ul>
<p>For SMTP, refer to <a href="../../../../protocols_about/smtp_pop3_about/smtp_config#Requesting_an_acknowledgement">Configuring SMTP: Requesting an acknowledgment</a>.</p>         </td>
      </tr>
      <tr>
         <td><p>Purge option</p>         </td>
         <td><p>To purge all files associated with the Transfer Request (via the <span class="code" style="font-weight: bold;">pelpur</span> command), set this option to <span style="font-weight: bold;">Yes</span>. The value that you set here overrides the Purge option setting in the Model definition.</p>         </td>
      </tr>
      <tr>
         <td><p>Permanent</p>         </td>
         <td><p>This parameter controls the availability of files for download by remote clients when Gateway is acting in <span style="font-style: italic;">server mode</span>.</p>
<p>Usually (when Permanent = <span style="font-weight: bold;">No</span>), Gateway makes a specified file available only to the first client that submits a Transfer Request for the file.</p>
<p>If you activate this option (Permanent = <span style="font-weight: bold;">Yes</span>), Gateway responds to each client's Transfer Requests by sending a copy of the requested file, keeping the original in the database available for subsequent client Transfer Requests.</p>
<p>Select one of the following:</p>
<ul>
<li><span style="font-weight: bold;">Yes</span> (to set Transfer availability to permanent)</li>
<li><span style="font-weight: bold;">No</span></li>
<li>(<span style="font-weight: bold;">Empty</span>)</li>
</ul>
<p>The value that you set here overrides the setting in the Model definition.</p>         </td>
      </tr>
      <tr>
         <td><p>Sites</p>
<p>In the <span style="font-weight: bold;">Sites</span> section, complete either the first two fields or the last four fields.</p>
<p>See the example below.</p>         </td>
      </tr>
      <tr>
         <td><p>Originator alias</p>         </td>
         <td><p>Enter the Site alias of the source Site of the file transfer.<br />
Maximum: 31 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p>Destination alias</p>         </td>
         <td><p>Enter the Site alias of the file transfer destination. If you specify a Diffusion List in this field, Gateway transmits the Transfer to several destinations.<br />
Maximum: 31 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>Local agent alias</p>         </td>
         <td><p>Enter the alias of the associated Local Site.<br />
Maximum: 31 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p>Remote agent alias</p>         </td>
         <td><p>Enter the alias of the associated Remote Site or Remote Site template.<br />
Maximum: 31 alphanumeric characters.<br />
Refer to <a href="../../../../managing_partners_start_here/sites_start_here">About Site objects</a>.</p>         </td>
      </tr>
      <tr>
         <td><p>Originator</p>         </td>
         <td><p>Enter the originator protocol identifier.<br />
Maximum: 31 alphanumeric characters.<br />
The name you enter in this field designates the source identifier of the Transfer.</p>         </td>
      </tr>
      <tr>
         <td><p>Destination</p>         </td>
         <td><p>Enter the destination protocol identifier.<br />
Maximum: 31 alphanumeric characters.<br />
The name you enter in this field designates the Transfer destination.</p>         </td>
      </tr>
      <tr>
         <td><p><span style="font-weight: bold;">Site attributes – example</span><br />
PeSIT transfer from Gateway to an FTP client:</p>
<ul>
<li>Local agent alias = GW</li>
<li>Remote agent alias = TFTP</li>
<li>Originator = Monitor (Local Site alias, originating transfer)</li>
<li>Destination = User (Remote Site alias, to receive transfer)</li>
</ul>         </td>
      </tr>
   </tbody>
</table>

Related topics

[Working with File Transfer Requests](../)

[Transfers: Parameters List](../../working_with_transfers_cli/transfer_req_parameter_list)

[Transferring multiple files with FTP](../../../../protocols_about/ftp_about/ftp_multiple_file_transfer)

[Transferring multiple files with SFTP](../../../../protocols_about/sftp_about/sftp_multiple_file_transfer)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
