{
    "title": "Configure multi-node simultaneous transfers",
    "linkTitle": "Configure simultaneous transfers ",
    "weight": "200"
}The Transfer CFT session management in a multi-node architecture differs from a standalone implementation. This section describes parameters you can use to customize a multi-node environment, and offers some recommendations.

<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Note</strong></span>         </td>
         <td>The diag 916 and 418 errors relate to these settings. See <a href="../../troubleshoot_intro/messages_and_error_codes_start_here/diagi_diagnostic_codes" class="MCXref xref">DIAGI - Diagnostic
codes</a>.         </td>
      </tr>
   </tbody>
</table>

## Global settings

The MAXCNX and MAXTRANS parameters control the Transfer CFT maximum number of simultaneous connections and authorized parallel transfers respectively. It is important to remember that the MAXCNX and MAXTRANS values in a multi-node architecture apply to each node. This means that if there are 3 nodes, multiply the MAXCNX value by 3 to have the actual value for that Transfer CFT.

If you have limited resources, set the MAXTRANS to a low value. If resources are not limited, a rule of thumb might be to set MAXTRANS to the sum of all partner CNXINOUT values (maximum value of 1000).

See also <a href="../../concepts/about_parallel_transfers" class="MCXref xref">Configure simultaneous transfers</a>.

## Session parameters

You can use the CNXIN, CNXOUT, and CNXINOUT parameters in CFTTCP to define the number of sessions. The formulas in this section apply equally to both a multi-node to multi-node configuration, and to a multi-node to standalone configuration, where the standalone installation has (<span class="code">nb\_nodes=1</span>) and the multi-node has (<span class="code">nb\_nodes=nodes</span>).

In the following example, the formulas calculate optimal values to help you avoid connection errors (such as [DIAGI 418](../../troubleshoot_intro/messages_and_error_codes_start_here/diagi_diagnostic_codes)):

<span style="font-family: 'Courier New';">CNXIN</span><sub>(local)</sub><span style="font-family: 'Courier New';"> = CNXOUT</span><sub>(remote)</sub><span style="font-family: 'Courier New';"> \* nb\_nodes</span><sub>(remote)</sub>

<span style="font-family: 'Courier New';">CNXOUT<sub>(local)</sub> = CNXIN<sub>(remote)</sub> / nb\_nodes<sub>(local)</sub></span>

<span style="font-family: 'Courier New';">CNXINOUT = CNXIN + CNXOUT</span> (you can use this value to limit resource usage, that is, a value less than the sum of CNXIN + CNXOUT)

You can reverse the formula for the remote Transfer CFT.

<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Note</strong></span>         </td>
         <td>This calculation takes into consideration that a single node may have to handle all of the incoming connections from the partner.         </td>
      </tr>
   </tbody>
</table>

Related topics

[About multi-node architecture](../)