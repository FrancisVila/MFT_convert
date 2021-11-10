{
    "title": "My first transfer flow ",
    "linkTitle": "First transfer flow with Central Governance",
    "weight": "110"
}This topic describes how to create basic <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> transfer flows using <span class="mc-variable Primary.CG or_UM variable">Central Governance</span>. Once you understand file transfer flow concepts, you can customize your application integrations and data flows.

## Learn how to...

-   [Create applications to use in flows](app_first_transfer_flow_using_cg)
-   [Create and deploy a basic flow](simple_first_transfer_flow_using_cg)
-   [Create a flow that sends multiple files](multi_file_first_transfer_flow_using_cg)
-   [Create an implicit mode flow](implicit_first_transfer_flow_using_cg)
-   [Perform broadcast and collect operations](broadcast_first_transfer_flow_using_cg)

> **Note:**
>
> Tip  
> Existing Transfer CFT users may want to refer to the Transfer CFT to Central Governance parameter mapping.

## What you will need

-   A running <span class="mc-variable suite_variables.Central_GovernanceName variable">Central Governance</span> system
-   Three started <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span>s that are registered with <span class="mc-variable Primary.CG or_UM variable">Central Governance</span>
-   Three files for exchanges. After creating the files, name them: SALES\_report, DAILY\_news, and INVENTORY

<!-- -->

-   Appropriate rights in <span class="mc-variable Primary.CG or_UM variable">Central Governance</span> for creating flows - refer to the <span class="mc-variable Primary.CG or_UM variable" style="mc-tag-and-class: ;font-style: italic;">Central Governance</span><span class="italic_in_para" style="font-style: italic;"> User's Guide</span> for more information on user rights
-   Familiarize yourself with the two user interfaces as described in the [Getting started overview](../)

## Goal

These exercises create the flow types shown in the diagram below.

Notice that the <span class="bold_in_para">NAME </span>of the flow in the Flow List is a user friendly name describing the flow, while the <span class="bold_in_para">IDENTIFIER </span>is the parameter (ID) that you will use in your transfer commands.

         <img src="/Images/TransferCFT/results_cg_flows.png" class="maxWidth" alt="This diagram lists the five flows to create, which are simple, multiple, implicit, broadcast, and collect." />

## Procedure overview

Use the **Details** arrows ![](/Images/TransferCFT/mapArrow.png) to get more information on a step as needed.

<span id="Create_applications"></span>

### Create applications to use in flows

When you are working in <span class="mc-variable Primary.CG or_UM variable">Central Governance</span>, you create *applications* that represent your exchange partners. In these exercises we create three applications in <span class="mc-variable Primary.CG or_UM variable">Central Governance</span>.

<table>
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">          </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Task         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Description         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1">Details         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>1         </td>
         <td><p>Check your Transfer CFTs in <span class="mc-variable Primary.CG or_UM variable">Central Governance</span>.<br />
</p>         </td>
         <td><p>In <span class="mc-variable Primary.CG or_UM variable">Central Governance</span> select <span class="bold_in_para">Products </span>on the top toolbar to open the <span class="bold_in_para">Product List</span> page and note the host name of the <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span>s to use in these exercises.</p>         </td>
         <td><a href="intro_cg_task_catalog/t_view_products_in_cg"><img src="/Images/TransferCFT/mapArrow.png" /></a>         </td>
      </tr>
      <tr>
         <td>2         </td>
         <td>Add an application.         </td>
         <td>In this example, create three applications to represent the MainOffice, Store_66, and Store_89.         </td>
         <td><a href="intro_cg_task_catalog/t_declareapplication"><img src="/Images/TransferCFT/mapArrow.png" /></a>         </td>
      </tr>
      <tr>
         <td> 
<p>Notice the association between the application <span class="bold_in_para">Name </span>and the<span class="bold_in_para"> Transfer CFT</span> instance identifier. You will need the Transfer CFT identifier, for example <span class="code">CFTlptxumcft4-01</span> in the example below, to use in your transfer commands.</p>
<p>Your <strong>Name</strong> list should look like this:</p>
<p><img src="/Images/TransferCFT/application_list_complete.png" class="maxWidth" alt="Application list in Central Governance showing 3 example applications to use in flows" /></p>
<p> </p>
<blockquote>
<p><strong>Note:</strong></p>
<p>Tip  The Transfer CFT field in Central Governance maps to the Transfer CFT PART parameter.</p>
</blockquote>         </td>
      </tr>
   </tbody>
</table>

<span id="Create_and_deploy_a_flow"></span>

### Create and deploy a basic flow

Let's begin by creating a simple flow, and then exchange a file. In this example, Store\_66 (server/sender) sends a daily SALES\_report to the MainOffice (requester/receiver).

<img src="/Images/TransferCFT/TransferCFT_Standard_w_cg.png" class="maxWidth" alt="Simplified diagram of a Source Transfer CFT sending a file to a Target" />

 

<table>
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">          </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Task         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Description         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1">Details         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>1         </td>
         <td><p>Define a flow.<br />
</p>         </td>
         <td><p>In <span class="mc-variable Primary.CG or_UM variable">Central Governance</span> define a flow named Simple_flow and give it the identifier flow01.</p>
<p>Use Store_66 as the Source and the MainOffice as the Target.<br />
Note: You cannot modify the Protocol until you have defined both the Source and Target.</p>         </td>
         <td><a href="intro_cg_task_catalog/t_defineflow"><img src="/Images/TransferCFT/mapArrow.png" /></a>         </td>
      </tr>
      <tr>
         <td>2         </td>
         <td><p>Deploy the flow.</p>         </td>
         <td>In <span class="mc-variable Primary.CG or_UM variable">Central Governance</span> you can save now and deploy at a later date, or click Deploy to save and deploy.         </td>
         <td><a href="intro_cg_task_catalog/t_savedeployflow"><img src="/Images/TransferCFT/mapArrow.png" /></a>         </td>
      </tr>
      <tr>
         <td>3         </td>
         <td>Create a file to exchange.         </td>
         <td>For this example, create a file named SALES_report, and place it in the Store_66's <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> runtime\pub folder .         </td>
         <td><a href="intro_cg_task_catalog/t_create_sample_files"><img src="/Images/TransferCFT/mapArrow.png" /></a>         </td>
      </tr>
      <tr>
         <td>4         </td>
         <td>Run the SEND command.         </td>
         <td><p>In <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span>, run the following command:<br />
CFTUTIL SEND part=&lt;instance_MainOffice&gt;, idf=flow01, fname=pub\SALES_report</p>
<p>Remember, replace &lt;instance_MainOffice&gt; with the Transfer CFT instance for the MainOffice as it displays in the list of applications.</p>
<blockquote>
<p><strong>Note:</strong></p>
<p>Tip  
The flow Identifier field is equivalent to the Transfer CFT IDF parameter.</p>
</blockquote>         </td>
         <td><a href="../../c_intro_userinterfaces/about_cftutil"><img src="/Images/TransferCFT/mapArrow.png" /></a>         </td>
      </tr>
      <tr>
         <td>5         </td>
         <td>Monitor the flow.         </td>
         <td>In <span class="mc-variable Primary.CG or_UM variable">Central Governance</span>, check the status of the file exchange.         </td>
         <td><a href="intro_cg_task_catalog/c_flow_monitoring"><img src="/Images/TransferCFT/mapArrow.png" /></a>         </td>
      </tr>
   </tbody>
</table>

<span id="Send_multiple_files_to_application"></span>

### Create a flow that sends multiple files to an application

This flow sends multiple files to a defined application. So a Store\_66 application might create several files and set them to an available state, and the MainOffice application can then retrieve these when ready, for example at a scheduled time.

<img src="/Images/TransferCFT/multiple_send_w_cg.png" class="maxWidth" alt="Simplified diagram of a Source Transfer CFT sending a multiple files to a Target" />

<table>
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">          </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Task         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Description         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1">Details         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>1         </td>
         <td><p>Create a flow.<br />
</p>         </td>
         <td><p>In <span class="mc-variable Primary.CG or_UM variable">Central Governance</span> define a flow called <span class="code">flow02 </span>with Store_66 as the Source, and the MainOffice as the Target.<br />
</p>         </td>
         <td><a href="intro_cg_task_catalog/t_multiple_filesflow"><img src="/Images/TransferCFT/mapArrow.png" /></a>         </td>
      </tr>
      <tr>
         <td>2         </td>
         <td><p>Enable multiple files for the exchange.</p>         </td>
         <td><p>Select the Source, and then File properties. Enable Multiple files.</p>         </td>
         <td><a href="intro_cg_task_catalog/t_multiple_files"><img src="/Images/TransferCFT/mapArrow.png" /></a>         </td>
      </tr>
      <tr>
         <td>3         </td>
         <td>Create the files for the exchange.         </td>
         <td><p>For this example, create a folder called Store_66 in the Store_66 <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> <span class="code">runtime\pub\ </span>directory.</p>
<p>Copy three files to this folder and call them <span class="code">SALES_report</span>, <span class="code">DAILY_news</span>, and <span class="code">INVENTORY</span>.</p>         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>4         </td>
         <td>Deploy the flow.         </td>
         <td>In <span class="mc-variable Primary.CG or_UM variable">Central Governance</span> you can save, and deploy later, or save and deploy immediately.         </td>
         <td><a href="intro_cg_task_catalog/t_savedeployflow"><img src="/Images/TransferCFT/mapArrow.png" /></a>         </td>
      </tr>
      <tr>
         <td>5         </td>
         <td>Run the SEND command.         </td>
         <td>In <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span>, run the following command: <span class="code"><br />
CFTUTIL SEND part=&lt;instance_MainOffice&gt;, idf=flow02, fname=#pub\Store_66\*</span>
<p>Remember, replace <span class="code">&lt;instance_MainOffice&gt;</span> with the Transfer CFT instance for the MainOffice as it displays in the list of applications.</p>         </td>
         <td><a href="../../c_intro_userinterfaces/about_cftutil"><img src="/Images/TransferCFT/mapArrow.png" /></a>         </td>
      </tr>
      <tr>
         <td>6         </td>
         <td>Monitor the flow.         </td>
         <td>In <span class="mc-variable Primary.CG or_UM variable">Central Governance</span>, check the status of the file exchange.         </td>
         <td><a href="intro_cg_task_catalog/c_flow_monitoring"><img src="/Images/TransferCFT/mapArrow.png" /></a>         </td>
      </tr>
   </tbody>
</table>

<span id="Create_implicit_mode_flow"></span>

### Create an implicit mode flow

You can use the transfer mode to make a file whose content is frequently changing available to applications. The file is always available, and applications can retrieve it as many time as necessary.

<img src="/Images/TransferCFT/CFT_w_CG_Implicit_mode.png" class="maxWidth" alt="Simplified diagram of a Target Transfer CFT requesting a file from the Source" />

<table>
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">          </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Task         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Description         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1">Details         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>1         </td>
         <td><p>Create an implicit flow.<br />
</p>         </td>
         <td><p>In <span class="mc-variable Primary.CG or_UM variable">Central Governance</span> define a flow called <span class="code">flow03</span>.</p>
<p>To enable implicit mode, you select <span class="bold_in_para">Target pulls file</span> in the flow's <span class="italic_in_para">General Information</span> page.</p>
<p>Continue to define the flow with the MainOffice as the Target, which will pull the file, and Store_89 as the file Source.<br />
</p>         </td>
         <td><img src="/Images/TransferCFT/mapArrow.png" />         </td>
      </tr>
      <tr>
         <td>2         </td>
         <td>Define the path to the file location.         </td>
         <td><p>In the File properties of the Source, define the path to the file to be sent.</p>
<p>In our example, use the TEST file located in the <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> runtime /pub folder.</p>         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>3         </td>
         <td><p>Deploy the flow.</p>         </td>
         <td>In <span class="mc-variable Primary.CG or_UM variable">Central Governance</span> you can save and deploy later, or save and deploy.         </td>
         <td><a href="intro_cg_task_catalog/t_savedeployflow"><img src="/Images/TransferCFT/mapArrow.png" /></a>         </td>
      </tr>
      <tr>
         <td>4         </td>
         <td>Run the RECV command.         </td>
         <td>In <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span>, run the following command: <span class="code"><br />
CFTUTIL RECV PART=&lt;instance_Store_89&gt;, IDF=flow03</span>
<p>Remember, replace <span class="code">&lt;instance_Store_89&gt;</span> with the Transfer CFT instance for Store_89 as it displays in the list of applications.</p>         </td>
         <td><a href="../../c_intro_userinterfaces/about_cftutil"><img src="/Images/TransferCFT/mapArrow.png" /></a>         </td>
      </tr>
      <tr>
         <td>5         </td>
         <td>Monitor the flow.         </td>
         <td>In <span class="mc-variable Primary.CG or_UM variable">Central Governance</span>, check the status of the file exchange.         </td>
         <td><a href="intro_cg_task_catalog/c_flow_monitoring"><img src="/Images/TransferCFT/mapArrow.png" /></a>         </td>
      </tr>
   </tbody>
</table>

<span id="Broadcast_and_collect_using_cg"></span>

### Perform broadcast and collect operations

Broadcast and collect modes allow you to send files to multiple partners and receiving files from multiple partners using a single command request for each.

#### Broadcasting

You can use broadcasting to send a file to an entire group of partners in one command, avoiding the task of sending the selected file individually to each of the partners in a flow.

The name of the broadcast list is itself a virtual partner, which contains a list of partners in your flow. This list of partners can be explicit, or it can reference a file that contains the list of partners.

Additionally, you can define what occurs if a partner is unknown, how the scripts are applied to the broadcast list, and so on. [More information](../../concepts/transfer_command_overview/broadcast_collect)...

![Simplified diagram of a Source Transfer CFT sending a file to multiple Targets](/Images/TransferCFT/TransferCFT_Broadcast_w_CG.png)

<table>
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">          </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Task         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Description         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1">Details         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>1         </td>
         <td><p>Create a flow.<br />
</p>         </td>
         <td><p>In <span class="mc-variable Primary.CG or_UM variable">Central Governance</span> define a flow called <span class="code">flow04</span>. In this flow the MainOffice is the Source with the two stores as the Targets.</p>         </td>
         <td><a href="intro_cg_task_catalog/t_defineflow_broadcast"><img src="/Images/TransferCFT/mapArrow.png" /></a>         </td>
      </tr>
      <tr>
         <td>2         </td>
         <td>Enable broadcasting mode.         </td>
         <td>In the Source Transfer properties, enable Broadcast list.         </td>
         <td><a href="intro_cg_task_catalog/t_defineflow_broadcast#enable_broadcast_cg"><img src="/Images/TransferCFT/mapArrow.png" /></a>         </td>
      </tr>
      <tr>
         <td>3         </td>
         <td>          </td>
         <td>For this example, copy a file SALES_report to transfer in the Store_66 <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> runtime\pub folder.         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>4         </td>
         <td><p>Deploy the flow.</p>         </td>
         <td>In <span class="mc-variable Primary.CG or_UM variable">Central Governance</span> you can save and deploy at a later date, or both save and deploy now.         </td>
         <td><a href="intro_cg_task_catalog/t_savedeployflow"><img src="/Images/TransferCFT/mapArrow.png" /></a>         </td>
      </tr>
      <tr>
         <td>5         </td>
         <td>Run the SEND command.         </td>
         <td><p>In <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span>, run the following command:</p>
<p><span class="code">CFTUTIL SEND PART=DEST_stores, IDF=flow04, FNAME=pub/SALES_report</span></p>         </td>
         <td><a href="../../c_intro_userinterfaces/about_cftutil"><img src="/Images/TransferCFT/mapArrow.png" /></a>         </td>
      </tr>
      <tr>
         <td>6         </td>
         <td>Monitor the flow.         </td>
         <td>In <span class="mc-variable Primary.CG or_UM variable">Central Governance</span>, check the status of the file exchange.         </td>
         <td><a href="intro_cg_task_catalog/c_flow_monitoring"><img src="/Images/TransferCFT/mapArrow.png" /></a>         </td>
      </tr>
   </tbody>
</table>

#### Collecting

Collecting files is the inverse of using a broadcast list. In the collect transfer mode you can receive a dedicated file from multiple partners (P*n*). This allows the receiver, or flow initiator, to receive a file from all defined partners using a single request command. More information...

![Simplified diagram of a Target Transfer CFT receiving files from multiple sources](/Images/TransferCFT/TransferCFT_Collect_w_CG.png)

 

<table>
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">          </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Task         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Description         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1">Details         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>1         </td>
         <td><p>Create a flow.<br />
</p>         </td>
         <td><p>In <span class="mc-variable Primary.CG or_UM variable">Central Governance</span> create a flow called <span class="code">flow05 </span>and define the Source as MainOffice and the stores as the Target.<br />
<span class="bold_in_para">Note</span>: You cannot define the Protocol until you have defined both the Source and Target.</p>         </td>
         <td><a href="intro_cg_task_catalog/t_define_simpleflow"><img src="/Images/TransferCFT/mapArrow.png" /></a>         </td>
      </tr>
      <tr>
         <td>2         </td>
         <td>Enable collect mode.         </td>
         <td>In the Collect_flow definition, modify to Target pulls file.         </td>
         <td><a href="intro_cg_task_catalog/t_defineflow_collect"><img src="/Images/TransferCFT/mapArrow.png" /></a>         </td>
      </tr>
      <tr>
         <td>3         </td>
         <td>Define the path to the Target file for each store.         </td>
         <td>In the Target (each store) select File properties. In Path field, enter the path to the file to send.         </td>
         <td><a href="intro_cg_task_catalog/t_collect_target_properties"><img src="/Images/TransferCFT/mapArrow.png" /></a>         </td>
      </tr>
      <tr>
         <td>4         </td>
         <td><p>Deploy the flow.</p>         </td>
         <td>In <span class="mc-variable Primary.CG or_UM variable">Central Governance</span> you can save and deploy later, or save and deploy.         </td>
         <td><a href="intro_cg_task_catalog/t_savedeployflow"><img src="/Images/TransferCFT/mapArrow.png" /></a>         </td>
      </tr>
      <tr>
         <td>5         </td>
         <td>Run the RECV command.         </td>
         <td>In <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span>, run the following command: <span class="code"><br />
CFTUTIL RECV PART=DEST_Stores, IDF=flow05</span>         </td>
         <td><a href="../../c_intro_userinterfaces/about_cftutil"><img src="/Images/TransferCFT/mapArrow.png" /></a>         </td>
      </tr>
      <tr>
         <td>6         </td>
         <td>Monitor the flow.         </td>
         <td>In <span class="mc-variable Primary.CG or_UM variable">Central Governance</span>, check the status of the file exchange.         </td>
         <td><a href="intro_cg_task_catalog/c_flow_monitoring"><img src="/Images/TransferCFT/mapArrow.png" /></a>         </td>
      </tr>
   </tbody>
</table>

<span id="Get"></span>

## Get more information

Once you understand the basic modes and concepts described in this section, you can add processing, symbolic variables, scripts and more to your transfers using other <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> options and features. See the dedicated sections in this document for details on customizing your transfer flows. A good place to start is [Transfer Concepts](../../concepts/transfer_command_overview), which presents high-level transfer processing concepts, transfer mode details, and procedural topics.

-   For more information on <span class="mc-variable suite_variables.Central_GovernanceName variable">Central Governance</span>, screen details, checking product status, and so on, please refer to the <span class="mc-variable suite_variables.Central_GovernanceName variable" style="font-style: italic;">Central Governance</span> <span class="mc-variable suite_variables.DocTypeUser variable" style="font-style: italic;">User Guide</span>.
-   For a complete listing of Source and Target parameters, refer to the Transfer CFT to <span class="mc-variable Primary.CG or_UM variable">Central Governance</span> parameter mapping available in the **Central Governance* <span class="mc-variable suite_variables.DocTypeUser variable" style="font-style: italic;">User Guide</span>*.
