{
    "title": "Editing TARGET2 files and objects",
    "linkTitle": "Editing TARGET2 files and objects",
    "weight": "310"
}**Prerequisite:** Install the TARGET2 package as described in the *Installation Guide &gt;* <span class="italic_in_para">[Installing the TARGET2 package to Gateway](#)</span>.

Configure Axway Gateway for TARGET2 as follows:

1.  Edit the <span class="code">cl\_objCRISTAL</span> script file which is located in the directory <span class="code">qt2/objExport/</span>. In this file, set values for the following parameters that correspond to your network configuration:
    -   LOCAL\_SITE - alias of the Local Remote Site
    -   SWIFT\_REMOTE\_SITE - alias of the SWIFTNet Remote Site
    -   LOCAL\_DN
    -   COPYDIR - the directory you choose to use to locally copy the received files, in ROUTE mode
2.  Edit the <span class="code">qt2/config</span> file. In this file, set values for the following parameters:
    -   MODE
    -   FILE\_ROUTING
    -   FULLCMPENGINE (FALSE for Gateway 6.10.1 and Gateway 6.11.2 Patch &lt;10 ; TRUE for Gateway 6.11.2 Patch >=10 and later versions)
3.  Run the script <span class="code">cl\_objCRISTAL</span>.  
    This script imports the set of objects that you downloaded and unzipped on your Gateway supporting machine to Gateway.
4.  Manually configure the following Remote Site template objects:
    -   CRISTAL\_IN
    -   CRISTAL\_OUT
    -   CRISTAL\_ERR
    -   CRISTAL\_FILE

      
    For configuration details, refer to [Customizing Gateway Remote Sites for TARGET2](../t_qt2_customizeremotesites).

For a summary of the Gateway objects you manage for TARGET2, refer to [Gateway objects for TARGET2 exchanges](../c_qt2_gtwobjectlist).

For examples of configuring Gateway objects for multiple CRISTAL applications, refer to [Multiple CRISTAL configurations](../c_qt2_multi_cristalconfig).

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
