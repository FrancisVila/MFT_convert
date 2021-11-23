{
    "title": "TARGET2 ",
    "linkTitle": "Configuring Gateway for TARGET2",
    "weight": "300"
}## Configuration overview

The {{< Gateway/solutionlongname  >}} TARGET2 package is delivered in the {{< Gateway/solutionshortname  >}} installation package. Alternatively download it from the {{< Gateway/companyname  >}} Support website: [{{< Gateway/supportwebsite  >}}](https://support.axway.com/ "Axway Software Technical Support website")

There are two typical contexts for TARGET2 configuration:

-   No version of TARGET2 is installed:  
    Unpack the {{< Gateway/solutionlongname >}} TARGET2 package, and configure as required.
-   TARGET2 v1.0.1 or v1.0.2 is already installed:
    -   Delete the existing QT2 folder.
    -   Unpack TARGET2 v1.0.3 last release.
    -   Delete all objects (Trading Partners, Models, Decision Rules and Remote Sites) using the script file `cl_delobjCRISTAL.sh`
    -   Import a new set of objects from the objExports folder using the script file `cl_objCRISTAL.sh`
    -   To update a previous V103 to the latest release, download and apply the latest patch.

 

Links to documentation set for Axway Gateway {{< Gateway/releasenumber  >}}:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
