{
    "title": "TARGET2 ",
    "linkTitle": "Configuring Gateway for TARGET2",
    "weight": "290"
}## Configuration overview

The <span class="mc-variable axway_variables.Solution_long_name variable">Axway Financial Exchange</span> TARGET2 package is delivered in the <span class="mc-variable axway_variables.Solution_short_name variable">FEX</span> installation package. Alternatively download it from the <span class="mc-variable axway_variables.Company_Name variable">Axway</span> Support website: [<span class="mc-variable axway_variables.Support_Web_Site variable">https://support.axway.com</span>](https://support.axway.com/ "Axway Software Technical Support website")

There are two typical contexts for TARGET2 configuration:

-   No version of TARGET2 is installed:  
    Unpack the <span class="mc-variable axway_variables.Solution_long_name variable">Axway Financial Exchange</span> TARGET2 package, and configure as required.
-   TARGET2 v1.0.1 or v1.0.2 is already installed:
    -   Delete the existing QT2 folder.
    -   Unpack TARGET2 v1.0.3 last release.
    -   Delete all objects (Trading Partners, Models, Decision Rules and Remote Sites) using the script file <span class="code">cl\_delobjCRISTAL.sh</span>
    -   Import a new set of objects from the objExports folder using the script file <span class="code">cl\_objCRISTAL.sh</span>
    -   To update a previous V103 to the latest release, download and apply the latest patch.

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
