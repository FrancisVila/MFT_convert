{
    "title": "Create an implicit mode flow and transfer a file",
    "linkTitle": "Create an implicit mode flow and transfer a file",
    "weight": "160"
}You can use the implicit transfer mode to make a file whose content is frequently changing available to other applications. In this case the file is always available, and applications can retrieve it as many time as necessary.

<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Note</strong></span>         </td>
         <td>Implicit Mode implies that the Target is requester, and as such it is the Target that pulls the file.         </td>
      </tr>
   </tbody>
</table>

<img src="/Images/TransferCFT/Implicit_mode_cft_w_cg.png" class="maxWidth" alt="Simplified diagram of a Target Transfer CFT requesting a file from the Source" />

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
<p> </p>
<p> </p>
<p> </p>         </td>
         <td><p>Create a flow where the target is the requester.</p>
<p> </p>
<p> </p>
<p><br />
</p>         </td>
         <td><p>In <span class="mc-variable Primary.CG or_UM variable">Central Governance</span> click <span class="bold_in_para">Flows </span>&gt; <span class="bold_in_para">Add flow</span>.</p>
<p>Create a flow named <span class="bold_in_para">implicit_flow</span> and define the identifier as <span class="bold_in_para">flow03</span>.</p>
<p>To enable implicit mode, select <span class="bold_in_para">Target pulls file</span>.</p>
<p>Define the MainOffice as the Target, which will pull the file, and Store_89 as the file Source.</p>
<p><br />
</p>         </td>
         <td><a href="../intro_cg_task_catalog/t_defineflow"><img src="/Images/TransferCFT/mapArrow.png" /></a>         </td>
      </tr>
      <tr>
         <td><p>2</p>
<p> </p>
<p> </p>         </td>
         <td><p>Define the path to the file location.</p>
<p> </p>
<p> </p>         </td>
         <td><p>In the File properties of the Source, define the path to the file to be sent.</p>
<p>You can use, for example, the <span class="code">TEST </span>file located by default in the source <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span>'s <span class="code">runtime/pub</span> folder.</p>
<p> </p>         </td>
         <td>          </td>
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
<p> </p>
<p> </p>         </td>
         <td><p>Execute the RECV command.</p>
<p> </p>
<p> </p>
<p> </p>         </td>
         <td>From the <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> (MainOffice), run the following command: <span class="code"><br />
CFTUTIL RECV PART=&lt;instance_source&gt;, IDF=flow03</span>
<p>Remember in our example the source is Store_89, you should replace <span class="code">&lt;instance_source&gt;</span> with the Transfer CFT instance as it appears in your applications.</p>
<p> </p>         </td>
         <td><a href="../../../c_intro_userinterfaces/about_cftutil"><img src="/Images/TransferCFT/mapArrow.png" /></a>         </td>
      </tr>
      <tr>
         <td>5         </td>
         <td>Monitor the file transfer status.         </td>
         <td>In <span class="mc-variable Primary.CG or_UM variable">Central Governance</span> select the <span class="bold_in_para">Flows </span>tab, and click <span class="bold_in_para">Monitoring</span>.         </td>
         <td><a href="../intro_cg_task_catalog/c_flow_monitoring"><img src="/Images/TransferCFT/mapArrow.png" /></a>         </td>
      </tr>
   </tbody>
</table>
