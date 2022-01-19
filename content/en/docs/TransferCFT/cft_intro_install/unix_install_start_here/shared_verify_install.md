{
    "title": "Post installation",
    "linkTitle": "Post installation",
    "weight": "120"
}## Verify your installation

You can check the installation log in the &lt;span class="code">&lt;code>&lt;installation directory>/install.log&lt;/code>&lt;/span> file. See the installation&lt;madcap:conditionaltext data-mc-conditions="axway\_conditions.ScreenOnly"> &lt;a href="../troubleshoot\_registration">troubleshooting section&lt;/a>&lt;/madcap:conditionaltext> if you encounter problems with starting &lt;span class="mc-variable axway\_variables.Component\_Long\_Name variable">Transfer CFT&lt;/span> or registering with &lt;span class="mc-variable suite\_variables.Central\_GovernanceName variable">Central Governance&lt;/span>.
&lt;/p>

### Installed directories

(missing or bad snippet)

### Installer-generated files

During the installation, the Transfer CFT installer creates two files in the installation directory that are working files for the installer. Do not modify these files unless instructed to do so by Axway. While they are not used for Transfer CFT operations, they are necessary for installer functions such as upgrades.

- .rundir
- .transfer\_cft.properties

## Standalone installations

If you are not using Transfer CFT{{< TransferCFT/transfercftname  >}} with Central Governance{{< TransferCFT/centralgovernancename  >}}, you must provide a certificate in order to be able to use the Transfer CFT{{< TransferCFT/transfercftname  >}} UI. See [Using the web-based browser UI](../../../c_intro_userinterfaces/web_copilot_ui#Connect2) page for details.

## Register with Central Governance{{< TransferCFT/centralgovernancename  >}}

Begin your registration with Central Governance{{< TransferCFT/centralgovernancename  >}} by starting the Copilot server, which launches the registration process.

### Start the Transfer CFT Copilot server

To set the environment variables from the runtime directory prompt enter:

```
../profile
```

To start the Copilot server, run the command:

```
copstart
```
<span id="Verify"></span>

## Verify the Transfer CFT registration with Central Governance{{< TransferCFT/centralgovernancename  >}}

### Log on Central Governance{{< TransferCFT/centralgovernancename  >}}

If you have not already done so, log on Central Governance{{< TransferCFT/centralgovernancename  >}}.

In Central Governance{{< TransferCFT/centralgovernancename  >}} from the **Product** page, check the Product List for your installed Transfer CFT{{< TransferCFT/componentlongname  >}}.

See the Troubleshooting installation section in the Transfer CFT{{< TransferCFT/componentlongname  >}} User Guide{{< TransferCFT/doctypeuser  >}} for tips in case of an error.

### Start the Transfer CFT server

To start Transfer CFT from the Central Governance{{< TransferCFT/centralgovernancename  >}} interface, use the following procedure.

1. Click **Products** on the top toolbar to open the page.
1. Select the product (Transfer CFT) to start.
1. Click Start. When started successfully, the Status column displays **Started**.

### View the log using Central Governance

1\. Click the name of the Transfer CFT system on the **Product List** page to open its details page.

2\. Click Logs on the right side of the page.

The log page is displayed where you can:

- Click Refresh anytime to update the log entries.
- Sort the entries by newest or oldest.
- Filter the entries, saving filters for future use.

> **Note**
>
> For details on starting, stopping and viewing the Transfer CFT refer to the Central Governance User Guide.

## Register with Central Governance

If you intend to implement Central Governance, please refer to the **Transfer CFT**{{< TransferCFT/componentlongname  >}} *User's Guide &gt; [*Register with* **Central Governance**](https://docs.axway.com/bundle/TransferCFT_36_UsersGuide_allOS_en_HTML5/page/Content/cft_installation/migrate/register_CG.htm)* page for registration details.
