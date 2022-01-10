{
    "title": "About governance services",
    "linkTitle": "About governance services",
    "weight": "160"
}In this guide, *flow* refers to the complete interaction between the source and target applications, more specifically Transfer CFT systems, to enable data exchanges between business applications or partners.

## Managed File Transfer services

Managed File Transfer services, using a blend of Axway products, can centralize flow definition and configuration deployment for {{< TransferCFT/componentlongname  >}} (file transfer) engines.

You can use Central Governance in your MFT architecture to easily create and deploy flows. You then trigger your flows at the system level.

![$2]($1)

> **Note**
>
> Connectivity may include connection to other or third-party products that are outside of the MFT reference solution.

### Additional documentation

- {{< TransferCFT/platformorsuitelongname >}} Supported Platforms
- {{< TransferCFT/centralgovernancename >}} documentation
- {{< TransferCFT/flowmanager >}} documentation

## Governance exchanges

The following types of exchanges occur between {{< TransferCFT/centralgovernancename  >}} or {{< TransferCFT/flowmanager  >}} and the managed Transfer CFTs:

- Flow management
- Certificate management
- Configuration management
- Update management

See [Exchanges with Central Governance](../cg_postregister) for more information.

## Overview and practical considerations

Begin by planning your MFT architecture and deployment strategy. After installing {{< TransferCFT/centralgovernancename  >}} or {{< TransferCFT/flowmanager  >}}, the following steps occur:

- In the {{< TransferCFT/componentlongname >}} installation select the Central Governance connectivity option
- After installing, start the Transfer CFT Copilot server (the Transfer CFT server can be running, but this is optional)
- Registration occurs automatically on Copilot start up
- From {{< TransferCFT/centralgovernancename >}} or {{< TransferCFT/flowmanager >}} start the Transfer CFT(s)
- If you migrated or upgraded, you may want to reference the following sections:
    -   [Manually activate Central Governance connectivity](../register_cg)
    -   Parameter mapping between products

<span id="Feature"></span>

## Feature support and management

Transfer CFTs running under {{< TransferCFT/centralgovernancename  >}} or {{< TransferCFT/flowmanager  >}} can manage or have support for the following features.


| Feature  |  Manage using {{< TransferCFT/flowmanager  >}} or  | Supported but not configurable using Central Governance or {{< TransferCFT/flowmanager  >}}  |
| --- | --- | --- |
| Folder monitoring  | yes  | yes  |
| Multi-node architecture  | no  | yes  |
| CRONJOB  | yes  | yes  |
| Exits  | no  | yes  |
| Network and protocol features  |   |   |
| IPv6  | yes  | yes  |
| pTCP (UNIX/Windows only)  | yes  | yes  |
| UDT (UNIX/Windows only)  | yes  | yes  |
| SOCKS  | no  | yes  |
| Heartbeat  | embedded  | yes  |
| Interoperability &lt;/th&gt;  |   |   |
| Secure Relay  | no  | yes  |
| TrustedFile (UNIX/Windows/and z/OS)  | no  | yes |
| PassPort AM  | embedded  | no (*)  |
| PassPort PS  | no  | yes  |
| Sentinel  | embedded  | yes  |
| Composer  | no  | no  |
| Protocols &lt;/th&gt;  |   |   |
| PeSIT  | yes  | yes  |
| ODETTE  | no  | yes  |
| SFTP *(UNIX, Windows)*  | no  | yes  |


\* If you perform a migration or upgrade from a previous version, you must migrate your PassPort AM.

<span id="Legacy"></span>

## Legacy flows

Legacy flows refer to former flow definitions available in migrated {{< TransferCFT/componentlongname  >}} systems. Central Governance or {{< TransferCFT/flowmanager  >}} can manage the following use cases:

- Via the Central Governance or {{< TransferCFT/flowmanager >}} user interface, you can add and manage partners, and use send and receive templates for a given Transfer CFT.
- You can migrate Transfer CFT flow definitions to the Central Governance or {{< TransferCFT/flowmanager >}} flow-management process.
