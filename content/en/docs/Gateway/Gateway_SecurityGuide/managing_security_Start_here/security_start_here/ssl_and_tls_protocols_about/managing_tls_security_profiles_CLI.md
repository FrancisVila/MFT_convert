{
    "title": "Managing TLS Security Profiles (command line)",
    "linkTitle": "Managing TLS Security Profiles (command line)",
    "weight": "250"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Managing Security

[<span class="code" style="font-weight: bold;">secadm create\_sprof</span>](#secadm_create_sprof)

[<span class="code" style="font-weight: bold;">secadm update\_sprof</span>](#secadm_update_sprof)

[<span class="code" style="font-weight: bold;">secadm import\_sprof</span>](#secadm_import_sprof)

[<span class="code" style="font-weight: bold;">secadm delete\_sprof</span>](#secadm_delete_sprof)

[<span class="code" style="font-weight: bold;">secdsp display\_sprof</span>](#secdsp_display_sprof)

[<span class="code" style="font-weight: bold;">secdsp select\_sprof</span>](#secdsp_select_sprof)

[<span class="code" style="font-weight: bold;">secdsp status\_sprof</span>](#secdsp_status_sprof)

[<span class="code" style="font-weight: bold;">secbase export\_sprof</span>](#secbase_export_sprof)

[TLS Profile file format](#TLS_Profile_file_format)

<span id="secadm_create_sprof"></span>

## Creating a TLS Profile : secadm create\_sprof

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><code>secadm create_sprof {-sprof_name (-spn)}</code>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to create a TLS Profile.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p>Mandatory</p>
<p><span class="code">-sprof_name (-spn)</span>: Enter the name of the TLS profile to create.</p>
<p><strong>Note</strong>: although specifying the TLS versions is not mandatory, it is highly recommended that you do it. A TLS profile without the accepted TLS versions specified is not usable.</p>
<p><strong>Note</strong>: to get the complete parameters list, execute the command :<br />
<strong>secadm create_sprof ?</strong></p>         </td>
      </tr>
      <tr>
         <td>          </td>
         <td><p>Optional</p>
<p><span class="code">-sprof_ciph_suites</span> (<span class="code">-spcsu</span>) : enter a comma-separated string list of up to 32 cypher suites to secure the connection.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p>The following command creates a basic TLS SERVER profile supporting TLS 1.1 and TLS 1.2 versions, with the default cipher suites selected: RSA_WITH_3DES_EDE_CBC_SHA and RSA_WITH_AES_128_CBC_SHA:</p>
<p><code style="font-weight: bold;">secadm create_sprof  –spn "sprof1" -sptv “TLSv11, TLSv12”</code></p>
<p><strong>Note</strong>: The name of the TLS Profile must be unique.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="secadm_update_sprof"></span>

## Updating a TLS Profile : secadm update\_sprof

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><code>secadm update_sprof {-sprof_name (-spn)}</code>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to modify the parameters of a TLS Profile.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p>Mandatory</p>
<p><span class="code">-sprof_name (-spn)</span>: Enter the name of the file that contains the TLS Profile to import.</p>
<p><span style="font-weight: bold;">Note:</span> The name of the TLS Profile cannot be changed.</p>
<p><span style="font-weight: bold;">Note:</span> To get the complete parameters list, execute the command:<br />
<span class="code" style="font-weight: bold;">secadm update_sprof ?</span></p>         </td>
      </tr>
      <tr>
         <td>          </td>
         <td><p>Optional</p>
<p><span class="code">-sprof_ciph_suites</span> (<span class="code">-spcsu</span>) : enter a comma-separated string list of up to 32 cypher suites to secure the connection.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p>The following command modifies a TLS Profile to extend the list of accepted cipher suites and to set client authentication mandatory:</p>
<p>secadm update_sprof –spn "sprof1" -spclia TLS_AUT_MANDATORY -spcsu “RSA_WITH_3DES_EDE_CBC_SHA, RSA_WITH_AES_128_CBC_SHA, RSA_WITH_NULL_MD5, RSA_WITH_RC4_128_MD5”</p>         </td>
      </tr>
   </tbody>
</table>

<span id="secadm_import_sprof"></span>

## Importing a TLS Profile : secadm import\_sprof

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><code>secadm import_sprof {-sprof_file (-spf)} {-encryption_key_file (-ekf)} {-import_pwd_cleartext }</code>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to import a TLS Profile from a file into the local database.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><table>
   <tbody>
      <tr>
         <td><p>Mandatory</p>
<p><span class="code">-sprof_file (-spf)</span>: Enter the name of the file that contains the TLS Profile to import.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-encryption_key_file</span> (<span class="code">-ekf</span>): Enter the path to the encryption key file to be used to decrypt passwords contained by the object to be imported</p>
<p>OR</p>
<p><span class="code">-import_pwd_cleartext</span>: Specifies a legacy import file containing unencrypted passwords.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Notes:</strong></p>
<ul>
<li>Only one of the <span class="code">-encryption_key_file</span> or <span class="code">-import_pwd_cleartext</span> options should be used. Using one of the parameter is mandatory.</li>
<li>To get the complete parameters list, execute the command <strong>secadm import_sshprof ?</strong></li>
</ul>         </td>
      </tr>
   </tbody>
</table>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p>The following command imports the TLS Profile contained in the file <span class="code">sprof1.sprof</span> into the database:</p>
<p>secadm import_sprof  –sprof_file "sprof1.sprof" -ekf &lt;decryption_key.dat&gt;</p>
<p><span style="font-weight: bold;">Note:</span> The name of the TLS Profile must be unique.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="secadm_delete_sprof"></span>

## Deleting a TLS Profile: secadm delete\_sprof

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><span class="code" style="font-weight: bold;">secadm delete_sprof</span><code>  {-sprof_name (-spn)}</code>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to delete a TLS Profile.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p>Mandatory</p>
<p><span class="code">-sprof_name (-spn)</span>: Enter the name of the TLS Profile.</p>
<p>Maximum: 31 characters.</p>
<p><strong>Note</strong>: to get the complete parameters list, execute the command <code style="font-weight: bold;">secadm delete_sprof ?</code></p>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p>The following command deletes the TLS Profile named <span style="font-style: italic;">sprof_1</span>:</p>
<p>secadm delete_sprof –sprof_name "sprof_1"</p>         </td>
      </tr>
   </tbody>
</table>

<span id="secdsp_display_sprof"></span>

## Displaying a TLS Profile: secdsp display\_sprof

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><code style="font-weight: bold;">secdsp display_sprof {-sprof_name (-spn)}</code>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to display a TLS Profile.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p>Mandatory</p>
<p><span class="code">-sprof_name (-spn)</span>: Enter the name of the TLS Profile.</p>
<p><strong>Note</strong>: to get the complete parameters list, execute the command:<br />
<code style="font-weight: bold;">secadm display_sprof ?</code></p>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p>The following command displays the TLS Profile named <span style="font-weight: bold;">sprof_1</span>:</p>
<p>secdsp display_sprof  -spn SPROF_INEXP</p>
<p>sp_name='SPROF_INEXP'</p>
<p>sp_type='SERVER'</p>
<p>sp_tls_versions = 'SSLv3' 'TLSv1'</p>
<p>sp_cache_enabled='N'</p>
<p>sp_exit_scheduling='N'</p>
<p>sp_un-upgraded_partner_refused='N'</p>
<p>sp_renegotiate_enabled='disabled'</p>
<p>sp_close_notify_disabled='Y'</p>
<p>sp_client_auth_policy='TLS_AUT_MANDATORY'</p>
<p>sp_server_auth_policy='TLS_AUT_MANDATORY'</p>
<p>sp_path_depth='15'</p>
<p>sp_user_param=''</p>
<p>sp_cipher_suites = 'RSA_WITH_3DES_EDE_CBC_SHA' 'RSA_WITH_AES_128_CBC_SHA'</p>
<p>sp_ft_sec_option='explicit'</p>
<p>sp_ft_session_policy='optional'</p>
<p>sp_ft_data_policy='optional'</p>
<p>sp_trust_hosted_certificates='N'</p>
<p>sp_remote_certificate_import='N'</p>
<p>sp_xpp_entity_name='EU3'</p>
<p>sp_xpp_entity_password='test'</p>
<p>sp_xpp_object_type='Entity'</p>
<p>sp_xpp_partner_entity_name=''</p>
<p>sp_xpp_partner_object_type='Entity'</p>
<p>sp_sprof_path_build_mode='rfc4158'</p>         </td>
      </tr>
   </tbody>
</table>

<span id="secdsp_select_sprof"></span>

## Listing all TLS Profile names: secdsp select\_sprof

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><code style="font-weight: bold;">secdsp select_sprof</code>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to list the names of all existing TLS Profiles.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p>None</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p>secdsp select_sprof</p>         </td>
      </tr>
   </tbody>
</table>

<span id="secdsp_status_sprof"></span>

## Listing all TLS Profile abstracts: secdsp status\_sprof

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><code style="font-weight: bold;">secdsp status_sprof</code>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to display an abstract of each TLS Profile.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p>None</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p>Enter the command:</p>
<p>secdsp status_sprof</p>
<p>Result:</p>
<p>Name Type  Exit Cache Client_auth Server _auth</p>
<p>SP   Server  N     N    Optional     Mandatory</p>         </td>
      </tr>
   </tbody>
</table>

<span id="secbase_export_sprof"></span>

## Exporting TLS Security Profile objects: secbase export\_sprof

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p><span class="code"><strong>secbase export_sprof</strong> <code>{-encryption_key_file} [-format] [-user_fmt] [-output] [-append]</code></span></p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to export the fields and field values of one or more TLS Security Profiles (SProfs). Gateway either displays the results on the screen or copies the results to an ASCII file. Use SProf attributes as selection criteria, as described below.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p><em>Mandatory</em></p>
<p><span class="code">-encryption_key_file</span> (<span class="code">-ekf</span>): Enter the path to the encryption key file to be used to decrypt passwords contained by the object to be imported</p>         </td>
      </tr>
      <tr>
         <td><em>Optional</em>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-format (-of)</span>: Output format.</p>
<p>Enter one of the following values:</p>
<ul>
<li><span style="font-weight: bold;">S</span> = Shell (example: field = <span style="font-style: italic;">value</span>). (Default)</li>
<li><span style="font-weight: bold;">C</span> = C-Shell (example: set field = <span style="font-style: italic;">value</span>)</li>
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
         <td><p><span class="code">-output (-f)</span>: Name of the output file.</p>
<p>Maximum: 127 alphanumeric characters.</p>
<p>If you do not specify this parameter, the standard output file is used.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-append (-ap)</span>: Concatenation at the end of the file (if it exists).</p>
<p>This parameter takes no value.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p>Enter the command:</p>
<p>secbase export_sprof</p>
<p>-ekf &lt;encryption_key.dat&gt;</p>
<p>-n SProf1</p>
<p>-f ExpSProf</p>
<p>Gateway creates the <span class="code">ExpSProf</span> export file. From the SProf object named SProf1, it extracts all fields and their corresponding values, and writes them to the <span class="code">ExpSProf</span> file.</p>
<p>The encryption key file <span class="code">&lt;encryption_key.dat&gt;</span> will be used to encrypt passwords contained by the SSH Security Profile.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="TLS_Profile_file_format"></span>

## Importing a TLS Profile: secbase import

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p><span class="code">secbase import {-input(-if)} {-encryption_key_file(-ekf)} {-import_pwd_cleartext} {-sprof(-sp)} [-error_free]</span></p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to import an TLS Profile from a text file into the local database.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p><em>Mandatory</em></p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-input (-if)</span>: Enter the name of the file that contains the TLS Security Profile to import.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-encryption_key_file</span> (<span class="code">-ekf</span>): Enter the path to the encryption key file which will be used to decrypt passwords contained by the object to be imported.</p>
<p>OR</p>
<p><span class="code">-import_pwd_cleartext</span>: Specifies a legacy import file which contains unencrypted passwords.</p>
<blockquote>
<p><strong>Note:</strong></p>
<p>Only one of the -encryption_key_file or -import_pwd_cleartext options should be used. Using one of the parameters is mandatory.</p>
</blockquote>         </td>
      </tr>
      <tr>
         <td><span class="code">-sprof</span> (<span class="code">sp</span>): Enter this parameter without entering a value to import all TLS Security Profile objects contained in the file specified in the input parameter.         </td>
      </tr>
      <tr>
         <td><em>Optional</em>         </td>
      </tr>
      <tr>
         <td><span class="code">-error_free</span>: Enter this parameter to create the different objects while ignoring the new parameters and without stopping the process at each error.         </td>
      </tr>
      <tr>
         <td><blockquote>
<p><strong>Note:</strong></p>
<p>To get the complete list of parameters, execute the command secbase import ?</p>
</blockquote>         </td>
      </tr>
      <tr>
         <td>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p>To import a TLS Security Profile contained in the file <span class="code">tlsprof_desc_file.txt</span>, enter:</p>
<p><span class="code">secbase import –if &lt;tlsprof_desc_file.txt&gt; -ekf &lt;decryption_key.dat&gt; -sp
</span></p>
<p>The Profile is described in the text file provided in the <span class="code">-if</span> parameter, in this case: <span class="code">&lt;tlsprof_desc_file.txt&gt;</span>. All of the Profile parameters are in this file.</p>
<p>The decryption key is specified in the <span class="code">-ekf </span>parameter.</p>
<p>If you have to import a TLS Security Profile export file containing cleartext passwords, generated with an older version, use the <span class="code">-import_pwd_cleartext</span> parameter instead.</p>         </td>
      </tr>
   </tbody>
</table>

## TLS Profile file format

Import TLS Profiles using a file that contains all the fields described in the Security Profile section. All unknown fields are ignored. If a field is absent or if the value is not correct, an error message is displayed and the import is aborted.

### Example of a TLS Profile file



    sp_name='SPROF1'

    sp_type='SERVER'

    sp_tls_versions = 'TLSv12'

    sp_cache_enabled='N'

    sp_exit_scheduling='N'

    sp_un-upgraded_partner_refused='N'

    sp_renegotiate_enabled='disabled'

    sp_close_notify_disabled='N'

    sp_client_auth_policy='TLS_AUT_MANDATORY'

    sp_server_auth_policy='TLS_AUT_MANDATORY'

    sp_path_depth='7'

    sp_user_param=''

    sp_cipher_suites = 'ECDHE_RSA_WITH_AES_256_GCM_SHA384' 'ECDHE_RSA_WITH_AES_128_G
    CM_SHA256' 'DHE_RSA_WITH_AES_256_GCM_SHA384' 'DHE_RSA_WITH_AES_128_GCM_SHA256' '
    RSA_WITH_AES_256_GCM_SHA384' 'RSA_WITH_AES_128_GCM_SHA256'

    sp_ft_sec_option='implicit'

    sp_ft_session_policy='optional'

    sp_ft_data_policy='optional'

    sp_protocol_header_policy='unused'

    sp_trust_hosted_certificates='Y'

    sp_remote_certificate_import='Y'

    sp_xpp_entity_name='PassPort_Entity'

    sp_xpp_entity_password='vUvLAyN0qg+XMM//1jgotgIGG9bNs2yX7MH/shiKM6ZuAa72jDwtVAcg
    vzi7uTuVAAIBAgIKCwUgCg=='

    sp_xpp_object_type='Entity'

    sp_xpp_partner_entity_name=''

    sp_xpp_partner_object_type='Entity'

     
    [ UserLocalCertificate ]

    sp_certificate_name='AxwayHTTP_Server'

     

    [ AcceptedAuthorities ]

    [ RemoteUserCertificate ]

    [ RemoteCACertificate ]

    [ RemoteRootCertificate ]

Related topics

<a href="../tls_security_profiles__gui_" class="MCXref xref">Managing TLS Security Profiles</a>

<a href="../managing_tls" class="MCXref xref">Managing TLS</a>

<a href="../tls_cipher_suites" class="MCXref xref">TLS cipher suites</a>

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
