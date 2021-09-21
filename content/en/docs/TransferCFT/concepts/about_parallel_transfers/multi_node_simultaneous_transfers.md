{
    "title": "Configure multi-node simultaneous transfers",
    "linkTitle": "Configure multi-node simultaneous transfers",
    "weight": "290"
}The Transfer CFT session management in a multi-node architecture differs from a standalone implementation. This section describes parameters you can use to customize a multi-node environment, and offers some recommendations.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note  &lt;/b&gt;" valign="top">The diag 916 and 418 errors relate to these settings.  See <a href="../../../troubleshoot_intro/messages_and_error_codes_start_here/diagi_diagnostic_codes" xrefformat="{paratext}">DIAGI - Diagnostic 
 codes</a>.         </td>
      </tr>
</table>

## Global settings

The MAXCNX and MAXTRANS parameters control the Transfer CFT maximum number of simultaneous connections and authorized parallel transfers respectively. It is important to remember that the MAXCNX and MAXTRANS values in a multi-node architecture apply to each node. This means that if there are 3 nodes, multiply the MAXCNX value by 3 to have the actual value for that Transfer CFT.

If you have limited resources, set the MAXTRANS to a low value. If resources are not limited, a rule of thumb might be to set MAXTRANS to the sum of all partner CNXINOUT values (maximum value of 1000).

See also [Configure simultaneous transfers](..//transfercft/concepts/about_parallel_transfers).

## Session parameters

You can use the CNXIN, CNXOUT, and CNXINOUT parameters in CFTTCP to define the number of sessions. The formulas in this section apply equally to both a multi-node to multi-node configuration, and to a multi-node to standalone configuration, where the standalone installation has (nb\_nodes=1) and the multi-node has (nb\_nodes=nodes).

In the following example, the formulas calculate optimal values to help you avoid connection errors (such as [DIAGI 418](../../../troubleshoot_intro/messages_and_error_codes_start_here/diagi_diagnostic_codes)):

CNXIN<sub>(local)</sub> = CNXOUT<sub>(remote)</sub> \* nb\_nodes<sub>(remote)</sub>

CNXOUT<sub>(local)</sub> = CNXIN<sub>(remote)</sub> / nb\_nodes<sub>(local)</sub>

CNXINOUT = CNXIN + CNXOUT (you can use this value to limit resource usage, that is, a value less than the sum of CNXIN + CNXOUT)

You can reverse the formula for the remote Transfer CFT.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note  &lt;/b&gt;" valign="top">This calculation takes into consideration that a single node may have to handle all of the incoming connections from the partner.         </td>
      </tr>
</table>

Related topics

[About multi-node architecture](../../../about_multinode)