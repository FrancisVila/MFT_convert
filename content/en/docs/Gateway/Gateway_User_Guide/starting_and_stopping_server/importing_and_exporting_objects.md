{
    "title": "Importing and exporting objects",
    "linkTitle": "Importing and exporting objects",
    "weight": "170"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Managing the Server

[Overview](#overview)

[Using the pelbase command](#using_pelbase_command)

[pelbase subcommands](#pelbase_subcommands)

<span id="overview"></span>

## Overview

The <span class="code" style="font-weight: bold;">pelbase</span> command enables you to:

-   Export and import objects between two Gateways
-   Transfer objects between two different versions of Gateway on the same machine, for example when upgrading to a newer version

<span id="using_pelbase_command"></span>

## Using the pelbase command

To transfer objects from one Gateway to another, or between versions:

1.  On the originating Gateway, execute the <span class="code" style="font-weight: bold;">pelbase export</span> command for the object or objects you want to export.  
    The result of each <span class="code" style="font-weight: bold;">pelbase export</span> command is a file describing the objects that you can transfer between machines or versions.  
    Use the object attribute parameters as object selection criteria. The command creates an output file with as many objects as meet all the criteria.  
    Use the <span class="code">-output (-f)</span> parameter to specify the name of the resulting file. If you do not enter a value, Gateway prints the command results on the screen.  
    When exporting from Gateway 6.17.2 or later, specifying an encryption key using the -encryption\_key\_file(-ekf) is mandatory.
    See the [Security Guide](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm) for how to generate an encryption key file.
2.  On the target Gateway, execute the <span class="code" style="font-weight: bold;">pelbase import</span> command. Execute the command as many times as necessary to import each file you created with the <span class="code" style="font-weight: bold;">pelbase export</span> command.  
    If the objects were exported with passwords encrypted, use the <span class="code">-encryption\_key\_file</span>(<span class="code">-ekf</span>) parameter to specify the key used for password encryption.  
    If the objects were exported from a Gateway version which does not support password encryption for exported objects, use the <span class="code">-import\_pwd\_cleartext</span> parameter to import clear-text passwords.  
    Password encryption applies for the following pelbase subcommands:  
    pelbase export\_site  
    pelbase export\_cgate  
    pelbase export\_sgate  
    pelbase export\_tradepart  
    and when importing the corresponding objects

<span id="pelbase_subcommands"></span>

## pelbase subcommands

-   [<span style="font-weight: bold;">pelbase export\_site</span>](#pelbase_export_site)
-   [<span style="font-weight: bold;">pelbase export\_lsite</span>](#pelbase_export_lsite)
-   [<span style="font-weight: bold;">pelbase export\_appli</span>](#pelbase_export_appli)
-   [<span style="font-weight: bold;">pelbase export\_list</span>](#pelbase_export_list)
-   [<span style="font-weight: bold;">pelbase export\_model</span>](#pelbase_export_model)
-   [<span style="font-weight: bold;">pelbase export\_purge\_model</span>](#pelbase_export_purge_model)
-   [<span style="font-weight: bold;">pelbase export\_user</span>](#pelbase_export_user)
-   [<span style="font-weight: bold;">pelbase export\_profile</span>](#pelbase_export_profile)
-   [<span style="font-weight: bold;">pelbase export\_cgate</span>](#pelbase_export_cgate)
-   [<span style="font-weight: bold;">pelbase export\_cgategroup</span>](#pelbase_export_cgategroup)
-   [<span style="font-weight: bold;">pelbase export\_sgate</span>](#pelbase_export_sgate)
-   [<span style="font-weight: bold;">pelbase export\_sgategroup</span>](#pelbase_export_sgategroup)
-   [<span style="font-weight: bold;">pelbase export\_decisionrule</span>](#pelbase_export_decisionrule)
-   [<span style="font-weight: bold;">pelbase export\_ruletable</span>](#pelbase_export_ruletable)
-   [<span style="font-weight: bold;">pelbase export\_proplist</span>](#pelbase_export_proplist)
-   [<span style="font-weight: bold;">pelbase export\_tradepart</span>](#pelbase_export_tradepart)
-   [<span style="font-weight: bold;">pelbase export\_proxy</span>](#pelbase_export_proxy)
-   pelbase export\_audit: see <a href="../../audit/working_with_audits_cli" class="MCXref xref">Working with Audits (command line)</a>
-   [<span style="font-weight: bold;">pelbase import</span>](#pelbase_import)

<span id="pelbase_export_site"></span>

### pelbase export\_site

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p>Syntax</p>         </td>
         <td><p><span class="code"><strong>pelbase export_site</strong> {-encryption_key_file} [-alias] [-proto_ident] [-group] [-protocol] [-comm_type] [-dest_address] [-format] [-user_fmt] [-output] [-append]</span></p>         </td>
      </tr>
      <tr>
         <td><p>Description</p>         </td>
         <td><p>Use this command to export fields and field values of one or more Sites. Gateway either displays the results on the screen or copies the results to an ASCII file. Use Site attributes as selection criteria, as described below.</p>
<p>For information about additional parameters for SWIFTNet output channel data, refer to <a href="../../connectors_about/swiftnet_about/swiftnet_input_channels/swiftnet_output_channels#swift_op_ch_paras">SWIFTNet output channels.</a></p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>Mandatory</p>
<p><span class="code">-encryption_key_file</span>(<span class="code">-ekf</span>): Enter the path to the encryption key file to be used to encrypt passwords contained by the object.</p>         </td>
      </tr>
      <tr>
         <td><em>Optional</em>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-alias (-a)</span>: Enter an alias that identifies the Site object you want to export.</p>
<p>Maximum: 31 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-proto_ident (-pi)</span>: Enter the protocol identifier of the Site object(s) you want to export.</p>
<p>Maximum: 25 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-group (-gr)</span>: Enter the group of the Site object(s) you want to export.</p>
<p>Maximum: 15 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-protocol (-pr)</span>: Enter the interchange protocol for the Site object(s) you want to export.</p>
<p>Enter one of the following values:</p>
<ul>
<li><span style="font-weight: bold;">PEL</span></li>
<li><span style="font-weight: bold;">ODETTE</span> (OFTP)</li>
<li><span style="font-weight: bold;">PHSE</span></li>
<li><span style="font-weight: bold;">PHSD</span></li>
<li><span style="font-weight: bold;">FTP</span></li>
<li><span style="font-weight: bold;">HTTP</span></li>
<li><span style="font-weight: bold;">FTP_HTTP</span></li>
<li><span style="font-weight: bold;">POP3</span></li>
<li><span style="font-weight: bold;">SFTP</span></li>
<li><span style="font-weight: bold;">SMTP</span></li>
<li><span style="font-weight: bold;">AS2</span></li>
<li><span style="font-weight: bold;">AS3</span></li>
<li><span style="font-weight: bold;">AS1_POP3</span></li>
<li><span style="font-weight: bold;">AS1_SMTP</span></li>
<li><span style="font-weight: bold;">RN_HTTP</span></li>
<li><span style="font-weight: bold;">RN_POP3</span></li>
<li><span style="font-weight: bold;">RN_SMTP</span></li>
<li><span style="font-weight: bold;">SWIFTNET</span></li>
<li><span style="font-weight: bold;">JMS</span></li>
<li><span style="font-weight: bold;">X420</span></li>
<li><span style="font-weight: bold;">X400</span></li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-comm_type (-ct)</span>: Enter the type of communications interface that corresponds to the Site object(s) you want to export:</p>
<ul>
<li><span style="font-weight: bold;">PAD</span></li>
<li><span style="font-weight: bold;">TCPIP</span> (default)</li>
<li><span style="font-weight: bold;">LU62</span></li>
<li><span style="font-weight: bold;">DSA</span></li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-dest_address (-da)</span>: Enter the Address to call (Remote Site network address).</p>
<p>In TCP/IP, specify the port number (example: 193.56.234.14/22000).</p>
<p>Maximum: 31 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-format (-of)</span>: Output format. Enter one of:</p>
<ul>
<li><span style="font-weight: bold;">S</span> = Shell (default). Example: field = <span style="font-style: italic;">value</span></li>
<li><span style="font-weight: bold;">C</span> = C-Shell. Example: set field = <span style="font-style: italic;">value</span></li>
<li><span style="font-weight: bold;">U</span> = User format</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-user_fmt (-uf)</span>: User format definition.</p>
<p>Enter a character string including the keywords %N and %V, where:</p>
<ul>
<li>%N = name of field</li>
<li>%V = value of field</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-output (-f)</span>: Name of the output file.</p>
<p>If you do not specify this parameter, the standard output file is used.</p>
<p>Maximum: 127 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-append (-ap)</span>: Concatenation at the end of the file (if it exists).</p>
<p>This parameter takes no value.</p>         </td>
      </tr>
      <tr>
         <td><p>Example</p>         </td>
         <td><p>Enter the command:</p>
<p><span class="code" style="font-weight: bold;">   pelbase export_site</span></p>
<p><span class="code" style="font-weight: bold;">   -encryption_key_file &lt;decryption_key.dat&gt;</span></p>
<p><span class="code" style="font-weight: bold;">   -gr gdefault</span></p>
<p><span class="code" style="font-weight: bold;">   -da SiteB</span></p>
<p><span class="code" style="font-weight: bold;">   -f UpgradeSite</span></p>
<p>Gateway creates an export file named <span class="code">UpgradeSite</span> containing all Site objects with SiteB as destination address.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="pelbase_export_lsite"></span>

### pelbase export\_lsite

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p>Syntax</p>         </td>
         <td><p><span class="code"><strong>pelbase export_lsite</strong> [-alias] [-protocol_ident] [-agent_alias] [-format] [-user_fmt] [-output] [-append]</span></p>         </td>
      </tr>
      <tr>
         <td><p>Description</p>         </td>
         <td><p>Use this command to export the fields and field values of one or more Logical Sites. Gateway either displays the results on the screen or copies the results to an ASCII file. Use LSite attributes as selection criteria, as described below.</p>
<p><span style="font-weight: bold;">Note:</span> It is not recommended to use Logical Sites. Logical Sites are still supported in this version of Gateway but are no longer accessible via the GUI.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>
<p>all optional</p>         </td>
         <td><p><span class="code">-alias (-a)</span>: Enter an alias that identifies the Logical Site object you want to export.</p>
<p>Maximum: 31 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-protocol_ident (-pi)</span>: Enter the protocol identifier of the Logical Site object(s) you want to export.</p>
<p>Maximum: 25 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-agent_alias (-ag)</span>: Enter the alias of an associated Site.</p>
<p>Maximum: 31 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-format (-of)</span>: Output format. Enter one of:</p>
<ul>
<li><span style="font-weight: bold;">S</span> = Shell (default). Example: field = <span style="font-style: italic;">value</span></li>
<li><span style="font-weight: bold;">C</span> = C-Shell. Example: set field = <span style="font-style: italic;">value</span></li>
<li><span style="font-weight: bold;">U</span> = User format</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-user_fmt (-uf)</span>: User format definition.</p>
<p>Enter a character string including the keywords %N and %V, where:</p>
<ul>
<li>%N = name of field</li>
<li>%V = value of field</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-output (-f)</span>: Name of the output file.</p>
<p>If you do not specify this parameter, the standard output file is used.</p>
<p>Maximum: 127 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-append (-ap)</span>: Concatenation at the end of the file (if it exists).</p>
<p>This parameter takes no value.</p>         </td>
      </tr>
      <tr>
         <td><p>Example</p>         </td>
         <td><p>Enter the command:</p>
<p><span class="code" style="font-weight: bold;">   pelbase export_lsite</span></p>
<p><span class="code" style="font-weight: bold;">   -a SITLOG01</span></p>
<p><span class="code" style="font-weight: bold;">   -of U</span></p>
<p><span class="code" style="font-weight: bold;">   -uf 'The value of field %N is %V'</span></p>
<p><span class="code" style="font-weight: bold;">   -f ExpLsite</span></p>
<p>Gateway creates an export file named <span class="code">ExpLsite</span> containing the definition of Logical Site SITLOG01.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="pelbase_export_appli"></span>

### pelbase export\_appli

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p>Syntax</p>         </td>
         <td><p><span class="code"><strong>pelbase export_appli</strong> [-name] [-group] [-site] [-format] [-user_fmt] [-output] [-append]</span></p>         </td>
      </tr>
      <tr>
         <td><p>Description</p>         </td>
         <td><p>Use this command to export the fields and field values of one or more Applications. Gateway either displays the results on the screen or copies the results to an ASCII file. Use Appli attributes as selection criteria, as described below.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>
<p>all optional</p>         </td>
         <td><p><span class="code">-name (-n)</span>: Enter an Application name.</p>
<p>Maximum: 8 alphanumeric characters for PEL.</p>
<p>Maximum: 16 alphanumeric characters for all other protocols.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-group (-gr)</span>: Enter the group of the Application object(s) you want to export.</p>
<p>Maximum: 15 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-site (-si)</span>: Enter the Site name of the Application object you want to export. Gateway selects Application objects having the same group as the Site you specify.</p>
<p>Maximum: 31 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-format (-of)</span>: Output format. Enter one of:</p>
<ul>
<li><span style="font-weight: bold;">S</span> = Shell (default). Example: field = <span style="font-style: italic;">value</span></li>
<li><span style="font-weight: bold;">C</span> = C-Shell. Example: set field = <span style="font-style: italic;">value</span></li>
<li><span style="font-weight: bold;">U</span> = User format</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-user_fmt (-uf)</span>: User format definition.</p>
<p>Enter a character string including the keywords %N and %V, where:</p>
<ul>
<li>%N = name of field</li>
<li>%V = value of field</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-output (-f)</span>: Name of the output file.</p>
<p>If you do not specify this parameter, the standard output file is used.</p>
<p>Maximum: 127 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-append (-ap)</span>: Concatenation at the end of the file (if it exists).</p>
<p>This parameter takes no value.</p>         </td>
      </tr>
      <tr>
         <td><p>Example</p>         </td>
         <td><p>Enter the command:</p>
<p><span class="code" style="font-weight: bold;">   pelbase export_appli</span></p>
<p><span class="code" style="font-weight: bold;">   -n APPLI</span></p>
<p><span class="code" style="font-weight: bold;">   -f ExpAppli</span></p>
<p>Gateway creates the <span class="code">ExpAppli</span> export file. From Application objects named APPLI, it extracts all fields and corresponding values, and writes them to the file.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="pelbase_export_list"></span>

### pelbase export\_list

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p>Syntax</p>         </td>
         <td><p><span class="code"><strong>pelbase export_list</strong> [-list_name] [-comments] [-format] [-user_fmt] [-output] [-append]</span></p>         </td>
      </tr>
      <tr>
         <td><p>Description</p>         </td>
         <td><p>Use this command to export the fields and field values of one or more Diffusion Lists. Gateway either displays the results on the screen or copies the results to an ASCII file. Use List attributes as selection criteria, as described below.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>
<p>all optional</p>         </td>
         <td><p><span class="code">-list_name (-n)</span>: Enter an existing Diffusion List name.</p>
<p>Maximum: 31 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-comments (-cts)</span>: Enter user comments.</p>
<p>Maximum: 80 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-format (-of)</span>: Output format. Enter one of:</p>
<ul>
<li><span style="font-weight: bold;">S</span> = Shell (default). Example: field = <span style="font-style: italic;">value</span></li>
<li><span style="font-weight: bold;">C</span> = C-Shell. Example: set field = <span style="font-style: italic;">value</span></li>
<li><span style="font-weight: bold;">U</span> = User format</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-user_fmt (-uf)</span>: User format definition.</p>
<p>Enter a character string including the keywords %N and %V, where:</p>
<ul>
<li>%N = name of field</li>
<li>%V = value of field</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-output (-f)</span>: Name of the output file.</p>
<p>If you do not specify this parameter, the standard output file is used.</p>
<p>Maximum: 127 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-append (-ap)</span>: Concatenation at the end of the file (if it exists).</p>
<p>This parameter takes no value.</p>         </td>
      </tr>
      <tr>
         <td><p>Example</p>         </td>
         <td><p>Enter the command:</p>
<p><span class="code" style="font-weight: bold;">   pelbase export_list</span></p>
<p><span class="code" style="font-weight: bold;">   -n LIST1</span></p>
<p><span class="code" style="font-weight: bold;">   -f ExpList</span></p>
<p>Gateway creates the <span class="code">ExpList</span> export file. From Diffusion List objects named LIST1, it extracts all fields and corresponding values, and writes them to the file.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="pelbase_export_model"></span>

### pelbase export\_model

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p>Syntax</p>         </td>
         <td><p><span class="code"><strong>pelbase export_model</strong> [-model] [-protocol] [-comments] [-format] [-user_fmt] [-output] [-append]</span></p>         </td>
      </tr>
      <tr>
         <td><p>Description</p>         </td>
         <td><p>Use this command to export the fields and field values of one or more Model objects. Gateway either displays the results on the screen or copies the results to an ASCII file. Use Model attributes as selection criteria, as described below.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>
<p>all optional</p>         </td>
         <td><p><span class="code">-model (-ml)</span>: Enter an existing Model name.</p>
<p>Maximum: 31 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-protocol (-pr)</span>: The protocol identifier of the Model object(s) you want to export.</p>
<p>Specify one of the following values:</p>
<ul>
<li><span style="font-weight: bold;">PEL</span></li>
<li><span style="font-weight: bold;">ODETTE</span> (OFTP)</li>
<li><span style="font-weight: bold;">PHSE</span></li>
<li><span style="font-weight: bold;">PHSD</span></li>
<li><span style="font-weight: bold;">FTP</span></li>
<li><span style="font-weight: bold;">HTTP</span></li>
<li><span style="font-weight: bold;">POP3</span></li>
<li><span style="font-weight: bold;">SFTP</span></li>
<li><span style="font-weight: bold;">SMTP</span></li>
<li><strong>TO_GTW</strong></li>
<li><strong>FROM_GTW</strong></li>
<li><span style="font-weight: bold;">AS2</span></li>
<li><span style="font-weight: bold;">AS3</span></li>
<li><span style="font-weight: bold;">AS1_POP3</span></li>
<li><span style="font-weight: bold;">AS1_SMTP</span></li>
<li><span style="font-weight: bold;">RN_HTTP</span></li>
<li><span style="font-weight: bold;">RN_POP3</span></li>
<li><span style="font-weight: bold;">RN_SMTP</span></li>
<li><span style="font-weight: bold;">SWIFTNET</span></li>
<li><span style="font-weight: bold;">JMS</span></li>
<li><span style="font-weight: bold;">X420</span></li>
<li><span style="font-weight: bold;">GENERAL</span></li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-comments (-cts)</span>: Enter user comments.</p>
<p>Maximum: 80 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-format (-of)</span>: Output format. Enter one of:</p>
<ul>
<li><span style="font-weight: bold;">S</span> = Shell (default). Example: field = <span style="font-style: italic;">value</span></li>
<li><span style="font-weight: bold;">C</span> = C-Shell. Example: set field = <span style="font-style: italic;">value</span></li>
<li><span style="font-weight: bold;">U</span> = User format</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-user_fmt (-uf)</span>: User format definition.</p>
<p>Enter a character string including the keywords %N and %V, where:</p>
<ul>
<li>%N = name of field</li>
<li>%V = value of field</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-output (-f)</span>: Name of the output file.</p>
<p>If you do not specify this parameter, the standard output file is used.</p>
<p>Maximum: 127 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-append (-ap)</span>: Concatenation at the end of the file (if it exists).</p>
<p>This parameter takes no value.</p>         </td>
      </tr>
      <tr>
         <td><p>Example</p>         </td>
         <td><p>Enter the command:</p>
<p><span class="code" style="font-weight: bold;">   pelbase export_model</span></p>
<p><span class="code" style="font-weight: bold;">   -ml MODEL1</span></p>
<p><span class="code" style="font-weight: bold;">   -pr GENERAL</span></p>
<p><span class="code" style="font-weight: bold;">   -f ExpModel</span></p>
<p>Gateway creates the <span class="code">ExpModel</span> export file. In the database it locates Model objects named MODEL1 that have GENERAL as protocol attribute values. From these Model objects, it extracts all fields and corresponding values, and writes them to the <span class="code">ExpModel</span> file.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="pelbase_export_purge_model"></span>

### pelbase export\_purge\_model

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p>Syntax</p>         </td>
         <td><p><span class="code"><strong>pelbase export_purge_model</strong> [-model] [-comments] [-format] [-user_fmt] [-output] [-append]</span></p>         </td>
      </tr>
      <tr>
         <td><p>Description</p>         </td>
         <td><p>Use this command to export the fields and field values of one or more Purge Model objects. Gateway either displays the results on the screen or copies the results to an ASCII file. Use Purge Model attributes as selection criteria, as described below.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>
<p>all optional</p>         </td>
         <td><p><span class="code">-model (-ml)</span>: Enter an existing Purge Model name.</p>
<p>Maximum: 31 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-comments (-cts)</span>: Enter user comments.</p>
<p>Maximum: 80 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-format (-of)</span>: Output format. Enter one of:</p>
<ul>
<li><span style="font-weight: bold;">S</span> = Shell (default). Example: field = <span style="font-style: italic;">value</span></li>
<li><span style="font-weight: bold;">C</span> = C-Shell. Example: set field = <span style="font-style: italic;">value</span></li>
<li><span style="font-weight: bold;">U</span> = User format</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-user_fmt (-uf)</span>: User format definition.</p>
<p>Enter a character string including the keywords %N and %V, where:</p>
<ul>
<li>%N = name of field</li>
<li>%V = value of field</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-output (-f)</span>: Name of the output file.</p>
<p>If you do not specify this parameter, the standard output file is used.</p>
<p>Maximum: 127 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-append (-ap)</span>: Concatenation at the end of the file (if it exists).</p>
<p>This parameter takes no value.</p>         </td>
      </tr>
      <tr>
         <td><p>Example</p>         </td>
         <td><p>Enter the command:</p>
<p><span class="code" style="font-weight: bold;">   pelbase export_purge_model</span></p>
<p><span class="code" style="font-weight: bold;">   -ml PURGEMODEL1</span></p>
<p><span class="code" style="font-weight: bold;">   -f ExpPurgeModel</span></p>
<p>Gateway creates the <span class="code">ExpPurgeModel</span> export file. In the database it locates Purge Model objects named PURGEMODEL1. From these Purge Model objects, it extracts all fields and corresponding values, and writes them to the <span class="code">ExpPurgeModel</span> file.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="pelbase_export_user"></span>

### pelbase export\_user

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p>Syntax</p>         </td>
         <td><p><span class="code"><strong>pelbase export_user</strong> [-username] [-group] [-profile] [-comments] [-disabled] [-administrator] [-allxfer] [-format] [-user_fmt] [-output] [-append]</span></p>         </td>
      </tr>
      <tr>
         <td><p>Description</p>         </td>
         <td><p>Use this command to export the fields and field values of one or more User objects. Gateway either displays the results on the screen or copies the results to an ASCII file. Use USER attributes as selection criteria, as described below.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>
<p>all optional</p>         </td>
         <td><p><span class="code">-user_name (-un)</span>: Enter an existing User login name.</p>
<p>Maximum: 31 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-group (-gr)</span>: Enter the Group of the User object(s) you want to export.</p>
<p>Maximum: 16 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-profile (-pr)</span>: Enter the Profile of the User object(s) you want to export.</p>
<p>Maximum: 16 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-comments (-cts)</span>: Enter user comments.</p>
<p>Maximum: 80 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-disabled (-dd)</span>: Enter a User status:</p>
<ul>
<li><span style="font-weight: bold;">N</span>: User enabled</li>
<li><span style="font-weight: bold;">Y</span>: User disabled</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-administrator (-admin)</span>: Enter an administrator status:</p>
<ul>
<li><span style="font-weight: bold;">N</span>: Non-administrator user</li>
<li><span style="font-weight: bold;">Y</span>: Administrator user</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-allxfer (-ax)</span>: Enter a User privilege status:</p>
<ul>
<li><span style="font-weight: bold;">N</span>: User without <em>access all transfers</em> privilege</li>
<li><span style="font-weight: bold;">Y</span>: User with <em>access all transfers</em> privilege</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-format (-of)</span>: Output format. Enter one of:</p>
<ul>
<li><span style="font-weight: bold;">S</span> = Shell (default). Example: field = <span style="font-style: italic;">value</span></li>
<li><span style="font-weight: bold;">C</span> = C-Shell. Example: set field = <span style="font-style: italic;">value</span></li>
<li><span style="font-weight: bold;">U</span> = User format</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-user_fmt (-uf)</span>: User format definition.</p>
<p>Enter a character string including the keywords %N and %V, where:</p>
<ul>
<li>%N = name of field</li>
<li>%V = value of field</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-output (-f)</span>: Name of the output file.</p>
<p>If you do not specify this parameter, the standard output file is used.</p>
<p>Maximum: 127 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-append (-ap)</span>: Concatenation at the end of the file (if it exists).</p>
<p>This parameter takes no value.</p>         </td>
      </tr>
      <tr>
         <td><p>Example</p>         </td>
         <td><p>Enter the command:</p>
<p><span class="code" style="font-weight: bold;">   pelbase export_user</span></p>
<p><span class="code" style="font-weight: bold;">   -group FINANCE</span></p>
<p>Gateway exports all User entries that belong to the group FINANCE.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="pelbase_export_profile"></span>

### pelbase export\_profile

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p>Syntax</p>         </td>
         <td><p><span class="code"><strong>pelbase export_profile</strong> [-profile] [-comments] [-format] [-user_fmt] [-output] [-append]</span></p>         </td>
      </tr>
      <tr>
         <td><p>Description</p>         </td>
         <td><p>Use this command to export the fields and field values of one or more Profile objects. Gateway either displays the results on the screen or copies the results to an ASCII file. Use USER attributes as selection criteria, as described below.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>
<p>all optional</p>         </td>
         <td><p><span class="code">-profile (-pr)</span>: Enter the name of the Profile object(s) you want to export.</p>
<p>Maximum: 16 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-comments (-cts)</span>: Enter user comments.</p>
<p>Maximum: 80 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-format (-of)</span>: Output format. Enter one of:</p>
<ul>
<li><span style="font-weight: bold;">S</span> = Shell (default). Example: field = <span style="font-style: italic;">value</span></li>
<li><span style="font-weight: bold;">C</span> = C-Shell. Example: set field = <span style="font-style: italic;">value</span></li>
<li><span style="font-weight: bold;">U</span> = User format</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-user_fmt (-uf)</span>: User format definition.</p>
<p>Enter a character string including the keywords %N and %V, where:</p>
<ul>
<li>%N = name of field</li>
<li>%V = value of field</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-output (-f)</span>: Name of the output file.</p>
<p>If you do not specify this parameter, the standard output file is used.</p>
<p>Maximum: 127 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-append (-ap)</span>: Concatenation at the end of the file (if it exists).</p>
<p>This parameter takes no value.</p>         </td>
      </tr>
      <tr>
         <td><p>Example</p>         </td>
         <td><p>Enter the command:</p>
<p><span class="code" style="font-weight: bold;">   pelbase export_profile</span></p>
<p><span class="code" style="font-weight: bold;">   -n OldProfile</span></p>
<p><span class="code" style="font-weight: bold;">   -f ExpProfile</span></p>
<p>Gateway creates the <span class="code">ExpProfile</span> export file. From the Profile object named <span class="code">OldProfile</span>, it extracts all fields and corresponding values, and writes them to the <span class="code">ExpProfile</span> file.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="pelbase_export_cgate"></span>

### pelbase export\_cgate

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p>Syntax</p>         </td>
         <td><p><span class="code"><strong>pelbase export_cgate</strong> {<span class="code">-encryption_key_file</span> (<span class="code">-ekf</span>)} [-name] [-parent_group] [-protocol] [-format] [-user_fmt] [-output] [-append]</span></p>         </td>
      </tr>
      <tr>
         <td><p>Description</p>         </td>
         <td><p>Use this command to export the fields and field values of one or more CGates. Gateway either displays the results on the screen or copies the results to an ASCII file. Use CGate attributes as selection criteria, as described below.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>Mandatory</p>
<p><span class="code">-encryption_key_file</span> (<span class="code">-ekf</span>): Enter the path to the encryption key file to be used to encrypt passwords contained by the object to be exported.</p>         </td>
      </tr>
      <tr>
         <td><em>Optional</em>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-name (-n)</span>: Enter an existing CGate name.</p>
<p>Maximum: 32 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-parent_group (-pg)</span>: Enter the name of the parent CGateGroup with which the CGate is associated.</p>
<p>Maximum: 32 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-protocol (-pr)</span>: Enter the protocol identifier of the CGate object(s) you want to export.</p>
<p>Specify one of the following values:</p>
<ul>
<li><span style="font-weight: bold;">FTP</span></li>
<li><span style="font-weight: bold;">HTTP</span></li>
<li><span style="font-weight: bold;">FTP_HTTP</span></li>
<li><span style="font-weight: bold;">PHSE</span></li>
<li><span style="font-weight: bold;">PHSD</span></li>
<li><span style="font-weight: bold;">ODETTE</span> (OFTP)</li>
<li><span style="font-weight: bold;">PEL</span></li>
<li><span style="font-weight: bold;">POP3</span></li>
<li><span style="font-weight: bold;">SFTP</span></li>
<li><span style="font-weight: bold;">SMTP</span></li>
<li><span style="font-weight: bold;">AS2</span></li>
<li><span style="font-weight: bold;">AS3</span></li>
<li><span style="font-weight: bold;">AS1_POP3</span></li>
<li><span style="font-weight: bold;">AS1_SMTP</span></li>
<li><span style="font-weight: bold;">RN_HTTP</span></li>
<li><span style="font-weight: bold;">RN_POP3</span></li>
<li><span style="font-weight: bold;">RN_SMTP</span></li>
<li><span style="font-weight: bold;">JMS</span></li>
<li><span style="font-weight: bold;">X420</span></li>
<li><span style="font-weight: bold;">*</span> = undefined</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-format (-of)</span>: Output format. Enter one of:</p>
<ul>
<li><span style="font-weight: bold;">S</span> = Shell (default). Example: field = <span style="font-style: italic;">value</span></li>
<li><span style="font-weight: bold;">C</span> = C-Shell. Example: set field = <span style="font-style: italic;">value</span></li>
<li><span style="font-weight: bold;">U</span> = User format</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-user_fmt (-uf)</span>: User format definition.</p>
<p>Enter a character string including the keywords %N and %V, where:</p>
<ul>
<li>%N = name of field</li>
<li>%V = value of field</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-output (-f)</span>: Name of the output file.</p>
<p>If you do not specify this parameter, the standard output file is used.</p>
<p>Maximum: 127 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-append (-ap)</span>: Concatenation at the end of the file (if it exists).</p>
<p>This parameter takes no value.</p>         </td>
      </tr>
      <tr>
         <td><p>Example</p>         </td>
         <td><p>Enter the command:</p>
<p><span class="code" style="font-weight: bold;">   pelbase export_cgate</span></p>
<p><span class="code" style="font-weight: bold;">   -encryption_key_file &lt;decryption_key.dat&gt;</span></p>
<p><span class="code" style="font-weight: bold;">   -n CGATE1</span></p>
<p><span class="code" style="font-weight: bold;">   -pg CGGROUP1</span></p>
<p><span class="code" style="font-weight: bold;">   -f ExpCGate</span></p>
<p>Gateway creates the <span class="code">ExpCGate</span> export file. In the database it locates CGate objects named CGATE1 that have CGGROUP1 as <span class="code">parent group</span> protocol attribute values. From these CGate objects, it extracts all fields and corresponding values, and writes them to the <span class="code">ExpCGate</span> file.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="pelbase_export_cgategroup"></span>

### pelbase export\_cgategroup

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p>Syntax</p>         </td>
         <td><p><span class="code"><strong>pelbase export_cgategroup</strong> [-name] [-format] [-user_fmt] [-output] [-append]</span></p>         </td>
      </tr>
      <tr>
         <td><p>Description</p>         </td>
         <td><p>Use this command to export the fields and field values of one or more CGateGroups. Gateway either displays the results on the screen or copies the results to an ASCII file. Use CGateGroup attributes as selection criteria, as described below.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>
<p>all optional</p>         </td>
         <td><p><span class="code">-name (-n)</span>: Enter an existing CGateGroup name.</p>
<p>Maximum: 32 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-format (-of)</span>: Output format. Enter one of:</p>
<ul>
<li><span style="font-weight: bold;">S</span> = Shell (default). Example: field = <span style="font-style: italic;">value</span></li>
<li><span style="font-weight: bold;">C</span> = C-Shell. Example: set field = <span style="font-style: italic;">value</span></li>
<li><span style="font-weight: bold;">U</span> = User format</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-user_fmt (-uf)</span>: User format definition.</p>
<p>Enter a character string including the keywords %N and %V, where:</p>
<ul>
<li>%N = name of field</li>
<li>%V = value of field</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-output (-f)</span>: Name of the output file.</p>
<p>If you do not specify this parameter, the standard output file is used.</p>
<p>Maximum: 127 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-append (-ap)</span>: Concatenation at the end of the file (if it exists).</p>
<p>This parameter takes no value.</p>         </td>
      </tr>
      <tr>
         <td><p>Example</p>         </td>
         <td><p>Enter the command:</p>
<p><span class="code" style="font-weight: bold;">   pelbase export_cgategroup</span></p>
<p><span class="code" style="font-weight: bold;">   -n CGGROUP1</span></p>
<p><span class="code" style="font-weight: bold;">   -f ExpCGGroup</span></p>
<p>Gateway creates the <span class="code">ExpCGGroup</span> export file. In the database it locates CGate objects named CGGROUP1. From these CGateGroup objects, it extracts all fields and corresponding values, and writes them to the <span class="code">ExpCGGroup</span> file.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="pelbase_export_sgate"></span>

### pelbase export\_sgate

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p>Syntax</p>         </td>
         <td><p><span class="code"><strong>pelbase export_sgate</strong> {-encryption_key_file} [-name] [-parent_group] [-format] [-user_fmt] [-output] [-append] </span></p>         </td>
      </tr>
      <tr>
         <td><p>Description</p>         </td>
         <td><p>Use this command to export the fields and field values of one or more SGates. Gateway either displays the results on the screen or copies the results to an ASCII file. Use SGate attributes as selection criteria, as described below.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>Mandatory</p>
<p><span class="code">-encryption_key_file</span> (<span class="code">-ekf</span>): Enter the path to the encryption key file to be used to encrypt passwords contained by the object to be exported.</p>         </td>
      </tr>
      <tr>
         <td><em>Optional</em>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-name (-n)</span>: Enter an existing SGate name.</p>
<p>Maximum: 32 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-parent_group (-pg)</span>: Enter the name of the parent SGateGroup with which the SGate is associated.</p>
<p>Maximum: 32 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-format (-of)</span>: Output format. Enter one of:</p>
<ul>
<li><span style="font-weight: bold;">S</span> = Shell (default). Example: field = <span style="font-style: italic;">value</span></li>
<li><span style="font-weight: bold;">C</span> = C-Shell. Example: set field = <span style="font-style: italic;">value</span></li>
<li><span style="font-weight: bold;">U</span> = User format</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-user_fmt (-uf)</span>: User format definition.</p>
<p>Enter a character string including the keywords %N and %V, where:</p>
<ul>
<li>%N = name of field</li>
<li>%V = value of field</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-output (-f)</span>: Name of the output file.</p>
<p>If you do not specify this parameter, the standard output file is used.</p>
<p>Maximum: 127 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-append (-ap)</span>: Concatenation at the end of the file (if it exists).</p>
<p>This parameter takes no value.</p>         </td>
      </tr>
      <tr>
         <td><p>Example</p>         </td>
         <td><p>Enter the command:</p>
<p><span class="code" style="font-weight: bold;">   pelbase export_sgate</span></p>
<p>   -encryption_key_file &lt;decryption_key.dat&gt;</p>
<p><span class="code" style="font-weight: bold;">   -n SGATE1</span></p>
<p><span class="code" style="font-weight: bold;">   -pg SGGROUP1</span></p>
<p><span class="code" style="font-weight: bold;">   -f ExpSGate</span></p>
<p>Gateway creates the <span class="code">ExpSGate</span> export file. In the database it locates SGate objects named SGATE1 that have SGGROUP1 as <code>parent group</code> protocol attribute values. From these SGate objects, it extracts all fields and corresponding values, and writes them to the <span class="code">ExpSGate</span> file.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="pelbase_export_sgategroup"></span>

### pelbase export\_sgategroup

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p>Syntax</p>         </td>
         <td><p><span class="code"><strong>pelbase export_sgategroup</strong> [-name] [-format] [-user_fmt] [-output] [-append]</span></p>         </td>
      </tr>
      <tr>
         <td><p>Description</p>         </td>
         <td><p>Use this command to export the fields and field values of one or more SGateGroups. Gateway either displays the results on the screen or copies the results to an ASCII file. Use SGateGroup attributes as selection criteria, as described below.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>
<p>all optional</p>         </td>
         <td><p><span class="code">-name (-n)</span>: Enter an existing SGateGroup name.</p>
<p>Maximum: 32 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-format (-of)</span>: Output format. Enter one of:</p>
<ul>
<li><span style="font-weight: bold;">S</span> = Shell (default). Example: field = <span style="font-style: italic;">value</span></li>
<li><span style="font-weight: bold;">C</span> = C-Shell. Example: set field = <span style="font-style: italic;">value</span></li>
<li><span style="font-weight: bold;">U</span> = User format</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-user_fmt (-uf)</span>: User format definition.</p>
<p>Enter a character string including the keywords %N and %V, where:</p>
<ul>
<li>%N = name of field</li>
<li>%V = value of field</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-output (-f)</span>: Name of the output file.</p>
<p>If you do not specify this parameter, the standard output file is used.</p>
<p>Maximum: 127 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-append (-ap)</span>: Concatenation at the end of the file (if it exists).</p>
<p>This parameter takes no value.</p>         </td>
      </tr>
      <tr>
         <td><p>Example</p>         </td>
         <td><p>Enter the command:</p>
<p><span class="code" style="font-weight: bold;">   pelbase export_sgategroup</span></p>
<p><span class="code" style="font-weight: bold;">   -n SGGROUP1</span></p>
<p><span class="code" style="font-weight: bold;">   -f ExpSGGroup</span></p>
<p>Gateway creates the <span class="code">ExpSGGroup</span> export file. In the database it locates SGate objects named SGGROUP1. From these SGateGroup objects, it extracts all fields and corresponding values, and writes them to the <span class="code">ExpSGGroup</span> file.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="pelbase_export_decisionrule"></span>

### pelbase export\_decisionrule

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p>Syntax</p>         </td>
         <td><p><span class="code"><strong>pelbase export_decisionrule</strong> [-name] [-type_of_decisionrules] [-comments] [-execution_type] [-model] [-perl_script] [-prop_list_name] [-format] [-user_fmt] [-output] [-append]</span></p>         </td>
      </tr>
      <tr>
         <td><p>Description</p>         </td>
         <td><p>Use this command to export the fields and field values of one or more Decision Rule objects. Gateway either displays the results on the screen or copies the results to an ASCII file. Use Decision Rule attributes as selection criteria, as described below.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>
<p>all optional</p>         </td>
         <td><p><span class="code">-name (-n)</span>: Enter a Decision Rule name.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-type_of_decisionrules (-type)</span>: Type of Decision Rule to export.</p>
<p>Enter one of the following values:</p>
<ul>
<li><span style="font-weight: bold;">XFER_CHANGE_STATE</span></li>
<li><span style="font-weight: bold;">TEMPORAL</span></li>
<li><span style="font-weight: bold;">FILE_STORING</span></li>
<li><span style="font-weight: bold;">XMS</span></li>
</ul>         </td>
      </tr>
      <tr>
         <td><span class="code">-comments (-cts)</span>: Enter user comments.
<p>Maximum: 80 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-execution_type (-et)</span>: The type of process triggered by the Decision Rule object(s) you want to export.</p>
<p>Enter one of the following values:</p>
<ul>
<li><span style="font-weight: bold;">MODEL</span> = the default execution is defined by a Model</li>
<li><span style="font-weight: bold;">AMTRIX</span></li>
<li><span style="font-weight: bold;">PERL</span></li>
<li><span style="font-weight: bold;">COMMAND</span></li>
<li><span style="font-weight: bold;">TO_XMS</span></li>
<li><strong>DEFAULT</strong></li>
<li><span style="font-weight: bold;">NONE</span></li>
<li><span style="font-weight: bold;">LOG_CLEANING</span></li>
<li><span style="font-weight: bold;">MAILBOX_CLEANING</span></li>
<li><span style="font-weight: bold;">STAT_CLEANING</span></li>
<li><span style="font-weight: bold;">XIB</span> = redirect the Transfer to Axway Integrator for processing</li>
</ul>         </td>
      </tr>
      <tr>
         <td><span class="code">-model (-ml)</span>: Model name.         </td>
      </tr>
      <tr>
         <td><span class="code">-perl_script (-ps)</span>: perl script file location.         </td>
      </tr>
      <tr>
         <td><span class="code">-prop_list_name (-pln)</span>: Name of the Property List to export.         </td>
      </tr>
      <tr>
         <td><p><span class="code">-format (-of)</span>: Output format. Enter one of:</p>
<ul>
<li><span style="font-weight: bold;">S</span> = Shell (default). Example: field = <span style="font-style: italic;">value</span></li>
<li><span style="font-weight: bold;">C</span> = C-Shell. Example: set field = <span style="font-style: italic;">value</span></li>
<li><span style="font-weight: bold;">U</span> = User format</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-user_fmt (-uf)</span>: User format definition.</p>
<p>Enter a character string including the keywords %N and %V, where:</p>
<ul>
<li>%N = name of field</li>
<li>%V = value of field</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-output (-f)</span>: Name of the output file.</p>
<p>If you do not specify this parameter, the standard output file is used.</p>
<p>Maximum: 127 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-append (-ap)</span>: Concatenation at the end of the file (if it exists).</p>
<p>This parameter takes no value.</p>         </td>
      </tr>
      <tr>
         <td><p>Example</p>         </td>
         <td><p>Enter the command:</p>
<p><span class="code" style="font-weight: bold;">   pelbase export_decisionrule</span></p>
<p><span class="code" style="font-weight: bold;">   -n OldRule</span></p>
<p><span class="code" style="font-weight: bold;">   -f ExpRule</span></p>
<p>Gateway creates the <span class="code">ExpRule</span> export file. From the Decision Rule object named OldRule, it extracts all fields and corresponding values, and writes them to the <span class="code">ExpRule</span> file.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="pelbase_export_ruletable"></span>

### pelbase export\_ruletable

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p>Syntax</p>         </td>
         <td><p><span class="code"><strong>pelbase export_ruletable</strong> [-name] [-type_of_rules_table] [-default_execution_type] [-default_model] [-default_perl_script] [-xms_connector_name] [-format] [-user_fmt] [-output] [-append]</span></p>         </td>
      </tr>
      <tr>
         <td><p>Description</p>         </td>
         <td><p>Use this command to export the fields and field values of one or more Rule Table objects. Gateway either displays the results on the screen or copies the results to an ASCII file.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>
<p>all optional</p>         </td>
         <td><p><span class="code">-name (-n)</span>: Name of the Rule Table you want to export.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-type_of_rules_table (-type)</span>: Type of Rule Table to export.</p>
<p>Enter one of the following values:</p>
<ul>
<li><span style="font-weight: bold;">XFER_CHANGE_STATE</span></li>
<li><span style="font-weight: bold;">TEMPORAL</span></li>
<li><span style="font-weight: bold;">FILE_STORING</span></li>
<li><span style="font-weight: bold;">XMS</span></li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-default_execution_type (-det)</span>: The type of process triggered by the Rule Table object(s) you want to export.</p>
<p>Enter one of the following values:</p>
<ul>
<li><span style="font-weight: bold;">MODEL</span> = the default execution is defined by a Model. Specify the Model in the <span class="code">default_model</span> parameter below.</li>
<li><span style="font-weight: bold;">AMTRIX</span></li>
<li><span style="font-weight: bold;">PERL</span></li>
<li><span style="font-weight: bold;">COMMAND</span></li>
<li><span style="font-weight: bold;">TO_XMS</span></li>
<li><strong>DEFAULT</strong></li>
<li><span style="font-weight: bold;">NONE</span></li>
<li><span style="font-weight: bold;">LOG_CLEANING</span></li>
<li><span style="font-weight: bold;">MAILBOX_CLEANING</span></li>
<li><span style="font-weight: bold;">STAT_CLEANING</span></li>
<li><span style="font-weight: bold;">XIB</span> = redirect the Transfer to AMTrix/ Axway Integrator for processing</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-default_model (-dm)</span>: Enter the name of the default Model to use with the Rule Table.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-default_perl_script (-dps)</span>: Enter the Perl script to apply by default to the current Transfer.</p>         </td>
      </tr>
      <tr>
         <td><span class="code">-xms_connector_name (-xcn)</span>: Name of the Axway Messaging connector associated with the exported Rule Table.         </td>
      </tr>
      <tr>
         <td><span class="code">-format (-of)</span>: Output format. Enter one of:
<ul>
<li><span style="font-weight: bold;">S</span> = Shell (default). Example: field = <span style="font-style: italic;">value</span></li>
<li><span style="font-weight: bold;">C</span> = C-Shell. Example: set field = <span style="font-style: italic;">value</span></li>
<li><span style="font-weight: bold;">U</span> = User format</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-user_fmt (-uf)</span>: User format definition.</p>
<p>Enter a character string including the keywords %N and %V, where:</p>
<ul>
<li>%N = name of field</li>
<li>%V = value of field</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-output (-f)</span>: Name of the output file.</p>
<p>If you do not specify this parameter, the standard output file is used.</p>
<p>Maximum: 127 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-append (-ap)</span>: Concatenation at the end of the file (if it exists).</p>
<p>This parameter takes no value.</p>         </td>
      </tr>
      <tr>
         <td><p>Example</p>         </td>
         <td><p>Enter the command:</p>
<p><span class="code" style="font-weight: bold;">   pelbase export_ruletable</span></p>
<p><span class="code" style="font-weight: bold;">   -n OldTable</span></p>
<p><span class="code" style="font-weight: bold;">   -f ExpTable</span></p>         </td>
      </tr>
   </tbody>
</table>

<span id="pelbase_export_proplist"></span>

### pelbase export\_proplist

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p>Syntax</p>         </td>
         <td><p><span class="code"><strong>pelbase export_proplist</strong> [-properties_list] [-comments] [-format] [-user_fmt] [-output] [-append]</span></p>         </td>
      </tr>
      <tr>
         <td><p>Description</p>         </td>
         <td><p>Use this command to export the fields and field values of one or more Property List objects. Gateway either displays the results on the screen or copies the results to an ASCII file.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>
<p>all optional</p>         </td>
         <td><p><span class="code">-properties_list (-pl)</span>: Name of the Properties List you want to export.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-comments (-cts)</span>: Enter user comments.</p>
<p>Maximum: 80 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-format (-of)</span>: Output format. Enter one of:</p>
<ul>
<li><span style="font-weight: bold;">S</span> = Shell (default). Example: field = <span style="font-style: italic;">value</span></li>
<li><span style="font-weight: bold;">C</span> = C-Shell. Example: set field = <span style="font-style: italic;">value</span></li>
<li><span style="font-weight: bold;">U</span> = User format</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-user_fmt (-uf)</span>: User format definition.</p>
<p>Enter a character string including the keywords %N and %V, where:</p>
<ul>
<li>%N = name of field</li>
<li>%V = value of field</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-output (-f)</span>: Name of the output file.</p>
<p>If you do not specify this parameter, the standard output file is used.</p>
<p>Maximum: 127 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-append (-ap)</span>: Concatenation at the end of the file (if it exists).</p>
<p>This parameter takes no value.</p>         </td>
      </tr>
      <tr>
         <td><p>Example</p>         </td>
         <td><p>Enter the command:</p>
<p><span class="code" style="font-weight: bold;">   pelbase export_proplist</span></p>
<p><span class="code" style="font-weight: bold;">   -n OldPList</span></p>
<p><span class="code" style="font-weight: bold;">   -f ExpPList1</span></p>         </td>
      </tr>
   </tbody>
</table>

<span id="pelbase_export_tradepart"></span>

### pelbase export\_tradepart

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p>Syntax</p>         </td>
         <td><p><span class="code"><strong>pelbase export_tradepart</strong> {-encryption_key_file} [-name] [-alias] [-is_local] [-trade_format] [-format] [-user_fmt] [-output] [-append]</span></p>         </td>
      </tr>
      <tr>
         <td><p>Description</p>         </td>
         <td><p>Use this command to export the fields and field values of one or more Trading Partner objects. Gateway either displays the results on the screen or copies the results to an ASCII file. Use Trading Partner attributes as selection criteria, as described below.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>Mandatory</p>
<p><span class="code">-encryption_key_file</span> (<span class="code">-ekf</span>): Enter the path to the encryption key file to be used to encrypt passwords contained by the object to be exported.</p>         </td>
      </tr>
      <tr>
         <td><em>Optional</em>         </td>
      </tr>
      <tr>
         <td><span class="code">-name (-n)</span>: Enter the name of the Trading Partner object to be exported.         </td>
      </tr>
      <tr>
         <td><p><span class="code">-alias (-a)</span>: Enter the Local alias that identifies the Trading Partner object to be exported.</p>         </td>
      </tr>
      <tr>
         <td><span class="code">-is_local (-loc)</span>: Enter one of the following values:
<ul>
<li><strong>Y</strong> = yes, local partner</li>
<li><strong>N</strong> = no, remote partner</li>
</ul>         </td>
      </tr>
      <tr>
         <td><span class="code">-trade_format</span>: Format of the Trading Partner exchange.
<p>Enter one of the following:</p>
<ul>
<li>AS1</li>
<li>AS2</li>
<li>AS3</li>
<li>SMIME</li>
<li>RN</li>
<li>SWIFTNET</li>
<li>CMS</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-format (-of)</span>: Output format. Enter one of:</p>
<ul>
<li><span style="font-weight: bold;">S</span> = Shell (default). Example: field = <span style="font-style: italic;">value</span></li>
<li><span style="font-weight: bold;">C</span> = C-Shell. Example: set field = <span style="font-style: italic;">value</span></li>
<li><span style="font-weight: bold;">U</span> = User format</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-user_fmt (-uf)</span>: User format definition.</p>
<p>Enter a character string including the keywords %N and %V, where:</p>
<ul>
<li>%N = name of field</li>
<li>%V = value of field</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-output (-f)</span>: Name of the output file.</p>
<p>If you do not specify this parameter, the standard output file is used.</p>
<p>Maximum: 127 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-append (-ap)</span>: Concatenation at the end of the file (if it exists).</p>
<p>This parameter takes no value.</p>         </td>
      </tr>
      <tr>
         <td><p>Example</p>         </td>
         <td><p>Enter the command:</p>
<p><span class="code" style="font-weight: bold;">   pelbase export_tradepart</span></p>
<p><span class="code" style="font-weight: bold;">   -encryption_key_file &lt;decryption_key.dat&gt;</span></p>
<p><span class="code" style="font-weight: bold;">   -n TradePart1</span></p>
<p><span class="code" style="font-weight: bold;">   -f TradePartExp</span></p>
<p>Gateway creates the <span class="code">TradePartExp</span> export file. From the Trading Partner object named TradePart1, it extracts all fields and corresponding values, and writes them to the <span class="code">TradePartExp</span> file.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="pelbase_export_proxy"></span>

### pelbase export\_proxy

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p>Syntax</p>         </td>
         <td><p><span class="code"><strong>pelbase export_proxy</strong> [-name] [-comments] [-protocol] [-format] [-user_fmt] [-output] [-append]</span></p>         </td>
      </tr>
      <tr>
         <td><p>Description</p>         </td>
         <td><p>Use this command to export the fields and field values of one or more Proxies. Gateway either displays the results on the screen or copies the results to an ASCII file. Use Proxy attributes as selection criteria, as described below.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>
<p>all optional</p>         </td>
         <td><p><span class="code">-name (-n)</span>: Enter the Proxy name.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-comments (-cts)</span>: Enter user comments.</p>
<p>Maximum: 80 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-protocol (-pr)</span>: The network layer protocol of the Proxy object(s) you want to export.</p>
<p>Enter one of the following values:</p>
<ul>
<li>SOCKS4</li>
<li>FTP</li>
<li>HTTP</li>
<li>HTTPS</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-format (-of)</span>: Output format. Enter one of:</p>
<ul>
<li><span style="font-weight: bold;">S</span> = Shell (default). Example: field = <span style="font-style: italic;">value</span></li>
<li><span style="font-weight: bold;">C</span> = C-Shell. Example: set field = <span style="font-style: italic;">value</span></li>
<li><span style="font-weight: bold;">U</span> = User format</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-user_fmt (-uf)</span>: User format definition.</p>
<p>Enter a character string including the keywords %N and %V, where:</p>
<ul>
<li>%N = name of field</li>
<li>%V = value of field</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-output (-f)</span>: Name of the output file.</p>
<p>If you do not specify this parameter, the standard output file is used.</p>
<p>Maximum: 127 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-append (-ap)</span>: Concatenation at the end of the file (if it exists).</p>
<p>This parameter takes no value.</p>         </td>
      </tr>
      <tr>
         <td><p>Example</p>         </td>
         <td><p>Enter the command:</p>
<p><span class="code" style="font-weight: bold;">   pelbase export_proxy</span></p>
<p><span class="code" style="font-weight: bold;">   -n NetProxy</span></p>
<p><span class="code" style="font-weight: bold;">   -f ExpProxy</span></p>
<p>Gateway creates the <span class="code">ExpProxy</span> export file. From the Proxy object named NetProxy, it extracts all fields and corresponding values, and writes them to the <span class="code">ExpProxy</span> file.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="pelbase_import"></span>

### 

<span id="pelbase_export_proxy"></span><span id="pelbase_export_audit"></span>

### pelbase export\_audit

See <a href="../../audit/working_with_audits_cli" class="MCXref xref">Working with Audits (command line)</a>

### pelbase import

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p>Syntax</p>         </td>
         <td><p><span class="code"><strong>pelbase import {-input}</strong> {-encryption_key_file} {-import_pwd_cleartext}[-site] [-lsite] [-appli] [-user] [-profile] [-list] [-model] [-proplist] [-purgemodel] [-cgategroup] [-cgate] [-decisionrule] [-ruletable] [-proxy] [-tradepart] [-xmsctor] [-sgategroup] [-sgate] [-error_free]</span></p>         </td>
      </tr>
      <tr>
         <td><p>Description</p>         </td>
         <td><p>Use this command to import the fields and field values of one or more objects contained in an importable object file.</p>
<p>You can create importable files using the <span class="code" style="font-weight: bold;">pelbase export</span> subcommands.</p>
<p>For information about additional parameters for SWIFTNet output channel data, refer to <a href="../../connectors_about/swiftnet_about/swiftnet_input_channels/swiftnet_output_channels#swift_op_ch_paras">SWIFTNet queues and output channels.</a></p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>Mandatory</p>
<p><span class="code">-input (-if)</span>: Enter the name of a file containing the objects you want to import.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-encryption_key_file</span> (<span class="code">-ekf</span>): Enter the path to the encryption key file to be used to decrypt passwords contained by the object to be imported.</p>
<p>OR</p>
<p><span class="code">-import_pwd_cleartext</span>: Specifies a legacy import file which contains unencrypted passwords.</p>
<p>The parameters are mandatory when importing: Site, CGate, SGate and Trading Partner objects, and should not be used otherwise.</p>
<p><strong>Note</strong>: <span class="code">-import_pwd_cleartext</span> and <span class="code">-ekf</span> are mutually exclusive.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-site (-si)</span>: Enter this parameter without entering a value to import all Site objects contained in the file specified in the <span class="code">input</span> parameter.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-lsite (-ls)</span>: Enter this parameter without entering a value to import all Logical Site objects contained in the file specified in the <span class="code">input</span> parameter.</p>
<p><span style="font-weight: bold;">Note:</span> It is not recommended to use Logical Sites. Logical Sites are still supported in this version of Gateway but are no longer accessible via the GUI.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-appli (-ap)</span>: Enter this parameter without entering a value to import all Application objects contained in the file specified in the <span class="code">input</span> parameter.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-user (-user)</span>: Enter this parameter without entering a value to import all User objects contained in the file specified in the <span class="code">input</span> parameter.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-profile (-pr)</span>: Enter this parameter without entering a value to import all Profile objects contained in the file specified in the <span class="code">input</span> parameter.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-list (-li)</span>: Enter this parameter without entering a value to import all Diffusion List objects contained in the file specified in the <span class="code">input</span> parameter.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-model (-ml)</span>: Enter this parameter without entering a value to import all Model objects contained in the file specified in the <span class="code">input</span> parameter.</p>         </td>
      </tr>
      <tr>
         <td><span class="code">-proplist (-pl)</span>: Enter this parameter without entering a value to import all Property List objects contained in the file specified in the <span class="code">input</span> parameter.         </td>
      </tr>
      <tr>
         <td><span class="code">-purgemodel (-pm)</span>: Enter this parameter without entering a value to import all Purge Model objects contained in the file specified in the <span class="code">input</span> parameter.         </td>
      </tr>
      <tr>
         <td><p><span class="code">-cgategroup (-cgg)</span>: Enter this parameter without entering a value to import all CGateGroup objects contained in the file specified in the <span class="code">input</span> parameter.</p>
<p><span style="font-weight: bold;">Note:</span> You must import CGateGroup objects <span style="font-style: italic;">before</span> CGate objects.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-cgate (-cg)</span>: Enter this parameter without entering a value to import all CGate objects contained in the file specified in the <span class="code">input</span> parameter.</p>
<p><span style="font-weight: bold;">Note:</span> You must import CGateGroup objects <span style="font-style: italic;">before</span> CGate objects.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-decisionrule (-rd)</span>: Enter this parameter without entering a value to import all Decision Rule objects contained in the file specified in the <span class="code">input</span> parameter.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-ruletable (-rt)</span>: Enter this parameter without entering a value to import all Rule Table objects contained in the file specified in the <span class="code">input</span> parameter.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-proxy (-px)</span>: Enter this parameter without entering a value to import all Proxy objects contained in the file specified in the <span class="code">input</span> parameter.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-tradepart (-tp)</span>: Enter this parameter without entering a value to import all Trading Partner objects contained in the file specified in the <span class="code">input</span> parameter.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-xmsctor (-xc)</span>: Enter this parameter without entering a value to import all Axway Messaging connector objects contained in the file specified in the <span class="code">input</span> parameter.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-sgategroup (-sgg)</span>: Enter this parameter without entering a value to import all SGateGroup objects contained in the file specified in the <span class="code">input</span> parameter.</p>
<p><span style="font-weight: bold;">Note:</span> You must import SGateGroup objects <span style="font-style: italic;">before</span> SGate objects.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-sgate (-sg)</span>: Enter this parameter without entering a value to import all SGate objects contained in the file specified in the <span class="code">input</span> parameter.</p>
<p><span style="font-weight: bold;">Note:</span> You must import SGateGroup objects <span style="font-style: italic;">before</span> SGate objects.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-error_free</span>: Enter this parameter to create the different objects while ignoring the new parameters and without stopping the process at each error.</p>         </td>
      </tr>
      <tr>
         <td><p>Example</p>         </td>
         <td><p>Enter the following command to import the object contents of the <span class="code">ImpObject</span> file:</p>
<p><span class="code" style="font-weight: bold;">   pelbase import</span></p>
<p><span class="code" style="font-weight: bold;">   -if ImpObject</span></p>
<p><span class="code" style="font-weight: bold;">   -ekf &lt;decryption_key.dat&gt;</span></p>
<p><span class="code" style="font-weight: bold;">   -site  -lsite  -model  -appli  -list</span></p>
<p><span class="code" style="font-weight: bold;">   -user  -profile  -cgategroup  -cgate  -error_free</span></p>         </td>
      </tr>
   </tbody>
</table>

Related topics

[Upgrading the Mailbox](../migrating_mailbox)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
