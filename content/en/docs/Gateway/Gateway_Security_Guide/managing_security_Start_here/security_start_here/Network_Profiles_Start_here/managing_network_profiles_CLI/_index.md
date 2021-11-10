{
    "title": "Managing Network Profiles (command line) ",
    "linkTitle": "Command line operations",
    "weight": "200"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Managing Security

#### Commands for creating and managing Network Profiles:

-   [<span class="code" style="font-weight: bold;">secadm create\_netprof</span>](#secadm_create_netprof) – Create a Network Profile
-   [<span class="code" style="font-weight: bold;">secadm update\_netprof</span>](#secadm_update_netprof) – Update a Network Profile
-   [<span class="code" style="font-weight: bold;">secadm delete\_netprof</span>](#secadm_delete_netprof) – Delete a Network Profile

#### Commands for displaying Network Profiles:

-   [<span class="code" style="font-weight: bold;">secdsp select\_netprof</span>](#secdsp_select_netprof) – Display a selected list of Network Profiles
-   [<span class="code" style="font-weight: bold;">secdsp display\_netprof</span>](#secdsp_display_netprof) – Display the parameters of a Network Profile
-   [<span class="code" style="font-weight: bold;">secdsp status\_netprof</span>](#secdsp_status_netprof) – Display a selected list of Network Profiles with a subset of information for each selected Profile

<span id="secbase"></span>

#### Commands for exchanging Network Profiles between Gateway installations or Gateway versions:

-   [<span class="code" style="font-weight: bold;">secbase export\_netprof</span>](#secbase_export_netprof) – Create an output file containing Network Profile definitions
-   [<span class="code" style="font-weight: bold;">secbase import</span>](#secbase_import) – Import a Network Profile

<span id="secadm_create_netprof"></span>

## Creating Network Profiles: secadm create\_netprof

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p><span class="code"><strong>secadm create_netprof {-nprof_name}</strong> [-security_option] [-comm_type] [-org_address] [-dest_address] [-user_data] [-state] [-sprof_name]</span></p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to create a Network Profile.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p>Mandatory</p>
<p><span class="code">-nprof_name (-npn)</span>: Enter a name for the Network Profile you are creating. The name of the Network Profile must be unique.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-security_option (-sec_opt)</span>: Enter the security option for the Network Profile.</p>
<p>Possible values are:</p>
<ul>
<li><span style="font-weight: bold;">None</span> (default)</li>
<li><span style="font-weight: bold;">TLS</span></li>
<li><span style="font-weight: bold;">SSH</span></li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-comm_type (-ct)</span>: Enter the type of network connection associated with the profile.</p>
<p>Enter:</p>
<ul>
<li><span style="font-weight: bold;">TCPIP</span> = TCP/IP (default)</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-org_address (-oa)</span>: Enter the originating address and SAP.<br />
Maximum: 31 characters.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-dest_address (-da)</span>: Enter the destination address and SAP.<br />
Maximum: 31 characters.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-sprof_name (-spn)</span>: Enter the Security Profile name in the Network Profile.<br />
Maximum: 31 characters.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p>The following command creates a Network Profile named <span class="code">local_netprof</span>. This Profile activates the use of TLS for any network connection coming from addresses 10.10.10.* towards address 10.10.10.1 and port 2205. The associated Security Profile is <span style="font-weight: bold;">sprof_1</span>.</p>
<p>secadm create_netprof  -nprof_name "local_netprof"</p>
<p>-org_address "10.10.10.*/*"</p>
<p>-dest_address "10.10.10.1/2205"</p>
<p>-sec_opt TLS</p>
<p>-sprof_name "sprof_1"</p>         </td>
      </tr>
   </tbody>
</table>

<span id="secadm_update_netprof"></span>

## Updating Network Profiles: secadm update\_netprof

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p><span class="code"><strong>secadm update_netprof {-nprof_name}</strong> [-security_option] [-comm_type] [-org_address] [-dest_address] [-user_data] [-state] [-sprof_name]</span></p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to modify and update a Network Profile.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p>Mandatory</p>
<p><span class="code">-nprof_name (-npn)</span>: Enter a name for the Network Profile you are updating.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-security_option (-sec_opt)</span>: Enter the security option for the Network Profile.</p>
<p>Possible values are:</p>
<ul>
<li><span style="font-weight: bold;">None</span> (default)</li>
<li><span style="font-weight: bold;">TLS</span></li>
<li><span style="font-weight: bold;">SSH</span></li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-comm_type (-ct)</span>: Enter the type of network connection associated with the profile.</p>
<p>Enter :</p>
<ul>
<li><span style="font-weight: bold;">TCPIP</span> = TCP/IP (default)</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-org_address (-oa)</span>: Enter the originating address and SAP.<br />
Maximum: 31 characters.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-dest_address (-da)</span>: Enter the destination address and SAP.<br />
Maximum: 31 characters.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-sprof_name (-spn)</span>: Enter the Security Profile name in the Network Profile.<br />
Maximum: 31 characters.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p>The following command modifies the Network Profile named <span class="code">local_netprof</span> by replacing the original address pattern with <span style="font-weight: bold;">10.10.*.*/*</span>.</p>
<p>secadm update_netprof</p>
<p>  -nprof_name "local_netprof"</p>
<p>  -org_address "10.10.*.*/*"</p>         </td>
      </tr>
   </tbody>
</table>

<span id="secadm_delete_netprof"></span>

## Deleting Network Profiles: secadm delete\_netprof

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p><span class="code"><strong>secadm delete_netprof {-nprof_name}</strong></span></p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to remove a Network Profile.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p>Mandatory</p>
<p><span class="code">-nprof_name (-npn)</span>: Enter the name of the Network Profile you want to delete.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p>The following command deletes the Network Profile named <span class="code">local_netprof</span>:</p>
<p>secadm delete_netprof  -nprof_name "local_netprof"</p>         </td>
      </tr>
   </tbody>
</table>

<span id="secdsp_display_netprof"></span>

## Displaying Network Profiles: secdsp display\_netprof

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p><span class="code"><strong>secdsp display_netprof {-nprof_name}</strong></span></p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to display the attributes of a Network Profile.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p><span style="font-style: italic;">Mandatory</span></p>
<p><span class="code">-nprof_name (-npn)</span>: Enter the name of the Network Profile for which you want to display the attributes.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p>The following command displays the attributes of the Network Profile named <span class="code">local_netprof</span>:</p>
<p>secdsp display_netprof  -nprof_name "local_netprof"</p>         </td>
      </tr>
   </tbody>
</table>

<span id="secdsp_select_netprof"></span>

## Listing Network Profile names: secdsp select\_netprof

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p><span class="code"><strong>secdsp select_netprof</strong> [-security_option] [-comm_type] [-org_address] [-dest_address] [-user_data] [-sprof_name]</span></p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to display a filtered list of the names of the Network Profiles in the database.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p><span class="code">-security_option (-sec_opt)</span>: Enter the security option for the Network Profile as display filtering criteria.</p>
<p>Possible values are:</p>
<ul>
<li><span style="font-weight: bold;">None</span> (default)</li>
<li><span style="font-weight: bold;">TLS</span></li>
<li><span style="font-weight: bold;">SSH</span></li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-comm_type (-ct)</span>: Enter the type of network connection associated with the profile as display filtering criteria.</p>
<p>Enter :</p>
<ul>
<li><span style="font-weight: bold;">TCPIP</span> = TCP/IP (default)</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-org_address (-oa)</span>: Enter the originating address and SAP as display filtering criteria.<br />
Maximum: 31 characters.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-dest_address (-da)</span>: Enter the destination address of the connection as display filtering criteria.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-sprof_name (-spn)</span>: Enter the Security Profile name in the Network Profile as display filtering criteria.<br />
Maximum: 31 characters.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p>The following command lists the names of all Network Profiles that activate TLS and use the Security Profile <span class="code">sprof_1</span>:</p>
<p>secdsp select_netprof  -sec_opt TLS  -<span style="font-weight: bold;">sprof_name "sprof_1"</span></p>         </td>
      </tr>
   </tbody>
</table>

<span id="secdsp_status_netprof"></span>

## Listing Network Profile abstracts: secdsp status\_netprof

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p><span class="code"><strong>secdsp status_netprof</strong> [-security_option] [-comm_type] [-org_address] [-dest_address] [-user_data] [-sprof_name]</span></p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to display lists of Network Profile abstracts, filtered according to selected criteria.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p><span class="code">-security_option (-sec_opt)</span>: Enter the security option for the Network Profile as display filtering criteria.</p>
<p>Possible values are:</p>
<ul>
<li><span style="font-weight: bold;">None</span> (default)</li>
<li><span style="font-weight: bold;">TLS</span></li>
<li><span style="font-weight: bold;">SSH</span></li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-comm_type (-ct)</span>: Enter the type of network connection associated with the profile as display filtering criteria.</p>
<p>Enter either:</p>
<ul>
<li><span style="font-weight: bold;">TCPIP</span> = TCP/IP (default)</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-org_address (-oa)</span>: Enter the originating address and SAP as display filtering criteria.<br />
Maximum: 31 characters.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-dest_address (-da)</span>: Enter the destination address of the connection as display filtering criteria.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-sprof_name (-spn)</span>: Enter the Security Profile name in the Network Profile as display filtering criteria.<br />
Maximum: 31 characters.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p>The following command lists abstracts of all Network Profiles that activate the use of TLS:</p>
<p>secdsp status_netprof  -tls_option Y</p>         </td>
      </tr>
   </tbody>
</table>

## Exporting and importing Network Profiles

Gateway provides two commands for exchanging security objects between Gateways and Gateway versions:

-   [<span class="code" style="font-weight: bold;">secbase export\_netprof</span>](#secbase_export_netprof)
-   [<span class="code" style="font-weight: bold;">secbase import</span>](#secbase_import)

<span id="secbase_export_netprof"></span>

### Exporting Network Profiles to a file: secbase export\_netprof

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p><span class="code"><strong>secbase export_netprof</strong></span> [optional parameters - listed below]</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to export the fields and field values of Network Profile objects to an ASCII format output file.</p>
<p>After running the command, you can open and edit the output file. Use the <a href="#secbase_import"><span class="code" style="font-weight: bold;">secbase import</span></a> command to import the file contents to Gateway.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p><span class="code">-security_option (-sec_opt)</span>: Enter one of the security option values as filtering criteria:</p>
<ul>
<li><strong>NONE</strong></li>
<li><strong>TLS</strong></li>
<li><strong>SSH</strong></li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-comm_type (-ct)</span>: Enter the communication type as filtering criteria:</p>
<ul>
<li><span style="font-weight: bold;">TCPIP</span></li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-org_address (-oa)</span>: Enter the originating address and SAP of the connection as filtering criteria.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-dest_address (-da)</span>: Enter the destination address and SAP of the connection as filtering criteria.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-sprof_name (-spn)</span>: Enter the name of the associated Security Profile as filtering criteria.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-format (-of)</span>: Select an output format.</p>
<p>Enter one of the following values:</p>
<ul>
<li><span style="font-weight: bold;">S</span> = Shell (default). For example, field = <span style="font-style: italic;">value</span></li>
<li><span style="font-weight: bold;">C</span> = C-Shell. For example, set field = <span style="font-style: italic;">value</span></li>
<li><span style="font-weight: bold;">U</span> = User format</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-user_fmt (-uf)</span>: User format definition. Enter a character string including the keywords %N and %V, where:</p>
<ul>
<li>%N = name of field</li>
<li>%V = value of field</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-output (-f)</span>: Enter the name of the output file that results from the command.</p>
<p>If you do not specify this parameter, the standard output file is used.</p>
<p>Maximum: 127 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-append (-ap)</span>: Concatenation at the end of the file (if it exists).</p>
<p>This parameter takes no value.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p>Enter the command:</p>
<p><span class="code" style="font-weight: bold;">   secbase export_netprof  -sec_opt SSH  -f ExpProf</span></p>
<p>Gateway creates the <span class="code">ExpProf</span> export file. In the database, it locates Network Profile objects named with SSH security options. From these objects, it extracts each field and its corresponding value, and writes them to the <span class="code">ExpProf</span> file.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="secbase_import"></span>

### Importing Network Profiles from a file: secbase import

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p><span class="code"><strong>secbase import {-input}</strong> [-netprof] [-sprof] [-sshprof] [-cert] [-key] [-error_free]</span></p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to import the fields and field values of one or more security objects (for example Network Profiles) contained in an importable object file.</p>
<p>You can create importable files of Network Profiles using the <a href="#secbase_export_netprof"><span class="code" style="font-weight: bold;">secbase export_netprof</span></a> command.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p>Mandatory</p>
<p><span class="code">-input (-if)</span>: Enter the name of the file containing the Network Profile objects you want to import.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-netprof (-np)</span>: Enter the name of a Network Profile contained in the output file named in the <span class="code">-input</span> parameter.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-sprof (-sp)</span>: Enter the name of a Security Profile contained in the output file named in the <span class="code">-input</span> parameter.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-sshprof (-shp)</span>: Enter the name of an SSH Security Profile contained in the output file named in the <span class="code">-input</span> parameter.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-error_free</span>: Use this parameter to create the different objects while ignoring the new parameters and without stopping the process at each error.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p>Enter the following command to import the object contents of the <span class="code">ExpProf</span> file:</p>
<p><span class="code" style="font-weight: bold;">   secbase import  -if ExpProf</span></p>         </td>
      </tr>
   </tbody>
</table>

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
