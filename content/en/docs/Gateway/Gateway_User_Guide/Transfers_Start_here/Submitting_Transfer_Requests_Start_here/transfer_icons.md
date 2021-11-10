{
    "title": "Transfer icons",
    "linkTitle": "Transfer icons",
    "weight": "160"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Managing Transfers

This topic describes the set of icons associated with Mailbox Transfer Request records in the GUI.

[Transfer record list](#Transfer_list) (in the right pane)

[Viewing a transfer](#Viewing_a_transfer) (in read-only mode in the Transfer Request record window)

<span id="Transfer_list"></span>

## Transfer record list

In the transfer record list displayed in the right pane, each line represents the record of a transfer. Each line, or record, contains an icon that indicates the following information about the nature and state of the transfer:

-   Mode (Initiator or Responder)
-   Direction (send or receive)
-   Transfer state
-   Use of Diffusion List
-   Routing state

Each icon includes a blue ellipse that represents Gateway.

<span id="Transfer_mode"></span>

### Transfer mode

If the Gateway symbol is positioned to the left of the arrow, the transfer mode is <span style="font-weight: bold;">Initiator</span>, otherwise the transfer mode is <span style="font-weight: bold;">Responder</span>:

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><img src="/Images/Gateway/transfer_icon_2.gif" width="31" height="31" /></p>         </td>
         <td><ul>
<li>mode: <span style="font-weight: bold;">Initiator</span></li>
<li>direction: send</li>
<li>state: ENDED</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><img src="/Images/Gateway/transfer_icon_14_32x32.gif" /></p>         </td>
         <td><ul>
<li>mode: <span style="font-weight: bold;">Responder</span></li>
<li>direction: send</li>
<li>state: ENDED</li>
</ul>         </td>
      </tr>
   </tbody>
</table>

<span id="Direction"></span>

### Direction

The transfer direction is indicated by an arrow. If the arrow points towards the Gateway symbol, the direction is <span style="font-weight: bold;">receive</span>, otherwise the direction is <span style="font-weight: bold;">send</span>.

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><img src="/Images/Gateway/transfer_icon_2.gif" width="31" height="31" /></p>         </td>
         <td><ul>
<li>mode: Initiator</li>
<li>direction: <span style="font-weight: bold;">send</span></li>
<li>state: ENDED</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><img src="/Images/Gateway/transfer_icon_15_32x32.gif" /></p>         </td>
         <td><ul>
<li>mode: Initiator</li>
<li>direction: <span style="font-weight: bold;">receive</span></li>
<li>state: ENDED</li>
</ul>         </td>
      </tr>
   </tbody>
</table>

<span id="Transfer_status"></span>

### Transfer states

The color of the arrow indicates the transfer state:

-   <span style="font-weight: bold;">black</span>: To begin, To restart, To cancel, To suspend, To sign, Delayed, Frozen
-   <span style="font-weight: bold;">yellow</span>: Beginning, In progress, Servicing, Canceling, Suspending, Created
-   <span style="font-weight: bold;">white</span>: Deleted
-   <span style="font-weight: bold;">green</span>: Ended, Acked, Ended to ack
-   <span style="font-weight: bold;">red</span>: Suspended, Canceled, Interrupted
-   <span style="font-weight: bold;">purple</span>: Nack by user, Nack by XFB

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><img src="/Images/Gateway/transfer_icon_17_32x32.gif" /></p>         </td>
         <td><ul>
<li>mode: Initiator</li>
<li>direction: send</li>
<li>state: <span style="font-weight: bold;">FROZEN, TO_BEGIN or TO_RESTART</span></li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><img src="/Images/Gateway/transfer_icon_22.gif" width="31" height="31" /></p>         </td>
         <td><ul>
<li>mode: Initiator</li>
<li>direction: send</li>
<li>state: <span style="font-weight: bold;">BEGINNING, IN PROGRESS, SERVICING, CANCELING, SUSPENDING, CREATED</span></li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><img src="/Images/Gateway/transfer_icon_22a.png" /></p>         </td>
         <td><ul>
<li>mode: Responder</li>
<li>direction: receive</li>
<li>state: <span style="font-weight: bold;">DELETED</span></li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><img src="/Images/Gateway/transfer_icon_2.gif" width="31" height="31" /></p>         </td>
         <td><ul>
<li>mode: Initiator</li>
<li>direction: send</li>
<li>state: <span style="font-weight: bold;">ENDED</span></li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><img src="/Images/Gateway/transfer_icon_16_32x32.gif" /></p>         </td>
         <td><ul>
<li>mode: Initiator</li>
<li>direction: send</li>
<li>state: <span style="font-weight: bold;">CANCELED, INTERRUPTED or SUSPENDED</span></li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><img src="/Images/Gateway/transfer_icon_23.gif" width="31" height="31" /></p>         </td>
         <td><ul>
<li>mode: Initiator</li>
<li>direction: send</li>
<li>state: <span style="font-weight: bold;">NACK BY USER, NACK BY XFB</span></li>
</ul>         </td>
      </tr>
   </tbody>
</table>

**Note**: On receiver side an interrupted transfer has the state "Deleted".

<span id="Diffusion_List"></span>

### Diffusion List

If a transfer uses a Diffusion List, the single arrow is replaced by three arrows:

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><img src="/Images/Gateway/transfer_icon_6.gif" width="31" height="31" /></p>         </td>
         <td><ul>
<li>mode: Initiator</li>
<li>direction: send</li>
<li>state: ENDED</li>
<li>uses a Diffusion List</li>
</ul>         </td>
      </tr>
   </tbody>
</table>

<span id="Routing_status"></span>

### Routing states

The following icon indicates that the transfer must be routed or has already been routed:

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><img src="/Images/Gateway/transfer_icon_18.gif" width="32" height="32" /></p>         </td>
         <td><ul>
<li>mode: Responder</li>
<li>direction: receive</li>
<li>state: ENDED</li>
<li>To route or routed</li>
</ul>         </td>
      </tr>
   </tbody>
</table>

If the direction of the small arrow is reversed, it indicates that the transfer was routed from another source:

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><img src="/Images/Gateway/transfer_icon_19.gif" width="32" height="32" /></p>         </td>
         <td><ul>
<li>mode: Initiator</li>
<li>direction: send</li>
<li>state: ENDED</li>
<li>Routed from</li>
</ul>         </td>
      </tr>
   </tbody>
</table>

<span id="Viewing_a_transfer"></span>

## Viewing a transfer

When you display a transfer in read-only mode, three icons can appear on the <span style="font-weight: bold;">General</span> tab of the Transfer Request window. The first icon is always displayed and is the same as the icon that appears in the transfer list. In addition, the window may display the following icons:

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><img src="/Images/Gateway/transfer_icon_10_32x32.gif" /></p>         </td>
         <td><p>Real File Directory type transfer</p>         </td>
      </tr>
      <tr>
         <td><p><img src="/Images/Gateway/transfer_icon_11_32x32.gif" /></p>         </td>
         <td><p>Virtual File Directory type transfer</p>         </td>
      </tr>
      <tr>
         <td><p><img src="/Images/Gateway/transfer_icon_12.gif" width="32" height="32" /></p>         </td>
         <td><p>Security implemented</p>         </td>
      </tr>
      <tr>
         <td><p><img src="/Images/Gateway/transfer_icon_13.gif" width="32" height="32" /></p>         </td>
         <td><p>Security not implemented</p>         </td>
      </tr>
   </tbody>
</table>

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
