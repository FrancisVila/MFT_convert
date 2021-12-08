{
    "title": "PeSIT partner interactions",
    "linkTitle": "PeSIT processing",
    "weight": "150"
}This topic describes the interactions and processes that occur between
partners when using the PeSIT protocol.

PeSIT provides a set of user services and a protocol
dialog used by two partners to exchange files and messages. A service
defines the interaction between two PeSIT end users.

Four types of service primitives implement this interaction:


| Primitive  | Notation  | Description  |
| --- | --- | --- |
|  Request  |  REQ  |  Request a given service  |
|  Indication  |  IND  |  Notify the arrival of a service request  |
|  Response  |  RSP  |  Answer a request  |
|  Confirmation  |  CNF  |  Confirm the arrival of a response to a previous request  |


At the very minimum, a service involves a request submitted by a user
and its corresponding indication to the partner. Some services also require
a response and a confirmation to be complete.

## Send-file flows

The following table illustrates the communication flows
between Initiator and Responder during file transmission.

> **Note**  
> A file exchange involves more than just sending a file's data. Control information also has to be conveyed before, during and after the data transfer. This extra information is contained in protocol messages called FPDU (File Protocol Data Unit).

<table>
   <thead>
      <tr>
<th colspan="4" >Sending a file         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td >          </td>
         <td >FPDU         </td>
         <td >          </td>
         <td >          </td>
      </tr>
      <tr>
         <td  data-bgcolor="#FFFFFF" data-valign="top" width="252px"><p>PeSIT</p>         </td>
         <td >          </td>
         <td  data-bgcolor="#FFFFFF" data-valign="top" width="105.1pt"><p>  </p>         </td>
         <td  data-bgcolor="#FFFFFF" data-valign="top" width="178.4pt"><p>PeSIT</p>         </td>
      </tr>
      <tr>
         <td  data-bgcolor="#FFFFFF" data-valign="top" width="252px"><p>INITIATOR</p>         </td>
         <td >          </td>
         <td  data-bgcolor="#FFFFFF" data-valign="top" width="105.1pt"><p>  </p>         </td>
         <td  data-bgcolor="#FFFFFF" data-valign="top" width="178.4pt"><p>RESPONDER</p>         </td>
      </tr>
      <tr>
         <td  data-valign="top" width="252px"><p>  </p>         </td>
         <td >          </td>
         <td  data-valign="top" width="105.1pt"><p>idle</p>         </td>
         <td  data-valign="top" width="178.4pt"><p>  </p>         </td>
      </tr>
      <tr>
         <td  data-valign="top" width="252px"><p>F.CONNECT, REQ ------&gt;</p>         </td>
         <td >          </td>
         <td  data-valign="top" width="105.1pt"><p>  </p>         </td>
         <td  data-valign="top" width="178.4pt"><p>------&gt;IND, F.CONNECT</p>         </td>
      </tr>
      <tr>
         <td  data-valign="top" width="252px"><p>F.CONNECT, CNF &lt;------</p>         </td>
         <td >          </td>
         <td  data-valign="top" width="105.1pt"><p>  </p>         </td>
         <td  data-valign="top" width="178.4pt"><p>&lt;------RSP, F.CONNECT</p>         </td>
      </tr>
      <tr>
         <td  data-valign="top" width="252px"><p>  </p>         </td>
         <td >          </td>
         <td  data-valign="top" width="105.1pt"><p>connected</p>         </td>
         <td  data-valign="top" width="178.4pt"><p>  </p>         </td>
      </tr>
      <tr>
         <td  data-valign="top" width="252px"><p>F.CREATE, REQ ------&gt;</p>         </td>
         <td >          </td>
         <td  data-valign="top" width="105.1pt"><p>  </p>         </td>
         <td  data-valign="top" width="178.4pt"><p>------&gt;IND, F.CREATE</p>         </td>
      </tr>
      <tr>
         <td  data-valign="top" width="252px"><p>F.CREATE, CNF &lt;------</p>         </td>
         <td >          </td>
         <td  data-valign="top" width="105.1pt"><p>  </p>         </td>
         <td  data-valign="top" width="178.4pt"><p>&lt;------RSP, F.CREATE</p>         </td>
      </tr>
      <tr>
         <td  data-valign="top" width="252px"><p>  </p>         </td>
         <td >          </td>
         <td  data-valign="top" width="105.1pt"><p>file selected</p>         </td>
         <td  data-valign="top" width="178.4pt"><p>  </p>         </td>
      </tr>
      <tr>
         <td  data-valign="top" width="252px"><p>F.OPEN, REQ ------&gt;</p>         </td>
         <td >          </td>
         <td  data-valign="top" width="105.1pt"><p>  </p>         </td>
         <td  data-valign="top" width="178.4pt"><p>------&gt;IND, F.OPEN</p>         </td>
      </tr>
      <tr>
         <td  data-valign="top" width="252px"><p>F.OPEN, CNF &lt;------</p>         </td>
         <td >          </td>
         <td  data-valign="top" width="105.1pt"><p>  </p>         </td>
         <td  data-valign="top" width="178.4pt"><p>&lt;------RSP, F.OPEN</p>         </td>
      </tr>
      <tr>
         <td  data-valign="top" width="252px"><p>  </p>         </td>
         <td >          </td>
         <td  data-valign="top" width="105.1pt"><p>file opened</p>         </td>
         <td  data-valign="top" width="178.4pt"><p>  </p>         </td>
      </tr>
      <tr>
         <td  data-valign="top" width="252px"><p>F.WRITE, REQ ------&gt;</p>         </td>
         <td >          </td>
         <td  data-valign="top" width="105.1pt"><p>  </p>         </td>
         <td  data-valign="top" width="178.4pt"><p>------&gt;IND, F.WRITE</p>         </td>
      </tr>
      <tr>
         <td  data-valign="top" width="252px"><p>F.WRITE, CNF &lt;------</p>         </td>
         <td >          </td>
         <td  data-valign="top" width="105.1pt"><p>  </p>         </td>
         <td  data-valign="top" width="178.4pt"><p>&lt;------RSP, F.WRITE</p>         </td>
      </tr>
      <tr>
         <td  data-valign="top" width="252px"><p>  </p>         </td>
         <td >          </td>
         <td  data-valign="top" width="105.1pt"><p>transfer started</p>         </td>
         <td  data-valign="top" width="178.4pt"><p>  </p>         </td>
      </tr>
      <tr>
         <td  data-valign="top" width="252px"><p>F.DATA, REQ -------&gt;</p>         </td>
         <td >          </td>
         <td  data-valign="top" width="105.1pt"><p>data transfer</p>         </td>
         <td  data-valign="top" width="178.4pt"><p>------&gt;IND, F.DATA</p>         </td>
      </tr>
      <tr>
         <td  data-valign="top" width="252px"><p>F.DATA, REQ -------&gt;</p>         </td>
         <td >          </td>
         <td  data-valign="top" width="105.1pt"><p>  </p>         </td>
         <td  data-valign="top" width="178.4pt"><p>------&gt;IND, F.DATA</p>         </td>
      </tr>
      <tr>
         <td  data-valign="top" width="252px"><p>F.CHECK, REQ -------&gt;</p>         </td>
         <td >          </td>
         <td  data-valign="top" width="105.1pt"><p>synchronization point</p>         </td>
         <td  data-valign="top" width="178.4pt"><p>------&gt;IND, F.CHECK</p>         </td>
      </tr>
      <tr>
         <td  data-valign="top" width="252px"><p>F.DATA, REQ -------&gt;</p>         </td>
         <td >          </td>
         <td  data-valign="top" width="105.1pt"><p>  </p>         </td>
         <td  data-valign="top" width="178.4pt"><p>------&gt;IND, F.DATA</p>         </td>
      </tr>
      <tr>
         <td  data-valign="top" width="252px"><p>F.DATA, REQ -------&gt;</p>         </td>
         <td >          </td>
         <td  data-valign="top" width="105.1pt"><p>  </p>         </td>
         <td  data-valign="top" width="178.4pt"><p>------&gt;IND, F.DATA</p>         </td>
      </tr>
      <tr>
         <td  data-valign="top" width="252px"><p>F.CHECK, REQ -------&gt;</p>         </td>
         <td >          </td>
         <td  data-valign="top" width="105.1pt"><p>  </p>         </td>
         <td  data-valign="top" width="178.4pt"><p>------&gt;IND, F.CHECK</p>         </td>
      </tr>
      <tr>
         <td  data-valign="top" width="252px"><p>F.DATA, REQ -------&gt;</p>         </td>
         <td >          </td>
         <td  data-valign="top" width="105.1pt"><p>  </p>         </td>
         <td  data-valign="top" width="178.4pt"><p>------&gt;IND, F.DATA</p>         </td>
      </tr>
      <tr>
         <td  data-valign="top" width="252px"><p>F.DATA-END, REQ -----&gt;</p>         </td>
         <td >          </td>
         <td  data-valign="top" width="105.1pt"><p>  </p>         </td>
         <td  data-valign="top" width="178.4pt"><p>------&gt;IND, F.DATA-END</p>         </td>
      </tr>
      <tr>
         <td  data-valign="top" width="252px"><p>  </p>         </td>
         <td >          </td>
         <td  data-valign="top" width="105.1pt"><p>  </p>         </td>
         <td  data-valign="top" width="178.4pt"><p>  </p>         </td>
      </tr>
      <tr>
         <td  data-valign="top" width="252px"><p>F.TRANSFER-END, REQ -----&gt;</p>         </td>
         <td >          </td>
         <td  data-valign="top" width="105.1pt"><p>  </p>         </td>
         <td  data-valign="top" width="178.4pt"><p>------&gt;IND,F.TRANSFER-END</p>         </td>
      </tr>
      <tr>
         <td  data-valign="top" width="252px"><p>F.TRANSFER-END, CNF &lt;-----</p>         </td>
         <td >          </td>
         <td  data-valign="top" width="105.1pt"><p>  </p>         </td>
         <td  data-valign="top" width="178.4pt"><p>&lt;------RSP,F.TRANSFER-END</p>         </td>
      </tr>
      <tr>
         <td  data-valign="top" width="252px"><p>  </p>         </td>
         <td >          </td>
         <td  data-valign="top" width="105.1pt"><p>transfer ended</p>         </td>
         <td  data-valign="top" width="178.4pt"><p>  </p>         </td>
      </tr>
      <tr>
         <td  data-valign="top" width="252px"><p>F.CLOSE, REQ ------&gt;</p>         </td>
         <td >          </td>
         <td  data-valign="top" width="105.1pt"><p>  </p>         </td>
         <td  data-valign="top" width="178.4pt"><p>------&gt;IND, F.CLOSE</p>         </td>
      </tr>
      <tr>
         <td  data-valign="top" width="252px"><p>F.CLOSE, CNF &lt;------</p>         </td>
         <td >          </td>
         <td  data-valign="top" width="105.1pt"><p>  </p>         </td>
         <td  data-valign="top" width="178.4pt"><p>&lt;------RSP, F.CLOSE</p>         </td>
      </tr>
      <tr>
         <td  width="252px"><p>  </p>         </td>
         <td >          </td>
         <td  data-valign="top" width="105.1pt"><p>file closed</p>         </td>
         <td  data-valign="top" width="178.4pt"><p>  </p>         </td>
      </tr>
      <tr>
         <td  width="252px"><p>F.DESELECT, REQ ------&gt;</p>         </td>
         <td >          </td>
         <td  data-valign="top" width="105.1pt"><p>  </p>         </td>
         <td  data-valign="top" width="178.4pt"><p>------&gt;IND, F.DESELECT</p>         </td>
      </tr>
      <tr>
         <td  width="252px"><p>F.DESELECT, CNF &lt;------</p>         </td>
         <td >          </td>
         <td  data-valign="top" width="105.1pt"><p>  </p>         </td>
         <td  data-valign="top" width="178.4pt"><p>&lt;------RSP, F.DESELECT</p>         </td>
      </tr>
      <tr>
         <td  width="252px"><p>  </p>         </td>
         <td >          </td>
         <td  data-valign="top" width="105.1pt"><p>file deselected</p>         </td>
         <td  data-valign="top" width="178.4pt"><p>  </p>         </td>
      </tr>
      <tr>
         <td  width="252px"><p>F.RELEASED, REQ ------&gt;</p>         </td>
         <td >          </td>
         <td  data-valign="top" width="105.1pt"><p>  </p>         </td>
         <td  data-valign="top" width="178.4pt"><p>------&gt;IND, F.RELEASED</p>         </td>
      </tr>
      <tr>
         <td  width="252px"><p>F.RELEASED, CNF &lt;------</p>         </td>
         <td >          </td>
         <td  data-valign="top" width="105.1pt"><p>  </p>         </td>
         <td  data-valign="top" width="178.4pt"><p>&lt;------RSP, F.RELEASED</p>         </td>
      </tr>
      <tr>
         <td  width="252px"><p>  </p>         </td>
         <td >          </td>
         <td  data-valign="top" width="105.1pt"><p>disconnected</p>         </td>
         <td  data-valign="top" width="178.4pt"><p>  </p>         </td>
      </tr>
   </tbody>
</table>

## Receive-file flows

The following diagram illustrates the communication flows
between Initiator and Responder during file reception.

<table>
   <thead>
      <tr>
<th colspan="3" >Receiving a file         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td  data-valign="top" width="108.6pt"><p>PeSIT</p>         </td>
         <td  data-valign="top" width="109.1pt"><p>  </p>         </td>
         <td  data-valign="top" width="243.1pt"><p>PeSIT</p>         </td>
      </tr>
      <tr>
         <td  data-valign="top" width="108.6pt"><p>INITIATOR</p>         </td>
         <td  data-valign="top" width="109.1pt"><p>  </p>         </td>
         <td  data-valign="top" width="243.1pt"><p>RESPONDER</p>         </td>
      </tr>
      <tr>
         <td  data-valign="top" width="108.6pt"><p>  </p>         </td>
         <td  data-valign="top" width="109.1pt"><p>connected</p>         </td>
         <td  data-valign="top" width="243.1pt"><p>  </p>         </td>
      </tr>
      <tr>
         <td  data-valign="top" width="108.6pt"><p>F.SELECT, REQ ------&gt;</p>         </td>
         <td  data-valign="top" width="109.1pt"><p>  </p>         </td>
         <td  data-valign="top" width="243.1pt"><p>------&gt;IND, F.SELECT</p>         </td>
      </tr>
      <tr>
         <td  data-valign="top" width="108.6pt"><p>F.SELECT, CNF &lt;------</p>         </td>
         <td  data-valign="top" width="109.1pt"><p>  </p>         </td>
         <td  data-valign="top" width="243.1pt"><p>&lt;------RSP, F.SELECT</p>         </td>
      </tr>
      <tr>
         <td  data-valign="top" width="108.6pt"><p>  </p>         </td>
         <td  data-valign="top" width="109.1pt"><p>file selected</p>         </td>
         <td  data-valign="top" width="243.1pt"><p>  </p>         </td>
      </tr>
      <tr>
         <td  data-valign="top" width="108.6pt"><p>F.OPEN, REQ ------&gt;</p>         </td>
         <td  data-valign="top" width="109.1pt"><p>  </p>         </td>
         <td  data-valign="top" width="243.1pt"><p>------&gt;IND, F.OPEN</p>         </td>
      </tr>
      <tr>
         <td  data-valign="top" width="108.6pt"><p>F.OPEN, CNF &lt;------</p>         </td>
         <td  data-valign="top" width="109.1pt"><p>  </p>         </td>
         <td  data-valign="top" width="243.1pt"><p>&lt;------RSP, F.OPEN</p>         </td>
      </tr>
      <tr>
         <td  data-valign="top" width="108.6pt"><p>  </p>         </td>
         <td  data-valign="top" width="109.1pt"><p>file opened</p>         </td>
         <td  data-valign="top" width="243.1pt"><p>  </p>         </td>
      </tr>
      <tr>
         <td  data-valign="top" width="108.6pt"><p>F.READ, REQ ------&gt;</p>         </td>
         <td  data-valign="top" width="109.1pt"><p>  </p>         </td>
         <td  data-valign="top" width="243.1pt"><p>------&gt;IND, F.READ</p>         </td>
      </tr>
      <tr>
         <td  data-valign="top" width="108.6pt"><p>F.READ, CNF &lt;------</p>         </td>
         <td  data-valign="top" width="109.1pt"><p>  </p>         </td>
         <td  data-valign="top" width="243.1pt"><p>&lt;------RSP, F.READ</p>         </td>
      </tr>
      <tr>
         <td  data-valign="top" width="108.6pt"><p>  </p>         </td>
         <td  data-valign="top" width="109.1pt"><p>transfer started</p>         </td>
         <td  data-valign="top" width="243.1pt"><p>  </p>         </td>
      </tr>
      <tr>
         <td  data-valign="top" width="108.6pt"><p>F.DATA, IND &lt;------</p>         </td>
         <td  data-valign="top" width="109.1pt"><p>  </p>         </td>
         <td  data-valign="top" width="243.1pt"><p>&lt;------REQ, F.DATA</p>         </td>
      </tr>
      <tr>
         <td  data-valign="top" width="108.6pt"><p>F.DATA, IND &lt;------</p>         </td>
         <td  data-valign="top" width="109.1pt"><p>  </p>         </td>
         <td  data-valign="top" width="243.1pt"><p>&lt;------REQ, F.DATA</p>         </td>
      </tr>
      <tr>
         <td  data-valign="top" width="108.6pt"><p>F.CHECK, IND &lt;------</p>         </td>
         <td  data-valign="top" width="109.1pt"><p>  </p>         </td>
         <td  data-valign="top" width="243.1pt"><p>&lt;------REQ, F.CHECK</p>         </td>
      </tr>
      <tr>
         <td  data-valign="top" width="108.6pt"><p>F.DATA, IND &lt;------</p>         </td>
         <td  data-valign="top" width="109.1pt"><p>  </p>         </td>
         <td  data-valign="top" width="243.1pt"><p>&lt;------REQ, F.DATA</p>         </td>
      </tr>
      <tr>
         <td  data-valign="top" width="108.6pt"><p>F.DATA, IND &lt;------</p>         </td>
         <td  data-valign="top" width="109.1pt"><p>  </p>         </td>
         <td  data-valign="top" width="243.1pt"><p>&lt;------REQ, F.DATA</p>         </td>
      </tr>
      <tr>
         <td  data-valign="top" width="108.6pt"><p>F.CHECK, IND &lt;------</p>         </td>
         <td  data-valign="top" width="109.1pt"><p>  </p>         </td>
         <td  data-valign="top" width="243.1pt"><p>&lt;------REQ, F.CHECK</p>         </td>
      </tr>
      <tr>
         <td  data-valign="top" width="108.6pt"><p>F.DATA, IND &lt;------</p>         </td>
         <td  data-valign="top" width="109.1pt"><p>  </p>         </td>
         <td  data-valign="top" width="243.1pt"><p>&lt;------REQ, F.DATA</p>         </td>
      </tr>
      <tr>
         <td  data-valign="top" width="108.6pt"><p>F.DATA-END, IND</p>         </td>
         <td  data-valign="top" width="109.1pt"><p>  </p>         </td>
         <td  data-valign="top" width="243.1pt"><p>&lt;------REQ, F.DATA-END</p>         </td>
      </tr>
      <tr>
         <td  data-valign="top" width="108.6pt"><p>  </p>         </td>
         <td  data-valign="top" width="109.1pt"><p>  </p>         </td>
         <td  data-valign="top" width="243.1pt"><p>  </p>         </td>
      </tr>
      <tr>
         <td  data-valign="top" width="108.6pt"><p>F.TRANSFER-END, REQ -----&gt;</p>         </td>
         <td  data-valign="top" width="109.1pt"><p>  </p>         </td>
         <td  data-valign="top" width="243.1pt"><p>------&gt;IND,F.TRANSFER-END</p>         </td>
      </tr>
      <tr>
         <td  data-valign="top" width="108.6pt"><p>F.TRANSFER-END, CNF &lt;-----</p>         </td>
         <td  data-valign="top" width="109.1pt"><p>  </p>         </td>
         <td  data-valign="top" width="243.1pt"><p>&lt;------RSP,F.TRANSFER-END</p>         </td>
      </tr>
      <tr>
         <td  data-valign="top" width="108.6pt"><p>  </p>         </td>
         <td  data-valign="top" width="109.1pt"><p>transfer ended</p>         </td>
         <td  data-valign="top" width="243.1pt"><p>  </p>         </td>
      </tr>
      <tr>
         <td  data-valign="top" width="108.6pt"><p>F.CLOSE, REQ ------&gt;</p>         </td>
         <td  data-valign="top" width="109.1pt"><p>  </p>         </td>
         <td  data-valign="top" width="243.1pt"><p>------&gt;IND, F.CLOSE</p>         </td>
      </tr>
      <tr>
         <td  data-valign="top" width="108.6pt"><p>F.CLOSE, CNF &lt;------</p>         </td>
         <td  data-valign="top" width="109.1pt"><p>  </p>         </td>
         <td  data-valign="top" width="243.1pt"><p>&lt;------RSP, F.CLOSE</p>         </td>
      </tr>
      <tr>
         <td  data-valign="top" width="108.6pt"><p>  </p>         </td>
         <td  data-valign="top" width="109.1pt"><p>file closed </p>         </td>
         <td  data-valign="top" width="243.1pt"><p>  </p>         </td>
      </tr>
      <tr>
         <td  data-valign="top" width="108.6pt"><p>F.DESELECT, REQ ------&gt;</p>         </td>
         <td  data-valign="top" width="109.1pt"><p>  </p>         </td>
         <td  data-valign="top" width="243.1pt"><p>------&gt;IND, F.DESELECT</p>         </td>
      </tr>
      <tr>
         <td  data-valign="top" width="108.6pt"><p>F.DESELECT, CNF &lt;------</p>         </td>
         <td  data-valign="top" width="109.1pt"><p>  </p>         </td>
         <td  data-valign="top" width="243.1pt"><p>&lt;------RSP, F.DESELECT</p>         </td>
      </tr>
      <tr>
         <td  data-valign="top" width="108.6pt"><p>  </p>         </td>
         <td  data-valign="top" width="109.1pt"><p>file deselected</p>         </td>
         <td  data-valign="top" width="243.1pt"><p>  </p>         </td>
      </tr>
   </tbody>
</table>

## Send-message flows

The following interaction illustrates the communication flows
between Initiator and Responder during message transmission.

<table>
   <thead>
      <tr>
<th colspan="3" >Sending a message         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td  data-valign="top" width="109.9pt"><p>PeSIT</p>         </td>
         <td  data-valign="top" width="109.1pt"><p>  </p>         </td>
         <td  data-valign="top" width="241.6pt"><p>PeSIT</p>         </td>
      </tr>
      <tr>
         <td  data-valign="top" width="109.9pt"><p>INITIATOR</p>         </td>
         <td  data-valign="top" width="109.1pt"><p>  </p>         </td>
         <td  data-valign="top" width="241.6pt"><p>RESPONDER</p>         </td>
      </tr>
      <tr>
         <td  data-valign="top" width="109.9pt"><p>  </p>         </td>
         <td  data-valign="top" width="109.1pt"><p>idle</p>         </td>
         <td  data-valign="top" width="241.6pt"><p>  </p>         </td>
      </tr>
      <tr>
         <td  data-valign="top" width="109.9pt"><p>F.CONNECT, REQ ------&gt;</p>         </td>
         <td  data-valign="top" width="109.1pt"><p>  </p>         </td>
         <td  data-valign="top" width="241.6pt"><p>------&gt;IND, F.CONNECT</p>         </td>
      </tr>
      <tr>
         <td  data-valign="top" width="109.9pt"><p>F.CONNECT, CNF &lt;------</p>         </td>
         <td  data-valign="top" width="109.1pt"><p>  </p>         </td>
         <td  data-valign="top" width="241.6pt"><p>&lt;------RSP, F.CONNECT</p>         </td>
      </tr>
      <tr>
         <td  data-valign="top" width="109.9pt"><p>  </p>         </td>
         <td  data-valign="top" width="109.1pt"><p>connected </p>         </td>
         <td  data-valign="top" width="241.6pt"><p>  </p>         </td>
      </tr>
      <tr>
         <td  data-valign="top" width="109.9pt"><p>F.MESSAGE, REQ ------&gt;</p>         </td>
         <td  data-valign="top" width="109.1pt"><p>  </p>         </td>
         <td  data-valign="top" width="241.6pt"><p>------&gt;IND, F.MESSAGE</p>         </td>
      </tr>
      <tr>
         <td  data-valign="top" width="109.9pt"><p>F.MESSAGE, CNF &lt;------</p>         </td>
         <td  data-valign="top" width="109.1pt"><p>  </p>         </td>
         <td  data-valign="top" width="241.6pt"><p>&lt;------RSP, F.MESSAGE</p>         </td>
      </tr>
      <tr>
         <td  data-valign="top" width="109.9pt"><p>  </p>         </td>
         <td  data-valign="top" width="109.1pt"><p>  </p>         </td>
         <td  data-valign="top" width="241.6pt"><p>  </p>         </td>
      </tr>
      <tr>
         <td  data-valign="top" width="109.9pt"><p>F.RELEASED, REQ ------&gt;</p>         </td>
         <td  data-valign="top" width="109.1pt"><p>  </p>         </td>
         <td  data-valign="top" width="241.6pt"><p>------&gt;IND, F.RELEASED</p>         </td>
      </tr>
      <tr>
         <td  data-valign="top" width="109.9pt"><p>F.RELEASED, CNF &lt;------</p>         </td>
         <td  data-valign="top" width="109.1pt"><p>  </p>         </td>
         <td  data-valign="top" width="241.6pt"><p>&lt;------RSP, F.RELEASED</p>         </td>
      </tr>
      <tr>
         <td  data-valign="top" width="109.9pt"><p>  </p>         </td>
         <td  data-valign="top" width="109.1pt"><p>disconnected</p>         </td>
         <td  data-valign="top" width="241.6pt"><p>  </p>         </td>
      </tr>
   </tbody>
</table>
