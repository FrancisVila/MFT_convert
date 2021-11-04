{
    "title": "Working with Purge Models (command line)",
    "linkTitle": "Working with Purge Models",
    "weight": "230"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Managing Transfers

<span class="code" style="font-weight: bold;">[peladm create\_purge\_model](#peladm_create_purge_model)</span>

<span class="code" style="font-weight: bold;">[peladm update\_purge\_model](#peladm_update_purge_model)</span>

<span class="code" style="font-weight: bold;">[peladm delete\_purge\_model](#peladm_delete_purge_model)</span>

<span class="code" style="font-weight: bold;">[peldsp display\_purge\_model](#peldsp_display_purge_model)</span>

<span class="code" style="font-weight: bold;">[peldsp select\_purge\_model](#peldsp_select_purge_model)</span>

<span id="peladm_create_purge_model"></span>

## Creating a Purge Model: peladm create\_purge\_model

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p><span class="code" style="font-weight: bold;">peladm create_purge_model {-model}</span> [<span style="font-style: italic;">optional parameters, see list below</span>]</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to create a Model that you can associate with either:</p>
<ul>
<li>A scheduling-type Decision Rule <span class="code">purge_model</span> parameter</li>
<li>A scheduling-type Rule Table <span class="code">default_purge_model</span> parameter</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p><span style="font-style: italic;">Mandatory</span></p>
<p><span class="code">-model (-ml)</span>: Enter a Purge Model name as selection criteria for the purge operation.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-comments (-cts)</span>: Enter a free text description of the Purge Model.</p>
<p>Maximum: 80 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-appli_name (-ap)</span>: Enter an application name as selection criteria for the purge operation.</p>
<p>Maximum: 25 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-dest_alias (-da)</span>: Enter a destination Site alias as selection criteria for the purge operation.</p>
<p>Maximum: 31 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-direction (-dir)</span>: Enter a transfer direction as selection criteria for the purge operation.</p>
<p>Enter one of the values:</p>
<ul>
<li><span style="font-weight: bold;">I</span> = Input</li>
<li><span style="font-weight: bold;">O</span> = Output</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-file_name (-fn)</span>: Enter a Protocol file name extension.</p>
<p>For FTP and HTTP DIR type Transfers, use this parameter to define a filter for the file names that the server returns as selection criteria for the purge operation.</p>
<p>For example: <span class="code" style="font-weight: bold;">*.txt</span> purges all <span class="code">.txt</span> files in the directory that you specify.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-file_type (-ft)</span>: <span style="font-style: italic;">For PeSIT HS transfers only</span>.</p>
<p>Enter a file type as selection criteria for the purge operation.</p>
<p>Maximum: 16 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-from_date (-fd)</span>: Enter the earliest date for the transfers to be selected for the purge operation, in the format <span style="font-style: italic;">YYYYMMDD HHMMSS</span>.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-ident_inf (-id_inf)</span>: Enter an integer to indicate the minimum value of the transfer identifiers to select for the purge operation.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-ident_sup (-id_sup)</span>: Enter an integer to indicate the maximum value of the transfer identifiers to select for the purge operation.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-keep_last_day (-kld)</span>: Do not purge transfers from the <span style="font-style: italic;">ddd</span> previous days.</p>
<p>Both the transfer <code>create_date</code> and <code>end_date</code> (if exists) are used for matching. They must be older than the <code>kld</code> value. The
<code>Kld</code> option is not applied as a filter over the "in memory" transfer list but iterates through the mailbox to select the matching transfers. This may impact performance when there is a large mailbox.</p>
<p>Enter an integer value.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-keep_mailbox_entries(-ke)</span>: Enter this parameter with Y value to skip purging the transfers from mailbox.</p>         </td>
      </tr>
      <tr>
         <td><span class="code">-force (-f)</span>: Enter this parameter with Y value to force files removal.         </td>
      </tr>
      <tr>
         <td><p><span class="code">-list_route_state (-lrs)</span>: Purge all transfers with the specified routing status:</p>
<ul>
<li><span style="font-weight: bold;">A</span> = Acked</li>
<li><span style="font-weight: bold;">R</span> = Routed</li>
<li><span style="font-weight: bold;">F</span> = Failed</li>
<li><span style="font-weight: bold;">T</span> = To Route</li>
<li><span style="font-weight: bold;">N</span> = Not Routed</li>
<li><span style="font-weight: bold;">E</span> = Empty</li>
<li><strong>P</strong> = <strong>P</strong>rocessing</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-list_trans_state (-lts)</span>: Purge all transfers with the specified status:</p>
<ul>
<li><span style="font-weight: bold;">F</span> = Frozen</li>
<li><span style="font-weight: bold;">D</span> = Delayed</li>
<li><span style="font-weight: bold;">B</span> = To_Begin</li>
<li><span style="font-weight: bold;">P</span> = Processing</li>
<li><span style="font-weight: bold;">R</span> = To_Restart</li>
<li><span style="font-weight: bold;">S</span> = Suspended</li>
<li><span style="font-weight: bold;">E</span> = Ended</li>
<li><span style="font-weight: bold;">C</span> = Canceled</li>
<li><span style="font-weight: bold;">I</span> = Interrupted</li>
<li><span style="font-weight: bold;">V</span> = servicing</li>
<li><span style="font-weight: bold;">A</span> = Acked (OFTP, PeSIT, FTP)</li>
<li><span style="font-weight: bold;">T</span> = Created</li>
<li><span style="font-weight: bold;">Z</span> = Deleted</li>
<li><span style="font-weight: bold;">W</span> = Ended_to_ack</li>
<li><span style="font-weight: bold;">G</span> = To_Sign</li>
<li><span style="font-weight: bold;">U</span> = Nacked_user</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-local_agent (-la)</span>: Enter an alias of the associated Local Site as selection criteria for the purge operation.</p>
<p>Maximum: 31 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-local_ident (-i)</span>: Enter a Local Transfer Identifier as selection criteria for the purge operation.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-master (-ma)</span>: Enter a Diffusion List Request identifier as selection criteria for the purge operation.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-mode (-m)</span>: Enter a Transfer Connection mode for the Transfer as selection criteria for the purge operation.</p>
<p>Enter one of the values:</p>
<ul>
<li><span style="font-weight: bold;">I</span> = Initiator</li>
<li><span style="font-weight: bold;">R</span> = Responder</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-no_archive (-no_arc)</span>: Purge the Transfer from the Mailbox without creating a Transfer archive file.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-org_alias (-oa)</span>: Enter an Originator Site alias as selection criteria for the purge operation.</p>
<p>Maximum: 31 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-protocol (-pr)</span>: Enter one of the following Protocol values as selection criteria for the purge operation:</p>
<ul>
<li><span style="font-weight: bold;">PEL</span> (Default)</li>
<li><span style="font-weight: bold;">PHSE</span> = PeSIT HS E</li>
<li><span style="font-weight: bold;">PHSD</span> = PeSIT HS D</li>
<li><span style="font-weight: bold;">FTP</span></li>
<li><span style="font-weight: bold;">HTTP</span></li>
<li><span style="font-weight: bold;">FTP_HTTP</span></li>
<li><span style="font-weight: bold;">ODETTE</span> = OFTP</li>
<li><span style="font-weight: bold;">SFTP</span></li>
<li><span style="font-weight: bold;">SMTP</span></li>
<li><span style="font-weight: bold;">POP3</span></li>
<li><span style="font-weight: bold;">TO_GTW</span></li>
<li><span style="font-weight: bold;">FROM_GTW</span></li>
<li><span style="font-weight: bold;">AS2</span></li>
<li><span style="font-weight: bold;">AS3</span></li>
<li><span style="font-weight: bold;">AS1_POP3</span></li>
<li><span style="font-weight: bold;">AS1_SMTP</span></li>
<li><span style="font-weight: bold;">RN_HTTP</span></li>
<li><span style="font-weight: bold;">RN_POP3</span></li>
<li><span style="font-weight: bold;">RN_SMTP</span></li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-purge_file (-pf)</span>: Enter this parameter with Y value to purge the transferred file.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-purge_tmp_file (-ptf))</span>: Enter this parameter with Y value to purge only the temporary file related to the transfers.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-purge_xpr (-px)</span>: Enter this parameter with Y value to purge the resolved script file and its output files for the selected transfers.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-remote agent (-ra)</span>: Enter the alias of the associated Remote Site as selection criteria for the purge operation.</p>
<p>Maximum: 31 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-req_name (-rn)</span>: Enter a name of the purge request to be used in the log file to print statistics.</p>
<p>Maximum: 25 alphanumeric characters (Default = PELPUR).</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-sequence_inf (-seq_inf)</span>: Enter the lowest number in a range of Transfers to purge.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-sequence_sup (-seq_sup)</span>: Enter the highest number in a range of Transfers to purge.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-to_date (-td)</span>: Enter the latest date in the range of Transfers to purge. The only transfer parameter that is checked is <code>create_date</code>.</p>
<p>Use the date format YYYYMMDD HHMMSS</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-type (-ty)</span>: Enter one of the following Transfer type values as selection criteria for the purge operation:</p>
<ul>
<li>TRANS</li>
<li>LIST</li>
<li>POLL</li>
<li>LOTS</li>
<li>EERP</li>
<li>SELECT</li>
<li>MSG</li>
<li>DIR</li>
<li>RECEIPT</li>
<li>MULTI</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-user_state (-usr_st)</span>: Enter a value for the User state field managed by the user application to be used as selection criteria for the purge operation. (Gateway does not interpret this field in transfer processing.)</p>
<p>Enter a single character.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-username (-un)</span>: Enter a user name as selection criteria for the Transfer records to be purged.</p>
<p>Maximum: 31 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-yday_inf (-yd_inf)</span>: Enter a start date in the format ddd for the range of Transfer records to be purged.</p>
<p>Integer: 001 - 366.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-yday_sup (yd_sup)</span>: Enter an end date in the format ddd for the range of Transfer records to be purged.</p>
<p>Integer: 001 - 366.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="peladm_update_purge_model"></span>

## Modifying a Purge Model: peladm update\_purge\_model

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p><span class="code" style="font-weight: bold;">peladm update_purge_model {-model}</span> [optional parameters]</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to modify an existing Purge Model.</p>
<p>If you update a Model using a parameter without a value, the command deletes the last parameter value.</p>
<p>Enter the Purge Model name (<span class="code">-model</span>) followed by all the fields you want to modify.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p>Mandatory</p>
<p><span class="code">-model (-ml)</span>: Enter the name of the existing Purge Model you want to modify.</p>         </td>
      </tr>
      <tr>
         <td><p><span style="font-style: italic;">Optional parameters:</span> The optional parameters are the same as in the <span class="code" style="font-weight: bold;"><a href="#peladm_create_purge_model">peladm create_purge_model</a></span> command above.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="peladm_delete_purge_model"></span>

## Deleting a Purge Model: peladm delete\_purge\_model

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p><span class="code" style="font-weight: bold;">peladm delete_purge_model {-model}</span></p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to delete a Purge Model.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p>Mandatory</p>
<p><span class="code">-model (-ml)</span>: Enter the name of the existing Purge Model that you want to delete.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p>The following command deletes the Purge Model named ModelIncoming:</p>
<p><span class="code" style="font-weight: bold;">   peladm delete_purge_model  -ml ModelIncoming</span></p>         </td>
      </tr>
   </tbody>
</table>

<span id="peldsp_select_purge_model"></span>

## Selecting Purge Models: peldsp select\_purge\_model

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p><span class="code" style="font-weight: bold;">peldsp select_purge_model [-model]</span></p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to list all the Purge Models available on your Gateway, or to confirm the presence of a specified Purge Model.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p>Optional</p>
<p><span class="code">-model (-ml)</span>: Enter the name of the existing Purge Model that you want to select. Gateway returns the name of this Purge Model if the Purge Model exists.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="peldsp_display_purge_model"></span>

## Displaying a Purge Model: peldsp display\_purge\_model

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p><span class="code" style="font-weight: bold;">peldsp display_purge_model {-model}</span></p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to display the details of a Purge Model identified by its name. The Transfer parameters are displayed by return.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p><span class="code">-model (-ml)</span>: Enter the name of the existing Purge Model for which you want to display details.</p>         </td>
      </tr>
   </tbody>
</table>

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
