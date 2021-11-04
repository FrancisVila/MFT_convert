{
    "title": "Post installation",
    "linkTitle": "Post installation",
    "weight": "130"
}After installing Transfer CFT, but before starting Transfer CFT and the Copilot server, you may need to perform the following tasks:

-   [Perform an update](#updates)
-   [Create a basic configuration](#Creating_a_basic_configuration)

Otherwise you can go to:

-   <a href="#Start" class="MCXref xref">Start the Transfer CFT Copilot server</a>
-   <a href="#Start2" class="MCXref xref">Start Transfer CFT</a>

For information on user rights, refer to the topic [Defining user rights UNIX](#).

## Installed directories and files

When you install Transfer CFT, the <span class="code">home</span> directory is created and populated under the <span class="code">Transfer\_CFT</span> installation directory. This <span class="code">home </span>directory contains installation libraries, binaries, and templates. Do not store any personal files in the <span class="code">home </span>directory, as they are erased during updates.

### Installer-generated files

During the installation, the Transfer CFT installer creates two files in the installation directory that are working files for the installer. Do not modify these files unless instructed to do so by Axway. While they are not used for Transfer CFT operations, they are necessary for installer functions such as upgrades.

-   .rundir
-   .transfer\_cft.properties

## Standalone installations

If you are not using <span class="mc-variable suite_variables.TransferCFTName variable">Transfer CFT</span> with <span class="mc-variable suite_variables.Central_GovernanceName variable">Central Governance</span>, you must provide a certificate in order to be able to use the <span class="mc-variable suite_variables.TransferCFTName variable">Transfer CFT</span> UI. See [Using the web-based browser UI](../../../c_intro_userinterfaces/web_copilot_ui#Connect2) page for details.

<span id="updates"></span>

## Perform an update

If you need to apply service packs or patches, refer to Update <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span>.

If you have already started Transfer CFT or Copilot, stop these servers prior to performing an update.

<span id="Creating_a_basic_configuration"></span>

## Create a basic configuration

This section describes how to create a basic Transfer CFT configuration
if you did not do so during the installation process. If you started Transfer CFT or Copilot, stop these servers before modifying the configuration.

### Update the profile

To add environment variables to your Transfer CFT profile
edit the following script:

-   Windows: <span class="code"> &lt;CFTDIRRUNTIME>\\profile.bat</span>
-   UNIX: <span class="code">./&lt;CFTDIRRUNTIME>/profile</span>

### UCONF

To determine the Transfer CFT variable values list the values using
the command:


    CFTUTIL listuconf

To change or update a value, start the Transfer CFT profile
and make modifications using either the Transfer CFT Copilot UI or command line UCONF tools. Refer to Transfer
CFT online
documentation for details.

For example, to change the user interface port:


    CFTUTIL 
     uconfset id=copilot.general.serverport,value=1766

### Configuration

Before you can start Transfer CFT for the first time, Transfer CFT must
have a basic configuration. Typically this is created during installation or migration.

### License key

If you did not enter the license key during installation, you can enter it post installation in the cft.key file located in: <span class="code">&lt;CFTDIRRUNTIME>/conf/</span>

You can enter a single key or a list of keys in this file. In the configuration default
file, the variable <span class="code">&lt;$CFTKEY></span> represents the <span class="code">cft.key</span> file.

### <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> internal datafile and configuration

Check the values, especially the key value, hostname, and port for TCP,
in the following file:

-   Windows and UNIX: <span class="code">&lt;CFTRUNTIME>/conf/cft-tcp.conf
    </span>

Start the Transfer CFT profile and, to create the Transfer CFT
internal datafile and update the basic configuration, execute:


    cftinit 
     cft-tcp.conf

To update the configuration at a later date, execute:


    cftupdate 
     cft-tcp.conf

### User interface configuration

To view the Copilot user interface configuration, execute:


    CFTUTIL 
     LISTUCONF id=copilot*

To change this configuration, you update the hostname and listening
port for Transfer CFT UI using CFTUTIL
<span class="code">uconfset</span>.

**Example**


    CFTUTIL 
     uconfset id=copilot.general.serverhost, value="127.0.0.1"CFTUTIL 
     uconfset id=copilot.general.serverport, value="7000"

### Configuration for Service Mode

This option is only available on Windows systems and must be selected during the installation process configuration.

<span id="Start"></span>

## Start the Transfer CFT Copilot server

If you have implemented <span class="mc-variable Primary.CG or_UM variable">Central Governance</span>, starting Copilot launches the registration process. For more information, see the topic <a href="../../../governance_services_intro/cg_register_overview" class="MCXref xref">Registration overview</a>.

**Windows**

1.  Change directory to the runtime.
2.  Execute profile.bat.
3.  To start the Copilot server, enter: copstart
4.  To check the Copilot status, enter: copstatus -v

**UNIX**



    cd <CFTDIRRUNTIME>
    . . /profile
    copstart
    http://myHostName:1766

<span id="Start2"></span>

## Start Transfer CFT

If you have implemented <span class="mc-variable Primary.CG or_UM variable">Central Governance</span>, you can start and stop Transfer CFT via the Central <span class="mc-variable suite_variables.Governance variable">Unified Flow Management</span> user interface. Otherwise perform the following command from the Transfer CFT runtime directory.

Enter:


     cft start

<span id="Service"></span>

## Service mode set up when using <span class="mc-variable Primary.CG or_UM variable">Central Governance</span>

Since you can start or restart a registered <span class="mc-variable axway_variables.Component_Long_Name variable">Transfer CFT</span> from <span class="mc-variable Primary.CG or_UM variable">Central Governance</span>, when using service mode you must set the **CFT UI service** account so that it can start the **CFT service**. Therefore, perform one of the following two tasks:

-   Add the account to the CFT server's **Local Administrator Group**, or
-   Provide the rights to start the Transfer CFT Service as a non Local Admin user:
    -   Use a Sysinternals utility such as Process Explorer to change Windows service permissions. Run Process Explorer as administrator and locate the CFT service (CFTSRVLD.exe) process.
    -   Open the process properties and click the **Services** tab. Click the **Permissions** button and add the user or group in the opened window. Then select the permissions that you want to assign (Full Control) and click **OK** to save.
    -   <img src="/Images/TransferCFT/services_rights.png" class="mediumWidth" />

## Register with <span class="mc-variable Primary.CG or_UM variable">Central Governance</span>

If you intend to implement <span class="mc-variable Primary.CG or_UM variable">Central Governance</span>, please refer to the <span class="mc-variable axway_variables.Component_Long_Name variable" style="font-style: italic;">Transfer CFT</span> *User's Guide &gt; [*Register with* <span class="mc-variable Primary.CG or_UM variable" style="font-style: italic;">Central Governance</span>](https://docs.axway.com/bundle/TransferCFT_36_UsersGuide_allOS_en_HTML5/page/Content/cft_installation/migrate/register_CG.htm)* page for registration details.