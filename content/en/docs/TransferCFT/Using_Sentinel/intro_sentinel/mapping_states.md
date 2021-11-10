{
    "title": "Map Transfer CFT and Sentinel states",
    "linkTitle": "Mapping Transfer CFT and Sentinel states",
    "weight": "250"
}You can use the <span class="bold_in_para">Mapping states</span> table to find equivalent states and phases as described below.

-   Phase: The phase indicates where you are in your transfer.
-   Phasestep: Within each phase there is a phase step, which is either a process or a step.
-   Diag: Diagnostic codes provide a explanation of the source of the error detected or the refusal.
-   <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> state: The <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> status as displayed in the catalog.
-   Compatibility state: The <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> status as displayed in the catalog when using the backward compatibility mode.
-   Sentinel state: The state attribute identifies the step of the transfer process.

For details on Sentinel states, see XFBTransfer Tracked Objects.

<span class="autonumber"></span>Mapping states

In the following table, the state that is sent to Sentinel when the COMPAT parameter is set to NO, is displayed in the Sentinel state column. When COMPAT is set to YES, the state listed in the Compatible Sentinel state column is sent to Sentinel. For more information on the COMPAT settings, see [<span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> backward compatibility](../../../concepts/phase_and_phasestep/processing_compatability).

<table>
   <thead>
      <tr>
<th style="text-align: center;" class="HeadE-Column1-Header1"><p> </p>         </th>
<th style="text-align: center;" class="HeadE-Column1-Header1"><p>Phase</p>         </th>
<th style="text-align: center;" class="HeadE-Column1-Header1"><p>Phasestep</p>         </th>
<th style="text-align: center;" class="HeadE-Column1-Header1"><p>Transfer CFT State</p>         </th>
<th style="text-align: center;" class="HeadE-Column1-Header1"><p>Transfer CFT Compatible State (uconf:</p>
<p>cft.state_compat=Yes)</p>         </th>
<th style="text-align: center;" class="HeadE-Column1-Header1"><p>Diagi</p>         </th>
<th style="text-align: center;" class="HeadE-Column1-Header1"><p>Acked</p>         </th>
<th style="text-align: center;" class="HeadE-Column1-Header1"><p>Sentinel</p>
<p>State</p>         </th>
<th style="text-align: center;" class="HeadD-Column1-Header1"><p>Compatible Sentinel State (uconf:</p>
<p>cft.state_compat=Yes)</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Pre-processing</p>         </td>
         <td><p>A</p>         </td>
         <td><p>H</p>         </td>
         <td><p>A</p>         </td>
         <td><p>A</p>         </td>
         <td><p>0</p>         </td>
         <td><p> </p>         </td>
         <td><p>PRE_PROC</p>         </td>
         <td><p>AVAILABLE</p>         </td>
      </tr>
      <tr>
         <td><p> </p>         </td>
         <td><p>A</p>         </td>
         <td><p>D</p>         </td>
         <td><p>A</p>         </td>
         <td><p>A</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>PRE_PROC</p>         </td>
         <td><p>TO_EXECUTE</p>         </td>
      </tr>
      <tr>
         <td><p> </p>         </td>
         <td><p>A</p>         </td>
         <td><p>C</p>         </td>
         <td><p>A</p>         </td>
         <td><p>A</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>PRE_PROC</p>         </td>
         <td><p>TO_EXECUTE</p>         </td>
      </tr>
      <tr>
         <td><p> </p>         </td>
         <td><p>A</p>         </td>
         <td><p>K</p>         </td>
         <td><p>A</p>         </td>
         <td><p>A</p>         </td>
         <td><p>121</p>         </td>
         <td><p> </p>         </td>
         <td><p>PRE_PROC_ABORT</p>         </td>
         <td><p>CANCELED</p>         </td>
      </tr>
      <tr>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>Transfer</p>         </td>
         <td><p>T</p>         </td>
         <td><p>H</p>         </td>
         <td><p>H</p>         </td>
         <td><p>H</p>         </td>
         <td><p>0</p>         </td>
         <td><p> </p>         </td>
         <td><p>AVAILABLE</p>         </td>
         <td><p>AVAILABLE</p>         </td>
      </tr>
      <tr>
         <td><p> </p>         </td>
         <td><p>T</p>         </td>
         <td><p>D</p>         </td>
         <td><p>D</p>         </td>
         <td><p>D</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>TO_EXECUTE</p>         </td>
         <td><p>TO_EXECUTE</p>         </td>
      </tr>
      <tr>
         <td>          </td>
         <td>T         </td>
         <td>D         </td>
         <td>D         </td>
         <td>D         </td>
         <td>NOT = 0         </td>
         <td>          </td>
         <td>INTERRUPTED         </td>
         <td>INTERRUPTED         </td>
      </tr>
      <tr>
         <td><p> </p>         </td>
         <td><p>T</p>         </td>
         <td><p>C</p>         </td>
         <td><p>C</p>         </td>
         <td><p>C</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>SENDING/RECEIVING</p>         </td>
         <td><p>SENDING/RECEIVING</p>         </td>
      </tr>
      <tr>
         <td><p> </p>         </td>
         <td><p>T</p>         </td>
         <td><p>K</p>         </td>
         <td><p>K</p>         </td>
         <td><p>K</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>CANCELED</p>         </td>
         <td><p>CANCELED</p>         </td>
      </tr>
      <tr>
         <td><p> </p>         </td>
         <td><p>T</p>         </td>
         <td><p>H</p>         </td>
         <td><p>H</p>         </td>
         <td><p>H</p>         </td>
         <td><p>121</p>         </td>
         <td><p> </p>         </td>
         <td><p>SUSPENDED</p>         </td>
         <td><p>SUSPENDED</p>         </td>
      </tr>
      <tr>
         <td><p> </p>         </td>
         <td><p>T</p>         </td>
         <td><p>H</p>         </td>
         <td><p>H</p>         </td>
         <td><p>H</p>         </td>
         <td><p>621</p>         </td>
         <td><p> </p>         </td>
         <td><p>INTERRUPTED</p>         </td>
         <td><p>INTERRUPTED</p>         </td>
      </tr>
      <tr>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>Post-processing</p>         </td>
         <td><p>Y</p>         </td>
         <td><p>E</p>         </td>
         <td><p>Y</p>         </td>
         <td><p>T/X</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>POST_PROC</p>         </td>
         <td><p>SENT/RECEIVED</p>         </td>
      </tr>
      <tr>
         <td><p> </p>         </td>
         <td><p>Y</p>         </td>
         <td><p>H</p>         </td>
         <td><p>Y</p>         </td>
         <td><p>T/X</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>POST_PROC</p>         </td>
         <td><p>SENT/RECEIVED</p>         </td>
      </tr>
      <tr>
         <td><p> </p>         </td>
         <td><p>Y</p>         </td>
         <td><p>D</p>         </td>
         <td><p>Y</p>         </td>
         <td><p>T/X</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>POST_PROC</p>         </td>
         <td><p>SENT/RECEIVED</p>         </td>
      </tr>
      <tr>
         <td><p> </p>         </td>
         <td><p>Y</p>         </td>
         <td><p>C</p>         </td>
         <td><p>Y</p>         </td>
         <td><p>T/X</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>POST_PROC</p>         </td>
         <td><p>SENT/RECEIVED</p>         </td>
      </tr>
      <tr>
         <td><p> </p>         </td>
         <td><p>Y</p>         </td>
         <td><p>C</p>         </td>
         <td><p>Y</p>         </td>
         <td><p>T/X</p>         </td>
         <td><p> </p>         </td>
         <td><p>A</p>         </td>
         <td><p>POST_PROC</p>         </td>
         <td><p>ENDED-TO-ACK/ACKED</p>         </td>
      </tr>
      <tr>
         <td><p> </p>         </td>
         <td><p>Y</p>         </td>
         <td><p>C</p>         </td>
         <td><p>Y</p>         </td>
         <td><p>T/X</p>         </td>
         <td><p> </p>         </td>
         <td><p>N</p>         </td>
         <td><p>POST_PROC</p>         </td>
         <td><p>ENDED-TO-NACK/NACKED</p>         </td>
      </tr>
      <tr>
         <td><p> </p>         </td>
         <td><p>Y</p>         </td>
         <td><p>K</p>         </td>
         <td><p>Y</p>         </td>
         <td><p>T/X</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>POST_PROC_ABORT</p>         </td>
         <td><p>SENT/RECEIVED</p>         </td>
      </tr>
      <tr>
         <td><p> </p>         </td>
         <td><p>Y</p>         </td>
         <td><p>K</p>         </td>
         <td><p>Y</p>         </td>
         <td><p>T/X</p>         </td>
         <td><p> </p>         </td>
         <td><p>A</p>         </td>
         <td><p>POST_PROC_ABORT</p>         </td>
         <td><p>ENDED-TO-ACK/ACKED</p>         </td>
      </tr>
      <tr>
         <td><p> </p>         </td>
         <td><p>Y</p>         </td>
         <td><p>K</p>         </td>
         <td><p>Y</p>         </td>
         <td><p>T/X</p>         </td>
         <td><p> </p>         </td>
         <td><p>N</p>         </td>
         <td><p>POST_PROC_ABORT</p>         </td>
         <td><p>ENDED-TO-NACK/NACKED</p>         </td>
      </tr>
      <tr>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>Ack-processing</p>         </td>
         <td><p>Z</p>         </td>
         <td><p>H</p>         </td>
         <td><p>Z</p>         </td>
         <td><p>T/X</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>ACK_EXPECTED</p>         </td>
         <td><p>SENT/RECEIVED</p>         </td>
      </tr>
      <tr>
         <td><p> </p>         </td>
         <td><p>Z</p>         </td>
         <td><p>D</p>         </td>
         <td><p>Z</p>         </td>
         <td><p>T/X</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>POST_PROC_ACK</p>         </td>
         <td><p>SENT/RECEIVED</p>         </td>
      </tr>
      <tr>
         <td><p> </p>         </td>
         <td><p>Z</p>         </td>
         <td><p>D</p>         </td>
         <td><p>Z</p>         </td>
         <td><p>T/X</p>         </td>
         <td><p> </p>         </td>
         <td><p>A</p>         </td>
         <td><p>ENDED-TO-ACK/ACKED</p>         </td>
         <td><p>ENDED-TO-ACK/ACKED</p>         </td>
      </tr>
      <tr>
         <td><p> </p>         </td>
         <td><p>Z</p>         </td>
         <td><p>D</p>         </td>
         <td><p>Z</p>         </td>
         <td><p>T/X</p>         </td>
         <td><p> </p>         </td>
         <td><p>N</p>         </td>
         <td><p>ENDED-TO-NACK/NACKED</p>         </td>
         <td><p>ENDED-TO-NACK/NACKED</p>         </td>
      </tr>
      <tr>
         <td><p> </p>         </td>
         <td><p>Z</p>         </td>
         <td><p>C</p>         </td>
         <td><p>Z</p>         </td>
         <td><p>T/X</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>POST_PROC_ACK</p>         </td>
         <td><p>SENT/RECEIVED</p>         </td>
      </tr>
      <tr>
         <td><p> </p>         </td>
         <td><p>Z</p>         </td>
         <td><p>C</p>         </td>
         <td><p>Z</p>         </td>
         <td><p>T/X</p>         </td>
         <td><p> </p>         </td>
         <td><p>A</p>         </td>
         <td><p>POST_PROC_ACK</p>         </td>
         <td><p>ENDED-TO-ACK/ACKED</p>         </td>
      </tr>
      <tr>
         <td><p> </p>         </td>
         <td><p>Z</p>         </td>
         <td><p>C</p>         </td>
         <td><p>Z</p>         </td>
         <td><p>T/X</p>         </td>
         <td><p> </p>         </td>
         <td><p>N</p>         </td>
         <td><p>POST_PROC_ACK</p>         </td>
         <td><p>ENDED-TO-NACK/NACKED</p>         </td>
      </tr>
      <tr>
         <td><p> </p>         </td>
         <td><p>Z</p>         </td>
         <td><p>K</p>         </td>
         <td><p>Z</p>         </td>
         <td><p>T/X</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>POST_PROC_ACK_ABORT</p>         </td>
         <td><p>SENT/RECEIVED</p>         </td>
      </tr>
      <tr>
         <td><p> </p>         </td>
         <td><p>Z</p>         </td>
         <td><p>K</p>         </td>
         <td><p>Z</p>         </td>
         <td><p>T/X</p>         </td>
         <td><p> </p>         </td>
         <td><p>A</p>         </td>
         <td><p>POST_PROC_ACK_ABORT</p>         </td>
         <td><p>ENDED-TO-ACK/ACKED</p>         </td>
      </tr>
      <tr>
         <td><p> </p>         </td>
         <td><p>Z</p>         </td>
         <td><p>K</p>         </td>
         <td><p>Z</p>         </td>
         <td><p>T/X</p>         </td>
         <td><p> </p>         </td>
         <td><p>N</p>         </td>
         <td><p>POST_PROC_ACK_ABORT</p>         </td>
         <td><p>ENDED-TO-NACK/NACKED</p>         </td>
      </tr>
      <tr>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>Done</p>         </td>
         <td><p>X</p>         </td>
         <td><p>X</p>         </td>
         <td><p>X</p>         </td>
         <td><p>T/X</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>COMPLETED</p>         </td>
         <td><p>CONSUMED</p>         </td>
      </tr>
      <tr>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
      </tr>
   </tbody>
</table>
