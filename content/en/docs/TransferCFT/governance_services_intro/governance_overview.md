{
    "title": "About governance services",
    "linkTitle": "About governance services",
    "weight": "160"
}In this guide, *flow* refers to the complete interaction between the source and target applications, more specifically Transfer CFT systems, to enable data exchanges between business applications or partners.

## Managed File Transfer services

Managed File Transfer services, using a blend of Axway products, can centralize flow definition and configuration deployment for Transfer CFT (file transfer) engines.

You can use Central Governance in your MFT architecture to easily create and deploy flows. You then trigger your flows at the system level.

![Multiple Transfer CFTs can send events from the data exchange environment towards Central Governance](/Images/TransferCFT/data_exchange_env.png)

<table data-cellpadding="0" data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td data-valign="top">         </td>
         <td data-valign="top"><span><strong>Note</strong></span>         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">Connectivity may include connection to other or third-party products that are outside of the MFT reference solution.         </td>
      </tr>
   </tbody>
</table>

### Additional documentation

-   AMPLIFY Supported Platforms
-   Central Governance documentation
-   Flow Manager documentation

## Governance exchanges

The following types of exchanges occur between Central Governance or Flow Manager and the managed Transfer CFTs:

-   Flow management
-   Certificate management
-   Configuration management
-   Update management

See [Exchanges with Central Governance](cg_postregister) for more information.

## Overview and practical considerations

Begin by planning your MFT architecture and deployment strategy. After installing Central Governance or Flow Manager, the following steps occur:

-   In the Transfer CFT installation select the Central Governance connectivity option
-   After installing, start the Transfer CFT Copilot server (the Transfer CFT server can be running, but this is optional)
-   Registration occurs automatically on Copilot start up
-   From Central Governance or Flow Manager start the Transfer CFT(s)
-   If you migrated or upgraded, you may want to reference the following sections:
    -   [Manually activate Central Governance connectivity](register_cg)
    -   Parameter mapping between products

## <span id="Feature"></span>Feature support and management

Transfer CFTs running under Central Governance or Flow Manager can manage or have support for the following features.

<table data-cellspacing="0">
   <thead>
      <tr class="header" data-mc-conditions="">
         <th>Feature</th>
         <th> Manage using <span>Flow Manager</span> or <span>Central Governance</span></th>
         <th>Supported but not configurable using Central Governance or <span>Flow Manager</span></th>
      </tr>
   </thead>
   <tbody>
      <tr class="odd" data-mc-conditions="">
         <th>Folder monitoring</th>
         <td>yes         </td>
         <td>yes         </td>
      </tr>
      <tr class="even" data-mc-conditions="">
         <th>Multi-node architecture</th>
         <td>no         </td>
         <td>yes         </td>
      </tr>
      <tr class="odd" data-mc-conditions="">
         <th>CRONJOB</th>
         <td>yes         </td>
         <td>yes         </td>
      </tr>
      <tr class="even" data-mc-conditions="">
         <th>Exits</th>
         <td>no         </td>
         <td>yes         </td>
      </tr>
      <tr class="odd" data-mc-conditions="">
         <th>Network and protocol features</th>
         <td>         </td>
         <td>         </td>
      </tr>
      <tr class="even" data-mc-conditions="">
         <th>IPv6</th>
         <td>yes         </td>
         <td>yes         </td>
      </tr>
      <tr class="odd" data-mc-conditions="">
         <th>pTCP (UNIX/Windows only)</th>
         <td>yes         </td>
         <td>yes         </td>
      </tr>
      <tr class="even" data-mc-conditions="">
         <th>UDT (UNIX/Windows only)</th>
         <td>yes         </td>
         <td>yes         </td>
      </tr>
      <tr class="odd" data-mc-conditions="">
         <th>SOCKS</th>
         <td>no         </td>
         <td>yes         </td>
      </tr>
      <tr class="even" data-mc-conditions="">
         <th>Heartbeat</th>
         <td>embedded         </td>
         <td>yes         </td>
      </tr>
      <tr class="odd" data-mc-conditions="">
         <th>Interoperability</th>
         <td>         </td>
         <td>         </td>
      </tr>
      <tr class="even" data-mc-conditions="">
         <th>Secure Relay</th>
         <td>no         </td>
         <td>yes         </td>
      </tr>
      <tr class="odd" data-mc-conditions="">
         <th>TrustedFile (UNIX/Windows/and z/OS)</th>
         <td>no         </td>
         <td>            <p>yes</p>         </td>
      </tr>
      <tr class="even" data-mc-conditions="">
         <th>PassPort AM</th>
         <td>embedded         </td>
         <td>no (*)         </td>
      </tr>
      <tr class="odd" data-mc-conditions="">
         <th>PassPort PS</th>
         <td>no         </td>
         <td>yes         </td>
      </tr>
      <tr class="even" data-mc-conditions="">
         <th>Sentinel</th>
         <td>embedded         </td>
         <td>yes         </td>
      </tr>
      <tr class="odd" data-mc-conditions="">
         <th>Composer</th>
         <td>no         </td>
         <td>no         </td>
      </tr>
      <tr class="even" data-mc-conditions="">
         <th>Protocols</th>
         <td>         </td>
         <td>         </td>
      </tr>
      <tr class="odd" data-mc-conditions="">
         <th>PeSIT</th>
         <td>yes         </td>
         <td>yes         </td>
      </tr>
      <tr class="even" data-mc-conditions="">
         <th>ODETTE</th>
         <td>no         </td>
         <td>yes         </td>
      </tr>
      <tr class="odd" data-mc-conditions="">
         <th>SFTP <em>(UNIX, Windows)</em></th>
         <td>no         </td>
         <td>yes         </td>
      </tr>
   </tbody>
</table>

\* If you perform a migration or upgrade from a previous version, you must migrate your PassPort AM.

## <span id="Legacy"></span>Legacy flows

Legacy flows refer to former flow definitions available in migrated Transfer CFT systems. Central Governance or Flow Manager can manage the following use cases:

-   Via the Central Governance or Flow Manager user interface, you can add and manage partners, and use send and receive templates for a given Transfer CFT.
-   You can migrate Transfer CFT flow definitions to the Central Governance or Flow Manager flow-management process.
