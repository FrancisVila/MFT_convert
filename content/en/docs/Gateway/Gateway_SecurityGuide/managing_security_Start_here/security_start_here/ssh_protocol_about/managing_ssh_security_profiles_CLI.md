{
    "title": "Managing SSH Security Profiles (command line)",
    "linkTitle": "Managing SSH Security Profiles (command line)",
    "weight": "240"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Managing Security

[<span class="code" style="font-weight: bold;">secadm create\_sshprof</span>](#secadm_create_sshprof)

[<span class="code" style="font-weight: bold;">secadm update\_sshprof</span>](#secadm_update_sshprof)

[<span class="code" style="font-weight: bold;">secadm import\_sshprof</span>](#secadm_import_sshprof)

[<span class="code" style="font-weight: bold;">secadm delete\_sshprof</span>](#secadm_delete_sshprof)

[<span class="code" style="font-weight: bold;">secdsp display\_sshprof</span>](#secdsp_display_sshprof)

[<span class="code" style="font-weight: bold;">secdsp select\_sshprof</span>](#secdsp_select_sshprof)

[<span class="code" style="font-weight: bold;">secdsp status\_sshprof</span>](#secdsp_status_sshprof)

[<span class="code" style="font-weight: bold;">secbase export\_sshprof</span>](#secbase_export_sshprof)

<a href="#secbase_import" class="MCXref xref">Importing an SSH Profile: secbase import</a>

[SSH Profile text file format](#SSH_Profile_text_file_format)

<span id="secadm_create_sshprof"></span>

## Creating an SSH Profile: secadm create\_sshprof

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><code style="font-weight: bold;">secadm create_sshprof {-sshprof_name (-shpf)}</code>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to create an SSH Security Profile .</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p>Mandatory</p>
<p><span class="code">-sshprof_name (-shpn)</span>: Enter the name of the SSH Profile to create.</p>
<p>Maximum: 31 characters.</p>
<p><strong>Notes:</strong></p>
<ul>
<li>Although specifying the public key algorithms and the authentication details are not mandatory, it is <strong>highly recommended</strong> that you do so. An SSH profile without the accepted public key algorithms and without the authentication details is not usable.</li>
<li>To get the complete parameters list, execute the command:<br />
<span class="code" style="font-weight: bold;">secadm create_sshprof ?</span></li>
<li>If <code>client_auth_methods </code>has both <code>PASSWORD </code>and <code>PUBLIC_KE</code>Y set:
<ul>
<li>if <span class="code">perform_all_auth_method</span> is set to <em>N</em>, the authentication method translates in Password <strong>or</strong> Public key</li>
<li>if <code>perform_all_auth_method</code> is set to <em>Y</em>, the authentication method translates in Password <strong>and</strong> Public key</li>
</ul></li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p>The following command creates an SSH Profile of type SERVER which accepts an RSA key:</p>
<p><code style="font-weight: bold;">secadm create_sshprof  –shpn “sshprof1” –shpt “SERVER” –sshppka “SSH_RSA”</code></p>         </td>
      </tr>
   </tbody>
</table>

<span id="secadm_update_sshprof"></span>

## Updating an SSH Profile: secadm update\_sshprof

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><code style="font-weight: bold;">secadm update_sshprof {-sshprof_name (-shpn)}</code>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to modify the parameters of a SSH Profile.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p>Mandatory</p>
<p><span class="code">-sshprof_name (-shpn)</span>: Enter the name of the SSH profile to update.</p>
<p><strong>Note</strong>: the name of the SSH profile cannot be changed.</p>
<p><strong>Note</strong>: to get the complete parameters list, execute the command:<br />
<code style="font-weight: bold;">secadm update_sshprof ?</code></p>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p>The following command modifies an SSH Profile to extend the list of accepted cipher suites and specify authentication details (private key):</p>
<p><code style="font-weight: bold;">secadm update_sshprof –shpn "sshprof1" -shpprvka “RSA_KEY”</code></p>         </td>
      </tr>
   </tbody>
</table>

<span id="secadm_import_sshprof"></span>

## Importing an SSH Profile: secadm import\_sshprof

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><span class="code" style="font-weight: bold;">secadm import_sshprof {-sshprof_file (-shpf)} {-encryption_key_file(-ekf)} {-import_pwd_cleartext}</span>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to import an SSH Security Profile from a text file into the local database.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p>Mandatory</p>
<p><span class="code">-sshprof_file (-shpf)</span>: Enter the name of the file that contains the SSH Profile to import.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">encryption_key_file</span> (<span class="code">-ekf</span>): Enter the path to the encryption key file to be used to decrypt passwords contained by the object to be imported</p>
<p>OR</p>
<p><span class="code">-import_pwd_cleartext:</span> Specifies a legacy import file containing unencrypted passwords.</p>
<p><strong>Notes:</strong></p>
<ul>
<li>Only one of the <span class="code">-encryption_key_file</span> or <span class="code">-import_pwd_cleartext</span> options should be used. Using one of the parameter is mandatory.</li>
<li>To get the complete parameters list, execute the command <strong>secadm import_sshprof ?</strong></li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p>To import an SSH Security Profile contained in the file <span class="code">sshprof_desc_file.txt</span>, enter:</p>
<p>secadm import_sshprof  –shpf &lt;sshprof_desc_file.txt&gt; -ekf &lt;decryption_key.dat&gt;</p>
<p>The Profile is described in the text file provided in the <span class="code" style="font-weight: bold;">-shpf</span> parameter, in this case: <span class="code">&lt;sshprof_desc_file.txt&gt;</span>. All of the Profile parameters are in this file.</p>
<p>The decryption key is specified in the <span class="code">-ekf</span> parameter. When importing an SSH Security Profile export file containing clear-text passwords, generated with an older version, use the <span class="code">-import_pwd_cleartext </span>parameter instead.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="secadm_delete_sshprof"></span>

## Deleting an SSH Profile: secadm delete\_sshprof

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p>secadm delete_sshprof {-sshprof_name (-shpn)}</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to delete an SSH Security Profile from the local database.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p>Mandatory</p>
<p><span class="code">-sshprof_name (-shpn)</span>: Enter the name of the SSH Profile.</p>
<p>Maximum: 31 characters.</p>
<p><strong>Note</strong>: to get the complete parameters list, execute the command:<br />
<code style="font-weight: bold;">secadm delete_sshprof ?</code></p>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p>The following command deletes an SSH Profile named <span style="font-style: italic;">sshprof1</span>:</p>
<p>secadm delete_sshprof  -shpn sshprof1</p>         </td>
      </tr>
   </tbody>
</table>

<span id="secdsp_display_sshprof"></span>

## Displaying an SSH Profile: secdsp display\_sshprof

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><code style="font-weight: bold;">secdsp display_sshprof {-sshprof_name (-shpn)}</code>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to display an SSH Security Profile in the database.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p>Mandatory</p>
<p><span class="code">-sshprof_name (-shpn)</span>: Enter the name of the SSH Profile.</p>
<p>Maximum: 31 characters.</p>
<p><strong>Note</strong>: to get the complete parameters list, execute the command:<br />
<code style="font-weight: bold;">secadm display_sshprof ?</code></p>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p>The following command displays the Security Profile named SSHPROF_CLI_01:</p>
<p>secdsp display_sshprof  -shpn sshprof_cli_01</p>
<p>Result:</p>
<p>[ General ]</p>
<p>shp_name = 'SSHPROF_CLI_01'</p>
<p>shp_type = 'CLIENT'</p>
<p>shp_state = 'ENABLED'</p>
<p>shp_exit_scheduling = 'N'</p>
<p>shp_key_exchange_algos = 'DH_GROUP1_SHA1'</p>
<p>shp_cipher_algos = 'AES128_CBC' '3DES_CBC' 'AES256_CBC'</p>
<p>shp_MAC_algos = 'HMAC_SHA1'</p>
<p>shp_compression_algos = 'ZLIB NONE'</p>
<p>shp_public_key_algos = 'SSH_DSS'</p>
<p>shp_client_auth_methods = 'PASSWORD'</p>
<p>shp_perform_all_auth_method = 'N'</p>
<p>shp_trust_hosted_public_keys = 'Y'</p>
<p>shp_remote_key_import = 'Y'</p>
<p>shp_trust_hosted_certificates = 'Y'</p>
<p>shp_remote_certificate_import = 'Y'</p>
<p>shp_MBytes_Before_New_Keys='1000'</p>
<p>shp_minutes_Before_New_Keys='60'</p>
<p>shp_xpp_entity_name = ''</p>
<p>shp_xpp_entity_password = ''</p>
<p><span class="code">shp_xpp_object_type='Entity'</span></p>
<p>shp_xpp_partner_entity_name = ''</p>
<p>shp_xpp_partner_object_type='Entity'</p>
<p> </p>
<p>[ AuthenticationAlias ]</p>
<p>shp_private_key_alias = 'KEY_CLI01_PRV'</p>
<p>shp_certificate_alias = ''</p>
<p> </p>
<p>[ AuthenticationControl ]</p>
<p>shp_issuer_certificate_alias = ''</p>
<p>shp_subject_name_pattern = ''</p>
<p>shp_issuer_name_pattern = ''</p>
<p> </p>
<p><span style="font-weight: bold;">Note:</span> The format is similar to the description file that you import, except that the fields have the prefix<span class="code"> shp_</span>.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="secdsp_select_sshprof"></span>

## Listing SSH Profile names: secdsp select\_sshprof

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><span class="code" style="font-weight: bold;">secdsp select_sshprof</span>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to list the names of all existing SSH Profiles in the database.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p>None</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p>Enter the command:</p>
<p>secdsp select_sshprof</p>
<p>Result:</p>
<p>SSHPROF_CLI_001</p>
<p>SSHPROF_SRV_001</p>         </td>
      </tr>
   </tbody>
</table>

<span id="secdsp_status_sshprof"></span>

## Listing SSH Profile abstracts: secdsp status\_sshprof

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><code style="font-weight: bold;">secdsp status_sshprof</code>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to display the status of each SSH Profile in the database.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p>None</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p>Enter the command:</p>
<p>secdsp status_sshprof</p>
<p>Result:</p>
<p>Name Type Exit Status</p>
<p>SSHPROF_CLI_001 CLIENT N ENABLED</p>
<p>SSHPROF_SRV_001 SERVER N ENABLED</p>         </td>
      </tr>
   </tbody>
</table>

<span id="secbase_export_sshprof"></span>

## Exporting SSH Security Profile objects: secbase export\_sshprof

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p><span class="code"><strong>secbase export_sshprof</strong> {-encryption_key_file} [-format] [-user_fmt] [-output] [-append]</span></p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to export the fields and field values of one or more SSH Security Profiles (SSHProfs). Gateway either displays the results on the screen or copies the results to an ASCII file. Use SSHProf attributes as selection criteria, as described below.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p><em>Mandatory</em></p>
<p><span class="code">-encryption_key_file</span>(<span class="code">-ekf</span>): Enter the path to the encryption key file to be used to encrypt passwords contained by the object.</p>         </td>
      </tr>
      <tr>
         <td><em>Optional</em>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-format (-of)</span>: Output format.</p>
<p>Enter one of the following values:</p>
<ul>
<li><span style="font-weight: bold;">S</span> = Shell (Default). Example: field = <span style="font-style: italic;">value</span></li>
<li><span style="font-weight: bold;">C</span> = C-Shell. Example: set field = <span style="font-style: italic;">value</span></li>
<li><span style="font-weight: bold;">U</span> = User format</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-user_fmt (-uf)</span>: User format definition.</p>
<p>Enter a character string including the keywords %N and %V, where:</p>
<ul>
<li>%N: name of field</li>
<li>%V: value of field</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-output (-f)</span>: Name of the file that results from the <span class="code" style="font-weight: bold;">secbase export_sshprof</span> command.</p>
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
<p><span class="code" style="font-weight: bold;">   secbase export_sshprof -ekf &lt;encryption_key.dat&gt; -n OldSSHProf  -f ExpSSHProf</span></p>
<p>Gateway creates the <span class="code">ExpSSHProf</span> export file. From the SSHProf object named <span class="code">OldSSHProf</span>, it extracts all fields and their corresponding values, and writes them to the <span class="code">ExpSSHProf</span> file.</p>
<p>The encryption key file <span class="code">&lt;encryption_key.dat&gt;</span> is used to encrypt passwords contained by the SSH Security Profile.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="SSH_Profile_text_file_format"></span>

## 

<span id="secbase_import"></span>

## Importing an SSH Profile: secbase import

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p>secbase import {-input(-if)} [-encryption_key_file(-ekf)] [-import_pwd_cleartext] [-sshprof(-shp)] [-error_free]</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to import an SSH Security Profile from a text file into the local database.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p><em>Mandatory</em></p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-sshprof </span>(<span class="code">-shp</span>): Enter this parameter without entering a value to import all SSH Security Profile objects contained in the file specified in the input parameter.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-encryption_key_file</span> (<span class="code">-ekf</span>): Enter the path to the encryption key file which will be used to decrypt passwords contained by the object to be imported.</p>
<p>OR</p>
<p><span class="code">-import_pwd_cleartext</span> : Specifies a legacy import file which contains unencrypted passwords.</p>
<blockquote>
<p><strong>Note:</strong></p>
<p>Only one of the -encryption_key_file or -import_pwd_cleartext options should be used. Using one of the parameters is mandatory.</p>
</blockquote>         </td>
      </tr>
      <tr>
         <td><em>Optional</em>         </td>
      </tr>
      <tr>
         <td><span class="code">-error_free</span>: Enter this parameter to create the different objects while ignoring the new parameters and without stopping the process at each error.         </td>
      </tr>
      <tr>
         <td>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p>To import an SSH Security Profile contained in the file <span class="code">sshprof_desc_file.txt</span>, enter:</p>
<p><span class="code">secbase import –if &lt;sshprof_desc_file.txt&gt; -ekf &lt;decryption_key.dat&gt; -shp</span></p>
<p>The Profile is described in the text file provided in the <span class="code">-if </span>parameter, in this case: <span class="code">&lt;sshprof_desc_file.txt&gt;</span>. All of the Profile parameters are in this file.</p>
<p>The decryption key is specified in the <span class="code">-ekf</span> parameter.</p>
<p>When importing an SSH Security Profile export file containing cleartext passwords, generated with an older version, use the <span class="code">-import_pwd_cleartext</span> parameter instead.</p>         </td>
      </tr>
   </tbody>
</table>

## SSH Profile text file format

Import SSH Security Profiles via a file that contains all the fields described in the Security Profile section. All unknown fields are ignored. If a field is absent or if the value is not correct, an error message is displayed and the import is aborted.

### Example of an SSH Profile text file


    [ General ]

    shp_name='SSHPROF_CLI_001'

    shp_type='CLIENT'

    shp_state='ENABLED'

    shp_exit_scheduling='N'

    shp_key_exchange_algos = 'DH_GROUP_EXCHANGE_SHA256'

    shp_cipher_algos = 'AES256_CTR' 'AES128_CTR'

    shp_mac_algos = 'HMAC_SHA256'

    shp_compression_algos = 'NONE'

    shp_public_key_algos = 'SSH_DSS'

    shp_client_auth_methods = 'PASSWORD'

    shp_perform_all_auth_method='N'

    shp_trust_hosted_public_keys='N'

    shp_remote_key_import='N'

    shp_trust_hosted_certificates='N'

    shp_remote_certificate_import='N'

    shp_MBytes_Before_New_Keys='1000'

    shp_minutes_Before_New_Keys='60'

    shp_xpp_entity_name='passport_entity'

    shp_xpp_entity_password='hPN6ANc5uWiHZB0yU48dq6nR/gNwWeag0aJ9Bl03oYBKsiVR3dHpms1
    KB2+I7o0NAAIDAgMACg8KDw=='

    shp_xpp_object_type='Entity'

    shp_xpp_partner_entity_name=''

    shp_xpp_partner_object_type='Entity'

     

    [ AuthenticationAlias ]

    shp_private_key_alias=''

    shp_certificate_alias=''

     

    [ AuthenticationControl ]

    shp_issuer_certificate_alias=''

    shp_subject_name_pattern=''

    shp_issuer_name_pattern=''

Related topics

[SSH protocol](../)

[Managing Keys and Certificates in SSH](../managing_keys_and_certificates_in_ssh)

[Using SSH](../using_ssh)

[Managing SSH Security Profiles](../ssh_security_profiles__gui_)

[SSH authentication](../ssh_authentication)

[SSH user exits](../../../../../gateway_userguide/customizing_gw_about/user_exits_about/user_exits_external/user_exits_ssh)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
