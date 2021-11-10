{
    "title": "SWIFTNet HA user exit Configuration",
    "linkTitle": "High Availability User Exit Configuration",
    "weight": "350"
}[Prerequisites](#Prerequi)

[Enabling the SWIFTNet High Availability feature](#Enabling)

[High availability user exit load and initialization](#High)

<span id="Prerequi"></span>

## Prerequisites

The prerequisites for activating the SWIFTNet High availability feature are:

-   The High Availability Database (Oracle 11g or MySQL 5.6.5 or later) must be available. An ODBC connection to the database must be configured.
-   Each Gateway node installation from a High Availability solution must connect to SWIFT through its own SAG.
-   When installing Gateway, the High Availability option must be used.
-   Each Gateway from the High Availability environment must be assigned a unique node identifier (See [About Gateway Node ID](#About)).
-   For monitoring Gateway from Sentinel you must use the file “<span class="code">XFB\_ALL\_EN\_HA.xml</span>”, not “<span class="code">XFB\_ALL\_EN.xml</span>”, located on the installation DVD in the /<span class="code">extras/sentinel</span> folder.  
    **Note**: The difference between the two files is determined by the “<span class="code">nullMngt</span>” option, which for SWIFTNet High Availability has the value “Last”, instead of “Default”: the event updates will be done relative to the last update. In cases where you are generating the Tracking object, set the “null management” option.

> **Note:**
>
> The SWIFTNet High Availability feature requires a valid license key in order to function.

Enabling SWIFTNet High Availability without a proper license key will result in Gateway SWIFTNet processes being unable to start.

<span id="About"></span>

### About Gateway Node ID

In environments where multiple Gateways are installed, for example connected to the same back-end application, it is desirable to have unique transfer identifiers for each Gateway installation. This functionality can be enabled by assigning each Gateway a unique node identifier. By default, this functionality is disabled.

A node identifier can have values from `0` to `15`, to a total of 16 nodes. If set, the transfer identifier allocation changes as follows:

-   Transfer identifiers are no longer allocated contiguously. Instead, a new transfer identifier will be the next number multiple of 16 + the node identifier (thus incremented by 16). This ensures that each Gateway allocates its own subset of transfer identifiers.
-   There is no change for transfers already in the mailbox; so it is possible to have old transfers not conforming with the above rule. However, activating the node identifier feature should be done on a new installation.

## Setting a Gateway node identifier

The Gateway node identifier can be set using the <span class="code">peluconf </span>command:

peluconf set -s monitor node\_id &lt;node identifier>

where the node identifier ranges from 0 to 15.

There is no equivalent command to unset the node identifier; effectively, this means that once activated, the node identifier feature cannot be disabled. A Gateway can be set to a different node identifier.

Ensure that each Gateway is assigned a unique node identifier.

<span id="Enabling"></span>

## Enabling the SWIFTNet High Availability feature

You must configure global parameters before using the SWIFTNet High Availability feature. This can be partially done using the Graphical User Interface, and/or the command line configuration.

Use the following steps to enable SWIFTNet High Availability and set the paths to the HA user exit library. If not properly defined, the Gateway SWIFTNet client and server processes will be unable to start.

1.  Set the <span class="code">node\_id</span> parameter to a value between 0 and 15.
2.  In the left pane of the main window in the user interface, right-click the Gateway server to enable for High Availability and select <span class="bold_in_para">Configure</span>.  
    The Configuration window is displayed.
3.  In the left pane of the Configuration window, go to <span class="bold_in_para">Connectivity > Axway connectivity > SWIFTNet</span> and select the <span class="bold_in_para">HA</span> tab.
4.  From the **High Availability Exit** drop-down list, select `Use correlation exit ` to enable the *High Availability with User Exit* feature.  
    Alternatively, enable the High Availability feature from the command line configuration:
    1.  peluconf set -s swnet swnet\_ack\_userexit\_option 1
5.  Set the path to the High Availability User Exit library, if changed from the default.  
    Alternatively, set the path to the High Availability User Exit library from the command line configuration:
    1.  peluconf set -s swnet swnet\_ack\_userexit\_library &lt;path to the HA User Exit library>
6.  Select the database type (MYSQL or ORACLE).  
    Alternatively, select the database type from the command line configuration:
    1.  peluconf set -s swnet swnet\_ack\_userexit\_db\_type &lt;database\_type>
7.  Select the database DSN name and user.

Alternatively, select the database DSN name and user:

peluconf set -s swnet swnet\_ack\_userexit\_db\_data\_source\_name &lt;ODBC data source name>

peluconf set -s swnet swnet\_ack\_userexit\_db\_user &lt;database user>

1.  Using the <span class="code">pelencpass</span> command, set and store the database password in an encrypted storage. For details about storing an encrypted password, see the documentation for the <span class="code">pelencpass</span> command.
2.  Set the resulting password files using the command line configuration:

peluconf set -s swnet swnet\_ack\_userexit\_db\_salt\_file &lt;password salt file>

peluconf set -s swnet swnet\_ack\_userexit\_db\_dk\_file &lt;password dk file>

peluconf set -s swnet swnet\_ack\_userexit\_db\_password\_file &lt;password file>

1.  Set the path to the DB High Availability User Exit library from the command line configuration, if changed from the default:

peluconf set -s swnet swnet\_ack\_userexit\_db\_library &lt;path to the DB User Exit Library>

1.  Restart Gateway for the change in configuration to take effect.

<span id="High"></span>

## High Availability User Exit load and initialization

When the High Availability feature is enabled, SWIFTNet client and server processes load the High Availability and DB user exit libraries at Gateway startup according to the preconfigured settings.

If errors occur during High Availability or DB user exit libraries loading or initialization, the SWIFTNet processes performing the operation are terminated. Correct the errors reported in the Gateway log.

An incorrectly configured High Availability feature can prevent the SWIFTNet module from functioning.

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
