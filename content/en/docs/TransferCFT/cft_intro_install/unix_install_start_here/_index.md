{
    "title": "Installation and operation UNIX",
    "linkTitle": "Installation and operation UNIX",
    "weight": "90"
}# <span id="UNIX_operations__Start_here"></span> UNIX: Installation and operation

This section introduces prerequisite information as well as installation and information on operating Transfer CFT in UNIX.

The information in this section
may be supplemented, corrected, or even contradicted by the
README.TXT file or the Release Notes supplied with the product. The README.TXT file and Release Notes take priority in this case.

## <span id="Product_presentation"></span>Product presentation

Transfer CFT can operate both as client and/or as server. The
number of simultaneous transfers that Transfer CFT can support
is defined by the license key. It is also limited by the properties of
the networks used. The TCP/IP network is supported.

## Installing Transfer CFT for Unix

The installation section describes prerequisites and how to install, migrate, update and uninstalTransfer CFT.

-   [Prerequisites](before_you_start_unix/prereqs_overview)
-   [Start the installation](../windows_install_start_here/before_you_start_win/install_transfer_cft_1)

## UNIX operations

-   [Transfer CFT
    UNIX utilities](run_first_time_ux/use_cft_utilities)
-   [Running
    Transfer CFT for the first time](running_cft_for_the_first_time_unix.htm)
-   [Building
    Transfer CFT API applications](run_first_time_ux/api_applications_start_here)
-   [Activating
    security](run_first_time_ux/run_first_time_ux/user_rights_and_interface_unix)
-   [Specific
    configurations](run_first_time_ux/aix_with_ibm_hacmp_intro/specific_configurations_intro)

## UNIX high availability

When installing a cluster for high availability, after enabling the cluster option you must set the multi-node option to NO.

-   [Using
    AIX with IBM](run_first_time_ux/aix_with_ibm_hacmp_intro)
-   [Solaris
    Sun cluster](run_first_time_ux/aix_with_ibm_hacmp_intro/solaris_sun_cluster_start_here)

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">The term 
  <span>Transfer CFT</span> is used to designate the Transfer 
 CFT software package on UNIX platforms.         </td>
      </tr>
</table>

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">Transfer CFT supports all POSIX file systems.          </td>
      </tr>
</table>

## Installation schematic overview

Standalone installation

![](install_multi.png)

Multi-node installation

![](install_multi.png)
