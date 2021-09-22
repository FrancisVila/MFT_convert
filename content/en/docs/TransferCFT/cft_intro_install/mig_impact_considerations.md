{
    "title": "Migration/upgrade impact and considerations",
    "linkTitle": "Migration/upgrade impact and considerations",
    "weight": "80"
}You should be aware of the following features or parameters, which were modified since their inception, and how these changes may impact your upgrade or migration.

<table cellspacing="0">
   <col/>
   <col/>
   <col/>
   <col/>
   <thead>
      <tr>
         <th>
            <p>Key element</p>
</th>
         <th>Originating versions</th>
         <th>Updated versions</th>
         <th>Description</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>API and Exits         </td>
         <td>all versions          </td>
         <td>to any version         </td>
         <td>You must recompile any API or Exit programs that are used by Transfer CFT.         </td>
      </tr>
      <tr>
         <td>
            <p>Configuration cache feature</p>
            <p>(cft.server.parm.cache_size)</p>
         </td>
         <td>Lower than 3.8         </td>
         <td>3.8 and higher         </td>
         <td>
            <p><a name="parmcache"></a>The default value  is now 5000 instead of zero, making the cache feature active by default. </p>
            <p>This means that updates no longer occur dynamically; you can execute <span>RECONFIG </span>type<span>=PARMCACHE </span>or wait for a cache timeout as defined in <span>cft.server.parm.cache_timeout (60 seconds).</span></p>
         </td>
      </tr>
      <tr>
         <td>
            <p>cft.listcat_compat   = No</p>
            <p> cft.state_compat     = No</p>
         </td>
         <td>Lower than 3.8         </td>
         <td>3.8 and higher         </td>
         <td>
            <p>Modified the default value for the <span>cft.listcat_compat </span>(lstcompat) and <span>  cft.state_compat     </span>(stacompat) parameters from YES to NO.</p>
         </td>
      </tr>
      <tr>
         <td>Amazon S3         </td>
         <td>Lower than 3.8         </td>
         <td>3.8 and higher         </td>
         <td>
            <p>When  using Amazon S3, the default setting FACTION=VERIFY is no longer ignored. </p>
            <p>If you would like to continue to have the same behavior of overwriting the file, please use FACTION=DELETE. Note, though, that the file is not available during the transfer.</p>
         </td>
      </tr>
      <tr>
         <td>CFTUIPREF          </td>
         <td>Lower than 3.8         </td>
         <td>3.8 and higher         </td>
         <td>After an upgrade you may need to check user privileges for creating filters in the CFTUIPREF object.         </td>
      </tr>
      <tr>
         <td>Copilot Java applet         </td>
         <td>Lower than 3.8         </td>
         <td>3.8 and higher         </td>
         <td>The Copilot Java applet was removed from the product. Users are invited to use the Transfer CFT UI or Flow Manager for a graphical UI experience.         </td>
      </tr>
      <tr>
         <td>SQLite database         </td>
         <td>3.7 and lower         </td>
         <td>3.8 and higher         </td>
         <td>
            <p>The CFTPARM object's PARTFNAM and PKIFNAME fields  are obsolete for Windows, UNIX, and HP NonStop. </p>
         </td>
      </tr>
      <tr>
         <td>
            <p>FTYPE=T </p>
            <p><i>Windows only</i>
</p>
         </td>
         <td>3.2.4 to 3.7 without appropriate patch or SP*         </td>
         <td>3.8 and higher         </td>
         <td>
            <p>On Windows systems, note the following difference when FTYPE=T. </p>
            <ul>
               <li>For versions 3.2.4 to 3.7 without the patch, an empty line terminated by a 1A character is transmitted.
               </li>
               <li>Prior to 3.2.4 and for the versions with the SP or patch applied, an empty line terminated by a 1A character is not transmitted.               </li>
            </ul>
            <p>*3.7 SP1 (patch), 3.3.2 SP8, 3.6 SP3, 3.8</p>
         </td>
      </tr>
      <tr>
         <td>Visual C++ Redistributable Package for Visual Studio 2019
                             </td>
         <td>3.6 and lower         </td>
         <td>3.7 and higher         </td>
         <td>
            <p>Transfer CFT on Windows  requires the <b>Visual C++ Redistributable Package for Visual Studio 2019</b> for proper functioning.  This provides the necessary library files (DLL) for Transfer CFT. </p>
            <p>You must install <code>vcredist_x64.exe</code> prior to installing or upgrading Transfer CFT. </p>
            <p><b>Issue</b>
</p>
            <p>If you perform an upgrade without first installing the Redistributable package, the runtime is not imported and Transfer CFT will not operate correctly. The following information displays in the <code>&lt;installdir&gt;/install.log</code> file:</p>
            <p>Script stderr:</p>
            <p>child killed: unknown signal</p>
            <p> </p>
            <p>Fail to import RUNTIME data.</p>
            <p>Problem running post-install step. Installation may not complete correctly</p>
            <p>Fail to import RUNTIME data.</p>
            <p><b>Corrective action</b>
</p>
<ol>
               <li value="1">Install the Redistributable  package.               </li>
               <li value="2">From the <span>cmd </span>console, load the profile.               </li>
               <li value="3">Import the runtime data by running the import command to complete the upgrade.               </li>
            <p>cd &lt;runtimedir&gt;\.up </p>
            <p>import.cmd</p>
               <li value="4">Check that the script executed correctly.                </li>
</ol>
         </td>
      </tr>
      <tr>
         <td>LISTPKI         </td>
         <td>3.6 and lower         </td>
         <td>3.7 and higher         </td>
         <td>To use the new LISTPKI format, copy the <code>dspcnf.xml</code> model file from <code>&lt;installdir&gt;/distrib/template/conf</code> to the <code>&lt;runtimedir&gt;/conf.</code>         </td>
      </tr>
      <tr>
         <td>CFTACCNT         </td>
         <td>3.5 and lower          </td>
         <td>3.6 and higher         </td>
         <td>
            <p>Updated the documentation for the account file in v24 format. Please note the changes in field length as described in the CFTACCNT list.</p>
         </td>
      </tr>
      <tr>
         <td>SORTBY         </td>
         <td>3.5 and lower         </td>
         <td>3.6 and higher         </td>
         <td>
<p width="59.777%">Catalog records are no longer displayed by IDTU. To have the same display as in previous versions, use the SORTBY parameter as follows: <br/><code>listcat sortby=idtu</code></p>
         </td>
      </tr>
      <tr>
         <td>EBICS         </td>
         <td>3.5 and lower         </td>
         <td>3.6 and higher         </td>
         <td>
            <p>Use the Axway  EBICS client. Please refer to the <a href="https://docs.axway.com/bundle/EBICSClient_10_allOS_en_HTML5/page/ebics_client_documentation_home.html">EBICS client documentation</a> for product details.  </p>
         </td>
      </tr>
      <tr>
         <td>
            <p>BUFSIZE</p>
            <p>FBUFSIZE</p>
         </td>
         <td>
            <p>3.3.2 and lower </p>
            <p><i>Unix and IBM i only</i>
</p>
         </td>
         <td>
            <p>3.4, 3.6  SP2 and lower, 3.7 and 3.8</p>
         </td>
         <td>
            <p>A  BUFSIZE or FBUFSIZE value greater than 32 kiB may lead to Transfer CFT failing to exchange messages between CFTTPRO and CFTTFIL.
If you have set a value higher than 32 kiB, please decrease it to 32768.
</p>
            <p><table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">As of 3.6 SP3, 3.8 SP1, and 3.9, the internal value limit is 32768.          </td>
      </tr>
</table></p>
         </td>
      </tr>
      <tr>
         <td>PKIFNAME         </td>
         <td>3.4 and lower         </td>
         <td>3.5 and higher         </td>
         <td>You can no longer reference a certificate with the PKIFNAME format (<span>CFTPARM:PKIFNAME=TXT://certificate</span>).            <p>Previously, when implementing an integrated 
 PKI, the PKIFNAME  parameter could indicate a flat-file database (<span>PKIFNAME=TXT://certificate</span>). If you were using this kind of file and then migrate, you must manually import all certificates into the PKI database.</p>         </td>
      </tr>
      <tr>
         <td>CFTCRON         </td>
         <td>Lower than 3.4         </td>
         <td>3.4 and higher         </td>
         <td>An upgrade from a version lower than Transfer CFT 3.4 to 3.4 or higher may fail due to an incorrect time syntax because the CFTCRON time syntax is checked when creating or editing a CFTCRON object.
         </td>
      </tr>
      <tr>
         <td>PKIPASSW         </td>
         <td>3.3.2 or lower         </td>
         <td>3.4 and higher         </td>
         <td>
            <p>Removed the PKIPASSW parameter from PKI commands (still available for CFTPARM).</p>
            <p><table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">In earlier versions of <span>Transfer CFT</span>, the PKIPASSW parameter was used for encryption in the multiple PKI commands. This functionality is now replaced by the UCONF <span>crypto.key_fname</span> parameter.         </td>
      </tr>
</table></p>
            <p><span>Impact</span>
</p>
            <p>If you are using PKIEXT to export  keys during a manual migration, you must use the  same PKIPASSW  (CFTPARM object) as was originally used to import the key. Using the same logic, to re-import a key that you extracted using PKIEXT, you require the same CFTPARM <a href="../../c_intro_userinterfaces/command_summary/parameter_intro/pkipassw">PKIPASSW</a>.</p>
            <p>For information on exporting keys, please refer to <a href="../../transport_security_start_here/certificates2/pkiutil_cli_intro/pkiext">Using PKIEXT</a>.</p>
         </td>
      </tr>
      <tr>
         <td>32-bit releases         </td>
         <td>3.3.2 and lower         </td>
         <td>3.4 and higher         </td>
         <td>End of 32-bit version deliveries.         </td>
      </tr>
      <tr>
         <td>Some default values         </td>
         <td>3.3.2 and lower         </td>
         <td>3.4 and higher         </td>
         <td>
            <p>Updated default values of the following parameters to optimize and standardize among platforms.</p>
            <p><table border="0" cellpadding="0" cellspacing="0" xmlns="http://www.w3.org/TR/REC-html40">
         <col xmlns=""/>
         <col xmlns=""/>
         <col xmlns=""/>
         <col xmlns=""/>
<thead xmlns="">
      <tr>
         <th>Object </th>
         <th>Parameter </th>
         <th>Old default</th>
         <th>New default</th>
      </tr>
   </thead>
<tbody xmlns="">
      <tr xmlns="http://www.w3.org/TR/REC-html40">
         <td rowspan="7">
            <p><b>CFTPARM</b>
</p>
            <p> </p>
            <p> </p>
            <p> </p>
            <p> </p>
            <p> </p>
            <p> </p>
         </td>
         <td>
            <p>MAXTRANS</p>
         </td>
         <td>
            <p>128 (Win), 256
 (os400, unix, vms), 990 (z/OS)</p>
         </td>
         <td>
            <p>256</p>
         </td>
      </tr>
      <tr xmlns="http://www.w3.org/TR/REC-html40">
         <td>
            <p>MAXTASK</p>
         </td>
         <td>
            <p>1 (Win), 16
 (os400, unix, vms), 400 (z/OS)</p>
         </td>
         <td>
            <p>8</p>
         </td>
      </tr>
      <tr xmlns="http://www.w3.org/TR/REC-html40">
         <td>
            <p>TRANTASK</p>
         </td>
         <td>
            <p>14 (z/OS), 16
 (os400, unix, vms), 128 (win)</p>
         </td>
         <td>
            <p>3</p>
         </td>
      </tr>
      <tr xmlns="http://www.w3.org/TR/REC-html40">
         <td>
            <p>WAITTASK</p>
         </td>
         <td>
            <p>1441</p>
         </td>
         <td>
            <p>10</p>
         </td>
      </tr>
      <tr xmlns="http://www.w3.org/TR/REC-html40">
         <td>
            <p>SSLMTASK</p>
         </td>
         <td>
            <p>1 (Win), 16
 (os400, unix, vms), 64 (z/OS)</p>
         </td>
         <td>
            <p>8</p>
         </td>
      </tr>
      <tr xmlns="http://www.w3.org/TR/REC-html40">
         <td>
            <p>SSLTTASK</p>
         </td>
         <td>
            <p>14 (z/OS), 16
 (os400, unix, vms), 128 (win)</p>
         </td>
         <td>
            <p>3</p>
         </td>
      </tr>
      <tr xmlns="http://www.w3.org/TR/REC-html40">
         <td>
            <p>SSLWTASK</p>
         </td>
         <td>
            <p>1441</p>
         </td>
         <td>
            <p>10</p>
         </td>
      </tr>
      <tr xmlns="http://www.w3.org/TR/REC-html40">
         <td rowspan="2">
            <p>CFTNET</p>
            <p> </p>
         </td>
         <td>
            <p>type</p>
         </td>
         <td>
            <p>x25</p>
         </td>
         <td>
            <p>TCP</p>
         </td>
      </tr>
      <tr xmlns="http://www.w3.org/TR/REC-html40">
         <td>
            <p>maxcnx</p>
         </td>
         <td>
            <p>32</p>
         </td>
         <td>
            <p>384</p>
         </td>
      </tr>
      <tr xmlns="http://www.w3.org/TR/REC-html40">
         <td rowspan="16">
            <p>CFTPROT type=PeSIT prof=ANY</p>
         </td>
         <td>
            <p>concat</p>
         </td>
         <td>
            <p>no</p>
         </td>
         <td>
            <p>yes</p>
         </td>
      </tr>
      <tr xmlns="http://www.w3.org/TR/REC-html40">
         <td>
            <p>multart</p>
         </td>
         <td>
            <p>no</p>
         </td>
         <td>
            <p>yes</p>
         </td>
      </tr>
      <tr xmlns="http://www.w3.org/TR/REC-html40">
         <td>
            <p>segment</p>
         </td>
         <td>
            <p>no</p>
         </td>
         <td>
            <p>yes</p>
         </td>
      </tr>
      <tr xmlns="http://www.w3.org/TR/REC-html40">
         <td>
            <p>rpacing</p>
         </td>
         <td>
            <p>36</p>
         </td>
         <td>
            <p>32767</p>
         </td>
      </tr>
      <tr xmlns="http://www.w3.org/TR/REC-html40">
         <td>
            <p>spacing</p>
         </td>
         <td>
            <p>36</p>
         </td>
         <td>
            <p>32767</p>
         </td>
      </tr>
      <tr xmlns="http://www.w3.org/TR/REC-html40">
         <td>
            <p>rrusize</p>
         </td>
         <td>
            <p>4056</p>
         </td>
         <td>
            <p>32750</p>
         </td>
      </tr>
      <tr xmlns="http://www.w3.org/TR/REC-html40">
         <td>
            <p>srusize</p>
         </td>
         <td>
            <p>4056</p>
         </td>
         <td>
            <p>32750</p>
         </td>
      </tr>
      <tr xmlns="http://www.w3.org/TR/REC-html40">
         <td>
            <p>disctc</p>
         </td>
         <td>
            <p>90</p>
         </td>
         <td>
            <p>60</p>
         </td>
      </tr>
      <tr xmlns="http://www.w3.org/TR/REC-html40">
         <td>
            <p>disctd</p>
         </td>
         <td>
            <p>120</p>
         </td>
         <td>
            <p>10</p>
         </td>
      </tr>
      <tr xmlns="http://www.w3.org/TR/REC-html40">
         <td>
            <p>disctr</p>
         </td>
         <td>
            <p>45</p>
         </td>
         <td>
            <p>45</p>
         </td>
      </tr>
      <tr xmlns="http://www.w3.org/TR/REC-html40">
         <td>
            <p>discts</p>
         </td>
         <td>
            <p>165</p>
         </td>
         <td>
            <p>60</p>
         </td>
      </tr>
      <tr xmlns="http://www.w3.org/TR/REC-html40">
         <td>
            <p>rchkw</p>
         </td>
         <td>
            <p>2</p>
         </td>
         <td>
            <p>3</p>
         </td>
      </tr>
      <tr xmlns="http://www.w3.org/TR/REC-html40">
         <td>
            <p>schkw</p>
         </td>
         <td>
            <p>2</p>
         </td>
         <td>
            <p>3</p>
         </td>
      </tr>
      <tr xmlns="http://www.w3.org/TR/REC-html40">
         <td>
            <p>rcomp</p>
         </td>
         <td>
            <p>10</p>
         </td>
         <td>
            <p>0</p>
         </td>
      </tr>
      <tr xmlns="http://www.w3.org/TR/REC-html40">
         <td>
            <p>scomp</p>
         </td>
         <td>
            <p>10</p>
         </td>
         <td>
            <p>0</p>
         </td>
      </tr>
      <tr xmlns="http://www.w3.org/TR/REC-html40">
         <td>sserv         </td>
         <td>PESIT
         </td>
         <td>GSIT         </td>
      </tr>
      <tr xmlns="http://www.w3.org/TR/REC-html40">
         <td xmlns=""><b>CFTPROT type=ODETTE</b>
         </td>
         <td>tcp         </td>
         <td>CFT         </td>
         <td>OFTP         </td>
      </tr>
      <tr xmlns="http://www.w3.org/TR/REC-html40">
         <td rowspan="4">
            <p><b>CFTTCP</b>
</p>
         </td>
         <td>
            <p>retryw</p>
         </td>
         <td>
            <p>7</p>
         </td>
         <td>
            <p>1</p>
         </td>
      </tr>
      <tr xmlns="http://www.w3.org/TR/REC-html40">
         <td>
            <p>retryn</p>
         </td>
         <td>
            <p>6</p>
         </td>
         <td>
            <p>4</p>
         </td>
      </tr>
      <tr xmlns="http://www.w3.org/TR/REC-html40">
         <td>
            <p>retrym</p>
         </td>
         <td>
            <p>12</p>
         </td>
         <td>
            <p>12</p>
         </td>
      </tr>
      <tr xmlns="http://www.w3.org/TR/REC-html40">
         <td>
            <p>cnxinout</p>
         </td>
         <td>
            <p>2</p>
         </td>
         <td>
            <p>4</p>
         </td>
      </tr>
   </tbody>
</table></p>
            <p><b>Impact </b>
</p>
            <p>Check the use in your flows and modify according.</p>
         </td>
      </tr>
      <tr>
         <td>cft.server.processing_scripts_variables_blacklist         </td>
         <td>3.3.2 SP3 and lower         </td>
         <td>3.3.2 SP4 and higher         </td>
         <td>POSIX Regular Extended expression that defines forbidden characters.         </td>
      </tr>
      <tr>
         <td>TLS         </td>
         <td>3.2.x and higher         </td>
         <td>
            <p>not applicable</p>
         </td>
         <td>
            <p>When migrating to 3.2.x or higher, SSL transfers may fail with a DIAGP e105s86 or e75s89 when performing transfers with the versions listed below (with the error occurring on the remote <span>Transfer CFT</span>). </p>
            <p>Affected versions:</p>
            <ul>
               <li>All 3.1.3 SP7 and lower                </li>
               <li> All 3.0.1 SP3 and lower               </li>
            </ul>
            <p>On even older versions, we recommend setting the CFTPROT:CONCAT parameter to No.</p>
         </td>
      </tr>
      <tr>
         <td>CA certificate chains         </td>
         <td>3.1.3 and lower         </td>
         <td>3.2.2 and higher         </td>
         <td>
            <p>In <span>Transfer CFT</span> 3.1.3 and lower, you can perform a SSL transfer  even if the certificate chain is not complete (not signed by a ROOT CA). </p>
            <p><b>Impact</b>
</p>
            <p>In <span>Transfer CFT</span> 3.2.2 and higher, the certificate chain must be complete for a transfer to succeed.</p>
            <p>For more information, see <a href="../../troubleshoot_intro/admin_troubleshooting_server/troubleshoot_security">Unknown CA leads to a failed certificate verification</a></p>
         </td>
      </tr>
      <tr>
         <td>PKIPASSW          </td>
         <td>3.1.3 and lower         </td>
         <td>3.3.2 and higher         </td>
         <td>
            <p>When upgrading from 3.1.3 to 3.3.2, first check that the PKIPASSW length value is not greater than 8 characters. </p>
            <p>If the value is 8 or less, you can proceed with the upgrade. </p>
            <p>If the PKIPASSW value in the CFTPARM command is greater than 8 characters,   perform the steps in the solution below.</p>
            <p><span>Solution </span>
</p>
            <p>Prior to migration you  must truncate the password on the Transfer CFT 3.1.3:</p>
<ol>
               <li value="1">Export the CFTPARM.<br/><code>CFTUTIL cftext type=parm, fout=file_parm.out</code>
               </li>
               <li value="2">Modify the PKIPASSW in the file. For example, if the old value was <span>PKIPASSW=12345678910</span>, replace it with <span>PKIPASSW=12345678.</span>               </li>
               <li value="3">Reimport: <br/><span>CFTUTIL config type=input,fname=file_parm.out</span>
               </li>
               <li value="4">Continue the Transfer CFT 3.3.2  upgrade process.               </li>
</ol>
         </td>
      </tr>
      <tr>
         <td>Copilot client         </td>
         <td>
            <p>3.1.3 or lower </p>
         </td>
         <td>3.2.2 and higher         </td>
         <td>
            <p>The Copilot  application changed from a Java applet to a Java Web Start program. </p>
            <p><span>Impact</span>
</p>
            <p>Copilot requires Java 7 or higher.</p>
         </td>
      </tr>
      <tr>
         <td>ROOTCID=NONE         </td>
         <td>3.1.3         </td>
         <td>3.2.2 and higher         </td>
         <td>
            <p>Non authentication method was available in 3.1.3 and lower (anonymous TLS connection).
</p>
            <p><span>Impact</span>
</p>
            <p>This support has been removed  in <span>Transfer CFT</span> 3.2.2 and higher.
You must update the ROOTCID parameter.</p>
         </td>
      </tr>
      <tr>
         <td>TLS          </td>
         <td>3.1.3 or lower         </td>
         <td>3.2.2 and higher         </td>
         <td>
            <p>To comply with security standards, as of Transfer CFT version 3.2.2 the use of the cipher suites 59, 60, and 61 is restricted to TLS 1.2 exclusively. </p>
            <p><span>Impact</span>
</p>
            <p>This means that if some of your partners use a version of Transfer CFT lower than 3.2.2 that does not support TLS 1.2, and you are using ciphers 59, 60 and 61, which requires TLS 1.2 in version 3.2.2 and higher, you must add another cipher in the cipher list and remove ciphers 59, 60, 61 from the partner's cipher list.</p>
            <p><table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">You do not have to remove ciphers 59, 60, 61 in the partner cipher list if you apply the Transfer CFT patch 3.0.1 SP11.         </td>
      </tr>
</table></p>
         </td>
      </tr>
      <tr>
         <td>Rotate the log         </td>
         <td>3.0.1 or lower         </td>
         <td>3.1.3 and higher         </td>
         <td>
            <p>Changed the switch log feature behavior.</p>
            <p> In version 3.0.1 or lower, there were two files that automatically alternated. </p>
            <p><span>Impact</span>
</p>
            <p>In version 3.1.3 and higher if you want to continue this functionality, you must set the alternate log file's uconf value <span>cft.cftlog.afname</span> to the alternate file path  (for example, <span>$CFTRUNTIME/log/cftloga</span>).</p>
         </td>
      </tr>
      <tr>
         <td>Demo certificates         </td>
         <td>3.0.1 or lower         </td>
         <td>3.1.2 and higher         </td>
         <td>
            <p>Axway no longer delivers the template certificates used in the Transfer CFT SSL.</p>
            <p>Impact</p>
            <p>If you were using the demo certificates, import your proper certificates and replace in the PKI database as the Demo certificates are expired. </p>
         </td>
      </tr>
      <tr>
         <td>
            <p>CFTPARM </p>
            <p>key parameter</p>
         </td>
         <td>2.7.1 or lower         </td>
         <td>3.0.1 and higher         </td>
         <td>If you had the CFTPARM key parameter set directly to a value, you must modify this so that key parameter points to an indirection file containing the license key.          </td>
      </tr>
   </tbody>
</table>

 
