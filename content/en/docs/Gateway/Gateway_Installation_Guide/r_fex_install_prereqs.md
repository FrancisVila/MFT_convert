{
    "title": "Installation prerequisites",
    "linkTitle": "Gateway Installation prerequisites",
    "weight": "50"
}## Gateway software prerequisites

### SWIFTNet services

Before you can use Gateway to send and receive transfers via SWIFTNet, you must:

1.  Install Gateway and SWIFTNet RA 7 (Remote API) on the same machine. This machine must comply with SWIFTNet 7 prerequisites. For the minimum patch level and details of supported platforms, go to [www.swift.com](http://www.swift.com) and select **Support**.
2.  Configure SWIFTNet RA 7 to access SAG 7 (SWIFT Alliance Gateway). RA contains the libraries that are required at runtime.
3.  In SAG, when defining a Message Partner to be used with Gateway:
    1.  In the **Type** field, select *ClientServer* as connection mode (Gateway uses both Server and Client, for instance to receive acknowledgments in Real Time)
    2.  In the **Host Adapter** field, select *Remote API Host Adapter* as message partner.
    3.  In the **Default Message Format for Emission** field, select *Strict SNL Format*.

    <!-- -->

    1.  In the **Supported Message Formats** pane, select *Strict SNL Format*. Do **not** use *Relaxed SNL Format*!
4.  Ensure that the user has the necessary rights to access RA.

<!-- -->

1.  Ensure that any DN you use in Gateway is related to a certificate defined with **strict** mode. Gateway always enforces the strict mode for any certificates it uses.

For supported platforms, refer to the *SWIFTNet documentation*.

### Perl commands on UNIX

To use Perl commands on UNIX, the following software must be installed:

-   <span class="mc-variable gateway_variables.PerlVersion variable">Perl version 5.24.0</span> 32-bit build on 32-bit UNIX deliveries or <span class="mc-variable gateway_variables.PerlVersion variable">Perl version 5.24.0</span> 64-bit build on 64-bit UNIX deliveries
-   C compiler for GIKCMDPL installation

### Perl commands on Windows

To use Perl commands on Windows, the following software must be installed:

-   Perl version 5.24.0 32-bit build for 32-bit Gateway

-   Perl version 5.24.0 64-bit build for 64-bit Gateway

### Recompiling user exits on Windows

To recompile user exits on Windows, the following software must be installed:

-   Microsoft Visual C++ 2012. To use it, you must add /D\_USE\_32BIT\_TIME\_T as a compilation flag in the makefile.

### Linux platforms

For Linux platforms, a bc package must be installed.

## Gateway RMA server prerequisites

### Preparation

-   The RMA Server must be defined inside PassPort AM, giving a Component Instance name to the RMA Server and a Shared Secret.
-   Prepare the name and password for one or two users:
    -   You may define one dedicated user to import ASP or Distribution files, and another user to be used from the User Exit, or
    -   You may choose to prepare only one user that is granted both roles.

### OS

-   Windows 2008 Server r2
-   AIX 6.1
-   Solaris 10

### JVM

Java 1.6 (installed automatically by the Axway Installer)

### Database

One of the following:

-   <span class="mc-variable suite_variables.AxwayDatabaseName variable">Axway Database</span> 4.6
-   MySQL Server 5.5 or 5.6
-   Oracle 11g

### Supporting software

#### Axway products

-   PassPort 4.6

## TARGET2 package installation prerequisites

To install the TARGET2 package you require:

-   A license key for Axway Gateway that enables InterAct/FileAct protocols and real-time/Store & Forward modes
-   An instance of the Gateway server installed with the JMS, SWIFTNet InterAct and FileAct options

The TARGET2 package is compatible with Gateway V6.11.2 Patch 10 and higher.

## SWIFTNet HA prerequisites

-   A license key that enables SWIFTNet HA
-   ODBC configured for Oracle connectivity
-   Oracle 11g

## FIPS prerequisites

• A license key that enables FIPS mode

• A non-Windows OS (FIPS support is not available on Windows platforms)

## AIX prerequisites

The uncompress utility used to install AIX must be able to handle path names that contain more than 100 characters.

This is important for AIX platforms as the default utility is not able to handle this.

<span id="Default"></span>

## Default port numbers

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Port name         </th>
<th class="HeadE-Column1-Header1">Port number         </th>
<th class="HeadD-Column1-Header1">Usage         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>Navigator Server         </td>
         <td>6390         </td>
         <td><span class="mc-variable axway_variables.prodname.Gateway_Navigator_long variable">Gateway Navigator</span>Server (GUI Server)         </td>
      </tr>
      <tr>
         <td>RMA         </td>
         <td>9696         </td>
         <td>Used by API port Gateway to communicate with RMA module         </td>
      </tr>
   </tbody>
</table>

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
