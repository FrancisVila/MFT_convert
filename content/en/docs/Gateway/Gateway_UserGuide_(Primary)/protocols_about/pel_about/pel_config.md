{
    "title": "Configuring Gateway for PEL",
    "linkTitle": "Configuring for PEL",
    "weight": "210"
}{{< Gateway/componentlongname  >}}: Protocols

[About PEL configuration](#About_the_PEL_configuration)

[Creating Site objects](#Creating_Site_objects)

[Creating an Application](#Creating_an_Application)

<span id="About_the_PEL_configuration"></span>

## About PEL configuration

Before submitting a Transfer Request, you must create the following Gateway objects if they do not already exist:

-   **Local Site**  
    On installation, you must create a Local Site corresponding to the <span class="code">local\_site\_alias</span> and <span class="code">local\_site\_proto\_ident</span> parameters in the configuration file <span class="code">&lt;Gateway installation directory>/run\_time/etc/conffile</span>. This is the only Local Site that you can use with the PEL protocol.
-   <span style="font-weight: bold;">Remote Site</span>  
    Define as many Remote Sites as needed.
-   <span style="font-weight: bold;">Application</span>  
    Define at least one Application.

You can use either the GUI or the<span class="code" style="font-weight: bold;"> peladm</span> online command to create these objects.

<span id="Creating_Site_objects"></span>

## Creating Site objects

The following examples describe how to create Gateway Site objects using the<span class="code" style="font-weight: bold;"> peladm</span> online command. If you do not supply attributes explicitly, Gateway uses either default values from the operator interface or from Gateway internal default attributes.

Certain platforms may require non-default values for some optional parameters. Refer to platform-specific documentation for more information.

#### Example 1: Local Site locpel

peladm create\_loc\_site  -alias locpel

   -comments "Local Site"

If you do not specify a group for the Remote Site that you create, the Site uses the default group <span style="font-style: italic;">GDEFAULT</span>.

#### Example 3: Remote Site using TCP/IP

The following command creates a Remote Site with the following attributes:

-   IP address: 193.56.234.20
-   port number: 22222
-   block size: 4000
-   number of data blocks between two acknowledgments: 5
-   maximum number of simultaneous server connections: 10

peladm create\_site  -alias tpelpc

   -protocol PEL

   -comments "Remote Site: PEL on TCP/IP"

   -comm\_type TCP

   -dest\_address 193.56.234.20/22222

   -data\_size\_max 4000

   -check\_window 5

  <span style="font-weight: bold;"> -resp\_conn\_max 10</span>

<span id="Creating_an_Application"></span>

## Creating an Application

The following example creates an Application object using the<span class="code" style="font-weight: bold;"> peladm</span> online command. If you do not supply attributes explicitly, Gateway uses either default values from the operator interface or from Gateway internal default attributes.

<span style="font-weight: bold;">Note:</span> For the PEL LOTS command specifically, the Application name is limited to four characters, instead of the standard eight.

#### Example

peladm create\_appli  -alias  fix255

   -comments "pelapplication"

 

Related topics

[About PEL](../)

[Submitting a PEL Transfer Request](../pel_submitting_transfer)

[Working with Local Sites](../../../managing_partners_start_here/sites_start_here/managing_local_sites)

[Working with Local Sites (command line)](../../../managing_partners_start_here/sites_start_here/managing_local_sites_cli)

[Working with Remote Sites](../../../managing_partners_start_here/sites_start_here/managing_remote_sites)

[Working with Remote Sites (command line)](../../../managing_partners_start_here/sites_start_here/managing_local_sites_cli/managing_remote_sites_cli)

[Working with Applications](../../../transfers_start_here/parameters_start_here/applications_start_here/working_with_applications_(gui))

[Working with Applications (command line)](../../../transfers_start_here/parameters_start_here/applications_start_here/working_with_applications_cli)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
