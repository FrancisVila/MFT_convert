{
    "title": "Upgrading the Mailbox",
    "linkTitle": "Migrating the Mailbox",
    "weight": "170"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Managing the Server

[Upgrading the Mailbox: pelmig](#pelmig)

The <span class="code" style="font-weight: bold;">pelmig</span> command enables you to upgrade the Mailbox file. The only supported migration is from 6.16 to 6.17. For more information, read <a href="../../../gateway_upgradeguide/migrating_to_6.17" class="MCXref xref">Upgrading to 6.17</a>.

<span id="pelmig"></span>

## Upgrading the Mailbox: pelmig

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p>Syntax</p>         </td>
         <td><p><strong>pelmig</strong></p>
<p>   {-input_version (-iv) { V6.16 | V6.17 }}</p>
<p>   {-output_version (-ov) { V6.16 | V6.17 }}</p>         </td>
      </tr>
      <tr>
         <td><p>Description</p>         </td>
         <td><p>Use the <span class="code" style="font-weight: bold;">pelmig</span> command to upgrade the Mailbox file between different versions of Gateway.</p>
<p><strong>Notes:</strong></p>
<ul>
<li>Before upgrading the Mailbox file, you must first upgrade all Gateway objects (Sites, Applications, etc.).</li>
<li>The <span class="code" style="font-weight: bold;">pelmig</span> command requires that both the input and output Mailbox files are located in the <span class="code">run_time/data directory</span> of the new version of Gateway. For this reason, it is recommended that you copy the input Mailbox to that directory and then run the <span class="code" style="font-weight: bold;">pelmig</span> command from that directory.</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><span class="code">-input_version (-iv): </span>Gateway version number from which you are upgrading (must be V6.16).<span class="code"></span>         </td>
      </tr>
      <tr>
         <td><span class="code">-output_version (-ov)</span>: Gateway version number to which you are upgrading (must be V6.17).<span class="code"></span>         </td>
      </tr>
      <tr>
         <td><p>Example</p>         </td>
         <td><p>To upgrade the Mailbox file from Gateway V6.16 to Gateway V6.17:</p>
<ol>
<li>Copy and rename the file <span class="code">xfer.dat</span> from Gateway V6.16 to Gateway V6.17 (name this file <span class="code">xfer616.dat</span>).</li>
<li>Change directory to the <span class="code">run_time/data</span> directory of Gateway V6.17.</li>
<li>Run the appropriate <span class="code" style="font-weight: bold;">pelmig</span> command.</li>
</ol>
<p>On a UNIX system, use the following command:</p>
<p>cd &lt;V617&gt;</p>
<p>. run_time/etc/profile</p>
<p>cd run_time/data</p>
<p>cp &lt;V616&gt;/run_time/data/xfer.dat xfer616.dat</p>
<p>pelmig –im xfer616.dat –iv V6.16 –om xfer.dat –ov V6.17</p>         </td>
      </tr>
   </tbody>
</table>

### Upgrading to an earlier version of Gateway

Although it is not recommended, you can use the <span class="code" style="font-weight: bold;">pelmig</span> command to upgrade the Mailbox file to an earlier version of Gateway. To make this possible, all Transfer Requests for upgrade must only use features that are available in both versions of Gateway.

By default, the <span class="code" style="font-weight: bold;">pelmig</span> command aborts the upgrade process if a Transfer Request that cannot upgrade is detected in the input Mailbox file. To change the default behavior, specify <span class="code">-upgrade\_mode partial</span> as input parameter. In partial mode, the <span class="code" style="font-weight: bold;">pelmig</span> command only upgrades Transfer Requests that are compatible with the target version of Gateway.

### Message and exit status after upgrade

If upgrade is successful, the <span class="code" style="font-weight: bold;">pelmig</span> command displays the following statistical information in the output and then exits with a status value of zero:

-   Total number of records successfully upgraded
-   Total number of upgraded records changed by the user exit
-   Total number of records not upgraded

Example output:

-   19 records upgraded
-   0 records updated
-   0 records ignored

Additional messages may also be written in the output depending on the value of the <span class="code">verbosity</span> parameter supplied to <span class="code" style="font-weight: bold;">pelmig</span>. For example, when <span class="code">verbosity</span> is either middle or high, the output also displays messages relating to changes applied to input data records or to information that was not moved to the upgraded records.

If an error occurs during upgrade, the <span class="code" style="font-weight: bold;">pelmig</span> command displays the cause of the error in the output and exits with a non-zero status.

For example, if the input Mailbox name cannot be opened for input because the specified name does not match an existing file, the following message will be displayed:

--2011/03/13 12:07:38 – ERROR from MigMailbox

--2011/03/13 12:07:38 – MbxOpen(xfer.dat) for reading returns error

--2011/03/13 12:07:38 – No such file or directory

--2011/03/13 12:07:38 – MAILBOX MIGRATION FAILED!

Related topics

[Managing the Mailbox (command line)](../../transfers_start_here/monitoring_transfers_start_here/viewing_and_managing_mailbox_contents_cli/managing_mailbox_cli)

[Maintaining the Mailbox (kfmcp command)](../../transfers_start_here/monitoring_transfers_start_here/viewing_and_managing_mailbox_contents_cli/maintaining_mailbox)

[Importing and exporting objects](../importing_and_exporting_objects)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
