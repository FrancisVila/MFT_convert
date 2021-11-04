{
    "title": "Windows platforms",
    "linkTitle": "Windows platforms",
    "weight": "110"
}Make sure you have administrative privileges on the machine where you want to install <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Server or Edge.

> **Note:**
>
> Local Administrator credentials are required to install SecureTransport. Installation by an LDAP user with Administrator privileges is not supported.

Make sure you have installed the Microsoft Visual C++ 2010 SP1 Redistributable Package (x64).

Make sure any antivirus software running on the computer is disabled during the installation. Leaving the antivirus software running can cause the install to fail.

## Supported Windows-based operating systems

All <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Servers in a cluster must run on the same operating system. All <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Edge servers that synchronize configuration must run on the same operating system. However, in a multitier security deployment, the operating system for <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Server systems can be different from the operating system for the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Edge systems.

<span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> is a 64-bit application.

For a full list of supported Windows-based operating systems and updates, refer to <a href="https://docs.axway.com/bundle/SecureTransport_55_AdministratorGuide_allOS_en_HTML5/page/Content/AdministratorsGuide/introduction/r_st_Axway_and_third-party_software_support.htm" class="MCXref xref"><em>Axway and third-party software support</em></a> .

For virtual platforms, refer to <a href="../virtualization_support#beforeinstallst_3365039947_1107263" class="MCXref xref">Virtualization support</a>.

## Minimum Windows hardware requirements

<span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> requires an x86\_64 processor with 2 cores and 8 GB RAM.
