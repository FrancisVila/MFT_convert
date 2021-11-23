{
    "title": "Create a flow to transfer multiple files",
    "linkTitle": "Create a flow to transfer multiple files",
    "weight": "150"
}This flow allows you to send multiple files to a defined application. In this scenario, the Store\_66 application sends several files to the MainOffice target.

<img src="/Images/TransferCFT/TransferCFT_Multiple_send_w_CG.png" class="maxWidth" />

<table>
   <thead>
      <tr>
<th style="text-align: center;" class="TableStyle-SynchTaskMap-HeadE-Column1-Header1">          </th>
<th style="text-align: left;" class="TableStyle-SynchTaskMap-HeadE-Column1-Header1">Task         </th>
<th style="text-align: left;" class="TableStyle-SynchTaskMap-HeadE-Column1-Header1">Description         </th>
<th class="TableStyle-SynchTaskMap-HeadD-Column1-Header1">Details         </th>
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
         <td><p>In click <strong>Flows</strong> &gt; <strong>Add flow</strong>.</p>
<p>Create a flow named <strong>multiple_files_flow</strong>, and give it the identifier <strong>flow02</strong>.</p>
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
         <td><p>Select the Source, and then <strong>File properties</strong>.</p>
<p>Under Filename select <strong>Multiple</strong>.</p>
<p> </p>         </td>
         <td><a href="../intro_cg_task_catalog/t_multiple_files"><img src="/Images/TransferCFT/mapArrow.png" /></a>         </td>
      </tr>
      <tr>
         <td><p>3</p>
<p> </p>         </td>
         <td><p>Deploy the flow.</p>
<p> </p>         </td>
         <td><p>In click <strong>Deploy</strong> to save and deploy.</p>
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
         <td><p>Create a folder, you can name it <strong>Store_66</strong>, in the Store_66 {{< TransferCFT/componentshortname  >}} <code>runtime/pub </code>directory.</p>
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
         <td>From the source {{< TransferCFT/componentshortname  >}}, run the following command: <code>CFTUTIL SEND part=&lt;instance_target&gt;, idf=flow02, fname=#pub/Store_66/*</code>
<p>Remember to replace <code>&lt;instance_target&gt;</code> with the Transfer CFT instance for the target as it displays in your application list.</p>
<p> </p>         </td>
         <td><a href="../../../c_intro_userinterfaces/about_cftutil"><img src="/Images/TransferCFT/mapArrow.png" /></a>         </td>
      </tr>
      <tr>
         <td>6         </td>
         <td>Monitor the transfer status.         </td>
         <td>In the <strong>Flows</strong> tab, click <strong>Monitoring</strong> to check the status of the file exchange.         </td>
         <td><a href="../intro_cg_task_catalog/c_flow_monitoring"><img src="/Images/TransferCFT/mapArrow.png" /></a>         </td>
      </tr>
   </tbody>
</table>
