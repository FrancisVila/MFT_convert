{
    "title": "frecfm",
    "linkTitle": "frecfm",
    "weight": "1320"
}<span id="frecfm"></span>

### frecfm

<span id="frecfm_CFTRECV"></span><span id="frecfm_CFTSEND"></span>

#### CFTRECV, CFTSEND, SEND, RECV

\[FRECFM = {see the platform specific
*Operations Guide* | F | U | V}\]    

Record format of the receiver (local) file:

-   F:
    fixed
-   V:
    variable
-   U:
    undefined

The possible values for each system are indicated in the corresponding
*Operations Guide*.

Receive:

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>IBM i (OS400), UNIX</strong></p>         </td>
         <td><p>The variable format concept is specific to <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span>,
and does not correspond to a reality for the systems indicated. A variable
format receiver file cannot consequently be interpreted directly by an
application, since it contains control information. Unless otherwise specified
FRECFM = V is  not
used.</p>         </td>
      </tr>
   </tbody>
</table>

Send:

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>OS400, UNIX</strong></p>         </td>
         <td><p>The variable format concept is specific to <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span>,
and does not correspond to a reality for the systems indicated. The Transfer
CFT can only send a variable format file if this file is
generated by a COPYFILE command, or already received by <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> (store
and forward, for example). Unless otherwise specified FRECFM = V is  not
used.</p>         </td>
      </tr>
   </tbody>
</table>

<span style="font-weight: bold;">z/OS (MVS)</span> If this parameter is not
defined, the default value is <span style="font-weight: bold;">U</span>.

[Return to Command index](../../)