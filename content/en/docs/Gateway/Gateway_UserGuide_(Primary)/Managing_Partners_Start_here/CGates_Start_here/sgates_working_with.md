{
    "title": "Working with SGates",
    "linkTitle": "Working with SGates",
    "weight": "210"
}{{< Gateway/componentlongname  >}}: Managing Partners

[Configuring Gateway to use SGates](#config_gw_for_sgates)

[Selecting the SGate name from Exit PCNX](#selecting_sgate_name_f_exit)

[Creating/Updating/Displaying SGates](#creating_updating_displaying_sgates)

[Upgrading existing CGates to SGates](#migrating_existing_cgates_to_sgates)

[Porting and compatibility of command scripts](#porting_and_compatibility_of_command_scripts)

<span id="config_gw_for_sgates"></span>

## Configuring Gateway to use SGates

The standard configuration of Gateway does not allow access to SGates by default.

You can force the display of SGates as follows:

1.  Go to the directory:` <Gateway installation directory>/run_time/etc`
2.  Edit the file `pelsetup.ini`. Go to the `[monitor]` section and add one of the following lines:

`xgate_gui_support=1`  to display CGates only (default mode)

`xgate_gui_support=2`  to display SGates only

`xgate_gui_support=3`  to display CGates and SGates

1.  Restart Gateway to take this parameter into account.
2.  In the configuration menu of the GUI, set the value of the **[Connection control method](../../../configuration_start_here/config_gateway_paras#connection_control_method)** parameter to Exit & SGate.

<span style="font-weight: bold;">Note:</span> You can only set the <span style="font-weight: bold;">Connection control method</span> to Exit & SGate in modes 2 (SGates only) and 3 (CGates and SGates). This option is not available in mode 1 (CGates only).

<span id="selecting_sgate_name_f_exit"></span>

## Selecting the SGate name from Exit PCNX

The SGate facility requires the SGate name to be selected by the Exit PCNX (Protocol Connection user exit ExitRcProtoConn\_C). If your application is based on <span style="font-style: italic;">best matching</span>, you must make appropriate changes for it to be based on the <span class="code">cgate\_forced</span> option.

Refer to the provided Exit PCNX C sample source for information about how to use this option.

<span id="creating_updating_displaying_sgates"></span>

## Creating/Updating/Displaying SGates

### Using online commands

All sub-commands of the <span class="code" style="font-weight: bold;">peladm</span> and <span class="code" style="font-weight: bold;">peldsp</span> online commands can operate on SGates in the same way as for CGates.

For example, to create an SGate, use the <span class="code" style="font-weight: bold;">peladm create\_sgate</span> command followed by the same argument list you would enter to create the equivalent CGate.

### Using the GUI

As the SGate is intended only to solve performance issues facing a large number of SGates, using the GUI in such a situation would be very impractical. As a result, the support of SGates from the GUI is only provided for testing purposes.

You must activate SGate support from the GUI if required, as described in [Configuring Gateway to use SGates](#config_gw_for_sgates).

<span id="migrating_existing_cgates_to_sgates"></span>

## Upgrading existing CGates to SGates

To upgrade existing CGates to SGates, perform the following steps using the <span class="code" style="font-weight: bold;">pelbase export</span> command:

1.  Export the CGateGroups to a text file.
2.  Export the CGates to a text file.
3.  Import the exported CGateGroups as SGateGroups.
4.  Import the exported CGates as SGates.

#### Example

pelbase export\_cgategroup  -f groups.txt

pelbase export\_cgate  -f gates.txt

pelbase import  -sgate\_group  -if groups.txt

pelbase import  -sgate  -if gates.txt

<span id="porting_and_compatibility_of_command_scripts"></span>

## Porting and compatibility of command scripts

Any command, or script of commands, written either in SHELL or PERL, can be ported to SGates by changing all occurrences of the word <span class="code">cgate</span> to <span class="code">sgate</span> in the sub-command fields, as long as all sub-commands are not expressed using their short form.

As such a process can be very impractical and error prone, the Gateway command interpreter has been changed in order to redirect CGate related sub-commands to the SGate equivalent sub-commands.

To activate this behavior, set the environment variable <span class="code">p\_cmd\_cgate\_to\_sgate</span> to <span class="code">1</span>.

The following example using CGate-related commands creates SGate equivalent objects (SGateGroup GFTP and SGate FTP).

export p\_cmd\_cgate\_to\_sgate=1

peladm create\_cgategroup  -n GFTP  -s E  -pr FTP  -sap "\*"  -ts TFTP

peladm create\_cgate  -n FTP  -pg GFTP  -s E  -lu user1  -lp user1 \\

-rd "/rfd"  -hd "/rfd"  -vr "/rfd:\*:R:L:Y;/rfd:\*:DRW:LCR:Y"

An environment variable has been chosen rather than a configuration variable in order to allow any combination of the two ways of dealing with CGate/SGate compatibility issues. It allows full user control of the behavior of SHELL or PERL scripts operating on CGates, either running locally (machine running Gateway) or remotely (through the Client API or online commands).

<span style="font-weight: bold;">Note:</span> The <span class="code">p\_cmd\_cgate\_to\_sgate</span> environment variable has no effect on the <span class="code" style="font-weight: bold;">pelbase</span> command, called either from SHELL or from PERL.

Related topics

[About SGates](../sgates_about)

[Working with CGates (command line)](../working_with_cgates_cli)

[Working with CGateGroups (command line)](../working_with_cgates_cli/working_with_cgategroups_cli)

[CGates and CGateGroups: Parameters List](../working_with_cgates_cli/cgates_parameter_list)

[About CGates and CGateGroups](../)

[Overview: Connection Gates](../../../ov_gateway/ov_connection_gates)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
