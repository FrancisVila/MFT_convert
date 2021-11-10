{
    "title": "Security best practices",
    "linkTitle": "Security best practices",
    "weight": "80"
}## Self-signed certificates

Using self-signed certificates may also be a security risk for many reasons, including:

-   Anyone can generate his own certificate and you need a very secure process to receive/send these certificates to make sure they are coming from the right partner. When using CA-signed certificates, you can rely on the CA.
-   If self-signed certificates are not securely stored, anyone change them. CA-signed certificates also must be securely stored, but no one can change them.
-   There is no way to revoke self-signed certificates.

## Privileged access user list

Maintain a list of users with privileged access. At a minimum, maintain a list of administrators and a list of users with access to multiple functions.

## Internet access limitation

As much as possible, limit the number of internet access points. Do not open useless Internet connections and limit interconnections with external networks as much as possible. This reduces the risk of external attacks and makes it easier to audit the product.

## Correct upgrade procedure

In the event of a possible vulnerability discovered in the product, you must be able to apply the patch or new Service Pack as soon as possible. Make sure you have the correct procedure to complete the upgrade. Always use the latest version of the product, if possible, as it contains fixes to known vulnerabilities.

## Generic or anonymous users

The term “generic users” means that the password is shared among multiple specific users. This makes it easier for an attacker to retrieve this password. In addition, the procedure to change shared passwords can be complicated and risky. In case of an incident, these generic or anonymous users make it impossible to determine who completed the erroneous action.

## Password policy

Password policy refers to size and complexity of the password, as well as to all the rules to manage this password. The size and complexity is important. The policy should define that the length be a minimum of 8 characters, contain a mix of alphabetic characters with numbers and special characters, and be case-sensitive.

Your password policy:

-   Must force passwords to be change periodically.
-   Should prohibit reuse of a password before n number of different passwords and within a certain period of time.
-   Must define how the password is created differently from the old one (such as: at least a certain number of different characters).
-   Must limit the number of failed attempts.

## Default authentication account

The product is delivered with the following default users:

-   User: admin
-   Password: can be chosen at install time. If none provided default password is <span class="code">admin</span>

Your first task after login with this user must be to create your own administrator account and to delete the default one, or at least to change this administrator password.

## Remote connections

You should limit your remote connections in the following ways:

-   If no one needs to access the product remotely, make sure that the UI ports are closed in your firewall.
-   If someone needs to connect remotely only occasionally, set a procedure to open the port only on demand.
-   If there are regular remote users, make sure that the connections are as secure as possible, such as using HSTS or VPN.

## Sensitive files and databases

You must protect your sensitive files and databases. The configuration file contains information that can be useful to a hacker. Even if part of this information is encrypted, access to this file must be restricted by your local access management. Only the product and one or two administrators should have access to this file in any mode (read, update, and delete).

The files containing the password used to generate encryption keys must be protected as well. This file is encrypted, but access to this file should only be granted to the product.

The file path to the passphrase used for encrypting the mailbox and database objects is configured through \[monitor\]ciphering\_passfile parameter.

### Location of files

-   The configuration files are located in $Gateway\_Home/run\_time/etc.
-   The name and location of the encryption key generating files are established when creating them using the <span class="code">pelencpass </span>command.

### List of sensitive files

The following files should have a high level of protection in Gateway:

-   the **mailbox** and the **object database files** in `run_time/data `directory of the installation:
    -   mailbox: `xfer.dat `and `xferb.dat`
    -   object databases: admin.dat, agenda.dat, cert.dat, cgate.dat, cgategroup.dat, dlist.dat, key.dat, model.dat, nprof.dat, profile.dat, proxy.dat, rules.dat, sgate.dat, sgateb.dat, sgategroup.dat, sgategroupb.dat, sprof.dat, sshprof.dat, trade.dat, user.dat
    -   The mailbox and object database files can be encrypted for higher level of protection, but they are not by default.
-   **certificate files**
    -   certificate for connecting to Passport - \[passport\]client\_cert\_file in configuration
    -   certificate for connecting to XSR RA - \[xsr\]master\_cert\_file in configuration
    -   certificate for connecting to Gateway server using the Navigator - \[cstcp\]TlsServerCertificateFile in configuration
-   **password files**  
    password files for XSR client certificate:
    -   \[xsr\]master\_cert\_password\_dkfile
    -   \[xsr\]master\_cert\_password\_saltfile
    -   \[xsr\]master\_cert\_password\_datafile

    password files for Passport client certificate:
    -   \[passport\]client\_cert\_password\_salt\_file
    -   \[passport\]client\_cert\_password\_dk\_file
    -   \[passport\]client\_cert\_password\_file

    password files for Passport login
    -   \[passport\]password\_salt\_file
    -   \[passport\]password\_dk\_file
    -   \[passport\]password\_file

    password files for XSR PKI login
    -   \[xsr\]pki\_password\_dkfile
    -   \[xsr\]pki\_password\_saltfile
    -   \[xsr\]pki\_password\_datafile

    shared secret files for Passport
    -   \[xsr\]pki\_password\_dkfile
    -   \[xsr\]pki\_password\_saltfile
    -   \[xsr\]pki\_password\_datafile

    password files for Swift HA database login
    -   \[swnet\]swnet\_ack\_userexit\_db\_salt\_file
    -   \[swnet\]swnet\_ack\_userexit\_db\_dk\_file
    -   \[swnet\]swnet\_ack\_userexit\_db\_password\_file
-   **configuration files**
    -   run\_time/etc/conffile – static configuration
    -   run\_time/etc/pelsetup.ini – static configuration
    -   run\_time/etc/dconfsave.ini – dynamic configuration
    -   run\_time/etc/pelsetup.def – default values
-   **temporary files**  
    Default location for temporary files is in `run_time/tmp`. The temporary files can be AES128 encrypted for a higher level of protection, but they are not by default. Use `[monitor]received_file_ciphered configuration` parameter to activate the received file encryption.

### Recommendations for files

When the product package is downloaded on the Axway Support web site, it is highly recommended:

-   to compute the hash of the downloaded file (a tool is required to do that)
-   to compare it with the hash that is displayed in the page you reach when clicking on the name of the package.  
    Both SHA 256 and MD5 hashes are displayed but it is safer to use SHA 256.

It is also recommended to protect files integrity after the product has been installed, using any file integrity monitoring tool.

  

<table>
   <tbody>
      <tr>
         <td>File
to monitor         </td>
         <td>Affected by...         </td>
         <td>Affected
by<span>  </span>users activity         </td>
      </tr>
      <tr>
         <td>Directory to monitor         </td>
         <td>files         </td>
         <td>Transfer mangmt         </td>
         <td>Partner mangmt         </td>
         <td>Event mangmt         </td>
         <td>Security mangmt         </td>
      </tr>
      <tr>
         <td>product
upgrade         </td>
         <td>Initial config         </td>
         <td>Uconf         </td>
      </tr>
      <tr>
         <td>$Gat<span>eway_Home/bin</span>         </td>
         <td>*.dll,*.exe         </td>
         <td>Yes         </td>
         <td>No         </td>
         <td>No         </td>
         <td>No         </td>
         <td>No         </td>
         <td>No         </td>
         <td>No         </td>
      </tr>
      <tr>
         <td>          </td>
         <td>capint         </td>
         <td>*.dll,*.LIB         </td>
         <td>Yes         </td>
         <td>No         </td>
         <td>No         </td>
         <td>No         </td>
         <td>No         </td>
         <td>No         </td>
         <td>No         </td>
      </tr>
      <tr>
         <td>UserGuide* &amp; sub-directories         </td>
         <td>*         </td>
         <td>Yes         </td>
         <td>No         </td>
         <td>No         </td>
         <td>No         </td>
         <td>No         </td>
         <td>No         </td>
         <td>No         </td>
      </tr>
      <tr>
         <td>$Gat<span>eway_Home/extras </span>         </td>
         <td>*.dll,*.LIB         </td>
         <td>Yes         </td>
         <td>No         </td>
         <td>No         </td>
         <td>No         </td>
         <td>No         </td>
         <td>No         </td>
         <td>No         </td>
      </tr>
      <tr>
         <td>          </td>
         <td>PassPort         </td>
         <td>*         </td>
         <td>Yes         </td>
         <td>No         </td>
         <td>No         </td>
         <td>No         </td>
         <td>No         </td>
         <td>No         </td>
         <td>No         </td>
      </tr>
      <tr>
         <td>Perl &amp; sub-directories         </td>
         <td>*         </td>
         <td>Yes         </td>
         <td>No         </td>
         <td>No         </td>
         <td>No         </td>
         <td>No         </td>
         <td>No         </td>
         <td>No         </td>
      </tr>
      <tr>
         <td>Sentinel<span>  </span>&amp; sub-directories         </td>
         <td>*         </td>
         <td>Yes         </td>
         <td>No         </td>
         <td>No         </td>
         <td>No         </td>
         <td>No         </td>
         <td>No         </td>
         <td>No         </td>
      </tr>
      <tr>
         <td>swnet &amp; sub-directories         </td>
         <td>*         </td>
         <td>Yes         </td>
         <td>No         </td>
         <td>No         </td>
         <td>No         </td>
         <td>No         </td>
         <td>No         </td>
         <td>No         </td>
      </tr>
      <tr>
         <td>$Gat<span>eway_Home/inc</span>         </td>
         <td>*         </td>
         <td>Yes         </td>
         <td>No         </td>
         <td>No         </td>
         <td>No         </td>
         <td>No         </td>
         <td>No         </td>
         <td>No         </td>
      </tr>
      <tr>
         <td>$Gat<span>eway_Home/jre*</span>         </td>
         <td>*         </td>
         <td>Yes         </td>
         <td>No         </td>
         <td>No         </td>
         <td>No         </td>
         <td>No         </td>
         <td>No         </td>
         <td>No         </td>
      </tr>
      <tr>
         <td>$Gat<span>eway_Home/licences</span>         </td>
         <td>*         </td>
         <td>Yes         </td>
         <td>No         </td>
         <td>No         </td>
         <td>No         </td>
         <td>No         </td>
         <td>No         </td>
         <td>No         </td>
      </tr>
      <tr>
         <td>$Gat<span>eway_Home/META-INF</span>         </td>
         <td>*         </td>
         <td>Yes         </td>
         <td>No         </td>
         <td>No         </td>
         <td>No         </td>
         <td>No         </td>
         <td>No         </td>
         <td>No         </td>
      </tr>
      <tr>
         <td>$Gat<span>eway_Homen/nlt &amp; sub-directories</span>         </td>
         <td>*         </td>
         <td>Yes         </td>
         <td>No         </td>
         <td>No         </td>
         <td>No         </td>
         <td>No         </td>
         <td>No         </td>
         <td>No         </td>
      </tr>
      <tr>
         <td>$Gat<span>eway_Home/obj</span>         </td>
         <td>*         </td>
         <td>Yes         </td>
         <td>No         </td>
         <td>No         </td>
         <td>No         </td>
         <td>No         </td>
         <td>No         </td>
         <td>No         </td>
      </tr>
      <tr>
         <td>          </td>
         <td>exitclnt         </td>
         <td>*         </td>
         <td>Yes         </td>
         <td>Yes         </td>
         <td>No         </td>
         <td>No         </td>
         <td>No         </td>
         <td>No         </td>
         <td>No         </td>
      </tr>
      <tr>
         <td>exitextc         </td>
         <td>*         </td>
         <td>Yes         </td>
         <td>Yes         </td>
         <td>No         </td>
         <td>No         </td>
         <td>No         </td>
         <td>No         </td>
         <td>No         </td>
      </tr>
      <tr>
         <td>exitrte         </td>
         <td>*         </td>
         <td>Yes         </td>
         <td>Yes         </td>
         <td>No         </td>
         <td>No         </td>
         <td>No         </td>
         <td>No         </td>
         <td>No         </td>
      </tr>
      <tr>
         <td>exituser         </td>
         <td>*         </td>
         <td>Yes         </td>
         <td>Yes         </td>
         <td>No         </td>
         <td>No         </td>
         <td>No         </td>
         <td>No         </td>
         <td>No         </td>
      </tr>
      <tr>
         <td>migexit         </td>
         <td>*         </td>
         <td>Yes         </td>
         <td>Yes         </td>
         <td>No         </td>
         <td>No         </td>
         <td>No         </td>
         <td>No         </td>
         <td>No         </td>
      </tr>
      <tr>
         <td>$Gat<span>eway_Home/run_time/</span>         </td>
         <td>          </td>
         <td>          </td>
         <td>No         </td>
         <td>          </td>
         <td>          </td>
         <td>          </td>
         <td>          </td>
      </tr>
      <tr>
         <td>          </td>
         <td>data         </td>
         <td> admin.dat,
trade.dat, cgate*.dat, sgate*.dat, dlist.dat, proxy.dat<br />
<br />
         </td>
         <td>Yes         </td>
         <td>Yes         </td>
         <td>No         </td>
         <td>No         </td>
         <td>Yes         </td>
         <td>No         </td>
         <td>No         </td>
      </tr>
      <tr>
         <td> cert.dat, nprof.dat, key.dat, sprof.dat,
sshprof.dat<br />
<br />
         </td>
         <td>Yes         </td>
         <td>Yes         </td>
         <td>No         </td>
         <td>No         </td>
         <td>No         </td>
         <td>No         </td>
         <td>Yes         </td>
      </tr>
      <tr>
         <td> model.dat         </td>
         <td>          </td>
         <td>          </td>
         <td>No         </td>
         <td>Yes         </td>
         <td>No         </td>
         <td>No         </td>
         <td>No         </td>
      </tr>
      <tr>
         <td> rules.dat, agenda.dat         </td>
         <td>          </td>
         <td>          </td>
         <td>No         </td>
         <td>No         </td>
         <td>No         </td>
         <td>Yes         </td>
         <td>No         </td>
      </tr>
      <tr>
         <td>etc         </td>
         <td> *.bat,
*.ini,<span> </span>         </td>
         <td>Yes         </td>
         <td>Yes         </td>
         <td>Yes         </td>
         <td>          </td>
         <td>          </td>
         <td>          </td>
         <td>          </td>
      </tr>
      <tr>
         <td>scripts &amp; subdir         </td>
         <td> *         </td>
         <td>Yes         </td>
         <td>Yes         </td>
         <td>Yes         </td>
         <td>No         </td>
         <td>No         </td>
         <td>No         </td>
         <td>No         </td>
      </tr>
      <tr>
         <td>$Gat<span>eway_Home/tools &amp; sub-directories</span>         </td>
         <td>*.dll,
*.exe, *.jar,<span> </span>         </td>
         <td>Yes         </td>
         <td>No         </td>
         <td>No         </td>
         <td>No         </td>
         <td>No         </td>
         <td>No         </td>
         <td>No         </td>
      </tr>
   </tbody>
</table>

**Notes:**

-   Files only modified on specific actions may also be modified during upgrade
-   All others file are modified at runtime and cannot be controlled by the monitoring tool.

<span id="identified_threats_and_possible_mitigations"></span>

## Identified threats and possible mitigations

During threat modeling process, several possible threats or weaknesses were identified:

-   **User exit and event scripts customization**:
    -   Gateway provides different user exits as entry points for custom code that modifies the Gateway behavior in different points of the flow of data. Please see the *User Guide > [External User exit](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/customizing_gateway/user_exits/user_exits_external.htm)* section for details about different user exits available.
    -   Also, in Gateway, you can define routing and scheduling rules that will handle different events. One of the routing/scheduling methods is through launching a script (e.g. perl, shell script, batch file).
    -   Both user exits and event scripts represent custom code that runs in Gateway context, meaning it will have the same privileges a Gateway process has.
    -   Please be aware that running custom code in Gateway context implies some potential risks if security best practices are not followed when writing custom user exits and event scripts.
    -   Risks include but are not limited to:
        -   compromise overall system functioning
        -   compromise different Gateway functionalities
        -   execute unwanted random/harmful code/commands
        -   compromise confidential data
    -   As Axway has little to no control over the way user exits are implemented, it is the implementor's responsibility to follow security procedures and best practices when writing custom code that will run in Gateway context.
    -   Possible mitigations and best-practices:
        -   always review and test a piece of code before running it in production
        -   use static and dynamic analysis tools (where available) for instrumenting, profiling and testing custom user exit and event script code
        -   never trust input data of the user exit or event script. Some of the values that a user exit or event script takes as input may come from untrusted sources (i.e. over the internet), even if it transits Gateway first. Gateway itself cannot encode/sanitize user input before passing it to the exit procedure, as Gateway doesn't know in advance the context where that data will be used and how to encode it/sanitize it. It is the custom user exit or event script implementors responsibility to validate input according to the data usage context.
        -   pay attention to buffer allocations and capacities. Always deallocate heap memory allocated within an exit. Always check sizes before reading/writing
        -   avoid (where possible) launching new processes from the user exit. The child process would run with Gateway privileges but will not be under Gateway's control. If you do launch child processes from the user exit, the same security concernsand verifications should be applied to the child process as for the user exit code itself.
        -   avoid storing or transmitting sensitive data in clear text  
-   **User / password can be sent plain text trough the URL**
    -   Possible mitigations and best practices: for HTTP connections, use TLS security over TCP (HTTPS) with mutual authentication. Avoid using Web basic authentication, where credentials are sent through the URL. Choose more secure authentication methods, like session cookie ID.  
-   **Private keys are not encrypted by default**
    -   Possible mitigations and best practices: database object files, including keys and certificates database files are not encrypted by default. It is recommended to AES128 encrypt the object database files using \[monitor\]ciphering\_option configuration parameter.  
-   **No mechanism that forces the change of the default password of the default admin user**
    -   Best practice: if not set at installation time, change the default password of the predefined admin user immediately after the installation.
-   **Configuration & the security configuration can be changed by command line that does not request any authentication**
    -   Best practice: it is recommended that access to configuration and database files be strictly controlled. See also the previous paragraph regarding the sensitive files.
-   **User passwords are not hashed and Salted in the system**
    -   Possible mitigations and best practices: CGate and SGate objects can keep the user passwords hashed, but they are not configured to do so by default. It is recommended to activate this option through \[monitor\]disable\_password\_regex='yes' and \[monitor\]cgate\_hashed\_password='yes' configuration parameters.
    -   For the other passwords it is recommended to encrypt the object database files. It is recommended to AES128 encrypt the object database files using \[monitor\]ciphering\_option configuration parameter.

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
