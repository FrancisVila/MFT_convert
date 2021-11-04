{
    "title": "About governance services",
    "linkTitle": "About governance services",
    "weight": "160"
}In this guide, *flow* refers to the complete interaction between the source and target applications, more specifically Transfer CFT systems, to enable data exchanges between business applications or partners.

## Managed File Transfer services

Managed File Transfer services, using a blend of Axway products, can centralize flow definition and configuration deployment for <span class="mc-variable axway_variables.Component_Long_Name variable">Transfer CFT</span> (file transfer) engines.

You can use Central Governance in your MFT architecture to easily create and deploy flows. You then trigger your flows at the system level.

<img src="/Images/TransferCFT/data_exchange_env.png" class="maxWidth" alt="Multiple Transfer CFTs can send events from the data exchange environment towards Central Governance" />

<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Note</strong></span>         </td>
         <td>Connectivity may include connection to other or third-party products that are outside of the MFT reference solution.         </td>
      </tr>
   </tbody>
</table>

### Additional documentation

-   <span class="mc-variable axway_variables.Platform_or_Suite_Long_Name variable">AMPLIFY</span> Supported Platforms
-   <span class="mc-variable suite_variables.Central_GovernanceName variable">Central Governance</span> documentation
-   <span class="mc-variable suite_variables.FlowManager variable">Flow Manager</span> documentation

## Governance exchanges

The following types of exchanges occur between <span class="mc-variable suite_variables.Central_GovernanceName variable">Central Governance</span> or <span class="mc-variable suite_variables.FlowManager variable">Flow Manager</span> and the managed Transfer CFTs:

-   Flow management
-   Certificate management
-   Configuration management
-   Update management

See [Exchanges with Central Governance](../cg_postregister) for more information.

## Overview and practical considerations

Begin by planning your MFT architecture and deployment strategy. After installing <span class="mc-variable suite_variables.Central_GovernanceName variable">Central Governance</span> or <span class="mc-variable suite_variables.FlowManager variable">Flow Manager</span>, the following steps occur:

-   In the <span class="mc-variable axway_variables.Component_Long_Name variable">Transfer CFT</span> installation select the Central Governance connectivity option
-   After installing, start the Transfer CFT Copilot server (the Transfer CFT server can be running, but this is optional)
-   Registration occurs automatically on Copilot start up
-   From <span class="mc-variable suite_variables.Central_GovernanceName variable">Central Governance</span> or <span class="mc-variable suite_variables.FlowManager variable">Flow Manager</span> start the Transfer CFT(s)
-   If you migrated or upgraded, you may want to reference the following sections:
    -   [Manually activate Central Governance connectivity](../register_cg)
    -   Parameter mapping between products

<span id="Feature"></span>

## Feature support and management

Transfer CFTs running under <span class="mc-variable suite_variables.Central_GovernanceName variable">Central Governance</span> or <span class="mc-variable suite_variables.FlowManager variable">Flow Manager</span> can manage or have support for the following features.

<table>
   <th>
      <tr>
<th>Feature         </th>
<th> Manage using <span class="mc-variable suite_variables.FlowManager variable">Flow Manager</span> or <span class="mc-variable Primary.CG or_UM variable">Central Governance</span>         </th>
<th>Supported but not configurable using Central Governance or <span class="mc-variable suite_variables.FlowManager variable">Flow Manager</span>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
<th>Folder monitoring         </th>
         <td>yes         </td>
         <td>yes         </td>
      </tr>
      <tr>
<th>Multi-node architecture         </th>
         <td>no         </td>
         <td>yes         </td>
      </tr>
      <tr>
<th>CRONJOB         </th>
         <td>yes         </td>
         <td>yes         </td>
      </tr>
      <tr>
<th>Exits         </th>
         <td>no         </td>
         <td>yes         </td>
      </tr>
      <tr>
<th>Network and protocol features         </th>
         <td>         </td>
         <td>         </td>
      </tr>
      <tr>
<th>IPv6         </th>
         <td>yes         </td>
         <td>yes         </td>
      </tr>
      <tr>
<th>pTCP (UNIX/Windows only)         </th>
         <td>yes         </td>
         <td>yes         </td>
      </tr>
      <tr>
<th>UDT (UNIX/Windows only)         </th>
         <td>yes         </td>
         <td>yes         </td>
      </tr>
      <tr>
<th>SOCKS         </th>
         <td>no         </td>
         <td>yes         </td>
      </tr>
      <tr>
<th>Heartbeat         </th>
         <td>embedded         </td>
         <td>yes         </td>
      </tr>
      <tr>
<th>Interoperability         </th>
         <td>         </td>
         <td>         </td>
      </tr>
      <tr>
<th>Secure Relay         </th>
         <td>no         </td>
         <td>yes         </td>
      </tr>
      <tr>
<th>TrustedFile (UNIX/Windows/and z/OS)         </th>
         <td>no         </td>
         <td><p>yes</p>         </td>
      </tr>
      <tr>
<th>PassPort AM         </th>
         <td>embedded         </td>
         <td>no (*)         </td>
      </tr>
      <tr>
<th>PassPort PS         </th>
         <td>no         </td>
         <td>yes         </td>
      </tr>
      <tr>
<th>Sentinel         </th>
         <td>embedded         </td>
         <td>yes         </td>
      </tr>
      <tr>
<th>Composer         </th>
         <td>no         </td>
         <td>no         </td>
      </tr>
      <tr>
<th>Protocols         </th>
         <td>         </td>
         <td>         </td>
      </tr>
      <tr>
<th>PeSIT         </th>
         <td>yes         </td>
         <td>yes         </td>
      </tr>
      <tr>
<th>ODETTE         </th>
         <td>no         </td>
         <td>yes         </td>
      </tr>
      <tr>
<th>SFTP <em>(UNIX, Windows)</em>         </th>
         <td>no         </td>
         <td>yes         </td>
      </tr>
   </tbody>
</table>

\* If you perform a migration or upgrade from a previous version, you must migrate your PassPort AM.

<span id="Legacy"></span>

## Legacy flows

Legacy flows refer to former flow definitions available in migrated <span class="mc-variable axway_variables.Component_Long_Name variable">Transfer CFT</span> systems. Central Governance or <span class="mc-variable suite_variables.FlowManager variable">Flow Manager</span> can manage the following use cases:

-   Via the Central Governance or <span class="mc-variable suite_variables.FlowManager variable">Flow Manager</span> user interface, you can add and manage partners, and use send and receive templates for a given Transfer CFT.
-   You can migrate Transfer CFT flow definitions to the Central Governance or <span class="mc-variable suite_variables.FlowManager variable">Flow Manager</span> flow-management process.
