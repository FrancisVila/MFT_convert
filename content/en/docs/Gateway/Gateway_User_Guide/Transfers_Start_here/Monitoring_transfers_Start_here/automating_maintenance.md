{
    "title": "Automating maintenance operations",
    "linkTitle": "Automating maintenance operations",
    "weight": "190"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Managing Transfers

[About Automating maintenance operations](#About)

[Setting up automatic Log file archiving](#auto_log_file_archiving)

[Setting up automatic Statistic file archiving](#auto_statistics_file_archiving)

<span id="About"></span>

## About Automating maintenance operations

You can use automatic maintenance to enable Gateway to run without interruption while archiving production data in Log or Statistics files. You use date/time periodic cycle and volumetric criteria to program the frequency of automatic maintenance tasks.

<span id="auto_log_file_archiving"></span>

## Setting up automatic Log file archiving

### About automatic Log file archiving

You can configure automatic archiving of the log file depending on one of the following criteria that you define in the configuration menu:

-   The date/time periodic cycle
-   The maximum log file size in Kbytes, defined via the configuration parameter <span style="font-weight: bold;">Threshold size</span> (<span class="code">auto\_arc\_bytes</span>)

To create an archive, Gateway uses three files:

-   File in use
-   First archive file
-   Second archive file

To archive a log file, Gateway:

1.  Renames the file in use to either archive file one or archive file two.
2.  Creates and opens a new, empty log file.
3.  Schedules the batch job defined by the configuration parameter <span class="code" style="font-weight: bold;">log\_arc\_cmdline</span>. This parameter calls the script <span class="code">arclog.sh</span> (UNIX) or <span class="code">arclog.bat</span> (Windows). As the first argument to this batch job, it passes the system pathname of the archived file. If this parameter is not set, the ExitLogArchived exit routine (synchronous routine) is called instead.

### How to set up automatic Log file archiving

To set up automatic archiving of Log files:

1.  In the left pane of the Gateway GUI, right-click the Gateway server that you want to configure and select <span style="font-weight: bold;">Configure</span>.
2.  Select <span style="font-weight: bold;">Gateway > Database > Archive</span>.
3.  Complete the [Log archive parameters](../../../configuration_start_here/config_gateway_paras#olh_gateway_database_archive):
    -   Select <span style="font-weight: bold;">Active</span>
    -   Complete <span style="font-weight: bold;">Start date</span> and <span style="font-weight: bold;">Period</span>, or complete <span style="font-weight: bold;">Threshold size</span>

    If you specify both the <span style="font-weight: bold;">Start date</span>/<span style="font-weight: bold;">Period</span> and the <span style="font-weight: bold;">Threshold size</span>, the <span style="font-weight: bold;">Start date</span>/<span style="font-weight: bold;">Period</span> is ignored and the <span style="font-weight: bold;">Threshold size</span> is used.
4.  Click <span style="font-weight: bold;">OK</span>.

<span id="auto_statistics_file_archiving"></span>

## Setting up automatic Statistics file archiving

The statistics file follows the same rules as the log file.

The configuration parameter that schedules the batch job is <span class="code">stat\_arc\_cmdline</span> rather than <span class="code">log\_arc\_cmdline</span>. This parameter calls the script <span class="code">arcstat.sh</span> (UNIX) or <span class="code">arcstat.bat</span> (Windows).

The exit routine used is ExitStatArchived instead of ExitLogArchived.

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
