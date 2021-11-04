{
    "title": "Managing certificates (command line)",
    "linkTitle": "Command line operations",
    "weight": "210"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Managing Security

[<span class="code" style="font-weight: bold;">secadm import\_cert</span>](#secadm_import_cert)

[<span class="code" style="font-weight: bold;">secadm update\_cert</span>](#secadm_update_cert)

[<span class="code" style="font-weight: bold;">secadm delete\_cert</span>](#secadm_delete_cert)

[<span class="code" style="font-weight: bold;">secbase export cert</span>](#secbase_export_cert)

[<span class="code" style="font-weight: bold;">secbase export\_cert\_chain</span>](#secbase_export_cert_chain)

[<span class="code" style="font-weight: bold;">secdsp select\_cert</span>](#secdsp_select_cert)

[<span class="code" style="font-weight: bold;">secdsp display\_cert</span>](#secdsp_display_cert)

[<span class="code" style="font-weight: bold;">secdsp status\_cert</span>](#secdsp_status_cert)

<span id="secadm_import_cert"></span>

## Importing a certificate: secadm import\_cert

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p><span class="code"><strong>secadm import_cert {-certificate_name} {-certificate_file}</strong> [-certificate_group] [-status] [-certificate_file_type] [-pos] [-list_only] [-certificate_type] [-certificate_password] [-private_key_file] [-private_key_file_type] [-private_key_password]</span></p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to import a certificate from a file into the local database.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p>Mandatory</p>
<p><span class="code">-certificate_name (-ctfn)</span>: Enter the name of the certificate to import.</p>
<p>Maximum: 31 characters</p>         </td>
      </tr>
      <tr>
         <td><p>Mandatory</p>
<p><span class="code">-certificate_file (-ctff)</span>: Enter the name of the file that contains the certificate to import.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-status (-cst)</span>: Enter the Status of the certificate you want to import.</p>
<p>Possible values:</p>
<ul>
<li><span style="font-weight: bold;">E</span> = Enabled (default)</li>
<li><span style="font-weight: bold;">D</span> = Disabled</li>
<li><span style="font-weight: bold;">C</span> = To check</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-certificate_file_type (-ctfft)</span>: Enter the encoding certificate file type.</p>
<p>Possible values:</p>
<ul>
<li><span style="font-weight: bold;">DER</span></li>
<li><span style="font-weight: bold;">BASE64</span></li>
<li><span style="font-weight: bold;">PKCS7</span></li>
<li><span style="font-weight: bold;">PKCS12</span></li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-pos</span>: Use this parameter to import only the certificate situated at this numbered position in the list.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-list_only</span>: Use this parameter to list the certificates contained in the file without importing them (PKCS12 only).</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-certificate_type (-ctft)</span>: Enter the certificate type. This parameter is mandatory if the imported certificate is an X.509 V1 certificate. For V3 certificates, Gateway determines the type automatically.</p>
<p>Possible values:</p>
<ul>
<li><span style="font-weight: bold;">USER</span> = User certificate</li>
<li><span style="font-weight: bold;">INTERMEDIATE</span> = Intermediate certification authority certificate</li>
<li><span style="font-weight: bold;">ROOT</span> = Root certification authority certificate</li>
<li><span style="font-weight: bold;">OTHER</span> = Undetermined type of certificate</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-certificate_password (-ctfp)</span>: Enter the password necessary to decrypt PKCS12 file.</p>
<p>Maximum: 16 characters.</p>
<p>This field is mandatory with the PKCS12 certificate file type. If it is not present, a password prompt is displayed.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-certificate_group (-ctfg)</span>:</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-private_key_file (-prkf)</span>: Enter the name of the separate file that contains private key elements.</p>
<p>Not required with full PKCS12 certificates</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-private_key_file_type (-prkft)</span>: Enter a type for the password file.</p>
<p>This parameter is mandatory when the <span style="font-style: normal;font-family: monospace;">–private_key_file</span> parameter is present.</p>
<p>Possible values:</p>
<ul>
<li><span style="font-weight: bold;">DER</span> = RSA private key structure</li>
<li><span style="font-weight: bold;">PKCS8</span> = PKCS8 structure</li>
<li><span style="font-weight: bold;">CR_PKCS8</span> = Encrypted PKCS8 structure</li>
<li><span style="font-weight: bold;">BASE64</span> = One of the above structures encoded with base64</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-private_key_password (-prkp)</span>: Enter the password required to decode an encrypted PKCS8 structure.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p>The following command imports the certificate contained in the file <span class="code">cert.cer</span> into the database and names it <span class="code">my_cert</span>. Since no file type is entered, the default value is used (<span style="font-style: italic;">DER</span>).</p>
<p>secadm import_cert  –certificate_name "my_cert"</p>
<p>–certificate_file "cert.cer"</p>
<p><span style="font-weight: bold;">Note:</span> The name of the certificate must be unique. The DN of the read certificate is checked to ensure that the certificate name is unique in the database.</p>
<p>When you import a user certificate, you must also import its associated private keys.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="secadm_update_cert"></span>

## Updating a certificate: secadm update\_cert

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p><span style="font-weight: bold;">secadm update_cert {-certificate_name}</span> [-certificate_group] [-status] [-certificate_type]</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to modify a certificate.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p>Mandatory</p>
<p><span class="code">-certificate_name (-ctfn)</span>: Enter the name of the certificate to modify.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-certificate_group (-ctfg)</span>:</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-status (-cst)</span>: Enter a Status for the specified certificate:</p>
<ul>
<li><span style="font-weight: bold;">E</span> = Enabled</li>
<li><span style="font-weight: bold;">D</span> = Disabled</li>
<li><span style="font-weight: bold;">C</span> = To check</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-certificate_type (-ctft)</span>: Enter the certificate type for the specified certificate.</p>
<p>Possible values:</p>
<ul>
<li><span style="font-weight: bold;">USER</span> = User certificate</li>
<li><span style="font-weight: bold;">INTERMEDIATE</span> = Intermediate certification authority certificate</li>
<li><span style="font-weight: bold;">ROOT</span> = Root certification authority certificate</li>
<li><span style="font-weight: bold;">OTHER</span> = Undetermined type of certificate</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p>The following command disables the use of the certificate <span class="code">my_cert</span> by resetting the status to<span style="font-style: italic;"> D (Disabled)</span>:</p>
<p>secadm update_cert  –certificate_name "my_cert"  –status D</p>         </td>
      </tr>
   </tbody>
</table>

<span id="secadm_delete_cert"></span>

## Deleting a certificate: secadm delete\_cert

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p>secadm delete_cert {-certificate_name}</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to remove a certificate from the database.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p>Mandatory</p>
<p><span class="code">-certificate_name (-ctfn)</span>: Enter the name of the certificate you want to delete.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p>The following command removes the certificate named <span class="code">my_cert</span>:</p>
<p>secadm delete_cert  –certificate_name "my_cert"</p>         </td>
      </tr>
   </tbody>
</table>

## Exporting a certificate: secbase <span id="secbase_export_cert"></span>export\_cert

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><code style="font-weight: bold;">secbase export_cert [-certificate_name] [-status] [-certificate_type] [-certificate_group] [-subject_name] [-subject_alt_name] [-issuer_name] [-output] [-append]</code>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td>Use this command to export a certificate from the local database to a file         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p><span><code>-certificate_name (-ctfn)</code>: Enter the name of the certificate to export.</span></p>
<p>Maximum: 31 characters</p>         </td>
      </tr>
      <tr>
         <td><p><span>-status (-cst): Enter the Status of the certificate you want to export.</span></p>
<p>Possible values:</p>
<ul>
<li><strong>E</strong><span> = Enabled (default)</span></li>
<li><p><strong>D</strong><span> = Disabled</span></p></li>
<li><p><strong>C</strong><span> = To check</span></p></li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span><code>-certificate_type (-ctft)</code>: Enter the certificate type for the certificate you want to export</span></p>
<p>Possible values:</p>
<ul>
<li><p><span style="font-weight: bold;">USER</span><span> = User certificate</span></p></li>
</ul>
<ul>
<li><p><span style="font-weight: bold;">INTERMEDIATE</span><span> = Intermediate certification authority certificate</span></p></li>
</ul>
<ul>
<li><p><span style="font-weight: bold;">ROOT</span><span> = Root certification authority certificate</span></p></li>
</ul>
<ul>
<li><p><span style="font-weight: bold;">OTHER</span><span> = Undetermined type of certificate</span></p></li>
</ul>         </td>
      </tr>
      <tr>
         <td>-certificate_group (-ctfg):         </td>
      </tr>
      <tr>
         <td>-subject_name (-csn): Enter the name stored in the Subject field of the public key as selection criteria for the certificate you want to export.         </td>
      </tr>
      <tr>
         <td><code>-subject_alt_name (-csa)</code><span>: Enter the name stored in the Subject_Alt field of the public key as selection criteria for the certificate you want to export.</span>         </td>
      </tr>
      <tr>
         <td><code>-issuer_name (-cin)</code><span>: Enter the Distinguished Name of the entity that signed and issued the certificates as selection criteria for the certificate you want to export.</span>         </td>
      </tr>
      <tr>
         <td><p><code>-output (-f)</code>: Name of the output file.</p>
<p>If you do not specify this parameter, the standard output file is used.</p>
<p>Maximum: 127 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p><code>-append (-ap)</code>: Concatenation at the end of the file (if it exists).</p>
<p>This parameter takes no value.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p><span>The following command exports the certificate with the name <code>my_cert </code>from database into the <code>file my_cert.outFile</code>.</span></p>
<p><code style="font-weight: bold;">secbase export_cert  –certificate_name "my_cert" -f my_cert.outFile</code></p>         </td>
      </tr>
   </tbody>
</table>

## Exporting a certificate chain: <span id="secbase_export_cert_chain"></span>secbase export\_cert\_chain

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p><code style="font-weight: bold;">secbase export_cert_chain [-certificate_name] [-status] [-certificate_type] [-human_readable] [-print_certificate_content] [-certificate_path_build_mode] [-output] [-append]</code></p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to display/export a certificate chain from the local database to a file</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p><span><code>-certificate_name (-ctfn)</code>: Enter the name of the certificate for which you want the certificate chain.</span></p>
<p>Maximum: 31 characters</p>         </td>
      </tr>
      <tr>
         <td><p><span><code>-status (-cst)</code>: Enter the Status of the certificate for which you want the certificate chain.</span></p>
<p>Possible values:</p>
<ul>
<li><span style="font-weight: bold;">E</span><span><strong> </strong>= Enabled (default)</span></li>
<li><span style="font-weight: bold;">D</span><span><strong> </strong>= Disabled</span></li>
<li><span style="font-weight: bold;">C</span><span><strong> </strong>= To check</span></li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span><code>-certificate_type (-ctft)</code>: Enter the certificate type of the certificate for which you want the certificate chain.</span></p>
<p>Possible values:</p>
<ul>
<li><span style="font-weight: bold;">USER</span><span> = User certificate</span></li>
<li><span style="font-weight: bold;">INTERMEDIATE</span><span> = Intermediate certification authority certificate</span></li>
<li><span style="font-weight: bold;">ROOT</span><span> = Root certification authority certificate</span></li>
<li><span style="font-weight: bold;">OTHER</span><span> = Undetermined type of certificate</span></li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><code>-h</code><span class="code_1"><code>uman_readable (-hr)</code>: displays the names of the certificates that builds the chain in an easier to view mode.</span></p>
<p>This parameter takes no value.</p>         </td>
      </tr>
      <tr>
         <td><p><code>-p</code><span class="code_1"><code>rint_certificate_content (-pcc)</code>: displays the content of the certificates that builds the chain, useful for moving a specific chain from a Gateway to another.</span></p>
<p>This parameter takes no value.</p>
<p><span>Note: print_certificate_content and human_readable cannot be used together.</span></p>         </td>
      </tr>
      <tr>
         <td><p><span><code>-certificate_path_build_mode (-cpbm)</code>: select the information used to build the certificate chain </span></p>
<p><span>Possible values:</span></p>
<ul>
<li><p><span style="font-weight: bold;">legacy </span><span>= based on matching issuer dn with Subject dn</span></p></li>
<li><p><span><strong>rfc4158</strong></span><span>= based on matching subject key ID with authority key ID certificate extensions.</span></p></li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><code>-output (-f)</code>: Name of the output file.</p>
<p>If you do not specify this parameter, the standard output file is used.</p>
<p>Maximum: 127 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p><code>-append (-ap)</code>: Concatenation at the end of the file (if it exists).</p>
<p>This parameter takes no value.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p><span>The following command d</span><span class="code_1">isplays</span><span> the certificate </span><span class="code_1">chain </span><span>for certificate with the name <code>my_cert</code>, in a parsable format, from database into the file <code>my_cert.outFile</code>.</span></p>
<p><code style="font-weight: bold;">secbase export_cert_chain  –certificate_name "my_cert" -f my_cert.outFile</code></p>
<p><span>#?BEGIN_CERT_CHAIN</span></p>
<p><span>[0][my_cert][ C=RO, O=Axway]</span></p>
<p><span>[1][root][ C=RO, O=Axway]</span></p>
<p><span>#?END_CERT_CHAIN</span></p>
<blockquote>
<p><strong>Note:</strong></p>
<p>Line format is :[number in chain] [gateway certificate name] [subject dn]</p>
</blockquote>
<blockquote>
<p><strong>Note:</strong></p>
<p>If the chain cannot be completed due to a missing certificate, a line like the following will be printed at the end of the chain:[-][----][ dn of the missing certificate]</p>
</blockquote>
<p> </p>
<p><span>The following command displays the certificate chain in a human readable format:</span></p>
<p><span style="font-weight: bold;">secbase export_cert_chain -ctfn "my_cert"  -f my_cert.outFile -hr</span></p>
<p><span>[1][root][ C=RO, O=Axway]</span></p>
<p>    \</p>
<p><span>    --&gt;[0][my_cert][ C=RO, O=Axway]</span></p>         </td>
      </tr>
   </tbody>
</table>

<span id="secdsp_display_cert"></span>

## Displaying a certificate: secdsp display\_cert

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p><span style="font-weight: bold;">secdsp display_cert {-certificate_name}</span> [-display_cert] [-display_key]</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to display names of certificates filtered by selection criteria.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p>Mandatory</p>
<p><span class="code">-certificate_name (-ctfn)</span>: Enter the name of the certificate to display.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-display_cert (-dspc)</span>: If present, certificate is displayed. No value required.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-display_key (-dspk)</span>: If present, key is displayed. No value required.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p>The following command displays attributes of the certificate named <span class="code">my_cert</span>:</p>
<p>secdsp display_cert  –certificate_name "my_cert"</p>         </td>
      </tr>
   </tbody>
</table>

<span id="secdsp_select_cert"></span>

## Listing certificate names: secdsp select\_cert

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p><span style="font-weight: bold;">secdsp select_cert</span> [-subject_name] [-subject_alt_name] [-issuer_name] [-status]</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to display a certificate.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p><span class="code">-subject_name (-csn)</span>: Enter the name stored in the Subject field of the public key as selection criteria for the certificate you want to display.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-subject_alt_name (-csa)</span>: Enter the name stored in the Subject_Alt field of the public key as selection criteria for the certificate you want to display.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-issuer_name (-cin)</span>: Enter the Distinguished Name of the entity that signed and issued the certificates as selection criteria for the certificate you want to display.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-status (-cst)</span>: Enter the Status as selection criteria for the certificate you want to display.</p>
<p>Possible values:</p>
<ul>
<li><span style="font-weight: bold;">E</span> = Enabled</li>
<li><span style="font-weight: bold;">D</span> = Disabled</li>
<li><span style="font-weight: bold;">C</span> = To check</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p>The following command displays the names of all the certificates in the database:</p>
<p>secdsp select_cert</p>         </td>
      </tr>
   </tbody>
</table>

<span id="secdsp_status_cert"></span>

## Listing certificate abstracts: secdsp status\_cert

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p><span style="font-weight: bold;">secdsp status_cert</span> [-subject_name] [-subject_alt_name] [-issuer_name] [-status]</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to display abstracts of the matched certificates.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p><span class="code">-subject_name (-csn)</span>: Enter the name stored in the Subject field of the public key as selection criteria for the certificate for which you want check the status.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-subject_alt_name (-csa)</span>: Enter the name stored in the Subject_Alt field of the public key as selection criteria for the certificate for which you want check the status.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-issuer_name (-cin)</span>: Enter the Distinguished Name of the entity that signed and issued the certificates as selection criteria for the certificate for which you want check the status.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-status (-cst)</span>: Enter the Status as selection criteria for the certificate for which you want check the status.</p>
<p>Possible values:</p>
<ul>
<li><span style="font-weight: bold;">E</span> = Enabled (default)</li>
<li><span style="font-weight: bold;">D</span> = Disabled</li>
<li><span style="font-weight: bold;">C</span> = To check</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p>The following command displays an abstract of each certificate in the database:</p>
<p>secdsp status_cert</p>         </td>
      </tr>
   </tbody>
</table>

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
