{
    "title": "Managing .pmq files with the pmqctl command ",
    "linkTitle": "Managing .pmq files",
    "weight": "260"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Connectors

The <span class="code" style="font-weight: bold;">pmqctl</span> command is only intended for system administrators, preferably with the supervision of Axway Support.

## Introduction

The <span class="code" style="font-weight: bold;">pmqctl</span> command enables you to manage<span class="code"> .pmq</span> files used to buffer data to send to Axway Sentinel. In certain cases you may need to optimize the space allocated for these files. files. This may be necessary if, for example, Sentinel is not fed fast enough or if events are not working. You can also use this command to see if the router queue is full.

The Router process also uses an internal <span class="code">router.pmq</span> file but this is handled internally by the supervisor process.

## pmqctl usage

Enter the <span class="code" style="font-weight: bold;">pmqctl</span> command, without arguments, to display the help text:

Usage:

> pmqctl read pathname \[\[nb\_to\_read\] \[nb\_per\_sync\]\]
>
> pmqctl enlarge pathname new\_size
>
> pmqctl create pathname \[size\]
>
> pmqctl info pathname
>
> pmqctl list pathname
>
> pmqctl dump pathname

## pmqctl enlarge pathname new\_size

Use this command to specify the useful data space of the file. You can use the command when Gateway is running.

For example, enter the following command to increase the space to 10 000 000 bytes:

**pmqctl enlarge $p\_home\_dir/run\_time/data/tracker.pmq 10000000**

The resulting file size will be 10 000 256 bytes (256 bytes of meta-data are added to the file).

## pmqctl info pathname

Use this command to print out information about the file. You can use the command when Gateway is running.

Enter:

**pmqctl info pathname**

### Example of output:


    --
        signature : a1b2c3d4
    version_major : 1
    version_minor : 0
           status : 1
       reader_pid : 25945
         sequence : 1001
        sync_seqn : 1000
       read_index : 2450
      write_index : 9852
        end_index : 8000000
    --
    5 records total, 7401 bytes total

## Other commands

The following commands are supplied for diagnostic purposes. Only use them if Axway Support advises you to use them.

pmqctl create pathname \[size\]

pmqctl read pathname \[\[nb\_to\_read\] \[nb\_per\_sync\]\]

pmqctl list pathname

pmqctl dump pathname

**Warning:** Never run the<span class="code" style="font-weight: bold;"> pmqctl read</span> command against an instance of the <span class="code">tracker.pmq</span> file on a production system as it can destroy data (information is read and removed from the file).

Related topics

[About Axway Sentinel](../)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
