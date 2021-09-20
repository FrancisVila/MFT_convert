{
    "title": "Windows platforms",
    "linkTitle": "Windows platforms",
    "weight": "110"
}Make sure you have administrative privileges on the machine where you want to install SecureTransport Server or Edge.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">Local Administrator credentials are required to install <span>SecureTransport</span>. Installation by an LDAP user with Administrator privileges is not supported.         </td>
      </tr>
</table>

Make sure you have installed the Microsoft Visual C++ 2010 SP1 Redistributable Package (x64).

Make sure any antivirus software running on the computer is disabled during the installation. Leaving the antivirus software running can cause the install to fail.

## Supported Windows-based operating systems

All SecureTransport Servers in a cluster must run on the same operating system. All SecureTransport Edge servers that synchronize configuration must run on the same operating system. However, in a multitier security deployment, the operating system for SecureTransport Server systems can be different from the operating system for the SecureTransport Edge systems.

SecureTransport is a 64-bit application.

For a full list of supported Windows-based operating systems and updates, refer to [*Axway and third-party software support*](https://docs.axway.com/bundle/SecureTransport_55_AdministratorGuide_allOS_en_HTML5/page/Content/AdministratorsGuide/introduction/r_st_Axway_and_third-party_software_support.htm) .

For virtual platforms, refer to [Virtualization support](../virtualization_support).

## Minimum Windows hardware requirements

SecureTransport requires an x86\_64 processor with 2 cores and 8 GB RAM.
