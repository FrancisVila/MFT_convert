{
    "title": "About governance services",
    "linkTitle": "About governance services",
    "weight": "160"
}In this guide, *flow* refers to the complete interaction between the source and target applications, more specifically Transfer CFT systems, to enable data exchanges between business applications or partners.

## Managed File Transfer services

Managed File Transfer services, using a blend of Axway products, can centralize flow definition and configuration deployment for {{< TransferCFT/componentlongname  >}} (file transfer) engines.

You can use Central Governance in your MFT architecture to easily create and deploy flows. You then trigger your flows at the system level.

<img src="/Images/TransferCFT/data_exchange_env.png" class="maxWidth" alt="Multiple Transfer CFTs can send events from the data exchange environment towards Central Governance" />

> **Note:**
>
> Connectivity may include connection to other or third-party products that are outside of the MFT reference solution.

### Additional documentation

-   {{< TransferCFT/platformorsuitelongname >}} Supported Platforms
-   {{< TransferCFT/centralgovernancename >}} documentation
-   {{< TransferCFT/flowmanager >}} documentation

## Governance exchanges

The following types of exchanges occur between {{< TransferCFT/centralgovernancename  >}} or {{< TransferCFT/flowmanager  >}} and the managed Transfer CFTs:

-   Flow management
-   Certificate management
-   Configuration management
-   Update management

See [Exchanges with Central Governance](../cg_postregister) for more information.

## Overview and practical considerations

Begin by planning your MFT architecture and deployment strategy. After installing {{< TransferCFT/centralgovernancename  >}} or {{< TransferCFT/flowmanager  >}}, the following steps occur:

-   In the {{< TransferCFT/componentlongname >}} installation select the Central Governance connectivity option
-   After installing, start the Transfer CFT Copilot server (the Transfer CFT server can be running, but this is optional)
-   Registration occurs automatically on Copilot start up
-   From {{< TransferCFT/centralgovernancename >}} or {{< TransferCFT/flowmanager >}} start the Transfer CFT(s)
-   If you migrated or upgraded, you may want to reference the following sections:
    -   [Manually activate Central Governance connectivity](../register_cg)
    -   Parameter mapping between products

<span id="Feature"></span>

## Feature support and management

Transfer CFTs running under {{< TransferCFT/centralgovernancename  >}} or {{< TransferCFT/flowmanager  >}} can manage or have support for the following features.

<table>
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Feature         </th>
<th style="text-align: center;" class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1"> Manage using {{< TransferCFT/flowmanager  >}} or         </th>
<th style="text-align: center;" class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1">Supported but not configurable using Central Governance or {{< TransferCFT/flowmanager  >}}         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-BodyE-Column1-Body2">Folder monitoring         </th>
         <td>yes         </td>
         <td>yes         </td>
      </tr>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-BodyE-Column1-Body2">Multi-node architecture         </th>
         <td>no         </td>
         <td>yes         </td>
      </tr>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-BodyE-Column1-Body2">CRONJOB         </th>
         <td>yes         </td>
         <td>yes         </td>
      </tr>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-BodyE-Column1-Body2">Exits         </th>
         <td>no         </td>
         <td>yes         </td>
      </tr>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-BodyD-Column1-Body2">Network and protocol features         </th>
         <td>         </td>
         <td>         </td>
      </tr>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-BodyE-Column1-Body2">IPv6         </th>
         <td>yes         </td>
         <td>yes         </td>
      </tr>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-BodyE-Column1-Body2">pTCP (UNIX/Windows only)         </th>
         <td>yes         </td>
         <td>yes         </td>
      </tr>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-BodyE-Column1-Body2">UDT (UNIX/Windows only)         </th>
         <td>yes         </td>
         <td>yes         </td>
      </tr>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-BodyE-Column1-Body2">SOCKS         </th>
         <td>no         </td>
         <td>yes         </td>
      </tr>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-BodyE-Column1-Body2">Heartbeat         </th>
         <td>embedded         </td>
         <td>yes         </td>
      </tr>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-BodyD-Column1-Body2">Interoperability         </th>
         <td>         </td>
         <td>         </td>
      </tr>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-BodyE-Column1-Body2">Secure Relay         </th>
         <td>no         </td>
         <td>yes         </td>
      </tr>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-BodyE-Column1-Body2">TrustedFile (UNIX/Windows/and z/OS)         </th>
         <td>no         </td>
         <td><p>yes</p>         </td>
      </tr>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-BodyE-Column1-Body2">PassPort AM         </th>
         <td>embedded         </td>
         <td>no (*)         </td>
      </tr>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-BodyE-Column1-Body2">PassPort PS         </th>
         <td>no         </td>
         <td>yes         </td>
      </tr>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-BodyE-Column1-Body2">Sentinel         </th>
         <td>embedded         </td>
         <td>yes         </td>
      </tr>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-BodyE-Column1-Body2">Composer         </th>
         <td>no         </td>
         <td>no         </td>
      </tr>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-BodyD-Column1-Body2">Protocols         </th>
         <td>         </td>
         <td>         </td>
      </tr>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-BodyE-Column1-Body2">PeSIT         </th>
         <td>yes         </td>
         <td>yes         </td>
      </tr>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-BodyE-Column1-Body2">ODETTE         </th>
         <td>no         </td>
         <td>yes         </td>
      </tr>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-BodyE-Column1-Body2">SFTP <em>(UNIX, Windows)</em>         </th>
         <td>no         </td>
         <td>yes         </td>
      </tr>
   </tbody>
</table>

\* If you perform a migration or upgrade from a previous version, you must migrate your PassPort AM.

<span id="Legacy"></span>

## Legacy flows

Legacy flows refer to former flow definitions available in migrated {{< TransferCFT/componentlongname  >}} systems. Central Governance or {{< TransferCFT/flowmanager  >}} can manage the following use cases:

-   Via the Central Governance or {{< TransferCFT/flowmanager >}} user interface, you can add and manage partners, and use send and receive templates for a given Transfer CFT.
-   You can migrate Transfer CFT flow definitions to the Central Governance or {{< TransferCFT/flowmanager >}} flow-management process.
