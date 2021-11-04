{
    "title": "Create a flow to transfer multiple files",
    "linkTitle": "Create a flow to transfer multiple files",
    "weight": "150"
}This flow allows you to send multiple files to a defined application. In this scenario, the Store\_66 application sends several files to the MainOffice target.

<img src="/Images/TransferCFT/TransferCFT_Multiple_send_w_CG.png" class="maxWidth" />

<table>
   <th>
      <tr>
<th>          </th>
<th>Task         </th>
<th>Description         </th>
<th>Details         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>1</p>
<p> </p>
<p> </p>         </td>
         <td><p>Create a flow.</p>
<p> </p>
<p><br />
</p>         </td>
         <td><p>In <span class="mc-variable Primary.CG or_UM variable">Central Governance</span> click <span class="bold_in_para">Flows </span>&gt; <span class="bold_in_para">Add flow</span>.</p>
<p>Create a flow named <span class="bold_in_para">multiple_files_flow</span>, and give it the identifier <span class="bold_in_para">flow02</span>.</p>
<p>Define Store_66 as the Source, and MainOffice as the Target.</p>
<p><br />
</p>         </td>
         <td><a href="../intro_cg_task_catalog/t_multiple_filesflow"><img src="/Images/TransferCFT/mapArrow.png" /></a>         </td>
      </tr>
      <tr>
         <td><p>2</p>
<p> </p>         </td>
         <td><p>Enable a multiple files exchange.</p>
<p> </p>         </td>
         <td><p>Select the Source, and then <span class="bold_in_para">File properties</span>.</p>
<p>Under Filename select <span class="bold_in_para">Multiple</span>.</p>
<p> </p>         </td>
         <td><a href="../intro_cg_task_catalog/t_multiple_files"><img src="/Images/TransferCFT/mapArrow.png" /></a>         </td>
      </tr>
      <tr>
         <td><p>3</p>
<p> </p>         </td>
         <td><p>Deploy the flow.</p>
<p> </p>         </td>
         <td><p>In <span class="mc-variable Primary.CG or_UM variable">Central Governance</span> click <span class="bold_in_para">Deploy </span>to save and deploy.</p>
<p> </p>         </td>
         <td><a href="../intro_cg_task_catalog/t_savedeployflow"><img src="/Images/TransferCFT/mapArrow.png" /></a>         </td>
      </tr>
      <tr>
         <td><p>4</p>
<p> </p>
<p> </p>         </td>
         <td><p>Add three files for the exchange.</p>
<p> </p>
<p> </p>         </td>
         <td><p>Create a folder, you can name it <span class="bold_in_para">Store_66</span>, in the Store_66 <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> <span class="code">runtime/pub </span>directory.</p>
<p>Copy three test files to this folder, for example SALES_report, DAILY_news, and INVENTORY.</p>
<p> </p>         </td>
         <td>          </td>
      </tr>
      <tr>
         <td><p>5</p>
<p> </p>
<p> </p>
<p> </p>         </td>
         <td><p>Execute the SEND command.</p>
<p> </p>
<p> </p>         </td>
         <td>From the source <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span>, run the following command: <span class="code"><br />
CFTUTIL SEND part=&lt;instance_target&gt;, idf=flow02, fname=#pub/Store_66/*</span>
<p>Remember to replace <span class="code">&lt;instance_target&gt;</span> with the Transfer CFT instance for the target as it displays in your application list.</p>
<p> </p>         </td>
         <td><a href="../../../c_intro_userinterfaces/about_cftutil"><img src="/Images/TransferCFT/mapArrow.png" /></a>         </td>
      </tr>
      <tr>
         <td>6         </td>
         <td>Monitor the transfer status.         </td>
         <td>In the <span class="mc-variable Primary.CG or_UM variable">Central Governance</span> <span class="bold_in_para">Flows </span>tab, click <span class="bold_in_para">Monitoring </span>to check the status of the file exchange.         </td>
         <td><a href="../intro_cg_task_catalog/c_flow_monitoring"><img src="/Images/TransferCFT/mapArrow.png" /></a>         </td>
      </tr>
   </tbody>
</table>
