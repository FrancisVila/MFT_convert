{
    "title": "Create an implicit mode flow and transfer a file",
    "linkTitle": "Create an implicit mode flow and transfer a file",
    "weight": "160"
}You can use the implicit transfer mode to make a file whose content is frequently changing available to other applications. In this case the file is always available, and applications can retrieve it as many time as necessary.

> **Note**  
> Implicit Mode implies that the Target is requester, and as such it is the Target that pulls the file.

<img src="/Images/TransferCFT/Implicit_mode_cft_w_cg.png" class="maxWidth" alt="Simplified diagram of a Target Transfer CFT requesting a file from the Source" />

<table>
   <thead>
      <tr>
<th  colspan="2" >  Task         </th>
<th  >Description         </th>
<th >Details         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td  ><p>1</p>
<p> </p>
<p> </p>
<p> </p>         </td>
         <td  ><p>Create a flow where the target is the requester.</p>
<p> </p>
<p> </p>
<p><br />
</p>         </td>
         <td  ><p>In click <strong>Flows</strong> &gt; <strong>Add flow</strong>.</p>
<p>Create a flow named <strong>implicit_flow</strong> and define the identifier as <strong>flow03</strong>.</p>
<p>To enable implicit mode, select <strong>Target pulls file</strong>.</p>
<p>Define the MainOffice as the Target, which will pull the file, and Store_89 as the file Source.</p>
<p><br />
</p>         </td>
         <td ><a href="../intro_cg_task_catalog/t_defineflow"><img src="/Images/TransferCFT/mapArrow.png" /></a>         </td>
      </tr>
      <tr>
         <td  ><p>2</p>
<p> </p>
<p> </p>         </td>
         <td  ><p>Define the path to the file location.</p>
<p> </p>
<p> </p>         </td>
         <td  ><p>In the File properties of the Source, define the path to the file to be sent.</p>
<p>You can use, for example, the <code>TEST </code>file located by default in the source {{< TransferCFT/componentshortname  >}}'s <code>runtime/pub</code> folder.</p>
<p> </p>         </td>
         <td >          </td>
      </tr>
      <tr>
         <td  ><p>3</p>
<p> </p>         </td>
         <td  ><p>Deploy the flow.</p>
<p> </p>         </td>
         <td  ><p>In click <strong>Deploy</strong> to save and deploy.</p>
<p> </p>         </td>
         <td ><a href="../intro_cg_task_catalog/t_savedeployflow"><img src="/Images/TransferCFT/mapArrow.png" /></a>         </td>
      </tr>
      <tr>
         <td  ><p>4</p>
<p> </p>
<p> </p>
<p> </p>         </td>
         <td  ><p>Execute the RECV command.</p>
<p> </p>
<p> </p>
<p> </p>         </td>
         <td  >From the  {{< TransferCFT/componentshortname  >}} (MainOffice),  run the following command: <code>CFTUTIL RECV PART=&lt;instance_source&gt;, IDF=flow03</code>
<p>Remember in our example the source is Store_89, you should replace <code>&lt;instance_source&gt;</code> with the Transfer CFT instance as it appears in your applications.</p>
<p> </p>         </td>
         <td ><a href="../../../c_intro_userinterfaces/about_cftutil"><img src="/Images/TransferCFT/mapArrow.png" /></a>         </td>
      </tr>
      <tr>
         <td  >5         </td>
         <td  >Monitor the file transfer status.         </td>
         <td  >In select the <strong>Flows</strong> tab, and click <strong>Monitoring</strong>.         </td>
         <td ><a href="../intro_cg_task_catalog/c_flow_monitoring"><img src="/Images/TransferCFT/mapArrow.png" /></a>         </td>
      </tr>
   </tbody>
</table>
