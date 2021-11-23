{
    "title": "Create a flow and transfer a file",
    "linkTitle": "Create a flow and transfer a file",
    "weight": "140"
}Let's begin by creating a simple flow, and then exchange a file. In this example, Store\_66 sends a daily SALES\_report to the MainOffice.

<img src="/Images/TransferCFT/TransferCFT_Standard_w_cg.png" class="maxWidth" alt="Simplified diagram of a Source Transfer CFT sending a file to a Target" />

#### In

1.  Define a flow.
    -   Select **Flows** > **Add flow**.
    -   <img src="/Images/TransferCFT/flow01.png" class="maxWidth" />

    <!-- -->

    -   Create a flow named `Simple_flow` and give it the identifier **`flow01`**.
    -   <img src="/Images/TransferCFT/flow02.png" class="maxWidth" />

    <!-- -->

    -   Select **Source** > **Applications** > then **Transfer CFT**. Choose, for example Store\_66 and click **Add source**. Repeat the same steps for **Target**, choosing the MainOffice as the Target. You can leave all other fields set to the default values.

    -   An *application* is the logical representation of a business software application that is the true sender or true receiver in a file exchange. An application can represent a back-end enterprise resource system, such as SAP or PeopleSoft.

    -   <img src="/Images/TransferCFT/flow03.png" class="maxWidth" />
2.  Click ****Deploy**** to save and deploy. [Details](../intro_cg_task_catalog/t_savedeployflow)

#### In {{< TransferCFT/componentshortname  >}}

1.  Add a file to exchange. Put a test file, for example **SALES\_report**, in the Store\_66 {{< TransferCFT/componentshortname >}}` runtime/pub` folder.
2.  From the source {{< TransferCFT/componentshortname >}}, run the SEND command.
    -   Remember to replace `<instance_target>` with your Transfer CFT for the MainOffice target.

    <!-- -->

    -   The flow **Identifier** field is equivalent to the {{< TransferCFT/componentshortname >}} IDF parameter.
