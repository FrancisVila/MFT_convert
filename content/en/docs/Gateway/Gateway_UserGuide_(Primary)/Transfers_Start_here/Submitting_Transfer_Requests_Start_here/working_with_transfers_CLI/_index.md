{
    "title": "Working with Transfers (command line)",
    "linkTitle": "Working with Transfers (command line)",
    "weight": "180"
}{{< Gateway/componentlongname  >}}: Managing Transfers

`peltrans`

`peladm update_trans`

`pelpur`

`pelpur clean_swha_db`

`peldsp select_trans`

`peldsp status_trans`

`peldsp display_trans`

`pelctl control_trans`

<span id="peltrans"></span>

## Submitting a Transfer: peltrans

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p><code>peltrans &lt;keyword&gt; value &lt;keyword&gt; value</code></p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to submit:</p>
<ul>
<li>Transfer Requests</li>
<li>Application Message Requests</li>
<li>acknowledgment Requests</li>
<li>List Requests: if the <code>dest_alias</code> parameter is a Diffusion List</li>
</ul>
<p>The <code>peltrans</code> command returns a Transfer Request identifier named <code>local_ident</code>.</p>
<p>Before you submit a Transfer Request, you must create the Site objects that the Transfer object references. Optionally, you can also create Application objects, Diffusion List objects and Model objects to use in the Transfer Request. Although these objects are not mandatory, they simplify Transfer Request definition.</p>
<p>Command arguments are keywords, each of which is followed by corresponding values (except for<code> f_text</code> which does not have a value: the argument is either present or not). Keywords are prefixed by the "<code>-</code>" (hyphen) character. Most keywords have abbreviated forms.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p>Optional parameters</p>
<p>Refer to:</p>
<ul>
<li><a href="transfer_req_parameter_list#General_transfer_parameters">General parameters for creating and updating Transfer Requests</a></li>
<li><a href="transfer_req_parameter_list#SWIFTNet_transfer_parameters">SWIFTNet Transfer Request parameters</a></li>
<li><a href="transfer_req_parameter_list#Diffusion_List_transfer_parameters">Diffusion List Transfer Request parameters</a></li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><strong>Usage rules</strong></p>         </td>
         <td><p><strong>Interactive mode:</strong> If you set the<span class="code"> interactive (-i)</span> parameter, Gateway waits for the end of the transfer (terminating normally, on error or cancellation) before it continues the script. However, this mode may lock the entire application program if the transfer cannot run.</p>
<p><span style="font-weight: bold;">Application:</span> The Application and the destination Site aliases must belong to the same group. If the Application and Transfer parameters are not the same, the Transfer parameters take precedence. If you do not specify the Application name:</p>
<ul>
<li>The file transfer takes the parameters that you explicitly specify in the Request</li>
<li>You must specify the parameters <span class="code">rec_fmt</span> and <span class="code">rec_len</span> (record format and record length)</li>
</ul>
<p>Gateway respects the following priorities when completing Transfer parameters:</p>
<ol>
<li>User parameters</li>
<li>Protocol Model parameters</li>
<li>General Model parameters</li>
</ol>
<p><span style="font-weight: bold;">Date:</span> Use the optional parameter <span class="code">date_to_begin</span> to defer the file transfer.</p>
<p>Use the optional parameter <span class="code">date_to_end</span> to define a validity period for the Transfer. If the Transfer has not taken place or is in progress when this period expires, it is considered timed out and is canceled.</p>
<p>Specify dates in the following format:</p>
<ul>
<li>Date in full:<span style="font-style: italic;"> YYYYMMDD HHMMSS</span></li>
<li>Time of day: <span style="font-style: italic;">hhmmss</span></li>
<li>Relative to the current time:<span style="font-style: italic;">+hhmmss</span></li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Example 1: Transfer Request <span id="with_an_Application1"></span>with an Application</p>         </td>
         <td><p>This example submits a Transfer Request for sending a file to SITEA using Application object FB80. The Application object parameters must be compatible with the file system attributes of the file to send.</p>
<p>peltrans  -dest_alias SITEA</p>
<p>-comments "fixed record length: 80"</p>
<p>-appli FB80</p>
<p>-file_component &lt;name_of_file_to_send&gt;</p>         </td>
      </tr>
      <tr>
         <td><p>Example 2: Transfer Request <span id="without_an_Application1"></span>without an Application</p>         </td>
         <td><p>Although it is recommended that you use an Application or a Model object to submit a Transfer Request, you can submit the same Transfer Request above without using an Application. In this case, you specify the record format and record length parameters.</p>
<p>peltrans  -dest_alias SITEA</p>
<p>-comments "fixed record length: 80"</p>
<p>-f_org S</p>
<p>-rec_fmt F</p>
<p>-rec_len 80</p>
<p>-data_code A</p>
<p>-x_rec_fmt F</p>
<p>-x_rec_len 80</p>
<p>-x_data_code E</p>
<p>-file_component &lt;name_of_file_to_send&gt;</p>         </td>
      </tr>
      <tr>
         <td><p>Example 3: Transfer Request <span id="with_a_Diffusion_List_and_a_Model"></span>with a Diffusion List and a Model</p>         </td>
         <td><p><a href="../../../managing_partners_start_here/diffusion_lists_start_here">Diffusion Lists</a> and <a href="../../parameters_start_here/models_start_here">Models</a> enable you to submit Transfer Requests more easily.</p>
<p>Create these objects <span style="font-weight: bold;">before</span> submitting the Transfer Request. If required, you can combine both a Diffusion List and a Model in a Request.</p>
<p>This example submits a Transfer Request that uses the Model object FBPELPC. This Model object supplies the parameters <span class="code">dest_alias</span>, <span class="code">appli</span>, <span class="code">compression</span>, and so on.</p>
<p>peltrans  -org_alias LOC_SITE</p>
<p>-model FBPELPC</p>
<p>-comments "fixed record length: 255"</p>
<p>-file_component &lt;name_of_file_to_send&gt;</p>
<p> </p>
<p>This example creates a Diffusion List Transfer Request using the Diffusion List SPAIN_L.</p>
<p>peltrans  -org_alias LOC_SITE</p>
<p>-dest_alias SPAIN_L</p>
<p>-appli FB80</p>
<p>-file_component &lt;name_of_file_to_send&gt;</p>         </td>
      </tr>
      <tr>
         <td><p>Example 4: Transfer Request <span id="in_frozen_state1"></span>in frozen state</p>         </td>
         <td><p>When you create a Transfer Request in frozen state, Gateway does not submit the Request immediately. To submit the Request, you must use the command <span class="code" style="font-weight: bold;">pelctl control_trans</span> and set the <span class="code" style="font-weight: bold;">action</span> parameter to <span class="code" style="font-weight: bold;">R</span> (restart). You can use frozen state in all kinds of Transfer Requests in initiator mode.</p>
<p>Creating Transfer Request in frozen state:</p>
<p>The following Transfer Request sends a file to SITEA with Application FB80.</p>
<p>peltrans  -dest_alias SITEA</p>
<p>-comments "Create Transfer in frozen state"</p>
<p>-frozen_state</p>
<p>-appli FB80</p>
<p>-file_component &lt;name_of_file_to_send&gt;</p>
<p> </p>
<p>Restarting a Transfer Request in frozen state</p>
<p>This example switches the state of Transfer Request <span style="font-weight: bold;">xxxx</span> from FROZEN to TO_BEGIN state.</p>
<p>pelctl control_trans  -i xxxx</p>
<p>-action R</p>         </td>
      </tr>
      <tr>
         <td><p>Example 5: PEL protocol Transfer Request</p>         </td>
         <td><p>peltrans  -org_alias PARIS</p>
<p>-dest_alias LILLE</p>
<p>-fc /u/Gateway/profile</p>
<p>-m I</p>
<p>-dir O</p>
<p>-ft 00002</p>
<p>-fn compta</p>
<p>-comp B</p>
<p>-date_to_begin +003000</p>
<p>-date_to_end "19990807 093000"</p>
<p>-prio 1</p>
<p>-f_org S</p>
<p>-rf F</p>
<p>-rl 80</p>
<p>-dc A</p>
<p>-alloc_unit R</p>
<p>-snd_msg file_compta</p>
<p> </p>
<p>peltrans  -server PARIS</p>
<p>-type LOTS</p>
<p>-org_alias PARIS</p>
<p>-dest_alias LILLE</p>
<p>-date_to_begin +003000</p>
<p>-appli FB80</p>         </td>
      </tr>
      <tr>
         <td><p>Example 6: PeSIT HS protocol Transfer Request</p>         </td>
         <td><p>This example is for a Local Site in Responder/Sender mode. The Local Site makes available the file named FILE to the Remote Site named REMOTE_SITE under the logical name APPLI:</p>
<p>peltrans  -org_alias SITE_LOCAL</p>
<p>-dest_alias REMOTE_SITE</p>
<p>-appli APPLI</p>
<p>-file_name APPLI</p>
<p>-file_type 0</p>
<p>-file_component FILE</p>
<p>-mode R</p>
<p>-direction O</p>         </td>
      </tr>
      <tr>
         <td><p>Example 7: Local Site: Initiator/ Receiver</p>         </td>
         <td><p>This example is for a PeSIT transfer, with a request for the reception of the logical file named APPLI from the Site named REMOTE_SITE.</p>
<p>peltrans  -org_alias REMOTE_SITE</p>
<p>-dest_alias SITE_LOCAL</p>
<p>-appli APPLI</p>
<p>-file_name APPLI</p>
<p>-file_type 0</p>
<p>-mode I</p>
<p>-direction I</p>         </td>
      </tr>
      <tr>
         <td><p>Example 8: Local Site: Initiator/ Sender</p>         </td>
         <td><p>This example is for a PeSIT transfer, sending the logical file named APPLI to the destination Site named REMOTE_SITE.</p>
<p>peltrans  -org_alias SITE_LOCAL</p>
<p>-dest_alias REMOTE_SITE</p>
<p>-appli APPLI</p>
<p>-file_name APPLI</p>
<p>-file_type 0</p>         </td>
      </tr>
      <tr>
         <td><p>Example 9: SWIFTNet Transfer Request</p>         </td>
         <td><p>This example is for a SWIFTNet message transfer. The local partner LSWTRADE is sending the message "Payload" through the destination Site SW_SITE to the partner SWTRADEIART.</p>
<p>peltrans  -type MSG</p>
<p>-dest_alias SW_SITE</p>
<p>-trade_org_alias LSWTRADE</p>
<p>-trade_dest_alias SWTRADEIART</p>
<p>-snd_msg "Payload"</p>
<p>-request_type abcd.0000.0000</p>
<p>-appli FTP_B</p>         </td>
      </tr>
   </tbody>
</table>

<span id="peladm_update_trans"></span>

## Modifying a Transfer: peladm update\_trans

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p><span class="code" style="font-weight: bold;">peladm update_trans {-ident}</span> [optional parameters]</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to modify the properties of a Transfer Request.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p><span class="code">-ident (-i)</span>: Enter the transfer identifier of the Transfer Request you want to modify.</p>         </td>
      </tr>
      <tr>
         <td><p><span style="font-style: italic;">Optional parameters</span></p>
<p>Refer to:</p>
<ul>
<li><a href="transfer_req_parameter_list#General_transfer_parameters">General parameters for creating and updating Transfer Requests</a></li>
<li><a href="transfer_req_parameter_list#SWIFTNet_transfer_parameters">SWIFTNet Transfer Request parameters</a></li>
<li><a href="transfer_req_parameter_list#Diffusion_List_transfer_parameters">Diffusion List Transfer Request parameters</a></li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-user_processed (-usr_proc)</span>: Enter <span style="font-weight: bold;">Y</span> (yes) or <span style="font-weight: bold;">N</span> (no) to activate a complementary status indicator showing whether or not the file has been correctly processed.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-user_state (-user_st)</span>: Enter a single character to create a customized indication of the transfer status. You can use the value of this parameter as a selection criteria.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-param1 (-p1)</span>: Enter up to 40 alphanumeric characters.</p>
<p>Gateway uses the values you enter in this parameter locally. It does not transfer the values to your transfer partner. Use this parameter to locally store values that you can reuse via Decision Rules, Models and batch procedures.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-param2 (-p2)</span>: Enter up to 40 alphanumeric characters.</p>
<p>Gateway uses the values you enter in this parameter locally. It does not transfer the values to your transfer partner. Use this parameter to locally store values that you can reuse via Decision Rules, Models and batch procedures.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-date_to_begin (-dtb)</span>: Enter a date in the format <span style="font-style: italic;">YYYYMMDD HHMMSS</span></p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-date_to_end (-dte)</span>: Enter a date in the format <span style="font-style: italic;">YYYYMMDD HHMMSS</span></p>         </td>
      </tr>
      <tr>
         <td><p><strong>Usage rules</strong></p>         </td>
         <td><p>All parameters except<span class="code"> ident</span> are optional. If not specified, a parameter keeps its previous value.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p>peladm update_trans</p>
<p>-i 2567</p>
<p>-purge_option Y</p>         </td>
      </tr>
   </tbody>
</table>

<span id="pelpur"></span>

## Purging a Transfer from the Mailbox: pelpur or pelpur xferPurge

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p><span class="code" style="font-weight: bold;">pelpur {-ident}</span> [optional parameters]</p>
<p>or</p>
<p><span class="code">pelpur xferPurge {-ident}</span> [optional parameters]</p>
<p><strong>Note</strong>: Both formats can be used. They have the same result.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to clear Transfer Request records that match the specified criteria from the Mailbox. To delete all matching Transfer Request records without creating an archive file, set the parameter <span class="code">no_archive</span>. To archive records before purging the Mailbox, do not set this parameter.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p><span class="code">-ident (-i)</span>: Enter the transfer identifier of the Transfer Request record you want to purge.</p>         </td>
      </tr>
      <tr>
         <td><p><span style="font-style: italic;">Optional parameters:</span> Refer to <a href="transfer_req_parameter_list#pelpur_parameters">pelpur parameters</a>.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Usage rules</strong></p>         </td>
         <td><p>Purge with archive option:</p>
<p>If you do not set the archive option <span class="code">no_archive</span> for <span class="code" style="font-weight: bold;">pelpur</span>, Gateway creates an archive file that contains information on selected and purged Transfers. The path name of the file is platform-dependent and is built from the current date and time.</p>
<p>The archive file contains one record for each purged Transfer. Each record describes a subset of Transfer Request parameters, separated by blank characters, and ending with a new line character. Within the record, numeric parameters are translated into character strings.</p>         </td>
      </tr>
      <tr>
         <td><p>Associated tasks</p>         </td>
         <td><p>You can also configure Gateway to archive Transfers automatically. Refer to <a href="../../../configuration_start_here/config_gateway_paras#olh_gateway_database_archive">Configuration: Gateway parameters</a>.</p>         </td>
      </tr>
      <tr>
         <td><p>Example 1: Purge all ended Transfers</p>         </td>
         <td><p>This example purges <span style="font-style: italic;">all</span> ended Transfers (state Ended, Canceled and Acked) from the Mailbox:</p>
<p><span class="code" style="font-weight: bold;">   pelpur  -all</span></p>         </td>
      </tr>
      <tr>
         <td><p>Example 2: Purge according to status</p>         </td>
         <td><p>This example purges Transfers with the status that you specify, in this case <span style="font-weight: bold;">C</span>anceled and <span style="font-weight: bold;">D</span>elayed:</p>
<p><span class="code" style="font-weight: bold;">   pelpur  -list_trans_state CD</span></p>         </td>
      </tr>
      <tr>
         <td><p>Example 3: Purge resolved script file</p>         </td>
         <td><p>This example purges the resolved script file (EXPR) and its output files for the Transfer:</p>
<p><span class="code" style="font-weight: bold;">   pelpur  -purge_xpr</span></p>         </td>
      </tr>
      <tr>
         <td><p>Example 4: Purge transferred file</p>         </td>
         <td><p>This example purges the file sent or received, on condition that the <span class="code">purge_option</span> parameter in the Transfer Request is set to <span style="font-weight: bold;">Y</span> (yes):</p>
<p><span class="code" style="font-weight: bold;">   pelpur  -purge_file</span></p>         </td>
      </tr>
      <tr>
         <td><p>Example 5: Purge selected transfers</p>         </td>
         <td><p>This example purges all Transfers with identifiers between 10 and 20 and in the <span style="font-weight: bold;">D</span>elayed, <span style="font-weight: bold;">C</span>anceled or <span style="font-weight: bold;">S</span>uspended states:</p>
<p><span class="code" style="font-weight: bold;">   pelpur</span></p>
<p><span class="code" style="font-weight: bold;">   -ident_inf 10</span></p>
<p><span class="code" style="font-weight: bold;">   -ident_sup 20</span></p>
<p><span class="code" style="font-weight: bold;">   -list_trans_state DCS</span></p>         </td>
      </tr>
   </tbody>
</table>

> **Note:**
>
> The payload file for a Transfer which was routed to Integrator is not deleted by a purge operation.

For more information, refer to [Purging for transfers routed from Gateway to Integrator](../../../connectors_about/integrator_about/integrator_connector#Purging).

<span id="Purging"></span>

## Purging a Transfer from the HA database (used by SWIFTNet High Availability): pelpur clean\_swha\_db

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p><span class="code" style="font-weight: bold;">pelpur clean_swha_db</span> [parameters]</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to remove transfer entries that match the specified criteria from the HA database (used by SWIFTNet High Availability).</p>
<p>To purge a transfer, the SWIFTNet High Availability feature has to be activated and connectivity with HA database must be functional.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p>Refer to <a href="transfer_req_parameter_list#pelpur_parameters">pelpur parameters</a>.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Usage rules</strong></p>         </td>
         <td><p>At least one parameter (criteria) has to be specified in the subcommand.</p>         </td>
      </tr>
      <tr>
         <td><p>Example 1: Purge a transfer with a specific gateway id</p>         </td>
         <td><p>Purging a transfer with gateway id “7”.</p>
<p><span class="code" style="font-weight: bold;">pelpur clean_swha_db -gatewayID 7</span></p>         </td>
      </tr>
      <tr>
         <td><p>Example 2: Purge transfers matching specific gateway id and transfer id range</p>         </td>
         <td><p>Purging a transfer with gateway id “7” and transfer id between “5” and “11’.</p>
<p><span class="code" style="font-weight: bold;">pelpur clean_swha_db -gatewayID 7 -fromTransferID 5 -toTransferID 11</span></p>         </td>
      </tr>
      <tr>
         <td><p>Example 3: Purge transfer with specific local partner alias and specific date</p>         </td>
         <td><p>Purging a transfer with local partner alias “bnpparibas” and create date “11 June 2014”.</p>
<p><span class="code" style="font-weight: bold;">pelpur clean_swha_db -localPartner bnpparibas -createDate 20140611</span></p>         </td>
      </tr>
      <tr>
         <td><p>Example 4: Purge transfers with specific request type and created between 2 dates</p>         </td>
         <td><p>Purging a transfer with requestType "xsys.xxx.fa.nro.hdo" and that was created after “12 June 2014” and before “20 June 2014”</p>
<p><span class="code" style="font-weight: bold;">pelpur clean_swha_db -requestType xsys.xxx.fa.nro.hdo -fromCreateDate 20140612 -toCreateDate 20140620</span></p>         </td>
      </tr>
   </tbody>
</table>

<span id="peldsp_select_trans"></span>

## Selecting a Transfer: peldsp select\_trans

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p><span class="code" style="font-weight: bold;">peldsp select_trans</span> [optional parameters]</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to select the Transfer or List Requests that match the criteria entered as parameters.</p>
<p>You can refine your search using the optional parameters.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p><span style="font-style: italic;">Optional parameters</span>: Refer to <a href="transfer_req_parameter_list#peldsp_parameters">peldsp parameters</a>.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p>This example displays all Transfer records for acknowledgment type Transfers.</p>
<p>peldsp select_trans  -type EERP</p>
<p>1</p>
<p>2</p>
<p>3</p>         </td>
      </tr>
   </tbody>
</table>

<span id="peldsp_status_trans"></span>

## Displaying Transfer Request states: peldsp status\_trans

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p><span class="code" style="font-weight: bold;">peldsp status_trans</span> [optional parameters]</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>This command displays the list of transfers and related attributes.
It can be used for debugging purposes.</p>
<p>Columns returned (that can be correlated with the <code>display_trans</code> sub-command):</p>
<table>
   <tbody>
      <tr>
         <td>Number         </td>
         <td>x_local_ident         </td>
      </tr>
      <tr>
         <td>Site         </td>
         <td>depends on the direction; if Incoming, its x_originator (or x_org_alias if x_originator is empty), while for Outgoing its x_destination (or x_dest_alias if x_destination is empty).         </td>
      </tr>
      <tr>
         <td>Type         </td>
         <td>x_type         </td>
      </tr>
      <tr>
         <td>D         </td>
         <td>x_direction         </td>
      </tr>
      <tr>
         <td>Day         </td>
         <td>x_yday         </td>
      </tr>
      <tr>
         <td>Proto_Id         </td>
         <td>"transfer protocol key" computed depending on the protocol, based on x_xfer_ident (it can also include x_file_name) except for PEL and ETB3 when it's x_sequence.         </td>
      </tr>
      <tr>
         <td>Appli         </td>
         <td>x_appli         </td>
      </tr>
      <tr>
         <td>State         </td>
         <td>x_state         </td>
      </tr>
      <tr>
         <td>File         </td>
         <td>x_file_component         </td>
      </tr>
      <tr>
         <td>R         </td>
         <td>x_retry_count         </td>
      </tr>
      <tr>
         <td>KBytes         </td>
         <td>x_f_bytes (in KB, rounded)         </td>
      </tr>
      <tr>
         <td>Sc         </td>
         <td>x_purge_option (Y/N)         </td>
      </tr>
      <tr>
         <td>U         </td>
         <td>x_user_processed (Y/N)         </td>
      </tr>
   </tbody>
</table>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p><span style="font-style: italic;">Optional parameters:</span> Refer to <a href="transfer_req_parameter_list#peldsp_parameters">peldsp parameters</a>.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p>When you enter the following command, Gateway returns the file transfer numbers that match the selection criteria.</p>
<p><span class="code" style="font-weight: bold;">   peldsp status_trans</span></p>
<p><a href="">Example of a return screen display</a>.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="peldsp_display_trans"></span>

## Displaying Transfer details: peldsp display\_trans

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p><span class="code" style="font-weight: bold;">peldsp display_trans {-local_ident}</span></p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to display the details of a Transfer that you specify by its identifier.</p>
<p>The command returns the Transfer parameters.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p><span class="code">-local_ident (-i):</span> Enter the transfer identifier of the Transfer Request you want to display.</p>         </td>
      </tr>
      <tr>
         <td><p>Usage</p>         </td>
         <td><p>Each parameter is displayed on a separate line in the form:</p>
<p><span class="code" style="font-weight: bold;">   name_of_field="value"</span></p>
<p>Each field name is prefixed by the string "<span style="font-weight: bold;">x_</span>", relating to the <span style="font-weight: bold;">x</span>fer (Transfer) object.</p>         </td>
      </tr>
      <tr>
         <td><p>Example 1: Displaying a Transfer Request</p>         </td>
         <td><p>When you enter the command:</p>
<p><span class="code" style="font-weight: bold;">   peldsp display_trans  -i 114</span></p>
<p>Gateway returns the following type of information:</p>
<p><span class="code">   x_local_ident=114</span></p>
<p><span class="code">   x_type=TRANS</span></p>
<p><span class="code">   x_org_alias=GFL660</span></p>
<p><span class="code">   x_dest_alias=LPC</span></p>
<p><span class="code">   x_appli=DEFAULT_B</span></p>
<p><span class="code">   x_originator=GFL660</span></p>
<p><span class="code">   x_destination=TPHSE</span></p>
<p><span class="code">   x_direction=O</span></p>
<p><span class="code">   x_mode=I</span></p>
<p><span class="code">   (....)</span></p>         </td>
      </tr>
      <tr>
         <td><p>Example 2: Displaying a Diffusion List Request</p>         </td>
         <td><p>When you enter the command:</p>
<p><span class="code" style="font-weight: bold;">   peldsp display_trans  -i 8</span></p>
<p>Gateway returns the following type of information:</p>
<p><span class="code">   x_local_ident=8</span></p>
<p><span class="code">   x_type=LIST</span></p>
<p><span class="code">   x_org_alias=R65</span></p>
<p><span class="code">   x_dest_alias=SLIST1</span></p>
<p><span class="code">   (...)</span></p>         </td>
      </tr>
   </tbody>
</table>

<span id="pelctl_control_trans"></span>

## Controlling a Transfer: pelctl control\_trans

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p><span class="code"><strong>pelctl control_trans {-local_ident} {-action}</strong> [-retry_delay]</span></p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to suspend, restart or cancel a Transfer Request or a Diffusion List Request.</p>
<p>You can only suspend a Request if its state is one of the following:</p>
<ul>
<li>To <span style="font-weight: bold;">B</span>egin</li>
<li><span style="font-weight: bold;">D</span>elayed</li>
<li><span style="font-weight: bold;">P</span>rocessing</li>
</ul>
<p>To restart a Request, use <span class="code" style="font-weight: bold;">pelctl control_trans</span> with the <span style="font-weight: bold;">R</span>estart operation.</p>
<p>A Restart operation only takes effect if the latest end-of-transfer date is already reached. If you perform a restart operation on a delayed Transfer Request:</p>
<ul>
<li><span style="font-style: italic;">before</span> the start date, the Transfer state switches to <span style="font-weight: bold;">Frozen</span></li>
<li><span style="font-style: italic;">after</span> the start date, the Transfer state switches to <span style="font-weight: bold;">Ended</span> (with error code)</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p><span class="code">-local_ident (-i)</span>: Enter the transfer identifier of the Transfer Request you want to display.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-action (-a)</span>: Enter one of the following values:</p>
<ul>
<li><span style="font-weight: bold;">C</span> = Cancel</li>
<li><span style="font-weight: bold;">S</span> = Suspend</li>
<li><span style="font-weight: bold;">R</span> = Restart</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-retry_delay (-rd)</span>: Enter the number of seconds of delay before retry.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p>This example suspends the Transfer with the identifier 36:</p>
<p>pelctl control_trans  -i 36  <span style="font-weight: bold;">-a S</span></p>         </td>
      </tr>
   </tbody>
</table>

Related topics

[Transfers: Parameters List](transfer_req_parameter_list)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
