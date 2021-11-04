{
    "title": "About Trusted File for file encryption",
    "linkTitle": "Using TrustedFile for file encryption",
    "weight": "210"
}## Encryption concepts

This topic describes how to implement Axway Trusted File encoding. <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> in conjunction with TrustedFile enables you to send encrypted files in S/MIME, CMS, and OpenPGP format, for increased security for data exchanges. To initiate this additional security, Transfer CFT delivers a set of samples and certificates to implement TrustedFile in your environment. To get started using TrustedFile with Transfer CFT, read the following sections:

-   [Before you start](#Before)
-   [About the Transfer CFT configuration file](#Transfer)
-   [Defining the unified configuration parameters](#Defining)
-   [Command example (to encode/decode a file)](#Command)

The topic [Delivered files and certificates](tf_delivered_files_certficates) describes the scripts, conversion tables, files and samples delivered with Transfer CFT. And for more information on TrustedFile functionality, please refer to the [TrustedFile Reference Guide](#) .

#### Limitations

-   You cannot use <span class="mc-variable Primary.CG or_UM variable">Central Governance</span> or <span class="mc-variable suite_variables.FlowManager variable">Flow Manager</span> to manage <span class="mc-variable suite_variables.TrustedFileName variable">TrustedFile</span> functionality with <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span>.

<span id="Before"></span>

## Before you start

In Transfer CFT you use the CFTTF utility, referred to as XPPTF in TrustedFile, to perform secured exchanges. To use this functionality your Transfer CFT key must include the Trusted File option. The Transfer CFT key is located in the file: <span class="code">$CFTDIRRUNTIME/conf/cft.key</span>. If your product key does not include the Trusted File option if you try to execute the CFTTF program, an error will occur and an error message is displayed in the CFTLOG file: <span class="code">CFTR19E XPPCFG\_Error\_#20:\_Invalid\_product\_key</span>.

Transfer CFT delivers useable examples that automatically implement TrustedFile in your preprocessing and post processing flow. The next section describes the delivered samples.

<span id="Transfer"></span>

## Understanding the delivered sample configuration file

The Transfer CFT sample configuration file <span class="code">runtime/conf/cft-tf-smp.conf</span> includes the TrustedFile IDF as shown here.

-   The delivered procedures are called during the preprocessing phase to encode the file (tf\_cipher.cmd), and delete the encoded file after sending (tf\_delfile.cmd).
-   The post processing script decodes on the receiving side (tf\_decipher.cmd).

Sending

<table>
   <tbody>
      <tr>
         <td>cftsend id = trusted_file,<br />
ftype = B,<br />
fcode = BINARY,<br />
fname = pub/FTEST,<br />
EXEC = $CFTDIREXEC/tf/tf_delfile.cmd,<br />
PREEXEC = $CFTDIREXEC/tf/tf_cipher.cmd,<br />
mode = replace         </td>
      </tr>
   </tbody>
</table>

Receiving

<table>
   <tbody>
      <tr>
         <td>cftrecv id = trusted_file,<br />
ftype = B,<br />
fcode = BINARY,<br />
fname = $CFTDIRPUB/TF_&amp;part_&amp;idtu,<br />
EXEC = $CFTDIREXEC/tf/tf_decipher.cmd,<br />
faction = delete ,<br />
fdisp = both,
mode = replace         </td>
      </tr>
   </tbody>
</table>

<span id="Defining"></span>

## Defining the unified configuration parameters

The Transfer CFT installation process automatically sets the following Transfer CFT unified configuration parameters to enable <span class="mc-variable suite_variables.TrustedFileName variable">TrustedFile</span> functioning. For information on uconf, see [About the Unified Configuration](../../admin_intro/uconf).

<table>
   <th>
      <tr>
<th>Parameter (uconf)         </th>
<th>Default values         </th>
<th>Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>tf.proofslocation         </td>
         <td>&lt;HOME&gt;/Axway/Transfer_CFT/runtime/data/tf         </td>
         <td>References the absolute path to the directory that the product uses to generate proofs         </td>
      </tr>
      <tr>
         <td>tf.proofsenabled         </td>
         <td>yes         </td>
         <td>Indicates whether proofs are enabled or not. This field takes the value yes or no (yes by default). If the value is set to no, the generation of proofs is deactivated         </td>
      </tr>
      <tr>
         <td>tf.messageslocation         </td>
         <td>&lt;HOME&gt;/Axway/Transfer_CFT/home/distrib/tf/english         </td>
         <td>Transfer CFT runtime directory         </td>
      </tr>
      <tr>
         <td>tf.entitieslocation         </td>
         <td>$HOME/Axway/Transfer_CFT/runtime/conf/tf/entities.xml         </td>
         <td><p>Indicates the TrustedFile configuration path.</p>
<p>If the <span class="bold_in_para">tf.entitieslocationtype</span> is:</p>
<ul>
<li>Local: Points locally to the entities.xml file by default</li>
<li>Remote: Configures the PassPort PS server host and listening port. Enter the same values that are used in the unified configuration for the following PassPort values:<br />
&lt;xppServer host="<span class="bold_in_para">pki.passport.hostname</span>"&gt;, &lt;xp3Protocol port="<span class="bold_in_para">pki.passport.port</span>"&gt;<br />
<span class="bold_in_para">Example</span>: <span class="code">&lt;xppServer host="172.17.171.202"&gt;, &lt;xp3Protocol port="7000"&gt;</span></li>
</ul>
<p>See <a href="../../admin_intro/uconf/uconf_pki">Unified Configuration: PKI PassPort PS</a>.</p>         </td>
      </tr>
      <tr>
         <td>tf.entitieslocationtype         </td>
         <td>local         </td>
         <td><p>Defines the type of TrustedFile configuration.
The configuration path is defined in <span class="bold_in_para">tf.entitieslocation</span>.</p>
<ul>
<li>Local: Indicates that Trusted File is configured in standalone mode (locally)</li>
<li>Remote: Indicates that Trusted File is configured with PassPort PS using the PassPort PS host and listening port</li>
</ul>         </td>
      </tr>
      <tr>
         <td>tf.defaultlocalcharset         </td>
         <td>ISO-8859-1         </td>
         <td>Default character set for the platform         </td>
      </tr>
      <tr>
         <td>tf.transcodingtablelocation         </td>
         <td>&lt;HOME&gt;/Axway/Transfer_CFT/runtime/conf/tf/transcoding.tbl         </td>
         <td>Absolute path to the character set conversion reference table         </td>
      </tr>
      <tr>
         <td>tf.overwritemode         </td>
         <td>enable         </td>
         <td>Defines how Axway TrustedFile behaves when it must open an existing plain file, acknowledgement or envelope in write mode. If this element is set to the value yes or enable, Axway TrustedFile overwrites the existing output files. Otherwise, it does not open the files and interrupts the current operation with an error message. Its default value is enable         </td>
      </tr>
      <tr>
         <td>tf.enablepasswordcipher         </td>
         <td>yes         </td>
         <td>Indicates that entities passphrases, either in the entities definition file (entities.xml) or in the operation description file, are stored in a ciphered format.         </td>
      </tr>
   </tbody>
</table>

<span id="Command"></span>

## Command example

Use the SAPPL variable to define the type of security format to use to encode the file. Note that you must
use the same security format as your partner (possible values are CMS, PGP, and S/MIME).

Example

To encode/decode messages using PGP, use the format:


    CFTUTIL  send part=loop,idf=trusted_file, SAPPL=pgp

## Not supported

When using <span class="mc-variable suite_variables.TrustedFileName variable">TrustedFile</span> with Transfer CFT, some <span class="mc-variable suite_variables.TrustedFileName variable">TrustedFile</span> functionalities are not delivered or available as described in the <span class="mc-variable suite_variables.TrustedFileName variable">TrustedFile</span> documentation. These include:

-   Overview: Graphical user interface (not delivered in the package)
-   Configuration sample: Encoding and decoding files with Java API
-   C-API

Related topics

-   [SAPPL](../../c_intro_userinterfaces/command_summary/parameter_intro/sappl)
-   [Delivered files and certificates](tf_delivered_files_certficates)
-   [How to generate a certificate for <span class="mc-variable suite_variables.TrustedFileName variable">TrustedFile</span>](tf_generate_cert)
