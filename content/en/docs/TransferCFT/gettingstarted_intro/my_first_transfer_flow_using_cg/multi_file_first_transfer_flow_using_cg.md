{
    "title": "Create a flow to transfer multiple files",
    "linkTitle": "Create a flow to transfer multiple files",
    "weight": "150"
}This flow allows you to send multiple files to a defined application. In this scenario, the Store\_66 application sends several files to the MainOffice target.

![](/Images/TransferCFT/TransferCFT_Multiple_send_w_CG.png)


|   | Task  | Description  | Details  |
| --- | --- | --- | --- |
| 1<br/> <br/>  | Create a flow.<br/> <br/> <br />  | In Central Governance click ****Flows**** &gt; ****Add flow****.<br/> Create a flow named ****multiple_files_flow****, and give it the identifier ****flow02****.<br/> Define Store_66 as the Source, and MainOffice as the Target.<br/> <br />  | <a href="../intro_cg_task_catalog/t_multiple_filesflow">![](/Images/TransferCFT/mapArrow.png)</a>  |
| 2<br/>  | Enable a multiple files exchange.<br/>  | Select the Source, and then ****File properties****.<br/> Under Filename select ****Multiple****.<br/>  | <a href="../intro_cg_task_catalog/t_multiple_files">![](/Images/TransferCFT/mapArrow.png)</a>  |
| 3<br/>  | Deploy the flow.<br/>  | In Central Governance click ****Deploy**** to save and deploy.<br/>  | <a href="../intro_cg_task_catalog/t_savedeployflow">![](/Images/TransferCFT/mapArrow.png)</a>  |
| 4<br/> <br/>  | Add three files for the exchange.<br/> <br/>  | Create a folder, you can name it ****Store_66****, in the Store_66 Transfer CFT{{< TransferCFT/componentshortname  >}} <code>runtime/pub </code>directory.<br/> Copy three test files to this folder, for example SALES_report, DAILY_news, and INVENTORY.<br/>  |   |
| 5<br/> <br/> <br/>  | Execute the SEND command.<br/> <br/>  | From the source Transfer CFT{{< TransferCFT/componentshortname  >}}, run the following command: <code>CFTUTIL SEND part=&lt;instance_target&gt;, idf=flow02, fname=#pub/Store_66/*</code> Remember to replace <code>&lt;instance_target&gt;</code> with the Transfer CFT instance for the target as it displays in your application list.<br/>  | <a href="../../../c_intro_userinterfaces/about_cftutil">![](/Images/TransferCFT/mapArrow.png)</a>  |
| 6  | Monitor the transfer status.  | In the Central Governance ****Flows**** tab, click ****Monitoring**** to check the status of the file exchange.  | <a href="../intro_cg_task_catalog/c_flow_monitoring">![](/Images/TransferCFT/mapArrow.png)</a>  |

