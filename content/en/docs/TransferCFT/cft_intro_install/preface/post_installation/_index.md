{
    "title": "Post installation",
    "linkTitle": "Post installation",
    "weight": "180"
}This chapter describes a series of checks that you should perform to verify your Transfer CFT installation. For more information on performing commands and using CFTUTIL, refer to the *Transfer CFT 3.9 [User Guide](https://docs.axway.com/u/documentation/transfer_cft/index.htm?version=3.2.4)*.

<table data-cellpadding="0" data-cellspacing="0">
<tbody>
<tr class="odd">
<td data-valign="top"></td>
<td data-valign="top"><span><strong>Note</strong></span></td>
<td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">The information in the Unix <a href="../../unix_install_start_here/run_first_time_ux/use_cft_utilities">Management utilities</a> page applies equally to the Unix-like interface used in HP NonStop.</td>
</tr>
</tbody>
</table>

## Verify the installation

### Check the Transfer CFT server

Load the Transfer CFT profile:

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td>. &lt;installation_directory&gt;/runtime/profile</td>
</tr>
</tbody>
</table>

Verify the Transfer CFT version:

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td>CFTUTIL about</td>
</tr>
</tbody>
</table>

*Optionally*, change the Transfer CFT Guardian process names *if you are performing multiple installations*. Because each Transfer CFT process is assigned a Guardian process name, these names should be globally unique.

-   Use the  [cft.guardian.process\_name\_prefix](hp_ns_batch.htm#cft.guardian.process_name_prefix) UCONF parameter as described in the UCONF parameters section.
-   Be certain to change this parameter's default value if you are running several Transfer CFT installations at the same time.

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td>CFTUTIL uconfset id=cft.guardian.process_name_prefix,value=LB</td>
</tr>
</tbody>
</table>

Start the Transfer CFT server:

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td>cft start</td>
</tr>
</tbody>
</table>

Verify that the default ports used in $CFTDIRRUNTIME/conf/cft-tcp.conf are available:

-   1761 (PeSIT Any protocol)
-   1762 (PeSIT Any protocol with SSL authentication)

If the ports are not available, modify the port(s) and re-apply the configuration:

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>cftupdate $CFTDIRRUNTIME/conf/cft-tcp.conf</p></td>
</tr>
</tbody>
</table>

Check that Transfer CFT server is started:

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>cftping -v</p>
<p>cftlog</p></td>
</tr>
</tbody>
</table>

Perform a transfer:

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td>CFTUTIL SEND PART=PARIS, IDF=TEST</td>
</tr>
</tbody>
</table>

Check the status of the transfer:

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td>CFTUTIL LISTCAT</td>
</tr>
</tbody>
</table>

Stop the Transfer CFT server:

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td>cft stop</td>
</tr>
</tbody>
</table>

Verify that the Transfer CFT server is stopped:

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td>cftping –v</td>
</tr>
</tbody>
</table>

### Start the Transfer CFT Copilot server

If you intend to use one of the following, configure it now:

-   Central Governance: see [Activate Central Governance connectivity](../../../governance_services_intro/register_cg)
-   Transfer CFT user interface: see [Using the web browser user interface](../../../c_intro_userinterfaces/web_copilot_ui)

After having configured one of these, you can run the Copilot server:

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>cd &lt;CFTDIRRUNTIME&gt;</p>
<p>. . /profile</p>
<p>copstart</p>
<p>http://MyHostName:1766</p></td>
</tr>
</tbody>
</table>

If you have activated the Central Governance connectivity, you can [Verify the Transfer CFT registration with Central Governance](../../unix_install_start_here/shared_verify_install).

Transfer CFT HP NonStop provides a start-process supervisor (CFTSUP) that can restart the Transfer CFT server or UI server in the case of an unexpected product stop. For more information, see [Use the NonStop mode](hp_ns_sup) .
