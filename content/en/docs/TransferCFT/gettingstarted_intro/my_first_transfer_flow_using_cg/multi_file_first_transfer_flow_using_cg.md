{
    "title": "Create a flow to transfer multiple files",
    "linkTitle": "Create a flow to transfer multiple files",
    "weight": "150"
}This flow allows you to send multiple files to a defined application. In this scenario, the Store\_66 application sends several files to the MainOffice target.

![](/Images/TransferCFT/TransferCFT_Multiple_send_w_CG.png)

<table data-cellspacing="0">
   <thead>
      <tr class="header">
         <th> </th>
         <th>Task</th>
         <th>Description</th>
         <th>Details</th>
      </tr>
   </thead>
   <tbody>
      <tr class="odd">
         <td>            <p>1</p>
            <p> </p>
            <p> </p>         </td>
         <td>            <p>Create a flow.</p>
            <p> </p>
            <p><br />
</p>         </td>
         <td>            <p>In <span>Central Governance</span> click <span>Flows </span>&gt; <span>Add flow</span>.</p>
            <p>Create a flow named <span>multiple_files_flow</span>, and give it the identifier <span>flow02</span>.</p>
            <p>Define Store_66 as the Source, and MainOffice as the Target.</p>
            <p><br />
</p>         </td>
         <td><a href="intro_cg_task_catalog/t_multiple_filesflow"><img src="/Images/TransferCFT/mapArrow.png" /></a>         </td>
      </tr>
      <tr class="even">
         <td>            <p>2</p>
            <p> </p>         </td>
         <td>            <p>Enable a multiple files exchange.</p>
            <p> </p>         </td>
         <td>            <p>Select the Source, and then <span>File properties</span>.</p>
            <p>Under Filename select <span>Multiple</span>.</p>
            <p> </p>         </td>
         <td><a href="intro_cg_task_catalog/t_multiple_files"><img src="/Images/TransferCFT/mapArrow.png" /></a>         </td>
      </tr>
      <tr class="odd">
         <td>            <p>3</p>
            <p> </p>         </td>
         <td>            <p>Deploy the flow.</p>
            <p> </p>         </td>
         <td>            <p>In <span>Central Governance</span> click <span>Deploy </span>to save and deploy.</p>
            <p> </p>         </td>
         <td><a href="intro_cg_task_catalog/t_savedeployflow"><img src="/Images/TransferCFT/mapArrow.png" /></a>         </td>
      </tr>
      <tr class="even">
         <td>            <p>4</p>
            <p> </p>
            <p> </p>         </td>
         <td>            <p>Add three files for the exchange.</p>
            <p> </p>
            <p> </p>         </td>
         <td>            <p>Create a folder, you can name it <span>Store_66</span>, in the Store_66 <span>Transfer CFT</span> <span>runtime/pub </span>directory.</p>
            <p>Copy three test files to this folder, for example SALES_report, DAILY_news, and INVENTORY.</p>
            <p> </p>         </td>
         <td>          </td>
      </tr>
      <tr class="odd">
         <td>            <p>5</p>
            <p> </p>
            <p> </p>
            <p> </p>         </td>
         <td>            <p>Execute the SEND command.</p>
            <p> </p>
            <p> </p>         </td>
         <td>From the source <span>Transfer CFT</span>, run the following command: <span><br />
CFTUTIL SEND part=&lt;instance_target&gt;, idf=flow02, fname=#pub/Store_66/*</span>
            <p>Remember to replace <span>&lt;instance_target&gt;</span> with the Transfer CFT instance for the target as it displays in your application list.</p>
            <p> </p>         </td>
         <td><a href="../../c_intro_userinterfaces/about_cftutil"><img src="/Images/TransferCFT/mapArrow.png" /></a>         </td>
      </tr>
      <tr class="even">
         <td>6         </td>
         <td>Monitor the transfer status.         </td>
         <td>In the <span>Central Governance</span> <span>Flows </span>tab, click <span>Monitoring </span>to check the status of the file exchange.         </td>
         <td><a href="intro_cg_task_catalog/c_flow_monitoring"><img src="/Images/TransferCFT/mapArrow.png" /></a>         </td>
      </tr>
   </tbody>
</table>
