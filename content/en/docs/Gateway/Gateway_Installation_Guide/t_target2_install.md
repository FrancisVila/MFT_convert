{
    "title": "Installing the TARGET2 package to Gateway",
    "linkTitle": "Installing the TARGET2 package to Gateway",
    "weight": "100"
}TARGET2 is the European Real Time Gross Settlement (RTGS) system which, since November 2007, replaces the TARGET system. TARGET2 is based on the Single Shared Platform (SSP), developed by Banca d’Italia, Banque de France, and Deutsche Bundesbank. These three banks operate the system on behalf of the Eurosystem. TARGET2 participants access the SSP using the SWIFT messaging services: FIN, FIN Copy, InterAct, FileAct and Browse.

## Locating the package

The files you require to configure Axway Gateway for TARGET2 are contained in the {{< Gateway/solutionlongname  >}} TARGET2 package. This package is included in the {{< Gateway/solutionshortname  >}} installation package. Alternatively you can request a copy of the package from your Axway representative.

Packages are available for the following platforms:

-   AIX
-   SUN
-   WIN 32bits

## Prerequisites

To install the TARGET2 package you require:

-   A license key for Axway Gateway that enables InterAct/FileAct protocols and real-time/Store & Forward modes
-   An instance of the Gateway server installed with the JMS, SWIFTNet InterAct and FileAct options
-   That the TARGET2 package is compatible with Gateway V6.11.2 Patch 10 and higher.

## Installing the package

1.  From the installation package, copy the compressed file contained in the directory:  
    `\Gateway\run_time\qt2\qt2_<version>_<OS>\Programs`
2.  On the machine that supports Gateway, uncompress the file to the Gateway installation directory.  
    If you prefer, you can unpack the package in another location without additional configuration.
3.  In the installation package, go to the directory:  
    `\Software\QT2\qt2_<version>_<OS>\Patches` and install the patch for your platform.

## Directory structure

After you unpack the package, the `qt2` folder should contain the following sub-folders and files:

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Subfolder or file         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>/objExports</p>         </td>
         <td><ul>
<li>Scripts for creating the required Target2 objects in Gateway</li>
<li>cl_delobjCRISTAL (contains command line to delete objects)</li>
<li>cl_objCRISTAL (contains command line to create objects)</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>/patch</p>         </td>
         <td><p>This folder is empty before installing a patch or a service pack. While installing a patch it may contain all files that relate to the delivered patch, as well as a subdirectory backup:</p>
<ul>
<li>backup</li>
<li>log.txt</li>
<li>archive: xxx-QT2-103-SP-2.zip</li>
<li>signature: xxx-QT2-103-SP-2.md5</li>
<li>text: xxx-QT2-103-SP-2.txt</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>/scripts</p>         </td>
         <td><ul>
<li>tg2msg (processing scripts for the SSP messages)</li>
<li>tg2file (processing scripts for SSP messages)</li>
<li>ssp_pull_s (SSP simulation script)</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>/tg2</p>         </td>
         <td><p>xslt transformation sheets for the XML message processing:</p>
<ul>
<li>tg2code.xsl</li>
<li>tg2copy.xsl</li>
<li>tg2retry.xsl</li>
<li>tg2strip.xsl</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>/tmp</p>         </td>
         <td><ul>
<li>sample.trace</li>
<li>Repository for temporary files created during QT2 processing</li>
<li>Location of the trace files (Location of generated trace files)</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>/tools</p>         </td>
         <td><p>Binaries and libraries (aupdate, Xalan, gzip, base64…)</p>         </td>
      </tr>
      <tr>
         <td><p>/xml</p>         </td>
         <td><p>Sample XML payloads used in the Simulation Mode</p>         </td>
      </tr>
      <tr>
         <td><p>aupver</p>         </td>
         <td><p>Text file containing the version information</p>         </td>
      </tr>
      <tr>
         <td><p>config</p>         </td>
         <td><p>QT2 configuration file</p>         </td>
      </tr>
   </tbody>
</table>

## Attributing UNIX execution rights

On UNIX platforms, you must give execution rights to the QT2 folder and its contents so that the scripts can be executed. Run the following command:

chmod -Rf u+x \*…

Links to documentation set for Axway Gateway {{< Gateway/releasenumber  >}}:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
