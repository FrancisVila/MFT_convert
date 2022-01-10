{
    "title": "Perform broadcast and collect operations",
    "linkTitle": "Perform broadcast and collect operations",
    "weight": "190"
}Broadcast and collect modes allow you to send files to multiple partners and receiving files from multiple partners using a single command request for each.

## Broadcast

You can use broadcasting to send a file to an entire group of partners in one command, avoiding the task of sending the selected file individually to each of the partners in a flow.

The name of the broadcast list is itself a virtual partner, which contains a list of partners in your flow. This list of partners can be explicit, or it can reference a file that contains the list of partners.

Additionally, you can define what occurs if a partner is unknown, how the scripts are applied to the broadcast list, and so on. [More information](../../../concepts/transfer_command_overview/broadcast_collect)...

![$2]($1)

QQQ\_QQQ\_QQQ


|   | Task  | Description  | Details  |
| --- | --- | --- | --- |
| 1<br/> <br/>  | Create a flow.<br/> <br/> <br />  | In click **Flows** &gt; **Add flow**.<br/> Create a flow named **Broadcast_flow**, and give it the identifier **flow04**.<br/> In this flow the MainOffice is the Source with the two stores as the Targets. | <a href="../intro_cg_task_catalog/t_defineflow_broadcast">![]($1)</a>  |
| 2 | Enable broadcasting mode. | In the Source Transfer properties, enable Broadcast list. | <a href="../intro_cg_task_catalog/t_defineflow_broadcast#enable_broadcast_cg">![]($1)</a>  |
| 3 | Deploy the flow. | In click **Deploy** to save and deploy the flow. | <a href="../intro_cg_task_catalog/t_savedeployflow">![]($1)</a>  |
| 4 | Create a file for the flow. | For this example, copy a file SALES_report to transfer in the Store_66 {{< TransferCFT/componentshortname  >}}<code> runtime/pub </code>folder. |   |
| 5 | Execute the SEND command. | From the source {{< TransferCFT/componentshortname  >}}, run the following command:<br/> <code>CFTUTIL SEND PART=DEST_stores, IDF=flow04, FNAME=pub/SALES_report</code> | <a href="../../../c_intro_userinterfaces/about_cftutil">![]($1)</a>  |
| 6  | Monitor the file transfer status.  | In select the **Flows** tab, and click **Monitoring**.  | <a href="../intro_cg_task_catalog/c_flow_monitoring">![]($1)</a>  |


## Collect

Collecting files is the inverse of using a broadcast list. In the collect transfer mode you can receive a dedicated file from multiple partners (P*n*). This allows the receiver, or flow initiator, to receive a file from all defined partners using a single request command. More information...

![Simplified diagram of a Target Transfer CFT receiving files from multiple sources](/Images/TransferCFT/TransferCFT_Collect_w_CG.png)

 

QQQ\_QQQ\_QQQ


|   |  Task  | Description  | Details  |
| --- | --- | --- | --- |
| 1<br/>  | Create a flow.<br/> <br />  | In define a flow named **Collect_flow**, and give it the identifier **flow05**.<br/> Use the Source as MainOffice and the stores as the Target.<br />  | <a href="../intro_cg_task_catalog/t_define_simpleflow">![]($1)</a>  |
| 2 | Enable collect mode. | In the Collect_flow definition, modify so that the Target pulls file. | <a href="../intro_cg_task_catalog/t_defineflow_collect">![]($1)</a>  |
| 3 | Define the path to the Target file for each store.  | In the Target (each store) select File properties. In Path field, enter the path to the file to send. | <a href="../intro_cg_task_catalog/t_collect_target_properties">![]($1)</a>  |
| 4 | Deploy the flow. | In you can save and deploy the flow. | <a href="../intro_cg_task_catalog/t_savedeployflow">![]($1)</a>  |
| 5 | Run the RECV command. | In {{< TransferCFT/componentshortname  >}}, run the following command: <code></code><code>CFTUTIL RECV PART=DEST_Stores, IDF=flow05</code>  | <a href="../../../c_intro_userinterfaces/about_cftutil">![]($1)</a>  |
| 6 | Monitor the file transfer status. | In select the **Flows** tab, and click **Monitoring**. | <a href="../intro_cg_task_catalog/c_flow_monitoring">![]($1)</a>  |

