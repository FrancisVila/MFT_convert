{
    "title": "Log files",
    "linkTitle": "Managing Logs",
    "weight": "210"
}{{< Gateway/componentlongname  >}}: Managing Transfers

## About Log files

Gateway stores traces of all monitoring, protocol, and network events in a **Log** file. This file provides you with detailed transfer tracking information.

The Log file contains a trace of all significant events relating to transfer monitor activities and to the transfers performed. Messages contained in the Log file are time-stamped. New messages are added to the end of the file as they are generated. This enables you to view messages in chronological order, inspecting processing events step by step.

You can display the entire contents of the Log file, or use filtering criteria to view a selected subset of Log messages.

When you start Gateway, the log file is either automatically created, or reopened if it already exists. By default, Gateway creates the first Log file at:

&lt;Gateway installation directory><span style="font-weight: bold;">/run\_time/data/log.dat</span>

Once Gateway begins logging to the Log file, it continues until one of the following events occurs:

-   Gateway stops
-   You suspend logging
-   You archive the current Log file  
    When you archive a Log file, Gateway creates an archive file from the current <span class="code">log.dat</span> file by adding the archiving timestamp.  
    Gateway names the archived log file <span class="code">log.dat\_20040212\_153322</span>, where <span class="code">20040212\_153322</span> represents the date and time when the archiving was triggered.

## Working with Log files

You can work with the Log:

-   In the GUI
-   Via the Command Line Interface
-   By navigating to the log directory on your host machine, and reading the Log file in a text editor (the log is an editable text file).

Related topics

[Working with Logs](working_with_logs_(gui))

[Working with Logs (command line)](working_with_logs_cli)

[Overview: Monitoring <span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>](../../../ov_gateway/ov_monitoring_gateway)

[Monitoring Transfers](../)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
