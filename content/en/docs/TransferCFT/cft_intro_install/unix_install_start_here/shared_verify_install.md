{
    "title": "Post installation",
    "linkTitle": "Post installation",
    "weight": "120"
}## Verify your installation

You can check the installation log in the &lt;installation directory>/install.log file. See the installation [troubleshooting section](../troubleshoot_registration) if you encounter problems with starting Transfer CFT or registering with Central Governance.

### Installed directories

(missing or bad snippet)

### Installer-generated files

During the installation, the Transfer CFT installer creates two files in the installation directory that are working files for the installer. Do not modify these files unless instructed to do so by Axway. While they are not used for Transfer CFT operations, they are necessary for installer functions such as upgrades.

-   .rundir
-   .transfer\_cft.properties

## Standalone installations

If you are not using Transfer CFT with Central Governance, you must provide a certificate in order to be able to use the Transfer CFT UI. See [Using the web-based browser UI](../../../c_intro_userinterfaces/web_copilot_ui) page for details.

## Register with Central Governance

Begin your registration with Central Governance by starting the Copilot server, which launches the registration process.

### Start the Transfer CFT Copilot server

To set the environment variables from the runtime directory prompt enter:

<table cellspacing="0">   <col/>   <tbody>      <tr>         <td>../profile         </td>      </tr>   </tbody></table>

To start the Copilot server, run the command:

<table cellspacing="0">   <col/>   <tbody>      <tr>         <td>copstart         </td>      </tr>   </tbody></table>

## <span id="Verify"></span>Verify the Transfer CFT registration with Central Governance

### Log on Central Governance

If you have not already done so, log on Central Governance.

In Central Governance from the **Product** page, check the Product List for your installed Transfer CFT.

See the Troubleshooting installation section in the Transfer CFT User Guide for tips in case of an error.

### Start the Transfer CFT server

To start Transfer CFT from the Central Governance interface, use the following procedure.

1.  Click **Products** on the top toolbar to open the page.
2.  Select the product (Transfer CFT) to start.
3.  Click Start. When started successfully, the Status column displays **Started**.

### View the log using Central Governance

1\. Click the name of the Transfer CFT system on the **Product List** page to open its details page.

2\. Click Logs on the right side of the page.

The log page is displayed where you can:

-   Click Refresh anytime to update the log entries.
-   Sort the entries by newest or oldest.
-   Filter the entries, saving filters for future use.

<table cellpadding="0" cellspacing="0">   <col/>   <col/>   <col/>      <tr>         <td valign="top">         </td>         <td valign="top"><span><b>Note</b></span>         </td>         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">For details on starting, stopping and viewing the Transfer CFT refer to the <strong>Central Governance </strong><strong>User Guide.</strong>         </td>      </tr></table>

## Register with Central Governance

If you intend to implement Central Governance, please refer to the Transfer CFT *User's Guide &gt; [*Register with* Central Governance](https://docs.axway.com/bundle/TransferCFT_36_UsersGuide_allOS_en_HTML5/page/Content/cft_installation/migrate/register_CG.htm)* page for registration details.
