{
    "title": "Perform broadcast and collect operations",
    "linkTitle": "Perform broadcast and collect operations",
    "weight": "190"
}Broadcast and collect modes allow you to send files to multiple partners and receiving files from multiple partners using a single command request for each.

## Broadcast

You can use broadcasting to send a file to an entire group of partners in one command, avoiding the task of sending the selected file individually to each of the partners in a flow.

The name of the broadcast list is itself a virtual partner, which contains a list of partners in your flow. This list of partners can be explicit, or it can reference a file that contains the list of partners.

Additionally, you can define what occurs if a partner is unknown, how the scripts are applied to the broadcast list, and so on. [More information](../../../concepts/transfer_command_overview/broadcast_collect)...

<img src="/Images/TransferCFT/Broadcast_w_cg.png" class="maxWidth" alt="Simplified diagram of a Source Transfer CFT sending a file to multiple Targets" />

<table>
   <th>
      <tr>
<th>  Task         </th>
<th>Description         </th>
<th>Details         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>1</p>
<p> </p>         </td>
         <td><p>Create a flow.</p>
<p> </p>
<p><br />
</p>         </td>
         <td><p>In <span class="mc-variable Primary.CG or_UM variable">Central Governance</span> click <span class="bold_in_para">Flows </span>&gt; <span class="bold_in_para">Add flow</span>.</p>
<p>Create  a flow named <span class="bold_in_para">Broadcast_flow</span>, and give it the identifier <span class="bold_in_para">flow04</span>.</p>
<p>In this flow the MainOffice is the Source with the two stores as the Targets.</p>         </td>
         <td><a href="../intro_cg_task_catalog/t_defineflow_broadcast"><img src="/Images/TransferCFT/mapArrow.png" /></a>         </td>
      </tr>
      <tr>
         <td><p>2</p>
<p> </p>         </td>
         <td><p>Enable broadcasting mode.</p>
<p> </p>         </td>
         <td><p> </p>
<p>In the Source Transfer properties, enable Broadcast list.</p>
<p> </p>         </td>
         <td><a href="../intro_cg_task_catalog/t_defineflow_broadcast#enable_broadcast_cg"><img src="/Images/TransferCFT/mapArrow.png" /></a>         </td>
      </tr>
      <tr>
         <td><p>3</p>
<p> </p>         </td>
         <td><p>Deploy the flow.</p>
<p> </p>         </td>
         <td><p>In <span class="mc-variable Primary.CG or_UM variable">Central Governance</span> click <span class="bold_in_para">Deploy </span>to save and deploy the flow.</p>
<p> </p>         </td>
         <td><a href="../intro_cg_task_catalog/t_savedeployflow"><img src="/Images/TransferCFT/mapArrow.png" /></a>         </td>
      </tr>
      <tr>
         <td><p>4</p>
<p> </p>         </td>
         <td><p>Create a file for the flow.</p>
<p> </p>         </td>
         <td><p>For this example, copy a file SALES_report to transfer in the Store_66 <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span><span class="code"> runtime/pub </span>folder.</p>
<p> </p>         </td>
         <td>          </td>
      </tr>
      <tr>
         <td><p>5</p>
<p> </p>         </td>
         <td><p>Execute the SEND command.</p>
<p> </p>         </td>
         <td><p>From the source <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span>, run the following command:</p>
<p><span class="code">CFTUTIL SEND PART=DEST_stores, IDF=flow04, FNAME=pub/SALES_report</span></p>
<p> </p>         </td>
         <td><a href="../../../c_intro_userinterfaces/about_cftutil"><img src="/Images/TransferCFT/mapArrow.png" /></a>         </td>
      </tr>
      <tr>
         <td>6         </td>
         <td>Monitor the file transfer status.         </td>
         <td>In <span class="mc-variable Primary.CG or_UM variable">Central Governance</span> select the <span class="bold_in_para">Flows </span>tab, and click <span class="bold_in_para">Monitoring</span>.         </td>
         <td><a href="../intro_cg_task_catalog/c_flow_monitoring"><img src="/Images/TransferCFT/mapArrow.png" /></a>         </td>
      </tr>
   </tbody>
</table>

## Collect

Collecting files is the inverse of using a broadcast list. In the collect transfer mode you can receive a dedicated file from multiple partners (P*n*). This allows the receiver, or flow initiator, to receive a file from all defined partners using a single request command. More information...

![Simplified diagram of a Target Transfer CFT receiving files from multiple sources](/Images/TransferCFT/TransferCFT_Collect_w_CG.png)

 

<table>
   <th>
      <tr>
<th>  Task         </th>
<th>Description         </th>
<th>Details         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>1</p>
<p> </p>         </td>
         <td><p>Create a flow.</p>
<p><br />
</p>         </td>
         <td><p>In <span class="mc-variable Primary.CG or_UM variable">Central Governance</span> define a flow named <span class="bold_in_para">Collect_flow</span>, and give it the identifier <span class="bold_in_para">flow05</span>.</p>
<p>Use the Source as MainOffice and the stores as the Target.<br />
</p>         </td>
         <td><a href="../intro_cg_task_catalog/t_define_simpleflow"><img src="/Images/TransferCFT/mapArrow.png" /></a>         </td>
      </tr>
      <tr>
         <td><p>2</p>
<p> </p>         </td>
         <td><p>Enable collect mode.</p>
<p> </p>         </td>
         <td><p> </p>
<p>In the Collect_flow definition, modify so that the Target pulls file.</p>
<p> </p>         </td>
         <td><a href="../intro_cg_task_catalog/t_defineflow_collect"><img src="/Images/TransferCFT/mapArrow.png" /></a>         </td>
      </tr>
      <tr>
         <td><p>3</p>
<p> </p>         </td>
         <td>Define the path to the Target file for each store.         </td>
         <td><p>In the Target (each store) select File properties. In Path field, enter the path to the file to send.</p>
<p> </p>         </td>
         <td><a href="../intro_cg_task_catalog/t_collect_target_properties"><img src="/Images/TransferCFT/mapArrow.png" /></a>         </td>
      </tr>
      <tr>
         <td><p>4</p>
<p> </p>         </td>
         <td><p>Deploy the flow.</p>
<p> </p>         </td>
         <td><p>In <span class="mc-variable Primary.CG or_UM variable">Central Governance</span> you can save and deploy the flow.</p>
<p> </p>         </td>
         <td><a href="../intro_cg_task_catalog/t_savedeployflow"><img src="/Images/TransferCFT/mapArrow.png" /></a>         </td>
      </tr>
      <tr>
         <td><p>5</p>
<p> </p>         </td>
         <td><p>Run the RECV command.</p>
<p> </p>         </td>
         <td>In <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span>, run the following command: <span class="code"><br />
</span><span class="code">CFTUTIL RECV PART=DEST_Stores, IDF=flow05</span>
<p> </p>         </td>
         <td><a href="../../../c_intro_userinterfaces/about_cftutil"><img src="/Images/TransferCFT/mapArrow.png" /></a>         </td>
      </tr>
      <tr>
         <td><p>6</p>
<p> </p>         </td>
         <td><p>Monitor the file transfer status.</p>
<p> </p>         </td>
         <td><p>In <span class="mc-variable Primary.CG or_UM variable">Central Governance</span> select the <span class="bold_in_para">Flows </span>tab, and click <span class="bold_in_para">Monitoring</span>.</p>         </td>
         <td><a href="../intro_cg_task_catalog/c_flow_monitoring"><img src="/Images/TransferCFT/mapArrow.png" /></a>         </td>
      </tr>
   </tbody>
</table>