{
    "title": "Submitting an SFTP Transfer Request",
    "linkTitle": "Submitting an SFTP Transfer Request",
    "weight": "260"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Protocols

<span id="Defining_the_remote_file_location"></span>

## Defining the remote file location

In Initiator mode, the Transfer Request <span class="code">dir\_name</span> parameter defines the location of a remote file. This location represents the file destination for an outgoing transfer, or the path for an incoming transfer.

In UNIX and Windows, this parameter typically indicates a path. However, since a remote FTP server does not manage files with a hierarchical file system, or file separators, the FTP server can only concatenate <span class="code">dir\_name</span> and <span class="code">file\_name</span> providing no further analysis of the two strings.

#### Example

The following transfer command sends the file named <span class="code">file</span> to directory <span class="code">dir1</span>.

peltrans  –mode I  –direction O  –dest\_alias SFTP\_SERVER  –appli FTP\_B

          –file\_component local\_file  –dir\_name /dir1/  -file\_name file

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
