{
    "title": "Create an implicit mode flow and transfer a file",
    "linkTitle": "Create an implicit mode flow and transfer a file",
    "weight": "160"
}You can use the implicit transfer mode to make a file whose content is frequently changing available to other applications. In this case the file is always available, and applications can retrieve it as many time as necessary.

> **Note**
>
> Implicit Mode implies that the Target is requester, and as such it is the Target that pulls the file.

![Simplified diagram of a Target Transfer CFT requesting a file from the Source](/Images/TransferCFT/Implicit_mode_cft_w_cg.png)

QQQ\_QQQ\_QQQ


|   | Task  | Description  | Details  |
| --- | --- | --- | --- |
| 1<br/> <br/> <br/>  | Create a flow where the target is the requester.<br/> <br/> <br/> <br />  | In Central Governance click ****Flows**** &gt; ****Add flow****.<br/> Create a flow named ****implicit_flow**** and define the identifier as ****flow03****.<br/> To enable implicit mode, select ****Target pulls file****.<br/> Define the MainOffice as the Target, which will pull the file, and Store_89 as the file Source.<br/> <br />  | <a href="../intro_cg_task_catalog/t_defineflow">![](/Images/TransferCFT/mapArrow.png)</a>  |
| 2<br/> <br/>  | Define the path to the file location.<br/> <br/>  | In the File properties of the Source, define the path to the file to be sent.<br/> You can use, for example, the TEST file located by default in the source Transfer CFT{{< TransferCFT/componentshortname  >}}'s runtime/pub folder.<br/>  |   |
| 3<br/>  | Deploy the flow.<br/>  | In Central Governance click ****Deploy**** to save and deploy.<br/>  | <a href="../intro_cg_task_catalog/t_savedeployflow">![](/Images/TransferCFT/mapArrow.png)</a>  |
| 4<br/> <br/> <br/>  | Execute the RECV command.<br/> <br/> <br/>  | From the Transfer CFT{{< TransferCFT/componentshortname  >}} (MainOffice), run the following command:<br /> CFTUTIL RECV PART=&lt;instance_source&gt;, IDF=flow03 Remember in our example the source is Store_89, you should replace &lt;instance_source&gt; with the Transfer CFT instance as it appears in your applications.<br/>  | <a href="../../../c_intro_userinterfaces/about_cftutil">![](/Images/TransferCFT/mapArrow.png)</a>  |
| 5  | Monitor the file transfer status.  | In Central Governance select the ****Flows**** tab, and click ****Monitoring****.  | <a href="../intro_cg_task_catalog/c_flow_monitoring">![](/Images/TransferCFT/mapArrow.png)</a>  |

