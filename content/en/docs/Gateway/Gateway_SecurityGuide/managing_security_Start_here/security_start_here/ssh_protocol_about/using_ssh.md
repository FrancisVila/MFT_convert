{
    "title": "Using SSH",
    "linkTitle": "Using SSH",
    "weight": "210"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Managing Security

[Installing SSH](#Installing_SSH)

[Configuring CGate objects for SSH use](#Configuring_CGate_objects_for_SSH)

[Configuring Remote Sites for SSH use](#Configuring_Remote_Sites_for_SSH)

<a href="#strong_weak" class="MCXref xref">Strong ciphers / weak ciphers</a>

[SSH usage example](#SSH_usage_example)

<span id="Installing_SSH"></span>

## Installing SSH

To install SSH processing on Gateway, select the SFTP file transfer protocol in the configuration menu.

<span id="Configuring_CGate_objects_for_SSH"></span>

## Configuring CGate objects for SSH use

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;">Field</span></p>         </td>
         <td><p>Description</p>         </td>
      </tr>
      <tr>
         <td><p><span style="font-weight: bold;">Public key alias</span></p>         </td>
         <td><p>Partner public key</p>
<p>Defines the public key to use to authenticate the partner.</p>         </td>
      </tr>
      <tr>
         <td><p><span style="font-weight: bold;">Public key group</span></p>         </td>
         <td><p>Key group name</p>
<p>Defines the group of the public key to use to authenticate the partner.</p>         </td>
      </tr>
      <tr>
         <td><p><span style="font-weight: bold;">Subject certificate alias</span></p>         </td>
         <td><p>Partner certificate</p>
<p>Defines the certificate to use to authenticate the partner.</p>         </td>
      </tr>
      <tr>
         <td><p><span style="font-weight: bold;">Issuer certificate alias</span></p>         </td>
         <td><p>Issuer certificate name</p>
<p>Defines the issuer (CA) certificate to use to authenticate the partner certificate.</p>         </td>
      </tr>
      <tr>
         <td><p><span style="font-weight: bold;">Subject name pattern</span></p>         </td>
         <td><p>Partner distinguished name pattern</p>
<p>Defines a filter template that the subject certificate must follow to be authenticated.</p>         </td>
      </tr>
      <tr>
         <td><p><span style="font-weight: bold;">Issuer name pattern</span></p>         </td>
         <td><p>Issuer distinguished name pattern</p>
<p>Defines a filter template that the issuer certificate must follow to be authenticated.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="strong_weak"></span>

## Strong ciphers / weak ciphers

### Ciphers using the CBC

Ciphers using the CBC (Cipher-Block Chaining) are considered weak, and their use is **strongly discouraged**.

A configuration option, `[ssh]enable_weak_ciphers` (default set to *yes*) is provided; if set to *no*, the cipher algorithms 3DES\_CBC, AES128\_CBC, AES256\_CBC and NONE are **not available** for the SSH protocol and configuring SSH profiles.

### Ciphers using the MD5 hash algorithm

The parameter <span class="code">\[monitor\]enable\_md5\_hash\_algorithm</span> enables ciphers using the MD5 hash algorithm.

When `enable_md5_hash_algorithm `is set to *no* and a cipher suite using the MD5 hash algorithm is selected, the HMAC\_MD5 and HMAC\_MD5\_96 hash algorithms are longer available for the SSH handshake and in the SSH security profile configuration.

<span id="Configuring_Remote_Sites_for_SSH"></span>

## Configuring Remote Sites for SSH use

To use SSH, you must configure Remote Sites to use the SFTP protocol and SSH network security type.

When you enable the SSH network security type for a Remote Site (server), you must define the SSH Profile.

The following table lists the SSH specific parameters to create or update Sites:

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;">Field</span></p>         </td>
         <td><p>Description</p>         </td>
      </tr>
      <tr>
         <td><p><span style="font-weight: bold;">Parameters to connect to Remote Site</span></p>         </td>
      </tr>
      <tr>
         <td><p><span style="font-weight: bold;">SSH Profile</span></p>         </td>
         <td><p>An existing SSH Profile name</p>
<p>Specifies which SSH Profile to use with the Remote Site.</p>         </td>
      </tr>
      <tr>
         <td><p><span style="font-weight: bold;">User name</span></p>         </td>
         <td><p>Login identifier</p>
<p>Specifies the user name you use to identify your Gateway client to the server partner this Site represents.</p>         </td>
      </tr>
      <tr>
         <td><p><span style="font-weight: bold;">Password</span></p>         </td>
         <td><p>Login password</p>
<p>Specifies the password you use to identify yourself to the server partner.</p>         </td>
      </tr>
      <tr>
         <td><p><span style="font-weight: bold;">Authentication alias</span></p>
<p>Only one of these two elements will be used, depending on the public key algorithm selected.</p>         </td>
      </tr>
      <tr>
         <td><p><span style="font-weight: bold;">Private key alias</span></p>         </td>
         <td><p>Local private key alias</p>
<p>Defines local private key used for authentication to a partner.</p>         </td>
      </tr>
      <tr>
         <td><p><span style="font-weight: bold;">Certificate alias</span></p>         </td>
         <td><p>Local certificate alias</p>
<p>Defines local certificate used for authentication to a partner.</p>         </td>
      </tr>
      <tr>
         <td><p><span style="font-weight: bold;">Remote Site authentication (initiator and responder mode)</span></p>
<p>Authentication Control parameters used to check the authenticity of a partner</p>         </td>
      </tr>
      <tr>
         <td><p><span style="font-weight: bold;">If the public key algorithm negotiated is a key pair algorithm:</span></p>         </td>
      </tr>
      <tr>
         <td><p><span style="font-weight: bold;">Public key alias</span></p>         </td>
         <td><p>Partner public key</p>
<p>Defines the public key to use to authenticate the partner.</p>         </td>
      </tr>
      <tr>
         <td><p><span style="font-weight: bold;">Public key group</span></p>         </td>
         <td><p>Key group name</p>
<p>Defines the group of the public key to use to authenticate the partner.</p>         </td>
      </tr>
      <tr>
         <td><p><span style="font-weight: bold;">Remote certificate filter</span></p>
<p>(If the public key algorithm negotiated is a certificate algorithm)</p>         </td>
      </tr>
      <tr>
         <td><p><span style="font-weight: bold;">Subject certificate alias</span></p>         </td>
         <td><p>Partner certificate name</p>
<p>Defines the certificate to use to authenticate the partner.</p>         </td>
      </tr>
      <tr>
         <td><p><span style="font-weight: bold;">Issuer certificate alias</span></p>         </td>
         <td><p>Issuer certificate name</p>
<p>Defines the issuer (CA) certificate to use to authenticate the partner certificate.</p>         </td>
      </tr>
      <tr>
         <td><p><span style="font-weight: bold;">Subject name pattern</span></p>         </td>
         <td><p>Partner distinguished name pattern</p>
<p>Defines a filter template that the subject certificate must follow to be authenticated.</p>         </td>
      </tr>
      <tr>
         <td><p><span style="font-weight: bold;">Issuer name pattern</span></p>         </td>
         <td><p>Issuer distinguished name pattern</p>
<p>Defines a filter template that the issuer certificate must follow to be authenticated.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="SSH_usage_example"></span>

## SSH usage example

To set up SSH for an SFTP transfer:

1.  Enable the SFTP option in the Gateway configuration menu.  
     
2.  Generate a DSS key with Open SSL. To generate the parameters file and private key <span class="code" style="font-weight: bold;">dsaparam1024.pem</span> and <span class="code" style="font-weight: bold;">dsaprv1024.pem</span> (includes a public key), enter the following commands:

openssl dsaparam -outform PEM -out dsaparam1024.pem -genkey 1024

openssl dsa -inform PEM -in dsaparam1024.pem -outform PEM -out dsaprv1024.pem

1.  Import the key manually into the database. To import the generated keys into the database, enter the following commands:

secadm import\_key  -name GW\_DSS\_PRV  -fn dsaprv1024.pem  -ff PEM  -algo DSS  -t PRIVATE  -cts "Generated with openssl DSS 1024"

1.  Create a CGateGroup and a CGate via the following commands:

peladm create\_cgategroup  -n CG\_SFTP\_GR  -state E  -pr SFTP  -sap "\*"  -ceda "\*"  -ts TSFTP  -vr /:\*:RWD:LRC:Y

peladm create\_cgate  -n CG\_SFTP  -pg CG\_SFTP\_GR  -s E  -lu "user1"  -cpo N  -ci "\*"  -cp "user1"

1.  Import two SSH Security Profiles. In the loop test cases, the public key is specified in the SSH Profile. In test cases towards another server, the public key is not known ahead of time. It will be imported if the <span class="code">remote\_certificate\_import</span> parameter is set to Y (yes) in the SSH Profile.

secadm import\_sshprof  -shpf SSHPROF\_LOOP\_PWD\_IN

secadm import\_sshprof  -shpf SSHPROF\_LOOP\_PWD\_OUT

The section <span style="font-weight: bold;">Authentication Alias</span> contains the local authentication information.

The section <span style="font-weight: bold;">Authentication Control</span> defines the characteristics of the Remote machine. These parameters are also defined in the Remote Site object.

1.  Create a Network Profile. To create a Network Profile to check incoming connections (port 6710 is declared on Gateway for SFTP) use the following commands:

secadm create\_netprof  -npn NPSSH\_ALL  -oa "\*.\*.\*.\*"  -da "\*.\*.\*.\*/6710"  -sec\_opt SSH  -sprof\_name SSHPROF\_LOOP\_PWD\_IN

1.  Create a Remote Site for a Gateway in Initiator mode to connect to a Gateway SFTP server.

peladm create\_site  -a SFTP\_LP\_CLT  -pi SV\_SFTP1  -pr SFTP  -nsopt SSH  -sshprf SSHPROF\_LOOP\_PWD\_OUT  -l\_id user1  -l\_pswd user1  -ct TCP  -da test.pc.pa.sopra/6710  -r\_max 10  -i\_max 10

1.  Create a Remote Site for a Gateway in Responder mode.

peladm create\_site  -a SFTP\_LP\_SRV  -pr SFTP  -nsopt SSH  -sshprf SSHPROF\_PC\_PWD\_OUT  -chkl\_id user1  –chkl\_password user1  -ct TCP  -r\_max 10  -i\_max 10

1.  Process a file transfer towards the Site configured in the previous step.

peltrans  -oa GW1  -da SFTP\_LP\_SRV  -fc toto-ban.txt  -appli FTP\_B  -mode I  -dir O

Related topics

[SSH protocol](../)

[Managing Keys and Certificates in SSH](../managing_keys_and_certificates_in_ssh)

[Managing SSH Security Profiles](../ssh_security_profiles__gui_)

[SSH authentication](../ssh_authentication)

[Managing SSH Security Profiles (command line)](../managing_ssh_security_profiles_cli)

[SSH user exits](../../../../../gateway_userguide/customizing_gw_about/user_exits_about/user_exits_external/user_exits_ssh)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
