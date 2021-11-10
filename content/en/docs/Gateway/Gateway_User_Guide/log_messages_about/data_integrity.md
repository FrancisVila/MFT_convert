{
    "title": "Payload integrity",
    "linkTitle": "Payload integrity",
    "weight": "340"
}  

## Diagnostic codes

Diagnostic codes related to data integrity, that are set as <span class="code">last\_end\_diag </span>on transfers failed due to data integrity errors:

-   0 No error
-   1 Failed to load signature information
-   2 Failed to save signature information
-   3 Failed to verify payload signature
-   4 Failed to build payload signature

## Errors

Errors reported by the data integrity helper process:

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="AMT522E"></span>100</p>         </td>
         <td><p><span style="font-weight: bold;">INT E KEYERR Couldn't load key from file '%1'</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Either the private key file or the public key file could not be loaded.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td>Path to the file the helper attempted to load         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td>Check that the file contains a rsa key in pem format. In case the file is password protected, make sure the password file is generated an the configuration points to it.         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="AMT522E"></span>101</p>         </td>
         <td><p><span style="font-weight: bold;">INT W NOCONF Missing configuration entry '%1'</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td>Warning         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td>Missing value for a configuration parameter         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td>The name of the parameter that is undefined         </td>
      </tr>
   </tbody>
</table>

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
