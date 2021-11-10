{
    "title": "Executing scripts as command lines from Decision Rules",
    "linkTitle": "Executing  scripts as command lines from Decision Rules",
    "weight": "230"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Managing Events

<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Caution  </strong></span>         </td>
         <td><strong>Please note that care should be taken when</strong> <span style="color: #8b0000;font-weight: bold;"><span class="mc-variable gateway_variables.in_Snippet_UserExitsCaution_ variable">using shell scripts</span></span><strong>, as there are some</strong> <span style="color: #8b0000;font-weight: bold;">security risks</span> <strong>involved if the custom code is not properly reviewed and security best practices are not followed. Please see the</strong> <em><strong>Security Guide &gt; Security best practices &gt; </strong><a href="/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/SecurityGuide/Security_best_practices.htm#identified_threats_and_possible_mitigations">Identified threats and possible mitigations</a></em> <strong>section for additional information.<br />
</strong>         </td>
      </tr>
   </tbody>
</table>

[UNIX platforms](#unix)

[Windows platforms](#windows)

[Advanced options](#advanced)

<span id="unix"></span>

## UNIX platforms

### Executing UNIX shell scripts

On UNIX platforms you can configure Gateway to execute a shell script as a result of a Decision Rule analysis. Do one of the following:

-   In a Rule Table:
    -   Enter <span style="font-weight: bold;">COMMAND</span> as the value for the <span class="code" style="font-weight: bold;">default\_execution\_type</span> parameter
    -   Enter the path and name of the shell script to execute in the <span class="code" style="font-weight: bold;">default\_command\_line</span> parameter
-   In a Decision Rule:
    -   Enter <span style="font-weight: bold;">COMMAND</span> as the value for the <span class="code" style="font-weight: bold;">execution\_type</span> parameter
    -   Enter the path and name of the shell script to execute in the <span class="code" style="font-weight: bold;">command\_line</span> parameter

When the execution criteria for the Decision Rule are satisfied, Gateway executes the specified shell script.

### Using environment variables

Gateway enables you to retrieve transfer characteristics through the use of environment variables.

To retrieve the value of any Gateway transfer attribute, you prefix the name of the attribute in the script with <span class="code" style="font-weight: bold;">x\_</span>. The list of available attribute variables is the same as the list of attributes for Decision Rule execution criteria and for Models.

For example, to use the values of the following transfer attributes in the shell script:

-   file\_name
-   originator
-   destination

...in the shell script, you retrieve the values by listing them in the following syntax:

$x\_file\_name, $x\_originator, $x\_destination

### Retrieving all variables

If you want to retrieve a list of every variable available for a transfer in the script, you can use a command such as:

env | grep x\_

All variable names and their values are printed in the <span class="code">Q0000x.out</span> router trace file.

### Specifying arguments

Additionally, you can specify arguments in the script command line. For example, you can enter the following shell script path and name:

&lt;Gateway installation directory>/run\_time/scripts/sample.sh var1 var2

<span class="code">var1</span> and <span class="code">var2</span> can be retrieved by using the syntax <span class="code" style="font-weight: bold;">$1</span>, <span class="code" style="font-weight: bold;">$2</span> as usual in the script.

### Sample shell script

A sample xpr shell script (<span class="code">xpr.sh</span> for UNIX, <span class="code">xpr.bat</span> for Windows) is provided with Gateway. These files are located in <span class="code">&lt;Gateway installation directory>/runtime/etc</span>.

<span id="windows"></span>

## Windows platforms

On Windows platforms you can retrieve variables in the usual way using batch files. In the batch file, use the syntax <span class="code" style="font-weight: bold;">%x\_param%</span> or <span class="code" style="font-weight: bold;">%1</span>, <span class="code" style="font-weight: bold;">%2</span> for parameters.

<span id="advanced"></span>

## Advanced options

In the [Advanced options of the configuration menu](../../../configuration_start_here/config_gateway_paras#Advanced_parameters), set the <span class="code">started\_command\_user\_control</span> option to <span style="font-weight: bold;">yes</span> if you want to control the maximum number of simultaneous activated scripts. This value is determined by the <span class="code">job\_max</span> parameter (that is only taken into account by Gateway if the <span class="code">started\_command\_user\_control</span> parameter is set to <span style="font-weight: bold;">yes</span>).

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
