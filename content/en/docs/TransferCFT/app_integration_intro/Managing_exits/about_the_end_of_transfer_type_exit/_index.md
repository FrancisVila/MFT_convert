{
    "title": "About end-of-transfer exits",
    "linkTitle": "End-of-transfer exit",
    "weight": "320"
}The exit interface provides
the user program with a structure containing information relating to the
transfer. This book describes the end-of-transfer exit. It begins with this topic, which explains the
transfer state and how it relates to an end-of-transfer exit.

The end of transfer type EXIT task enables the user to take control
at the end of a send or receive file or message transfer, independently
of whether or not the transfer is completed.

<span id="Transfer_state"></span>

### Transfer state

The user program can also ask the <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> to modify the
transfer state (UPDATE) or to delete the catalog record (DELETE).

The following changes of state are authorized in the event of an UPDATE:

-   H --> K
-   K --> H
-   T --> X
-   H or K --> D
-   T --> T

If a transfer procedure is submitted, it is initiated when the exit
call ends.

When the EXIT task is called without any request for change to the related
catalog entry’s state, the end-of-transfer procedure is submitted according
to standard <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> rules.

When the EXIT task initiates a change of state, the procedure submission
rule depends on the final state of the catalog entry returned by the EXIT.

The following
table shows the transfer possible changes of state.

<table>
   <th>
      <tr>
<th><p>Change of state </p>         </th>
<th><p>End of transfer procedure
submitted </p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>H to K </p>         </td>
         <td><p>Abnormal end of transfer procedure </p>         </td>
      </tr>
      <tr>
         <td><p>K to H </p>         </td>
         <td><p>Abnormal end of transfer procedure </p>         </td>
      </tr>
      <tr>
         <td><p>T to X </p>         </td>
         <td><p>No call </p>         </td>
      </tr>
      <tr>
         <td><p>H to D </p>         </td>
         <td><p>No call </p>         </td>
      </tr>
      <tr>
         <td><p>K to D </p>         </td>
         <td><p>No call </p>         </td>
      </tr>
      <tr>
         <td><p>T to T </p>         </td>
         <td><p>Normal end of transfer procedure </p>         </td>
      </tr>
   </tbody>
</table>