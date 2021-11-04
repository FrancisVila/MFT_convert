{
    "title": "Post installation",
    "linkTitle": "Post installation",
    "weight": "120"
}## Verify your installation

You can check the installation log in the <span class="code">&lt;installation directory>/install.log</span> file. See the installation [troubleshooting section](../troubleshoot_registration) if you encounter problems with starting <span class="mc-variable axway_variables.Component_Long_Name variable">Transfer CFT</span> or registering with <span class="mc-variable suite_variables.Central_GovernanceName variable">Central Governance</span>.

### Installed directories

(missing or bad snippet)

### Installer-generated files

During the installation, the Transfer CFT installer creates two files in the installation directory that are working files for the installer. Do not modify these files unless instructed to do so by Axway. While they are not used for Transfer CFT operations, they are necessary for installer functions such as upgrades.

-   .rundir
-   .transfer\_cft.properties

## Standalone installations

If you are not using <span class="mc-variable suite_variables.TransferCFTName variable">Transfer CFT</span> with <span class="mc-variable suite_variables.Central_GovernanceName variable">Central Governance</span>, you must provide a certificate in order to be able to use the <span class="mc-variable suite_variables.TransferCFTName variable">Transfer CFT</span> UI. See [Using the web-based browser UI](../../../c_intro_userinterfaces/web_copilot_ui#Connect2) page for details.

## Register with <span class="mc-variable suite_variables.Central_GovernanceName variable">Central Governance</span>

Begin your registration with <span class="mc-variable suite_variables.Central_GovernanceName variable">Central Governance</span> by starting the Copilot server, which launches the registration process.

### Start the Transfer CFT Copilot server

To set the environment variables from the runtime directory prompt enter:

    ../profile

To start the Copilot server, run the command:

    copstart

<span id="Verify"></span>

## Verify the Transfer CFT registration with <span class="mc-variable suite_variables.Central_GovernanceName variable">Central Governance</span>

### Log on <span class="mc-variable suite_variables.Central_GovernanceName variable">Central Governance</span>

If you have not already done so, log on <span class="mc-variable suite_variables.Central_GovernanceName variable">Central Governance</span>.

In <span class="mc-variable suite_variables.Central_GovernanceName variable">Central Governance</span> from the **Product** page, check the Product List for your installed <span class="mc-variable axway_variables.Component_Long_Name variable">Transfer CFT</span>.

See the Troubleshooting installation section in the <span class="mc-variable axway_variables.Component_Long_Name variable">Transfer CFT</span> <span class="mc-variable suite_variables.DocTypeUser variable">User Guide</span> for tips in case of an error.

### Start the Transfer CFT server

To start Transfer CFT from the <span class="mc-variable suite_variables.Central_GovernanceName variable">Central Governance</span> interface, use the following procedure.

1.  Click **Products** on the top toolbar to open the page.
2.  Select the product (Transfer CFT) to start.
3.  Click Start. When started successfully, the Status column displays **Started**.

### View the log using <span class="mc-variable Primary.CG or_UM variable">Central Governance</span>

1\. Click the name of the Transfer CFT system on the **Product List** page to open its details page.

2\. Click Logs on the right side of the page.

The log page is displayed where you can:

-   Click Refresh anytime to update the log entries.
-   Sort the entries by newest or oldest.
-   Filter the entries, saving filters for future use.

<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Note</strong></span>         </td>
         <td>For details on starting, stopping and viewing the Transfer CFT refer to the <strong>Central Governance</strong> <strong>User Guide.</strong>         </td>
      </tr>
   </tbody>
</table>

## Register with <span class="mc-variable Primary.CG or_UM variable">Central Governance</span>

If you intend to implement <span class="mc-variable Primary.CG or_UM variable">Central Governance</span>, please refer to the <span class="mc-variable axway_variables.Component_Long_Name variable" style="font-style: italic;">Transfer CFT</span> *User's Guide &gt; [*Register with* <span class="mc-variable Primary.CG or_UM variable" style="font-style: italic;">Central Governance</span>](https://docs.axway.com/bundle/TransferCFT_36_UsersGuide_allOS_en_HTML5/page/Content/cft_installation/migrate/register_CG.htm)* page for registration details.
