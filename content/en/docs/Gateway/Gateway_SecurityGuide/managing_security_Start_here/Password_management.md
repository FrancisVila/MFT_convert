{
    "title": "Password management",
    "linkTitle": "Password Management",
    "weight": "110"
}<a href="#Secure" class="MCXref xref">Secure Password Storage</a>

<a href="#Creating" class="MCXref xref">Creating a Secure Password Storage using pelencpass</a>

<a href="#Secure_Password_Export" class="MCXref xref">Secure Password Export</a>

<span id="Secure"></span>

## Secure Password Storage

Password-based authentication usually requires a you to enter a password in order to gain access to a protected resource. The password can be said to be “stored” in the user’s memory; the system controlling the access to the resource must not store the password itself, but only enough information to validate the password - with no way of deriving the password data back from the stored information. A salted hash can be used to transform the password to a value which can be stored safely, while not allowing the reverse operation.

However, password-based authentication can also take place between software components communicating with each other. In this case, the password must be stored by the component authenticating (playing the role of the “user”), being possible to retrieve it when needed. A secure, encrypted storage is an absolute requirement for such sensitive data.

Gateway features a secure storage mechanism for passwords and other sensitive data (like encryption keys). The encryption is performed with a strong symmetric algorithm (AES 256 CBC), using a PBES2 encryption scheme.

Creating an encrypted password storage file set is done using the <span class="code">pelencpass</span> command. See [Creating a Secure Password Storage using <span class="code">pelencpass</span>](#Creating)).

Starting from a user input string (for generating the derived key) and the password, 3 files are created:

-   A salt file
-   A derived key file, containing the key used for securing the password
-   An encrypted password file, containing the password encrypted with the derived key

The <span class="code">pelencpass </span>command also allows reusing a previously generated derived key file.

## Using the Secure Password

Separate configuration entries for the 3 output files - the salt, derived key and encrypted password files - replaces the single entry for the password. The secure mechanism is implemented for PassPort AM/PassPort PM, SecureRelay and the SWIFTNet High Availability Database connection. Refer to the specific documentation sections for details regarding the new configuration parameters.

The encryption keys must be stored in a secure location, separate from the data they are protecting. Use operating system security features like local server access, Access Control Lists (ACLs), strong passwords and session timeouts to control access to the files containing encryption keys.

<span id="Creating"></span>

## Creating a Secure Password Storage using pelencpass

<table>
         
         
         
   
   <tbody>
      <tr>
         <td>Syntax         </td>
         <td><p>pelencpass  encrypt_pass</p>
<blockquote>
<p>{-encrypt_input_string(-encis)}</p>
<p>{-password_to_encrypt(-encpwd)}</p>
<p>{-salt_file(-saltf)}</p>
<p>{-derived_key_file(-dkf)}</p>
<p>{-encrypted_data_file(-encf)}</p>
<p>[-generate_key(-genkey) { (generate) | reuse }]</p>
<p>[-output_format(-fmt) { (binary) | base64 }]</p>
</blockquote>         </td>
      </tr>
      <tr>
         <td>Description         </td>
         <td>Use this command to generate the encryption key.         </td>
      </tr>
      <tr>
         <td>Parameters         </td>
         <td><ul>
<li><p><span class="code">password_to_encrypt(-encpwd)</span>: Enter the password to be encrypted.</p></li>
<li><p><span class="code">encrypt_input_string(-encis)</span>: Enter a user input string to generate the derived key (required when <span class="code">-generate_key</span> is <em>generate</em>).</p></li>
<li><p><span class="code">salt_file(-saltf)</span>: The full path to the file to store the salt.</p></li>
<li><p><span class="code">derived_key_file(-dkf)</span>: The full path to the file to store the derived key (when <span class="code">-generate_key</span> is <em>generate</em>), or that contains a previously generated derived key (when <span class="code">-generate_key</span> is <em>reuse</em>).</p></li>
<li><p><span class="code">encrypted_data_file(-encf)</span>: The full path to the file to store the encrypted password.</p></li>
<li><p><span class="code">generate_key(-genkey)</span>: Specify if a new key should be generated (<em>generate</em>, default) or if a previously generated key should be used (<em>reuse</em>).</p></li>
<li><p><span class="code">output_format(-fmt)</span>: Specify the output format.</p></li>
</ul>         </td>
      </tr>
   </tbody>
</table>

Once a derived key file is created, it can be reused by subsequent <span class="code">pelencpass encrypt\_pass </span>commands, by specifying the <span class="code">-generate\_key reuse</span> parameter. If <span class="code">-generate\_key</span> is set to *generate* (or not specified), a new derived key file will be created. Note that when creating a new key, any existing content of the derived key file will be overwritten.

The <span class="code">-output\_format</span> parameter specifies the output format as *binary* (default) or *base64*. <span class="mc-variable suite_variables.GatewayName variable">Gateway</span> configuration requires using the binary format encrypted files. The *base64* option converts the encrypted password to a human-readable BASE64 representation, the same as used in Gateway objects export files. For more information, see <a href="#Secure_Password_Export" class="MCXref xref">Secure Password Export</a>.

<span id="Login_for_operations"></span>

## Login for operations

The password used for authorizing operations on <span class="mc-variable suite_variables.GatewayName variable">Gateway</span> through commands (command line utility, exists, scripts) when access management is enabled is stored in encrypted form.

To use the online commands with user access security, Gateway uses the following environment variables to define the user login and user password:

User name:

-   p\_cs\_username

Password:

-   <span class="code">p\_cs\_dk\_file</span>: path to the key file used for password encryption (produced by <span class="code">pelencpass </span>tool)
-   <span class="code">p\_cs\_encpass\_file</span>: path to the encrypted password file (produced by <span class="code">pelencpass </span>tool)

## Password files

The encrypted password files are created with a <span class="mc-variable suite_variables.GatewayName variable">Gateway</span> tool named <span class="code">pelencpass</span>. For information about how to do this, see [Creating a Secure Password Storage using <span class="code">pelencpass</span>](#Creating) above.

<span id="Secure_Password_Export"></span>

## Secure Password Export

Some Gateway objects can contain passwords which would be revealed, if they were exported in a clear text form. Those objects include Remote Sites, Connection Gates (CGates) and Super CGates, Trading Partners, SSH Security Profiles and TLS Security Profiles.

Gateway offers a mandatory mechanism for encrypting such sensitive information in the export files. This is done by specifying an additional parameter (<span class="code">-encryption\_key\_file</span>) in the corresponding export command (<span class="code">pelbase</span>, <span class="code">secbase</span>). The password is first encrypted using the specified key, then BASE64-encoded. If the password field is not set, an empty value is used instead.

The encryption key file is an AES 256 symmetric key generated by the same mechanism as the derived key file generated using <span class="code">[pelencpass encrypt\_pass](#Creating)</span>; however, since only the encryption key file is needed, the syntax is simpler.

<table>
         
         
         
   
   <tbody>
      <tr>
         <td>Syntax         </td>
         <td><p>pelencpass generate_key</p>
<blockquote>
<p>{-encrypt_input_string(-encis)}</p>
<p>{-derived_key_file(-dkf)}</p>
<p>[-salt_file(-saltf)]</p>
</blockquote>         </td>
      </tr>
      <tr>
         <td>Description         </td>
         <td>Use this command to generate an AES 256 encryption key.         </td>
      </tr>
      <tr>
         <td>Parameters         </td>
         <td><ul>
<li><span class="code">encrypt_input_string(-encis)</span>: Enter a user input string to generate the derived key.</li>
<li><span class="code">derived_key_file(-dkf)</span>: The full path to file that contains the derived key.</li>
<li><span class="code">salt_file(-saltf)</span>: The full path to file that contains the salt.</li>
</ul>         </td>
      </tr>
   </tbody>
</table>

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
