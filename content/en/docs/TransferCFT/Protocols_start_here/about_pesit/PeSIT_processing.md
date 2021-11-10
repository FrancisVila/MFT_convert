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

<table>
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Primitive         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Notation         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Request</p>         </td>
         <td><p>REQ</p>         </td>
         <td><p>Request a given service</p>         </td>
      </tr>
      <tr>
         <td><p>Indication</p>         </td>
         <td><p>IND</p>         </td>
         <td><p>Notify the arrival of a service request</p>         </td>
      </tr>
      <tr>
         <td><p>Response</p>         </td>
         <td><p>RSP</p>         </td>
         <td><p>Answer a request</p>         </td>
      </tr>
      <tr>
         <td><p>Confirmation</p>         </td>
         <td><p>CNF</p>         </td>
         <td><p>Confirm the arrival of a response to a previous request</p>         </td>
      </tr>
   </tbody>
</table>

At the very minimum, a service involves a request submitted by a user
and its corresponding indication to the partner. Some services also require
a response and a confirmation to be complete.

## Send-file flows

The following table illustrates the communication flows
between Initiator and Responder during file transmission.

> **Note:**
>
> A file exchange involves more than just sending a file's data. Control information also has to be conveyed before, during and after the data transfer. This extra information is contained in protocol messages called FPDU (File Protocol Data Unit).

<table>
   <thead>
      <tr>
<th colspan="4" class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1">Sending a file         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>          </td>
         <td>FPDU         </td>
         <td>          </td>
         <td>          </td>
      </tr>
      <tr>
         <td><p>PeSIT</p>         </td>
         <td>          </td>
         <td><p>  </p>         </td>
         <td><p>PeSIT</p>         </td>
      </tr>
      <tr>
         <td><p>INITIATOR</p>         </td>
         <td>          </td>
         <td><p>  </p>         </td>
         <td><p>RESPONDER</p>         </td>
      </tr>
      <tr>
         <td><p>  </p>         </td>
         <td>          </td>
         <td><p>idle</p>         </td>
         <td><p>  </p>         </td>
      </tr>
      <tr>
         <td><p>F.CONNECT, REQ ------&gt;</p>         </td>
         <td>          </td>
         <td><p>  </p>         </td>
         <td><p>------&gt;IND, F.CONNECT</p>         </td>
      </tr>
      <tr>
         <td><p>F.CONNECT, CNF &lt;------</p>         </td>
         <td>          </td>
         <td><p>  </p>         </td>
         <td><p>&lt;------RSP, F.CONNECT</p>         </td>
      </tr>
      <tr>
         <td><p>  </p>         </td>
         <td>          </td>
         <td><p>connected</p>         </td>
         <td><p>  </p>         </td>
      </tr>
      <tr>
         <td><p>F.CREATE, REQ ------&gt;</p>         </td>
         <td>          </td>
         <td><p>  </p>         </td>
         <td><p>------&gt;IND, F.CREATE</p>         </td>
      </tr>
      <tr>
         <td><p>F.CREATE, CNF &lt;------</p>         </td>
         <td>          </td>
         <td><p>  </p>         </td>
         <td><p>&lt;------RSP, F.CREATE</p>         </td>
      </tr>
      <tr>
         <td><p>  </p>         </td>
         <td>          </td>
         <td><p>file selected</p>         </td>
         <td><p>  </p>         </td>
      </tr>
      <tr>
         <td><p>F.OPEN, REQ ------&gt;</p>         </td>
         <td>          </td>
         <td><p>  </p>         </td>
         <td><p>------&gt;IND, F.OPEN</p>         </td>
      </tr>
      <tr>
         <td><p>F.OPEN, CNF &lt;------</p>         </td>
         <td>          </td>
         <td><p>  </p>         </td>
         <td><p>&lt;------RSP, F.OPEN</p>         </td>
      </tr>
      <tr>
         <td><p>  </p>         </td>
         <td>          </td>
         <td><p>file opened</p>         </td>
         <td><p>  </p>         </td>
      </tr>
      <tr>
         <td><p>F.WRITE, REQ ------&gt;</p>         </td>
         <td>          </td>
         <td><p>  </p>         </td>
         <td><p>------&gt;IND, F.WRITE</p>         </td>
      </tr>
      <tr>
         <td><p>F.WRITE, CNF &lt;------</p>         </td>
         <td>          </td>
         <td><p>  </p>         </td>
         <td><p>&lt;------RSP, F.WRITE</p>         </td>
      </tr>
      <tr>
         <td><p>  </p>         </td>
         <td>          </td>
         <td><p>transfer started</p>         </td>
         <td><p>  </p>         </td>
      </tr>
      <tr>
         <td><p>F.DATA, REQ -------&gt;</p>         </td>
         <td>          </td>
         <td><p>data transfer</p>         </td>
         <td><p>------&gt;IND, F.DATA</p>         </td>
      </tr>
      <tr>
         <td><p>F.DATA, REQ -------&gt;</p>         </td>
         <td>          </td>
         <td><p>  </p>         </td>
         <td><p>------&gt;IND, F.DATA</p>         </td>
      </tr>
      <tr>
         <td><p>F.CHECK, REQ -------&gt;</p>         </td>
         <td>          </td>
         <td><p>synchronization point</p>         </td>
         <td><p>------&gt;IND, F.CHECK</p>         </td>
      </tr>
      <tr>
         <td><p>F.DATA, REQ -------&gt;</p>         </td>
         <td>          </td>
         <td><p>  </p>         </td>
         <td><p>------&gt;IND, F.DATA</p>         </td>
      </tr>
      <tr>
         <td><p>F.DATA, REQ -------&gt;</p>         </td>
         <td>          </td>
         <td><p>  </p>         </td>
         <td><p>------&gt;IND, F.DATA</p>         </td>
      </tr>
      <tr>
         <td><p>F.CHECK, REQ -------&gt;</p>         </td>
         <td>          </td>
         <td><p>  </p>         </td>
         <td><p>------&gt;IND, F.CHECK</p>         </td>
      </tr>
      <tr>
         <td><p>F.DATA, REQ -------&gt;</p>         </td>
         <td>          </td>
         <td><p>  </p>         </td>
         <td><p>------&gt;IND, F.DATA</p>         </td>
      </tr>
      <tr>
         <td><p>F.DATA-END, REQ -----&gt;</p>         </td>
         <td>          </td>
         <td><p>  </p>         </td>
         <td><p>------&gt;IND, F.DATA-END</p>         </td>
      </tr>
      <tr>
         <td><p>  </p>         </td>
         <td>          </td>
         <td><p>  </p>         </td>
         <td><p>  </p>         </td>
      </tr>
      <tr>
         <td><p>F.TRANSFER-END, REQ -----&gt;</p>         </td>
         <td>          </td>
         <td><p>  </p>         </td>
         <td><p>------&gt;IND,F.TRANSFER-END</p>         </td>
      </tr>
      <tr>
         <td><p>F.TRANSFER-END, CNF &lt;-----</p>         </td>
         <td>          </td>
         <td><p>  </p>         </td>
         <td><p>&lt;------RSP,F.TRANSFER-END</p>         </td>
      </tr>
      <tr>
         <td><p>  </p>         </td>
         <td>          </td>
         <td><p>transfer ended</p>         </td>
         <td><p>  </p>         </td>
      </tr>
      <tr>
         <td><p>F.CLOSE, REQ ------&gt;</p>         </td>
         <td>          </td>
         <td><p>  </p>         </td>
         <td><p>------&gt;IND, F.CLOSE</p>         </td>
      </tr>
      <tr>
         <td><p>F.CLOSE, CNF &lt;------</p>         </td>
         <td>          </td>
         <td><p>  </p>         </td>
         <td><p>&lt;------RSP, F.CLOSE</p>         </td>
      </tr>
      <tr>
         <td><p>  </p>         </td>
         <td>          </td>
         <td><p>file closed</p>         </td>
         <td><p>  </p>         </td>
      </tr>
      <tr>
         <td><p>F.DESELECT, REQ ------&gt;</p>         </td>
         <td>          </td>
         <td><p>  </p>         </td>
         <td><p>------&gt;IND, F.DESELECT</p>         </td>
      </tr>
      <tr>
         <td><p>F.DESELECT, CNF &lt;------</p>         </td>
         <td>          </td>
         <td><p>  </p>         </td>
         <td><p>&lt;------RSP, F.DESELECT</p>         </td>
      </tr>
      <tr>
         <td><p>  </p>         </td>
         <td>          </td>
         <td><p>file deselected</p>         </td>
         <td><p>  </p>         </td>
      </tr>
      <tr>
         <td><p>F.RELEASED, REQ ------&gt;</p>         </td>
         <td>          </td>
         <td><p>  </p>         </td>
         <td><p>------&gt;IND, F.RELEASED</p>         </td>
      </tr>
      <tr>
         <td><p>F.RELEASED, CNF &lt;------</p>         </td>
         <td>          </td>
         <td><p>  </p>         </td>
         <td><p>&lt;------RSP, F.RELEASED</p>         </td>
      </tr>
      <tr>
         <td><p>  </p>         </td>
         <td>          </td>
         <td><p>disconnected</p>         </td>
         <td><p>  </p>         </td>
      </tr>
   </tbody>
</table>

## Receive-file flows

The following diagram illustrates the communication flows
between Initiator and Responder during file reception.

<table>
   <thead>
      <tr>
<th colspan="3" class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1">Receiving a file         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>PeSIT</p>         </td>
         <td><p>  </p>         </td>
         <td><p>PeSIT</p>         </td>
      </tr>
      <tr>
         <td><p>INITIATOR</p>         </td>
         <td><p>  </p>         </td>
         <td><p>RESPONDER</p>         </td>
      </tr>
      <tr>
         <td><p>  </p>         </td>
         <td><p>connected</p>         </td>
         <td><p>  </p>         </td>
      </tr>
      <tr>
         <td><p>F.SELECT, REQ ------&gt;</p>         </td>
         <td><p>  </p>         </td>
         <td><p>------&gt;IND, F.SELECT</p>         </td>
      </tr>
      <tr>
         <td><p>F.SELECT, CNF &lt;------</p>         </td>
         <td><p>  </p>         </td>
         <td><p>&lt;------RSP, F.SELECT</p>         </td>
      </tr>
      <tr>
         <td><p>  </p>         </td>
         <td><p>file selected</p>         </td>
         <td><p>  </p>         </td>
      </tr>
      <tr>
         <td><p>F.OPEN, REQ ------&gt;</p>         </td>
         <td><p>  </p>         </td>
         <td><p>------&gt;IND, F.OPEN</p>         </td>
      </tr>
      <tr>
         <td><p>F.OPEN, CNF &lt;------</p>         </td>
         <td><p>  </p>         </td>
         <td><p>&lt;------RSP, F.OPEN</p>         </td>
      </tr>
      <tr>
         <td><p>  </p>         </td>
         <td><p>file opened</p>         </td>
         <td><p>  </p>         </td>
      </tr>
      <tr>
         <td><p>F.READ, REQ ------&gt;</p>         </td>
         <td><p>  </p>         </td>
         <td><p>------&gt;IND, F.READ</p>         </td>
      </tr>
      <tr>
         <td><p>F.READ, CNF &lt;------</p>         </td>
         <td><p>  </p>         </td>
         <td><p>&lt;------RSP, F.READ</p>         </td>
      </tr>
      <tr>
         <td><p>  </p>         </td>
         <td><p>transfer started</p>         </td>
         <td><p>  </p>         </td>
      </tr>
      <tr>
         <td><p>F.DATA, IND &lt;------</p>         </td>
         <td><p>  </p>         </td>
         <td><p>&lt;------REQ, F.DATA</p>         </td>
      </tr>
      <tr>
         <td><p>F.DATA, IND &lt;------</p>         </td>
         <td><p>  </p>         </td>
         <td><p>&lt;------REQ, F.DATA</p>         </td>
      </tr>
      <tr>
         <td><p>F.CHECK, IND &lt;------</p>         </td>
         <td><p>  </p>         </td>
         <td><p>&lt;------REQ, F.CHECK</p>         </td>
      </tr>
      <tr>
         <td><p>F.DATA, IND &lt;------</p>         </td>
         <td><p>  </p>         </td>
         <td><p>&lt;------REQ, F.DATA</p>         </td>
      </tr>
      <tr>
         <td><p>F.DATA, IND &lt;------</p>         </td>
         <td><p>  </p>         </td>
         <td><p>&lt;------REQ, F.DATA</p>         </td>
      </tr>
      <tr>
         <td><p>F.CHECK, IND &lt;------</p>         </td>
         <td><p>  </p>         </td>
         <td><p>&lt;------REQ, F.CHECK</p>         </td>
      </tr>
      <tr>
         <td><p>F.DATA, IND &lt;------</p>         </td>
         <td><p>  </p>         </td>
         <td><p>&lt;------REQ, F.DATA</p>         </td>
      </tr>
      <tr>
         <td><p>F.DATA-END, IND</p>         </td>
         <td><p>  </p>         </td>
         <td><p>&lt;------REQ, F.DATA-END</p>         </td>
      </tr>
      <tr>
         <td><p>  </p>         </td>
         <td><p>  </p>         </td>
         <td><p>  </p>         </td>
      </tr>
      <tr>
         <td><p>F.TRANSFER-END, REQ -----&gt;</p>         </td>
         <td><p>  </p>         </td>
         <td><p>------&gt;IND,F.TRANSFER-END</p>         </td>
      </tr>
      <tr>
         <td><p>F.TRANSFER-END, CNF &lt;-----</p>         </td>
         <td><p>  </p>         </td>
         <td><p>&lt;------RSP,F.TRANSFER-END</p>         </td>
      </tr>
      <tr>
         <td><p>  </p>         </td>
         <td><p>transfer ended</p>         </td>
         <td><p>  </p>         </td>
      </tr>
      <tr>
         <td><p>F.CLOSE, REQ ------&gt;</p>         </td>
         <td><p>  </p>         </td>
         <td><p>------&gt;IND, F.CLOSE</p>         </td>
      </tr>
      <tr>
         <td><p>F.CLOSE, CNF &lt;------</p>         </td>
         <td><p>  </p>         </td>
         <td><p>&lt;------RSP, F.CLOSE</p>         </td>
      </tr>
      <tr>
         <td><p>  </p>         </td>
         <td><p>file closed </p>         </td>
         <td><p>  </p>         </td>
      </tr>
      <tr>
         <td><p>F.DESELECT, REQ ------&gt;</p>         </td>
         <td><p>  </p>         </td>
         <td><p>------&gt;IND, F.DESELECT</p>         </td>
      </tr>
      <tr>
         <td><p>F.DESELECT, CNF &lt;------</p>         </td>
         <td><p>  </p>         </td>
         <td><p>&lt;------RSP, F.DESELECT</p>         </td>
      </tr>
      <tr>
         <td><p>  </p>         </td>
         <td><p>file deselected</p>         </td>
         <td><p>  </p>         </td>
      </tr>
   </tbody>
</table>

## Send-message flows

The following interaction illustrates the communication flows
between Initiator and Responder during message transmission.

<table>
   <thead>
      <tr>
<th colspan="3" class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1">Sending a message         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>PeSIT</p>         </td>
         <td><p>  </p>         </td>
         <td><p>PeSIT</p>         </td>
      </tr>
      <tr>
         <td><p>INITIATOR</p>         </td>
         <td><p>  </p>         </td>
         <td><p>RESPONDER</p>         </td>
      </tr>
      <tr>
         <td><p>  </p>         </td>
         <td><p>idle</p>         </td>
         <td><p>  </p>         </td>
      </tr>
      <tr>
         <td><p>F.CONNECT, REQ ------&gt;</p>         </td>
         <td><p>  </p>         </td>
         <td><p>------&gt;IND, F.CONNECT</p>         </td>
      </tr>
      <tr>
         <td><p>F.CONNECT, CNF &lt;------</p>         </td>
         <td><p>  </p>         </td>
         <td><p>&lt;------RSP, F.CONNECT</p>         </td>
      </tr>
      <tr>
         <td><p>  </p>         </td>
         <td><p>connected </p>         </td>
         <td><p>  </p>         </td>
      </tr>
      <tr>
         <td><p>F.MESSAGE, REQ ------&gt;</p>         </td>
         <td><p>  </p>         </td>
         <td><p>------&gt;IND, F.MESSAGE</p>         </td>
      </tr>
      <tr>
         <td><p>F.MESSAGE, CNF &lt;------</p>         </td>
         <td><p>  </p>         </td>
         <td><p>&lt;------RSP, F.MESSAGE</p>         </td>
      </tr>
      <tr>
         <td><p>  </p>         </td>
         <td><p>  </p>         </td>
         <td><p>  </p>         </td>
      </tr>
      <tr>
         <td><p>F.RELEASED, REQ ------&gt;</p>         </td>
         <td><p>  </p>         </td>
         <td><p>------&gt;IND, F.RELEASED</p>         </td>
      </tr>
      <tr>
         <td><p>F.RELEASED, CNF &lt;------</p>         </td>
         <td><p>  </p>         </td>
         <td><p>&lt;------RSP, F.RELEASED</p>         </td>
      </tr>
      <tr>
         <td><p>  </p>         </td>
         <td><p>disconnected</p>         </td>
         <td><p>  </p>         </td>
      </tr>
   </tbody>
</table>
