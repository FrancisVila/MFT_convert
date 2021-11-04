{
    "title": "Add a relay (store and forward)",
    "linkTitle": "Add a relay (store and forward)",
    "weight": "180"
}This page describes how to use a relay in a SEND/RECV operation. You can use a SEND/RECV to perform a transfer with a single partner via an intermediate machine, or relay, using the store and forward mode. Additionally, you can combine the store and forward mode with broadcasting when using the SEND command.

## On <span class="mc-variable Primary.CG or_UM variable">Central Governance</span>

1.  In the toolbar, select **Flows** > **Add flow**.  

    ![](/Images/TransferCFT/flow1.png)

2.  **Name** the flow `Relay_flow`.  
    ![](/Images/TransferCFT/flow3.png)

3.  Select **Source? > Add source**, and click to select the source <span class="mc-variable axway_variables.Component_Long_Name variable">Transfer CFT</span>. Choose `Store_66` and then click **Select as source**.  
    You can leave all other fields set to the default values.  
    ![](/Images/TransferCFT/flow4.png)

4.  Click **Protocol?** and select **PeSIT**. Enter <span class="code">flow22 </span>as the **Flow identifier**.  
    Use the other default values, and remember that the flow identifier is the IDF on Transfer CFT.  
    ![](/Images/TransferCFT/flow5.png)

5.  Select **Target? > Add target**. Then click to choose the target <span class="mc-variable axway_variables.Component_Long_Name variable">Transfer CFT</span>. Select <span class="code">MainOffice </span>and then click **Select as target**.

6.  Click **Relay** then click **Edit relay**. Select the relay, and confirm by clicking **Select as relay**.  
    ![](/Images/TransferCFT/flow8.png)

7.  The **Enable store and forward** option displays, leave it set to Yes.  
    ![](/Images/TransferCFT/flow9.png)

8.  In the newly displayed **Protocol?** and select **PeSIT**. Enter <span class="code">flow22 </span>as the **Flow identifier**. Use the other default values.

9.  Click <span class="bold_in_para">Save</span>.<span class="bold_in_para"> </span>You can check that you have correctly selected the source, target, and relay, then click<span class="bold_in_para"> Deploy.</span> [Details](../intro_cg_task_catalog/t_savedeployflow)

#### In <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span>

You will need to add a file locally for the transfer exchange and execute the SEND command.

1.  Put a test file, for example <span class="bold_in_para"> SALES\_report</span>, in the Store\_66 <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span><span class="code"> runtime/pub</span> folder.
2.  From the source <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span>, run the SEND command. Remember:
    -   Replace <span class="code">&lt;instance\_target></span> with your Transfer CFT for the `MainOffice `target.

    <!-- -->

    -   The flow <span class="bold_in_para">Identifier </span>field is equivalent to the <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> IDF parameter.

<!-- -->



    CFTUTIL SEND part=<instance_target>, idf=flow22, fname=pub/SALES_report

     
    CFTUTIL LISTLOG /to check the status/

 
