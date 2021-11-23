{
    "title": "New Remote Site: SWIFTNet tab",
    "linkTitle": "SWIFTNet tab",
    "weight": "290"
}{{< Gateway/componentlongname  >}}: Managing Partners

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Field         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p><strong>Login</strong> <span style="font-style: italic;">(mandatory)</span></p>         </td>
         <td><p>Client user name to send to the Remote Site during the connection phase.<br />
Maximum: 63 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p><span style="font-weight: bold;">Set password</span> <span style="font-style: italic;">(mandatory)</span></p>         </td>
         <td><p>Opens a dialog box to set the password to send to the Remote Site during the connection phase.<br />
Maximum: 20 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p><span style="font-weight: bold;">RA instance</span> <span style="font-style: italic;">(mandatory)</span></p>         </td>
         <td><p>Name of the SWIFTNet RA (Remote API host adapter) local access point.</p>         </td>
      </tr>
      <tr>
         <td><p><span style="font-weight: bold;">Message partner</span> <span style="font-style: italic;">(mandatory)</span></p>         </td>
         <td><p>Application name declared in SAG.</p>         </td>
      </tr>
      <tr>
         <td><p><span style="font-weight: bold;">Event end point</span> <span style="font-style: italic;">(mandatory)</span></p>         </td>
         <td><p>Arbitrary name allowing SAG to route received events.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>General</strong> sub-tab</p>         </td>
      </tr>
      <tr>
         <td><p>Alternate RA installation pathname</p>         </td>
         <td><p>Only if SWIFTNet RA has been installed in more than one place</p>
<p>Alternative path for SWIFTNet RA.</p>         </td>
      </tr>
      <tr>
         <td><p>Alternate configuration file</p>         </td>
         <td><p>Alternative configuration file for the instance of SWIFTNet RA.</p>         </td>
      </tr>
      <tr>
         <td><p>Maximum number of client processes</p>         </td>
         <td><p>Maximum number of simultaneous client processes allowed.</p>
<p>Default = 1.</p>         </td>
      </tr>
      <tr>
         <td><p>Maximum number of server processes</p>         </td>
         <td><p>Maximum number of simultaneous server processes allowed.</p>
<p>Default = 1.</p>         </td>
      </tr>
      <tr>
         <td><p><span id="Sign_ident_list"></span>Sign ident list</p>         </td>
         <td><p>List of signatory SWIFTNet users. This is a list of user login ids with their corresponding passwords.</p>
<p>For each user, enter the login id in the first field and the password in the second field. Then click <span style="font-weight: bold;">Add</span> to add the user to the list.</p>
<p>You can also modify a user and/or password. Select the user in the list, make the required changes and then click <span style="font-weight: bold;">Update</span>.</p>
<p>To delete a user from the list, click <span style="font-weight: bold;">Delete</span>.</p>         </td>
      </tr>
      <tr>
         <td><p><span id="Decrypt_ident_list"></span>Decrypt ident list</p>         </td>
         <td><p>List of decrypting SWIFTNet users. This is a list of user login ids with their corresponding passwords.</p>
<p>For each user, enter the login id in the first field and the password in the second field. Then click <span style="font-weight: bold;">Add</span> to add the user to the list.</p>
<p>You can also modify a user and/or password. Select the user in the list, make the required changes and then click <span style="font-weight: bold;">Update</span>.</p>
<p>To delete a user from the list, click <span style="font-weight: bold;">Delete</span>.</p>         </td>
      </tr>
      <tr>
         <td><p><span id="Backup_site_alias"></span>Backup sites</p>         </td>
         <td><p>The list of backup sites selected. You can add or remove Sites from the list by clicking the <strong>Change</strong>… button. Up to 4 backup Sites can be selected.</p>         </td>
      </tr>
      <tr>
         <td><span id="Maximum"></span>Maximum number of initiator transfers         </td>
         <td><p>The value of the maximum number of transfers in Initiator mode, FileAct only. By default, this parameter is set to 0, meaning unlimited. The maximum value allowed is 999. Transfers switched from a nominal site to a backup site will be subject to the nominal's site limit. The site parameter is not available to the connection related user exits.</p>
<p><strong>Note</strong>: Both the per-site and the global maximum number of initiator transfers are applied simultaneously (if set to a non-0 value); whichever limit is reached first will come into effect.</p>         </td>
      </tr>
      <tr>
         <td><strong>SnF (Store-and-Forward)</strong> sub-tab         </td>
      </tr>
      <tr>
         <td><p>Queues</p>         </td>
         <td><p>List of all SnF queues to be managed.</p>         </td>
      </tr>
      <tr>
         <td><p>SNL end point</p>         </td>
         <td><p>Name allowing the reception of SnF events.</p>         </td>
      </tr>
      <tr>
         <td><p>Input Channel</p>         </td>
         <td><p>The name of the input channel.</p>
<p><strong>Note:</strong> The input channel must already exist! First create the channel using the <span class="codeBold_in_para">pelctl create_input_channel</span> command.</p>         </td>
      </tr>
      <tr>
         <td>[List of output channels with their details]         </td>
      </tr>
      <tr>
         <td><p><strong>New</strong>, <strong>Modify</strong> and <strong>Delete</strong> buttons</p>         </td>
         <td><p>Use these buttons to create, modify or delete output channels.</p>
<p>When you click <strong>New</strong> or <strong>Modify</strong>, the <em>Output Channel Parameters</em> window opens.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="olh_output_ch_paras"></span>

## Output channel parameters

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Field         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Channel name</p>         </td>
         <td><p>The name of the output channel.</p>         </td>
      </tr>
      <tr>
         <td><p>Queue name</p>         </td>
         <td><p>The output channel's queue name.</p>         </td>
      </tr>
      <tr>
         <td><p>Window size</p>         </td>
         <td><p><em>Optional</em></p>
<p>The output channel window size.</p>
<p>In SWIFT, the window size is an optional element that is used to limit the number of concurrent messages or files sent by SWIFT on a push session. If the element is not present, then a default value is used for the window size (specified in SWIFT documentation). SWIFT adjusts the window size to the maximum value in case the application requests a higher value than the maximum allowed value.</p>
<p>Normally you do not need to change the default value. Only specify the window size if you want to restrict the value.</p>         </td>
      </tr>
      <tr>
         <td>Receive retrieved messages         </td>
         <td><p><em>Optional</em></p>
<p>Enable the attribute in order to receive retrieved messages.
By setting this parameter, the output channel will be opened having the element “<span class="code">protocolLevel</span>” set to value “2”, as indicated by SWIFT documentation.</p>
<p>Example:
<span class="code"> -receive_retrieved_messages "Y"</span></p>
<p><strong>Note</strong>: To receive retrieved messages, the queue for which the session is being started:</p>
<ul>
<li>Must have been defined for service “<span class="code">swift.snf.system (!p, !x)”</span></li>
<li>Must have been used on the retrieval request payload</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><em>Optional</em></p>
<p>Click <strong>Select subset</strong> to open the <em>Output Channel Subset</em> window and define the Subset elements for the output channel.</p>         </td>
      </tr>
      <tr>
         <td><p><em>Output Channel Subset</em> window</p>         </td>
         <td><p>Select the required subset elements:</p>
<ul>
<li>InterAct</li>
<li>FileAct</li>
<li>System</li>
<li>Urgent</li>
<li>Normal</li>
<li>InterAct_Urgent</li>
<li>InterAct_Normal</li>
<li>FileAct_Urgent</li>
<li>FileAct_Normal</li>
<li>System_Urgent</li>
<li>System_Normal</li>
</ul>
<p>The order in which the subsets are listed is important! Use the up and down arrows to specify the order of the elements.</p>
<p><strong>Note:</strong> If no subset is selected, the output channel will receive all types of message of all priorities, in a first in, first out order.</p>         </td>
      </tr>
   </tbody>
</table>

Related topics

[Working with Remote Sites](../)

[Site objects: Parameters List](../../managing_local_sites_cli/sites_parameter_list)

[SWIFTNet connector](../../../../connectors_about/swiftnet_about/swiftnet_connector)

[Configuring the <span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>/SWIFTNet environment](../../../../connectors_about/swiftnet_about/swiftnet_connector/swiftnet_configuring)

[Backup Remote Sites for SWIFTNet](../../../../connectors_about/swiftnet_about/swiftnet_backup_sites)

[SWIFTNet input channels](../../../../connectors_about/swiftnet_about/swiftnet_input_channels)

[SWIFTNet queues and output channels](../../../../connectors_about/swiftnet_about/swiftnet_input_channels/swiftnet_output_channels)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
