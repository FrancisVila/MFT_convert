{
    "title": "Define a flow",
    "linkTitle": "Define a flow",
    "weight": "300"
}Click <span class="bold_in_para">Flows </span>on the top toolbar to open the<span class="bold_in_para"> Flows / Monitoring </span>page.

The following outlines tasks for defining a flow. Optional steps, such as defining source and target properties, have default values in the user interface and are not described in this getting started topic.

In the <span class="bold_in_para">Flow List</span> page click <span class="bold_in_para">Add flow</span> and perform the following steps:

1.  Select **General information** and complete the fields. The following fields are mandatory (\* denotes mandatory):
    -   Name: Enter a user friendly name, for example <span class="bold_in_para">Simple flow</span>
    -   Identifier: Enter the id that will be used in the transfer commands, for example <span class="bold_in_para">flow01 </span>(Transfer CFT IDF)
2.  In the left panel, select <span class="bold_in_para">Source </span>and click <span class="bold_in_para">Edit</span>. The source is the owner of the data being transferred.
3.  Select <span class="bold_in_para">Target </span>and click <span class="bold_in_para">Edit</span>. The target is the receiver of the exchange.
4.  Optionally, select Protocol and define. You cannot define a protocol until you have defined both the source and target.
5.  Save the flow, or save and deploy the flow.

Result

<img src="/Images/TransferCFT/new_flow_cg_w_store.png" class="maxWidth" />

<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Tip  </strong></span>         </td>
         <td>Existing <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> users may want to refer to the Transfer CFT to <span class="mc-variable Primary.CG or_UM variable">Central Governance</span> parameter mapping in the sections see <a href="../r_flow_target">Flow definition: Target</a> and <a href="../r_flow_source">Flow definition: Source</a>.         </td>
      </tr>
   </tbody>
</table>

<span class="bold_in_para">&lt;&lt; </span><a href="../../" class="bold_in_para MCXref xref xrefbold_in_para">My first transfer flow</a>
