{
    "title": "UNIX: Installation and operation",
    "linkTitle": "Installation and operation UNIX",
    "weight": "90"
}This section introduces prerequisite information as well as installation and information on operating Transfer CFT in UNIX.

The information in this section
may be supplemented, corrected, or even contradicted by the
README.TXT file or the Release Notes supplied with the product. The README.TXT file and Release Notes take priority in this case.

<span id="Product_presentation"></span>

## Product presentation

<span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> can operate both as client and/or as server. The
number of simultaneous transfers that <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> can support
is defined by the license key. It is also limited by the properties of
the networks used. The TCP/IP network is supported.

## Installing <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> for Unix

The installation section describes prerequisites and how to install, migrate, update and uninstal<span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span>.

-   [Prerequisites](before_you_start_unix/prereqs_overview)
-   [Start the installation](../windows_install_start_here/before_you_start_win/install_transfer_cft_1)

## UNIX operations

-   [<span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span>
    UNIX utilities](run_first_time_ux/use_cft_utilities)
-   Running
    <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> for the first time
-   [Building
    <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> API applications](run_first_time_ux/api_applications_start_here)
-   [Activating
    security](#)
-   [Specific
    configurations](run_first_time_ux/aix_with_ibm_hacmp_intro/specific_configurations_intro)

## UNIX high availability

When installing a cluster for high availability, after enabling the cluster option you must set the multi-node option to NO.

-   [Using
    AIX with IBM](run_first_time_ux/aix_with_ibm_hacmp_intro)
-   [Solaris
    Sun cluster](run_first_time_ux/aix_with_ibm_hacmp_intro/solaris_sun_cluster_start_here)

<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Note</strong></span>         </td>
         <td>The term
<span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> is used to designate the Transfer
CFT software package on UNIX platforms.         </td>
      </tr>
   </tbody>
</table>

<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Note</strong></span>         </td>
         <td>Transfer CFT supports all POSIX file systems.         </td>
      </tr>
   </tbody>
</table>

## Installation schematic overview

Standalone installation

![](/Images/TransferCFT/install01_(2).png)

Multi-node installation

![](/Images/TransferCFT/install_multi.png)
