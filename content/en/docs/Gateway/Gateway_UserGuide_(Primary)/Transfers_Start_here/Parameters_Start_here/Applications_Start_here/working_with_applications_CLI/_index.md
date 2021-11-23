{
    "title": "Working with Applications (command line)",
    "linkTitle": "Command line operations",
    "weight": "180"
}{{< Gateway/componentlongname  >}}: Managing Transfers

`peladm create_appli`

`peladm update_appli`

`peladm delete_appli`

`peldsp select_appli`

`peldsp display_appli`

<span id="peladm_create_appli"></span>

## Creating an Application: peladm create\_appli

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p>Syntax</p>         </td>
         <td><p>peladm create_appli {-name} [optional parameters]</p>         </td>
      </tr>
      <tr>
         <td><p>Description</p>         </td>
         <td><p>Use this command to create an Application. An Application defines a type of file structure. Application attributes must be compatible with the local file system features.</p>
<p>To create an Application, set up all necessary parameters, including platform-specific parameters if they are required. Some parameters have default values supplied either by the administrative interface, or internally by Gateway. For example, if you do not specify the group name, the Application takes the default group name: <strong>GDEFAULT</strong>.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p><span class="code">-name (-n)</span>: Enter the name of the application you are creating.</p>         </td>
      </tr>
      <tr>
         <td><p><span style="font-style: italic;">Optional parameters:</span> Refer to <a href="application_object_parameter_list">Application objects: Parameters List</a>.</p>         </td>
      </tr>
      <tr>
         <td><p>About the examples</p>         </td>
         <td><p>The following examples do not supply platform-specific parameters. You must adapt these specific parameters to your own configuration.</p>
<p><span style="font-weight: bold;">Note:</span> You can create two Applications with the same name if they each belong to a different group.</p>         </td>
      </tr>
      <tr>
         <td><p>Example 1</p>         </td>
         <td><p>The following command creates an Application object named APPLI that belongs to the group ALPHA. This Application object can be used to transfer files with horizontal compression, variable record format and record length of 160. The record format of the transferred file is fixed and the record length is 1024.</p>
<p>peladm create_appli  -name APPLI</p>
<p>-gr ALPHA</p>
<p>-comp H</p>
<p>-rec_fmt V</p>
<p>-rec_len 160</p>
<p>–text_file Y</p>
<p>–xrf F</p>
<p>–xrl 1024</p>         </td>
      </tr>
      <tr>
         <td><p>Example 2</p>         </td>
         <td><p>The following command creates an Application used to transfer ASCII files of 255 byte fixed record length, using the default group name:</p>
<p>peladm create_appli  -n fix255</p>
<p>-cts "fixed record length: 255"</p>
<p>-f_org Sequential</p>
<p>-rec_fmt Fixed</p>
<p>-rec_len 255</p>
<p>–dc ASCII</p>
<p>–xrf F</p>
<p>–xrl 255</p>
<p>-xdc ASCII</p>
<p>-dp &lt;your Received files directory&gt;</p>         </td>
      </tr>
      <tr>
         <td><p>Example 3</p>         </td>
         <td><p>The following command creates an Application used to transfer ASCII files of fixed 80 byte record length, ending with '\n' or '\r' depending on the system, and that uses the default group name. The end-of-line characters are deleted from the file content and the file content is converted into EBCDIC before transmission:</p>
<p>peladm create_appli  -n fix80</p>
<p>-cts "fixed record length: 80"</p>
<p>-f_org Sequential</p>
<p>-rec_fmt Fixed text</p>
<p>-rec_len 80</p>
<p>–dc ASCII</p>
<p>–xrf F</p>
<p>–xrl 80</p>
<p>-xdc EBCDIC</p>
<p>-dp &lt;your Received files directory&gt;</p>         </td>
      </tr>
      <tr>
         <td><p>Example 4</p>         </td>
         <td><p>The following example creates an Application used to transfer EBCDIC files in stream mode record format, record length of 4000 bytes (except for the last record that can be shorter) and with the group name: GRAPPLIS:</p>
<p>peladm create_appli&amp;  -n str4000</p>
<p>-g GRAPPLIS</p>
<p>-cts "Stream: 4000"</p>
<p>-f_org Sequential</p>
<p>-rec_fmt Stream</p>
<p>-rec_len 4000</p>
<p>–dc EBCDIC</p>
<p>–xrf V</p>
<p>–xrl 4000</p>
<p>-xdc EBCDIC</p>
<p>-dp &lt;your Received files directory&gt;</p>         </td>
      </tr>
   </tbody>
</table>

<span id="peladm_update_appli"></span>

## Modifying an Application: peladm update\_appli

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p>Syntax</p>         </td>
         <td><p>peladm update_appli {-name} [optional parameters]</p>         </td>
      </tr>
      <tr>
         <td><p>Description</p>         </td>
         <td><p>Use this command to modify an existing Application object.</p>
<p>Enter the Application name and the group name (optional parameter; default = GDEFAULT) as parameters, followed by all the fields you want to modify.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p><span class="code">-name (-n)</span>: Enter the name of the application you are modifying.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-group (-gr)</span>: Enter the group name of the application.</p>         </td>
      </tr>
      <tr>
         <td><p><span style="font-style: italic;">Optional parameters</span>: Refer to <a href="application_object_parameter_list">Application objects: Parameters List</a>.</p>         </td>
      </tr>
      <tr>
         <td><p>Example</p>         </td>
         <td><p>The following command modifies the group and the compression value for the Application APPLI:</p>
<p>peladm update_appli  -name APPLI</p>
<p>-gr ALPHA</p>
<p>-comp B</p>         </td>
      </tr>
   </tbody>
</table>

<span id="peladm_delete_appli"></span>

## Deleting an Application: peladm delete\_appli

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p>Syntax</p>         </td>
         <td><p>peladm delete_appli {-name} [optional parameters]</p>         </td>
      </tr>
      <tr>
         <td><p>Description</p>         </td>
         <td><p>Use this command to delete an Application. Since Applications in different Groups can have the same name, you must specify the Application name <span style="font-style: italic;">and</span> the Group name.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p><span class="code">-name (-n)</span>: Enter the name of the Application object you are deleting.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-group (-gr)</span>: Enter the group name of the Application  object you are deleting.</p>         </td>
      </tr>
      <tr>
         <td><p>Example</p>         </td>
         <td><p>The following command deletes Application object APPLI in the group ALPHA.</p>
<p>peladm delete_appli  -name APPLI  <span style="font-weight: bold;">-gr ALPHA</span></p>         </td>
      </tr>
   </tbody>
</table>

<span id="peldsp_select_appli"></span>

## Selecting Applications: peldsp select\_appli

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p>Syntax</p>         </td>
         <td><p>peldsp select_appli {-name} [-group] [-site]</p>         </td>
      </tr>
      <tr>
         <td><p>Description</p>         </td>
         <td><p>Use this command to select the Applications that match the criteria entered as parameters.</p>
<p>To list all Applications, enter no parameters. Use the optional parameters to refine your search.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p><span class="code">-name (-n)</span>: Enter the name of the Application object you are deleting.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-group (-gr)</span>: Enter the group name of the Application object you are deleting.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-site (si)</span>: Enter the name of a Remote Site associated with the Application.</p>         </td>
      </tr>
      <tr>
         <td><p>Example</p>         </td>
         <td><p>Gateway returns all Application names that match the selection criteria.</p>
<p>Each string parameter is seen as a truncated search key.</p>
<p>The following command returns a list of the Applications whose names begin with B.</p>
<p>peldsp select_appli  -n B</p>
<p>I_DEFAULT GDEFAULT</p>
<p>I_FNAM_F3N GDEFAULT</p>         </td>
      </tr>
   </tbody>
</table>

<span id="peldsp_display_appli"></span>

## Displaying an Application: peldsp display\_appli

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p>Syntax</p>         </td>
         <td><p>peldsp display_appli {-name} [-group] [-site]</p>         </td>
      </tr>
      <tr>
         <td><p>Description</p>         </td>
         <td><p>Use this command to display the parameters of an Application object that you identify by its name. The Application parameters are displayed on the screen.</p>
<p>If the Application group is not <span style="font-weight: bold;">GDEFAULT</span>, the group parameter is mandatory.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p><span class="code">-name (-n)</span>: Enter the name of the Application object for which you want to display the attributes.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-group (-gr)</span>: Enter the group name of the Application object for which you want to display the attributes.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-site (si)</span>: Enter the name of a Remote Site associated with the Application for which you want to display the attributes.</p>         </td>
      </tr>
      <tr>
         <td><p>Results of the command</p>         </td>
         <td><p>Gateway returns a display in which each parameter is displayed on a separate line, in the format:</p>
<p>name_of_field="value"</p>
<p>Gateway prefixes each field name with the string "<span class="code" style="font-weight: bold;">a_</span>", referring to the <span style="font-weight: bold;">A</span>pplication object.</p>         </td>
      </tr>
   </tbody>
</table>

Related topics

[Application objects: Parameters List](application_object_parameter_list)

 

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
