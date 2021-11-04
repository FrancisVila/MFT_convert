{
    "title": "System requirements",
    "linkTitle": "System requirements",
    "weight": "160"
}The following are the system requirements for <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span>.

## Supported operating systems and browsers

Refer to the [<span class="mc-variable axway_variables.Company_Name variable">Axway</span> S*upported Platforms Guide*](https://docs.axway.com/bundle/Axway_Products_SupportedPlatforms_allOS_en/resource/Axway_Products_SupportedPlatforms_allOS_en.pdf) for more information.

## Disk space and RAM requirements

<span class="mc-variable axway_variables.Component_Long_Name variable">Transfer CFT</span> has the following hardware requirements:

-   Disk space requirement
    -   1.5 to 5 Gigabyte: minimum disk space to allow for future updates, SPs, and continued performance
-   RAM Requirement
    -   128 Megabyte: the minimum storage space required per host

## Windows operating system prerequisites

Transfer CFT on Windows requires the **Visual C++ Redistributable Package for Visual Studio 2019** for proper functioning. This provides the necessary library files (DLL) for Transfer CFT. You must install `vc_redist.x64.exe` prior to installing or upgrading Transfer CFT.

<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Note</strong></span>         </td>
         <td>If the redistribution package is already installed on your Windows system, there is no need to reinstall.         </td>
      </tr>
   </tbody>
</table>

## Java

If you intend to implement Secure Relay, you require Java 8, which is not delivered with Transfer CFT.