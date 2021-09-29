{
    "title": "Post-installation",
    "linkTitle": "Post-installation",
    "weight": "170"
}This section presents JCL examples that you can use to create the JOBs necessary to run Transfer CFT. All of the JCLs are located in the **target.INSTALL** library.

-   [Starting Transfer CFT JOB CFTMAIN](#starting%20the%20cftmain%20example)
-   [Transfer CFT user interface server commands](#transfer%20cft%20user%20interface%20server)

<table data-cellpadding="0" data-cellspacing="0">
<tbody>
<tr class="odd">
<td data-valign="top"></td>
<td data-valign="top"><span><strong>Note</strong></span></td>
<td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">If you installed <span>Transfer CFT</span> along with <span>Central Governance</span>, the uconf <span>copilot.misc.cftstart.enable</span> is automatically set to <span>Yes</span>. This allows <span>Central Governance</span> to control stopping and starting your <span>Transfer CFT</span>.</td>
</tr>
</tbody>
</table>

## <span id="Starting the CFTMAIN example"></span>Start Transfer CFT 

The CFTMAIN JOB is an example of a JCL to start Transfer CFT. Beginning with the CFTMAIN sample, you can create JOBs to meet your operating requirements.

You can perform Transfer CFT commands using the CFTUTIL utility, the Transfer CFT user interface, or the console interface.

Start the CFTMAIN JCL in the target.INSTALL library.

<table data-cellpadding="0" data-cellspacing="0">
<tbody>
<tr class="odd">
<td data-valign="top"></td>
<td data-valign="top"><span><strong>Note</strong></span></td>
<td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">CFTMAIN must be APF authorized to start if the UCONF <span>cft.mvs.monitor.check_apf </span>variable is set to <span>Yes</span>. Otherwise, the Transfer CFT log displays <span>CFTI01F CFT error CFT is not APF-authorized</span>.</td>
</tr>
</tbody>
</table>

## Stop Transfer CFT 

The following are commands that you can use to stop Transfer CFT outside of a customized JCL (such as the delivered sample JCL, **CFTSTOP**, in the target.INSTALL library).

**Normal stop**

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td>/F &lt;Jobname&gt;,SHUT FAST=NO <em>or</em> SHUT FAST=YES</td>
</tr>
</tbody>
</table>

**Quick stop**

Enter the operator command:

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td>/P &lt;<span>Transfer CFT</span> Jobname&gt;</td>
</tr>
</tbody>
</table>

\- or -

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td>/F &lt;<span>Transfer CFT</span> Jobname&gt;,SHUT FAST=YES</td>
</tr>
</tbody>
</table>

**Force** Transfer CFT **shut down**

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td>/F &lt;<span>Transfer CFT</span> Jobname&gt;,SHUT FAST=KILL</td>
</tr>
</tbody>
</table>

### Restart

The following command restarts Transfer CFT outside of a customized JCL. Enter the operator command:

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td>/F Jobname,SHUT RESTART=YES</td>
</tr>
</tbody>
</table>

### Status

Use the CFTPING in the target.INSTALL library to ping your Transfer CFT.

## <span id="Transfer CFT user interface server"></span>Transfer CFT Copilot server commands

The Transfer CFT Copilot server is a sub component that is mandatory when using Central Governance. Additionally, this server may function as the node manager when using multi-node.

### Starting the Copilot server

COPRUN is an example of a JCL statement that starts the Transfer CFT Copilot server. The server can be started as a Start Task. The Transfer CFT Copilot server STEPLIB, and then JOBLIB should be defined as an APF. If it is not defined as an APF, no RACF check can be performed. This results in no log-on check being available and all requests are done with the user associated with the server JOB.

When the copilot.misc.CreateProcessAsUser variable is set, STEPLIB or JOBLIB can be non-APF. Only a Central Governance/PassPort user can sign on to Copilot user interface.

<table data-cellpadding="0" data-cellspacing="0">
<tbody>
<tr class="odd">
<td data-valign="top"></td>
<td data-valign="top"><span><strong>Note</strong></span></td>
<td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">When the ‘cft.mvs.copilot.check_apf’ uconf variable is set to ‘Yes’, CFTCOPL must be APF authorized to start.</td>
</tr>
</tbody>
</table>

LOG message: +CFTI42E Copilot must be APF-authorized.

<table data-cellpadding="0" data-cellspacing="0">
<tbody>
<tr class="odd">
<td data-valign="top"></td>
<td data-valign="top"><span><strong>Note</strong></span></td>
<td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">CFTCOPL must be APF authorized to start if the UCONF <span>cft.mvs.copilot.check_apf </span>variable is set to <span>Yes</span>. Otherwise, the Transfer CFT log displays <span>CFTI42E Copilot must be APF-authorized</span>.</td>
</tr>
</tbody>
</table>

### Stopping user interface (Copilot) server

COPSTOP is an example of the JCL stop statement for the Transfer CFT UI server. You can also stop the Transfer CFT UI server using the operator command pause (/P jobname) for the server-associated task.

### Checking the Copilot server status

You can use COPSTATU, for example, as the JCL statement to display the Transfer CFT Copilot server status in the current LPAR.

## Register with Central Governance

If you intend to implement Central Governance, please refer to the Transfer CFT *User's Guide &gt; [*Register with* Central Governance](https://docs.axway.com/bundle/TransferCFT_36_UsersGuide_allOS_en_HTML5/page/Content/cft_installation/migrate/register_CG.htm)* page for registration details.
