{
    "title": "Create an implicit mode flow and transfer a file",
    "linkTitle": "Create an implicit mode flow and transfer a file",
    "weight": "160"
}You can use the implicit transfer mode to make a file whose content is frequently changing available to other applications. In this case the file is always available, and applications can retrieve it as many time as necessary.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">Implicit Mode implies that the Target is requester, and as such it is the Target that pulls the file.          </td>
      </tr>
</table>

![Simplified diagram of a Target Transfer CFT requesting a file from the Source](mapArrow.png)

<table cellspacing="0">
   <col/>
   <col/>
   <col/>
   <col/>
   <thead>
      <tr>
<th colspan="2">  Task</th>
         <th>Description</th>
         <th>Details</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>
            <p>1</p>
            <p> </p>
            <p> </p>
            <p> </p>
         </td>
         <td>
            <p>Create a flow where the target is the requester. </p>
            <p> </p>
            <p> </p>
            <p>
<br/>
</p>
         </td>
         <td>
            <p>In <span>Central Governance</span> click <span>Flows </span>&gt; <span>Add flow</span>.</p>
            <p>Create a flow named <span>implicit_flow</span> and define the identifier as <span>flow03</span>.</p>
            <p> To enable implicit mode, select <span>Target pulls file</span>. </p>
            <p>Define the MainOffice as the Target, which will pull the file, and Store_89 as the file Source.</p>
            <p>
<br/>
</p>
         </td>
         <td><a href="../intro_cg_task_catalog/t_defineflow"><img alt="" src="mapArrow.png"/></a>
         </td>
      </tr>
      <tr>
         <td>
            <p>2</p>
            <p> </p>
            <p> </p>
         </td>
         <td>
            <p>Define the path to the file location.</p>
            <p> </p>
            <p> </p>
         </td>
         <td>
            <p>In the File properties of the Source, define the path to the file to be sent. </p>
            <p>You can use, for example, the <span>TEST </span>file located by default in the source <span>Transfer CFT</span>'s <span>runtime/pub</span> folder.</p>
            <p> </p>
         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>
            <p>3</p>
            <p> </p>
         </td>
         <td>
            <p>Deploy the flow.</p>
            <p> </p>
         </td>
         <td>
            <p>In <span>Central Governance</span> click <span>Deploy </span>to save and deploy.</p>
            <p> </p>
         </td>
         <td><a href="../intro_cg_task_catalog/t_savedeployflow"><img alt="" src="mapArrow.png"/></a>
         </td>
      </tr>
      <tr>
         <td>
            <p>4</p>
            <p> </p>
            <p> </p>
            <p> </p>
         </td>
         <td>
            <p>Execute the RECV command.</p>
            <p> </p>
            <p> </p>
            <p> </p>
         </td>
         <td>From the  <span>Transfer CFT</span> (MainOffice),  run the following command: <span><br/>CFTUTIL RECV PART=&lt;instance_source&gt;, IDF=flow03</span>            <p>Remember in our example the source is Store_89, you should replace <span>&lt;instance_source&gt;</span> with the Transfer CFT instance as it appears in your applications.</p>            <p> </p>         </td>
         <td><a href="../../../c_intro_userinterfaces/about_cftutil"><img alt="" src="mapArrow.png"/></a>
         </td>
      </tr>
      <tr>
         <td>5         </td>
         <td>Monitor the file transfer status.          </td>
         <td>In <span>Central Governance</span> select the <span>Flows </span>tab, and click <span>Monitoring</span>.         </td>
         <td><a href="../intro_cg_task_catalog/c_flow_monitoring"><img alt="" src="mapArrow.png"/></a>
         </td>
      </tr>
   </tbody>
</table>
