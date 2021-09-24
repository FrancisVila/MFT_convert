{
    "title": "Transfer  phase",
    "linkTitle": "Transfer  phase",
    "weight": "200"
}This is the key and only mandatory phase, which is activated for all flows. The former state and the adapted state will both be synchronized with the former state.

During this phase, the phase step is the same as the former state:

-   \(H\) Hold: waiting for an incoming receive to start the transfer or a start command
-   \(D\) Disposable: scheduled to start
-   \(C\) Current: transferring/processing
-   \(K\) Keep: transfer failed or stopped

As soon as the transfer is successfully finished, it passes to the next phase - post processing, acknowledgement, or done.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">See <a href="../../about_transfer_processing/proc_commands">Processing commands: general usage</a> for a description of the processing command parameters and values.         </td>
      </tr>
</table>
