{
    "title": "Common installation steps (A03PARM and A12OPTSP)",
    "linkTitle": "Common installation steps (A03PARM and A12OPTSP)",
    "weight": "180"
}This section applies to either an SMP/E or non-SMP/E installation.

<span id="kanchor27"></span>

## Customize parameters in the JCL

-   <a href="#Modifying_A03PARM" class="MCXref xref">Set standard JCL parameters A03PARM</a>
-   <a href="#Selectin" class="MCXref xref">Configure the SGINSTAL using UCONF or A12OPTSP</a>

Execute the JOB:

1.  Adapt the customization parameters in the [A03PARM](#Modifying_A03PARM) member.
2.  Submit the JOB.
3.  Quit both EDIT and the library.
4.  Wait for the JOB to execute.

When you modify the A03PARM member, respect the following keyword conventions:

-   Enter keywords in lower case
-   Enter keyword values between quotes ' '
-   Refer to the Keyword description table for details, and adapt bold parameters to suit your environment

<span id="Modifying_A03PARM"></span>

## Set standard JCL parameters A03PARM

Before submitting JCL A00CUSTO to customize the **Target.INSTALL** library JCL, modify the Target.INSTALL (A03PARM) member.

**<span id="Keyword descriptions zOS JCL "></span>Keyword descriptions**

When modifying the A03PARM member, adapt any parameters displayed in bold text to suit your environment. If you used the installer to install, the starred (\*) parameters are already customized.

<span id="Password"></span>

### Password encryption (CFTGNKEY)

Before you can customize the instance environment, you require a password to generate a key to use for internal encryption. The password you enter must be at least 8 characters long, contain upper and lower case characters as well as numeric and special characters (\*#$!?+-@).

The password is temporarily stored in the '`pswfname`' file, with the syntax `--pass <password>`, and is then removed after installation. See [pswfname](#pswfname) for details.

### Environment customization

<table>
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Keyword         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Default         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>jobname</p>         </td>
         <td>'&amp;%strip(substr(userid(),1,6))"I"''         </td>
         <td><p>Name of the JOB for submitting the installation JCLs <strong>(*)</strong>.</p>         </td>
      </tr>
      <tr>
         <td><p>userid</p>         </td>
         <td>'&amp;SYSUID'         </td>
         <td><p>Name of user authorized to submit the installation JCLs.</p>         </td>
      </tr>
      <tr>
         <td><p>account</p>         </td>
         <td>'valacc'          </td>
         <td><p>Account number with which the installation JCLs are submitted <strong>(*)</strong>.</p>         </td>
      </tr>
      <tr>
         <td><p>msgclass</p>         </td>
         <td>'MSGCLASS=R,'         </td>
         <td><p>Message output class. To add other JOB statement parameter use, for example: 'MSGCLASS=R,REGION=0M,'</p>         </td>
      </tr>
      <tr>
         <td><p>class</p>         </td>
         <td>'CLASS=P,'         </td>
         <td><p>JCL installation execution class <strong>(*)</strong>.</p>
<p>Keyword and value with a comma. The keyword can be omitted by using (two) single quotation marks ''.</p>         </td>
      </tr>
      <tr>
         <td><p>jobparm</p>         </td>
         <td>'//*JOBPARM ROOM=CFTx'         </td>
         <td><p>Parameters relating to JES2 installation JOBs <strong>( //* if none)</strong>.</p>         </td>
      </tr>
      <tr>
         <td><p>sysout</p>         </td>
         <td>'*'         </td>
         <td><p>Execution report output class.</p>         </td>
      </tr>
      <tr>
         <td><p>sysda</p>         </td>
         <td>'VIO'         </td>
         <td><p>UNITNAME for the LINK-EDIT temporary files (VIO/SYSDA).</p>         </td>
      </tr>
      <tr>
         <td><p>lepfx</p>         </td>
         <td>'CEE'         </td>
         <td><p>LE Language Environment libraries alias.</p>         </td>
      </tr>
      <tr>
         <td><p>cpfx</p>         </td>
         <td>'CBC’         </td>
         <td><p>C/C++ libraries alias.</p>         </td>
      </tr>
      <tr>
         <td><p>isppfx</p>         </td>
         <td>'ISP'         </td>
         <td><p>ISPF libraries prefix.</p>         </td>
      </tr>
      <tr>
         <td><p>asmcmp</p>         </td>
         <td>'ASMA90'         </td>
         <td><p>High Level Assembler.</p>         </td>
      </tr>
      <tr>
         <td><p>lcobol</p>         </td>
         <td>'IGY'         </td>
         <td><p>COBOL data set prefix that is used in JCL I91APICP.</p>         </td>
      </tr>
      <tr>
         <td>acmp         </td>
         <td>'yes'         </td>
         <td>Compile/link ASM EXITs and APIs.         </td>
      </tr>
      <tr>
         <td>cobcmp         </td>
         <td>'yes'         </td>
         <td>Compile/link COBOL EXITs and APIs.         </td>
      </tr>
      <tr>
         <td>ccmp         </td>
         <td>'yes'         </td>
         <td>Compile/link C EXITs and APIs.         </td>
      </tr>
      <tr>
         <td><p>cftvol</p>         </td>
         <td>'volsert'          </td>
         <td><p>Name of the volume for Transfer CFT z/OS file creation <strong>(*)</strong>.</p>         </td>
      </tr>
      <tr>
         <td><p>cftunit</p>         </td>
         <td>'3390'         </td>
         <td><p>Disk unit type.</p>         </td>
      </tr>
      <tr>
         <td><p>cftv2</p>         </td>
         <td>'&amp;&amp;TARGET'         </td>
         <td><p>Transfer CFT z/OS file creation alias <strong>(*)</strong>.</p>         </td>
      </tr>
      <tr>
         <td>hostadd         </td>
         <td>'&amp;&amp;HOSTBYADDR'         </td>
         <td>Host address (or '&amp;&amp;HOSTID')         </td>
      </tr>
   </tbody>
</table>

#### Transfer CFT loadlib management

{{< TransferCFT/componentlongname  >}} z/OS allows you to concatenate two libraries, a user library and the product library. The user library is not mandatory, but is strongly advised, and should be positioned first.

> **Note:**
>
>  

-   A `..USER.LOAD` load is created during the installation.
-   If the Transfer CFT LOAD is an APF, the USER load must also be an APF.
-   Set `cftuload '&&TARGET".LOAD"'` to manage only one LOAD.

<table>
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Keyword         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Default         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>cftuload         </td>
         <td>'&amp;&amp;TARGET".USER.LOAD"'         </td>
         <td>First loadlib in steplib / joblib         </td>
      </tr>
      <tr>
         <td>cftload         </td>
         <td>'&amp;&amp;TARGET".LOAD"'         </td>
         <td>Second loadlib in steplib / joblib         </td>
      </tr>
      <tr>
         <td>syslmods         </td>
         <td>'&amp;%$cftuload'         </td>
         <td>SYSLMOD (link output) for SGINSTAL
Or $cftload         </td>
      </tr>
      <tr>
         <td>syslmodx         </td>
         <td>'&amp;%$cftuload'         </td>
         <td>SYSLMOD for Exit(s) and/or API(s)
or $cftload         </td>
      </tr>
   </tbody>
</table>

#### Transfer CFT parameters customization

<table>
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Keyword         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Default         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><span id="pswfname"></span>pswfname         </td>
         <td>'&amp;&amp;TARGET".UPARM(GENKEY)"'         </td>
         <td><p>The password, required to generate the key for installation, is temporarily stored in the 'pswfname' file (and is removed after installation).</p>
<p><strong>Syntax</strong>: <code>--pass &lt;password&gt;</code></p>         </td>
      </tr>
      <tr>
         <td>keyfname         </td>
         <td>'&amp;&amp;TARGET".CRYPKEY"'         </td>
         <td>File in which the generated key is stored.         </td>
      </tr>
      <tr>
         <td>sltfname         </td>
         <td>'&amp;&amp;TARGET".CRYPSALT"'         </td>
         <td>File in which the computed salt is stored.         </td>
      </tr>
      <tr>
         <td>stacompat         </td>
         <td>'NO'         </td>
         <td>Catalog state compatibility: cft.state_compat         </td>
      </tr>
      <tr>
         <td>lstcompat         </td>
         <td>'NO'         </td>
         <td>Catalog state compatibility: cft.listcat_compat         </td>
      </tr>
      <tr>
         <td>pesitany         </td>
         <td>'1761'         </td>
         <td>Port id defined in the protocol PeSIT ANY parameter.         </td>
      </tr>
      <tr>
         <td>pesitssl         </td>
         <td>'1762'         </td>
         <td>Protocol PeSIT SSL port.         </td>
      </tr>
      <tr>
         <td>sftpprot         </td>
         <td>'1763'         </td>
         <td>Protocol SFTP port.         </td>
      </tr>
      <tr>
         <td><p>apisp</p>         </td>
         <td>'1765'         </td>
         <td><p>Synchronous API TCP/IP port (The address is 127.0.0.1 in* ..SAMPLE(CFTPARM) cftcom).</p>         </td>
      </tr>
      <tr>
         <td>idparm         </td>
         <td>'IDPARM0'         </td>
         <td><p>CFTPARM identifier: (cft.idparm).</p>
<ul>
<li>This parameter is set during installation.</li>
<li>JCL CFTMAIN uses this parameter, where MNRMAIN (PARM=).</li>
</ul>         </td>
      </tr>
      <tr>
         <td>cftinst         </td>
         <td>'&amp;%"Z11"$pesitany'         </td>
         <td><p>The Transfer CFT instance ID, CFTPARM partner (value size &lt;= 24). This value identifies the Transfer CFT and must be unique (cft.instance_id).</p>
<p>If Composer is enabled, the naming conventions differs:</p>
<ul>
<li>Value size &lt;= 8</li>
<li>First alphabetic character</li>
<li>Naming convention: the same as the PDS’s member</li>
</ul>
<p>The sentence '&amp;%Mvsvar("SYSNAME")" "$pesitany' is replaced with the result of the REXX function Mvsvar("SYSNAME")" concatenated with the value of the previously customized pesitany field.</p>
<p>"Z11" represents the z/OS partition’s name. For example, $pesitany corresponds to the value assigned to keyword 'pesitany'.</p>         </td>
      </tr>
      <tr>
         <td>cftgroup         </td>
         <td>'Production.zos'         </td>
         <td>                       Transfer CFT instance GROUP         </td>
      </tr>
   </tbody>
</table>

#### Transfer CFT {{< TransferCFT/copilotname  >}} server customization

<table>
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Keyword         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Default         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>copenable</p>         </td>
         <td>'yes'         </td>
         <td><p>Enable the {{< TransferCFT/transfercftname  >}} {{< TransferCFT/copilotname  >}} server.</p>         </td>
      </tr>
      <tr>
         <td><p>copladdr</p>         </td>
         <td>'&amp;&amp;HOSTBYADDR'         </td>
         <td><p>Transfer CFT {{< TransferCFT/copilotname  >}} server TCP/IP address. The key word '&amp;&amp;HOSTBYADDR' is substituted by the result of the REXX function socket ("GETHOSTBYADDR"). (copilot.general.serverhost)</p>         </td>
      </tr>
      <tr>
         <td><p>coplport</p>         </td>
         <td>'1766'         </td>
         <td><p>Transfer CFT {{< TransferCFT/copilotname  >}} listening port (copilot.general.serverport).</p>         </td>
      </tr>
      <tr>
         <td>coplsslp         </td>
         <td>'1767'         </td>
         <td><p>Copilot server SSL listening port.
*Mandatory for (copilot.general.ssl_serverport).</p>         </td>
      </tr>
      <tr>
         <td>coppath         </td>
         <td>'/home/AXWAY/CFT32X/inst/cop'         </td>
         <td>USS directory for Transfer CFT {{< TransferCFT/copilotname  >}} server files. (copilot.http.httprootdir)         </td>
      </tr>
      <tr>
         <td>restenable         </td>
         <td>'yes'         </td>
         <td>Enable Copilot REST API (Yes/No).         </td>
      </tr>
      <tr>
         <td>restport         </td>
         <td>'1768'         </td>
         <td>Copilot REST API server port         </td>
      </tr>
   </tbody>
</table>

#### Transfer CFT Heartbeat for Sentinel Dashboards

<table>
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Keyword         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Default         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>jobcft         </td>
         <td>'S:&amp;:1.8SJOBNAME'         </td>
         <td>Transfer CFT job name.         </td>
      </tr>
      <tr>
         <td>jobcop         </td>
         <td>'N:COPP'         </td>
         <td><p>Transfer CFT Copilot server port.</p>
<p>* 'COPP' is a keyword, and the asterisk value * is found via the uconf file.</p>         </td>
      </tr>
   </tbody>
</table>

#### Certificates management

<table>
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Keyword         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Default         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>xpkiopt          </td>
         <td>'YES'         </td>
         <td><p>Exit PKI used (YES or NO)</p>
<p>Note that xpkiopt=YES is mandatory when <strong>pkitype</strong>=system, and that you should use the YES option when possible, even if using pkitype=<strong>cft</strong> or pkitype=<strong>passport</strong>.</p>         </td>
      </tr>
      <tr>
         <td>csflib         </td>
         <td>'CSF.SCSFMOD0'         </td>
         <td>CSF library, mandatory if xpkiopt=yes         </td>
      </tr>
      <tr>
         <td>pkitype         </td>
         <td>'cft'         </td>
         <td><p>Possible values:</p>
<ul>
<li>cft: certificates are stored in a PKI internal datafile</li>
</ul>
<ul>
<li>passport: manages certificates via PassPort</li>
</ul>
<ul>
<li>system: PKI system is activated</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>pasaddr</p>         </td>
         <td>'pasaddr'         </td>
         <td><p>If pkitype=<strong>passport</strong> then the PassPort server TCP/IP listening address.</p>         </td>
      </tr>
      <tr>
         <td><p>pasport</p>         </td>
         <td>'7000'         </td>
         <td><p>PassPort server port (7000).</p>         </td>
      </tr>
      <tr>
         <td>exitpki         </td>
         <td>'YES'         </td>
         <td>          </td>
      </tr>
   </tbody>
</table>

#### Sentinel installation customization

<table>
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Keyword         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Default         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>snenable         </td>
         <td>'no'         </td>
         <td>Enable Sentinel services.         </td>
      </tr>
      <tr>
         <td>sntlload         </td>
         <td>'&amp;&amp;TARGET".LOAD"'         </td>
         <td>Location of the Universal Agent (TRKUTIL Load library).         </td>
      </tr>
      <tr>
         <td><p>sntllocad</p>         </td>
         <td>'127.0.0.1'         </td>
         <td><p>Local TCP/IP address for Sentinel.</p>         </td>
      </tr>
      <tr>
         <td><p>sntladdr</p>         </td>
         <td>'sntl.srv.xx'         </td>
         <td><p>Sentinel server or Event Router address (TCP/IP).</p>         </td>
      </tr>
      <tr>
         <td><p>sntlp</p>         </td>
         <td>'1305'         </td>
         <td><p>Sentinel server or Event Router port (TCP/IP).</p>         </td>
      </tr>
      <tr>
         <td><p>sntlgstr</p>         </td>
         <td>'CFTLG30X'         </td>
         <td><p>LOGGER file identification with a maximum length of 26 characters, or '', available exclusively with the Event Router.</p>         </td>
      </tr>
   </tbody>
</table>

#### Parameters for RACF (or SAF enabled) control of Transfer CFT

Use these parameters only with the {{< TransferCFT/componentshortname  >}} z/OS security setup described in [Setting up RACF Security]().

<table>
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Keyword         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Default         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>grpcft  </p>         </td>
         <td><p>'grpcft'  </p>         </td>
         <td><p>Transfer CFT administrator SAF group.</p>         </td>
      </tr>
      <tr>
         <td>grpmon           </td>
         <td>'grpmon'         </td>
         <td>Transfer CFT SAF group.         </td>
      </tr>
      <tr>
         <td>grpaprm         </td>
         <td>'grpaprm'         </td>
         <td>All parameters access SAF group.         </td>
      </tr>
      <tr>
         <td>grpfprm         </td>
         <td>'grpfprm'         </td>
         <td>PARM and PART access SAF group.         </td>
      </tr>
      <tr>
         <td>grpdesk          </td>
         <td>'grpdesk'          </td>
         <td>Transfer CFT help desk SAF group.         </td>
      </tr>
      <tr>
         <td>grptrf           </td>
         <td>'grptrf'         </td>
         <td>Transfer CFT transfer SAF group.         </td>
      </tr>
      <tr>
         <td>userdef          </td>
         <td>'userdef'         </td>
         <td>Default CFTRECV userid.         </td>
      </tr>
      <tr>
         <td>safcftcl         </td>
         <td>'safcftcl'         </td>
         <td>SAF class for Transfer CFT profiles.         </td>
      </tr>
   </tbody>
</table>

#### Default identification values for Transfer CFT files

If you modify the following values, you must un-comment them in the JCL \* CFT$SET corresponding steps CUSTOM3 and resubmit CFT$SET.

<table>
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Keyword         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Default         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>cftenv</p>         </td>
         <td>'CFTENV'         </td>
         <td><p>Id member included in each JCL:</p>
<p>//   INCLUDE MEMBER=CFTENV</p>
<p>This member contains the command SET for the variables used in the JCL (except for CFTMAIN, and COPRUN).</p>         </td>
      </tr>
      <tr>
         <td>icftcat         </td>
         <td>'CATALOG'            </td>
         <td>Transfer CFT catalog file identifier         </td>
      </tr>
      <tr>
         <td><p>icftcom</p>         </td>
         <td><p> 'COM' </p>         </td>
         <td><p>Transfer CFT com file identifier</p>         </td>
      </tr>
      <tr>
         <td>icftparm          </td>
         <td>'PARM'         </td>
         <td>Transfer CFT parameter file identifier         </td>
      </tr>
      <tr>
         <td>icftpart         </td>
         <td>'PART'         </td>
         <td>Transfer CFT partner file identifier         </td>
      </tr>
      <tr>
         <td>icftpki         </td>
         <td>'PKIFILE'          </td>
         <td>Transfer CFT PKI file identifier         </td>
      </tr>
      <tr>
         <td><p>cftloga</p>         </td>
         <td><p>'LOG1'</p>         </td>
         <td><p>Transfer CFT log file identifier</p>         </td>
      </tr>
      <tr>
         <td><p>cftlogb</p>         </td>
         <td>'LOG2'         </td>
         <td>Transfer CFT log alternate file identifier         </td>
      </tr>
      <tr>
         <td>cftacca         </td>
         <td>'ACCNT1'         </td>
         <td>Transfer CFT account file identifier         </td>
      </tr>
      <tr>
         <td>cftaccb         </td>
         <td>'ACCNT2'         </td>
         <td>Transfer CFT account alternate file identifier         </td>
      </tr>
      <tr>
         <td>cftuconf         </td>
         <td>'UCONF'          </td>
         <td>Unified configuration file         </td>
      </tr>
      <tr>
         <td>cftucrun         </td>
         <td>'UCONFRUN'         </td>
         <td>Unified configuration file runtime identifier         </td>
      </tr>
      <tr>
         <td>cftuparm         </td>
         <td>'UPARM'         </td>
         <td>The unified configuration file definition (member DEFAULT)         </td>
      </tr>
      <tr>
         <td>secini            </td>
         <td>'SECINI'         </td>
         <td>        Security files identifier         </td>
      </tr>
      <tr>
         <td>secact         </td>
         <td>'SECACT'         </td>
         <td>Security actions         </td>
      </tr>
      <tr>
         <td>secobj         </td>
         <td>'SECOBJ'         </td>
         <td>Security objects         </td>
      </tr>
   </tbody>
</table>

#### 

<table>
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Keyword         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Default         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>cgenable         </td>
         <td>'no'         </td>
         <td>Enables exchanges with the server. (yes | no)         </td>
      </tr>
      <tr>
         <td>cghost         </td>
         <td>'cghost'         </td>
         <td>server host address.         </td>
      </tr>
      <tr>
         <td>cgport         </td>
         <td>'cgport' ('12553')         </td>
         <td>Transfer CFT’s port for registering with Central Governance.         </td>
      </tr>
      <tr>
         <td>cgsecret         </td>
         <td>'cgsecret'         </td>
         <td>shared secret.         </td>
      </tr>
      <tr>
         <td>amsusers         </td>
         <td>'&amp;%userid()'         </td>
         <td>AM superuser(s) for .         </td>
      </tr>
   </tbody>
</table>

#### {{< TransferCFT/securerelayname  >}}

<table>
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Keyword         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Default         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>srenable         </td>
         <td>'no'         </td>
         <td>Enable/disable {{< TransferCFT/securerelayname  >}}.         </td>
      </tr>
      <tr>
         <td>srmapath         </td>
         <td>'/home/AXWAY/CFT32X/inst'         </td>
         <td><p>USS directory for Secure Relay Master Agent
(/xsr is automatically added).</p>
<blockquote>
<p><strong>Note:</strong></p>
<p>Read only, you can share the directory with other Transfer CFTs.</p>
</blockquote>         </td>
      </tr>
      <tr>
         <td>srmarun         </td>
         <td>'/home/AXWAY/CFT32X/runtime/xsr'         </td>
         <td>Runtime directory for Secure Relay Master Agent; one per instance, with Read/Write rights for {{< TransferCFT/componentshortname  >}}.         </td>
      </tr>
      <tr>
         <td>srmacopo         </td>
         <td>'srmacopo'         </td>
         <td>Secure Relay Master Agent communication port.         </td>
      </tr>
      <tr>
         <td>srrahost         </td>
         <td>'srrahost'         </td>
         <td>Secure Relay Router Agent host.         </td>
      </tr>
      <tr>
         <td>srraadpo         </td>
         <td>'6810'         </td>
         <td>Secure Relay Router Agent administration port.         </td>
      </tr>
      <tr>
         <td>srracopo         </td>
         <td>'6811'         </td>
         <td>Secure Relay Router Agent communication port, with one port per Transfer CFT instance.         </td>
      </tr>
      <tr>
         <td>srrasap         </td>
         <td>'srrasap'         </td>
         <td>Transfer CFT/Secure Relay configuration listening port on Router Agent side.         </td>
      </tr>
      <tr>
         <td>srrassap         </td>
         <td>'srrassap'         </td>
         <td>SSL listening port on Router Agent side.         </td>
      </tr>
   </tbody>
</table>

#### SAML

<table>
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Keyword         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Default         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Description         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1">Example         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>saml_enable         </td>
         <td>no         </td>
         <td>Enable SAML as the authentication method for this Transfer CFT (the UCONF am.type=saml).         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>saml_client_id         </td>
         <td>'$(cft.instance_id)'         </td>
         <td>Specify the Client_ID value to use as issuer for SAML requests.
This should match the Identity Provider configuration.         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>authserver_host         </td>
         <td>' '         </td>
         <td><p>Specify the SAML endpoint for AuthnRequest (HTTP-Redirect binding).</p>
<p>If Keycloak is the Identity Provider, this should resemble:
<code>https://authserver.host/auth/realms/\{realm-name}/protocol/saml.       authserver_host ' '</code></p>         </td>
         <td>'https://aa.bb.cc.int:8443'         </td>
      </tr>
      <tr>
         <td>saml_idp_signonservice         </td>
         <td>' '         </td>
         <td><p>Specify the SAML endpoint for SignonRequest (HTTP-Redirect binding).</p>
<p>If Keycloak is the Identity Provider, this should resemble:</p>
<p>https://authserver.host/auth/realms/\{realm-name}/protocol/saml.</p>
<p>saml_idp_signonservice ' '</p>         </td>
         <td>'/auth/realms/synapses/protocol/saml'         </td>
      </tr>
      <tr>
         <td>saml_idp_logoutservice         </td>
         <td>' '         </td>
         <td><p>Specify the endpoint for SAML LogoutRequest (HTTP-Redirect binding).</p>
<p>If Keycloak is the Identity Provider, this should resemble:</p>
<p>https://authserver.host/auth/realms/\{realm-name}/protocol/saml.</p>
<p>saml_idp_logoutservice ' '</p>         </td>
         <td>'/auth/realms/synapses/protocol/saml'         </td>
      </tr>
      <tr>
         <td>saml_idp_certificate_path         </td>
         <td>' '         </td>
         <td>Specify the path to the certificate that verifies the SAML Identity Provider
server's signatures.
This certificate is stored in the internal PKI database.         </td>
         <td>          </td>
      </tr>
   </tbody>
</table>

#### File prefixes

You can customize specific prefixes for the following Transfer CFT files.

<table>
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Keyword         </th>
<th style="text-align: center;" class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Default         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>pfx_cat         </td>
         <td>'*'         </td>
         <td>Catalog file         </td>
      </tr>
      <tr>
         <td>pfx_com         </td>
         <td>'*'         </td>
         <td>Communication file         </td>
      </tr>
      <tr>
         <td>pfx_parm         </td>
         <td>'*'         </td>
         <td>Parameter file         </td>
      </tr>
      <tr>
         <td>pfx_part         </td>
         <td>'*'         </td>
         <td>Partner file         </td>
      </tr>
      <tr>
         <td>pfx_pki         </td>
         <td>'*'         </td>
         <td>PKI file         </td>
      </tr>
      <tr>
         <td>pfx_log         </td>
         <td>'*'         </td>
         <td>Log file         </td>
      </tr>
      <tr>
         <td>pfx_acc         </td>
         <td>'*'         </td>
         <td>Account fie         </td>
      </tr>
      <tr>
         <td>pfx_sec         </td>
         <td>'*'         </td>
         <td>Security files         </td>
      </tr>
      <tr>
         <td>pfx_uconf         </td>
         <td>'*'         </td>
         <td>Uconf runtime file         </td>
      </tr>
   </tbody>
</table>

> **Note:**
>
> \(1\) The UCONF and UCONFRUN files are created at the same time as the instance environment, so you must manually re-create when a specific prefix is used (recfm= VB, lrecl=2048).

<span id="Selectin"></span>

## Configure the SGINSTAL using UCONF or A12OPTSP

As of {{< TransferCFT/componentlongname  >}} 3.2.4 SP2, you are no longer required to submit the JOB A12OPTS to generate the SGINSTAL executable in the LOAD library or the USER.LOAD.

If the executable is not present in the LOAD library, the default values are used in the executables of Transfer CFT: CFTMAIN, CFTCOPL, CFTUTIL, etc. Additionally, you can configure the SGINSTAL macro parameters as UCONF variables.

Syntax

See the table below for possible keywords and values.


    UCONFSET id=cft.mvs.sginstal.<keyword>,value=<value>

Example


    UCONFSET id=cft.mvs.sginstal.sdsfopt,value=’monitor’

For continued compatibility, you can generate the Transfer CFT z/OS options tables. You can modify the parameters in the A12OPTSP member.

<table>
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Parameters that can be used as the &lt;keyword&gt;=&lt;value&gt;         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>SYST = MVS</p>         </td>
         <td><p>Transfer CFT operating system support type.</p>         </td>
      </tr>
      <tr>
         <td><p>[ARM  = {<u>YES</u> | NO}]</p>         </td>
         <td><p>Transfer CFT transfer support of the Automatic Restart Manager component:</p>
<ul>
<li>YES (default value): Transfer CFT is authorized (APF) and registers with the ARM component.<br />
Transfer CFT uses an element named Xidparm, where idparm is the startup parameter for Transfer CFT. For details, refer to Using Services &gt; Automatic Restart Manager.</li>
</ul>
<ul>
<li>NO: Transfer CFT does not register with ARM.</li>
</ul>
<blockquote>
<p><strong>Note:</strong></p>
<p>The delivered sample uses the value 'ARM=NO'.</p>
</blockquote>         </td>
      </tr>
      <tr>
         <td><p>[BLKSIZE = {27920 | n}] {4100…32760}</p>         </td>
         <td><p>Maximum value used to calculate the BLKSIZE for files created by Transfer CFT, when this information is absent.</p>
<p>You may reduce the default value by 32 if you want to create DF/SMS managed EXTENDED or LARGE format data sets.</p>
<blockquote>
<p><strong>Note:</strong></p>
<p>The delivered sample uses the value 'BLKSIZE=27998'.</p>
</blockquote>         </td>
      </tr>
      <tr>
         <td>[ALLPRIM = {100 | n}]{1…255}         </td>
         <td>The % factor applied to the primary allocation computed to create a single volume file.         </td>
      </tr>
      <tr>
         <td>[ALLSEC = {10 | n}]{1…255}         </td>
         <td>The % of the primary space used as the secondary allocation when creating a single volume file.         </td>
      </tr>
      <tr>
         <td>[VOLNUM = {20 | n}]{1…127}         </td>
         <td>The maximum number of volumes in a multi-volume allocation.         </td>
      </tr>
      <tr>
         <td>[ALLONE = {100 | n}]{1…255}         </td>
         <td><p>The % factor applied to the primary allocation computed to create a multi-volume file.</p>
<p>Use extreme care when changing this parameter.</p>         </td>
      </tr>
      <tr>
         <td>[ALLNEXT= {100 | n}]{1…255}         </td>
         <td><p>The % factor applied to the secondary allocation when creating a multi-volume file.</p>
<p>Use extreme care when changing this parameter.</p>         </td>
      </tr>
      <tr>
         <td>[DSNTYPE = { <u>NONE</u> | EXTPREF/EXTREQ/LARGE}         </td>
         <td>Values other than NONE (default value) are added to create DF/SMS managed EXTENDED or LARGE files. You can also control the
DSNTYPE via DF/SMS customization.         </td>
      </tr>
      <tr>
         <td><p>[BLKPDS = {150 | n}]{1…32760}</p>         </td>
         <td><p>Number of PDS blocks allocated while creating a partitioned file by Transfer CFT.</p>         </td>
      </tr>
      <tr>
         <td><p>[DESC = { Value of the DESCRIPTOR CODE field of the WTO | n} ]</p>         </td>
         <td><p>The left bit corresponds to 1. The right bit corresponds to 16.</p>         </td>
      </tr>
      <tr>
         <td>[EMCSOPT = { <u>USER</u> | MONITOR | IGNORE}]         </td>
         <td><p>How Transfer CFT processes a MODIFY command issued from a program using SVC 34:</p>
<ul>
<li>USER (default value): the left 8 bytes of EMCS console name are used as the user id issuing the command.</li>
<li>MONITOR: the USERID associated with the monitor is always used.</li>
<li>IGNORE: MODIFY commands issued from SVC 34 are ignored.</li>
</ul>
<p>*See Note.</p>         </td>
      </tr>
      <tr>
         <td><p>[FORMATVB  = {YES | <u>NO</u>}]</p>         </td>
         <td><ul>
<li>YES: Active. You receive a file with a V-type RECFM, and the file is created with the type VB.</li>
<li>NO: Default value.</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>[HSMASYNC  = {YES | <u>NO</u>}]</p>         </td>
         <td><ul>
<li>NO (default value): For all Transfer CFT handled files, the HSM recall is performed synchronously.  </li>
</ul>
<ul>
<li>YES: If a file to be sent is migrated, the HSM recall is performed asynchronously, and the transfer is delayed until HSM completes the request. Transfer CFT will always wait for the HSM recall of received files. </li>
</ul>
<blockquote>
<p><strong>Note:</strong></p>
<p>If a Transfer CFT EXEC procedure is HSM migrated, it is not executed. An error message indicating this is displayed in the Transfer CFT LOG: CFTS02E migrated.</p>
</blockquote>
<blockquote>
<p><strong>Note:</strong></p>
<p>The delivered sample uses the value ‘HSMASYNC=YES’.</p>
</blockquote>         </td>
      </tr>
      <tr>
         <td><p>[MAXAB  = {15 | n}]{1…255}</p>         </td>
         <td><p>Number of ABENDs allowed by Transfer CFT before shutting down.</p>         </td>
      </tr>
      <tr>
         <td><p>[MAXDUMP = {2 | n}] {1…255}</p>
<p> </p>         </td>
         <td><p>Number of ABENDs that are the object of a Transfer CFT requested DUMP.</p>
<p>Additional ABENDs do not provoke a DUMP.</p>         </td>
      </tr>
      <tr>
         <td><p>[MAXTRACE = {80000 | n}]</p>         </td>
         <td><p>Size limit for SGTRACE.</p>         </td>
      </tr>
      <tr>
         <td>[MCSOPT = { <u>CHECK</u> |MONITOR}]         </td>
         <td><p>How Transfer CFT adds a user id to a z/OS MODIFY command:</p>
<ul>
<li>CHECK (default value): The console name is checked for a valid security definition, and is used if yes. Else the user id associated with the monitor is used.
SAF checking applies only if Transfer CFT is running APF authorized.</li>
<li>MONITOR: The USERID associated with the monitor is always used.</li>
</ul>
<p>*See Note.</p>         </td>
      </tr>
      <tr>
         <td>PDSESHARING [ <u>NO</u> | YES]         </td>
         <td><ul>
<li>NO (default) = Do not allow others to write to PDSE in sharing mode.</li>
<li>YES = Allow simultaneous writing to a PDSE file type. Other intervening applications must also use the shared mode option though for sharing to occur.</li>
</ul>
<blockquote>
<p><strong>Note:</strong></p>
<p>On a shared SYSPLEX you must customize the following z/OS system parameter, either:</p>
</blockquote>
<ul>
<li>NORMAL: SYSn.PARMLIB member IGDSMSxx to specify PDSESHARING, or</li>
<li>EXTENDED: SYSn.PARMLIB member IGDSMSxx to specify PDSESHARING</li>
</ul>
<blockquote>
<p><strong>Note:</strong></p>
<p>The delivered sample uses the value ‘PDSESHARING=YES’.</p>
</blockquote>         </td>
      </tr>
      <tr>
         <td><p>[ROUTCDE = {Value of the ROUTCODE CODE field of the WTO | n}]</p>         </td>
         <td><p>The left bit corresponds to 1. The right bit corresponds to 16. The default value ROUTCDE=X‘0008’ corresponds to ROUTCDE=(13).</p>
<p>This value is used with the ‘OPERMSG’ option of the ‘CFTLOG’ parameter.</p>
<p>For the options DESC and ROUTCE, refer to the IBM document Supervisor services and macros, which explains the use of DESCRIPTOR CODES and ROUTCODES.</p>         </td>
      </tr>
      <tr>
         <td>[SDSFOPT = { <u>USER</u> | MONITOR | IGNORE}]         </td>
         <td><p>How Transfer CFT processes a MODIFY command issued from SDSF:</p>
<ul>
<li>USER (default value): the console name defined in SDSF options is used as the user id issuing the command.</li>
<li>MONITOR: the USERID associated with the monitor is used.</li>
<li>IGNORE: MODIFY commands issued from SDSF are ignored.</li>
</ul>
<p>*See Note.</p>         </td>
      </tr>
      <tr>
         <td><p>[SHARECAT = { <strong>YES</strong> | NO | INACT }]</p>         </td>
         <td><ul>
<li>YES (default value): The catalog is cached in a common dataspace that is shared with the Copilot user interface, the CFTUTIL utility, and so on. This parameter improves catalog reading, especially from the Copilot user interface, when enabled.
<ul>
<li><p>If the catalog is full and an extension is created (using either the <code>cft.cftcat.auto_expand_*</code> parameters or <code>RECONFIG TYPE=CAT</code>), new records are stored in the extension and not in the cache. Accessing records in the extension may negatively impact performance.</p></li>
<li>Do not use YES when implementing a multi-node architecture.</li>
</ul></li>
<li>NO: The catalog is cached in a dataspace, but the dataspace is not shared.</li>
<li>INACT: The catalog is not cached, and no dataspace is created.</li>
</ul>
<p>NO: The catalog is cached in a dataspace, but the dataspace is not shared.</p>
<p>INACT: The catalog is not cached, and no dataspace is created.</p>
<blockquote>
<p><strong>Note:</strong></p>
<p>When the Transfer CFT is an APF-authorized program (Authorized Program Facility), specify if the catalog dataspace cache is available to be read by other Transfer CFT applications.</p>
</blockquote>
<blockquote>
<p><strong>Note:</strong></p>
<p>The delivered sample uses the value ‘SHARECAT=YES’.</p>
</blockquote>         </td>
      </tr>
      <tr>
         <td><p>[SGTRACE = {0 | n}] {1…65535}</p>         </td>
         <td><p>Initial value of the SGTRACE trace file.</p>
<p>A value other than 0 may be used if requested by Transfer CFT customer support.</p>
<p>Possible combinations are:</p>
<ul>
<li>1: Network actions (TCP)</li>
</ul>
<ul>
<li>2: Erroneous actions</li>
</ul>
<ul>
<li>4: File manager actions</li>
</ul>
<ul>
<li>8: Read/write to files</li>
</ul>
<ul>
<li>16: C functions</li>
</ul>
<ul>
<li>32: Long messages</li>
</ul>
<ul>
<li>64: Inter-task communication actions</li>
</ul>
<ul>
<li>128: Program calls and return messages</li>
</ul>
<ul>
<li>256: Interactive interface actions</li>
</ul>
<ul>
<li>512: User exit calls</li>
</ul>
<blockquote>
<p><strong>Note:</strong></p>
<p>When you use the SGTRACE options with the Transfer CFT interface under VTAM, the non-encrypted passwords are listed in the trace records.</p>
</blockquote>         </td>
      </tr>
      <tr>
         <td>[SUBOPT = { 0 | 1 | 3 } ]         </td>
         <td><p>Manages 2 statistic lines for a job submitted by Transfer CFT:</p>
<ul>
<li>0: Default. Generates 2 lines at the end of JCL
//* SUBMITTED BY:jobname AT DD/MM/YY hh:mm:ss ,USERID=username ,CARDS= 0000000
//
.</li>
<li>1: Generates only the statistic line at the end of the JCL and no card ‘//’
//* SUBMITTED BY:jobname AT DD/MM/YY hh:mm:ss ,USERID=username ,CARDS= 0000000
.</li>
<li>3: Does not generate a line at the end of the JCL.</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>[TRACE = { <u>128</u> | n}] {4…16383}</p>         </td>
         <td><p>Transfer CFT internal trace size (in Kb).</p>         </td>
      </tr>
      <tr>
         <td><p>[TAPE = {NOTSUP | <u>UPDATE</u> | OUTPUT}]</p>         </td>
         <td><ul>
<li>NOTSUP: Forbids access to tape files for all Transfer CFT programs.</li>
</ul>
<ul>
<li>UPDATE: Default. Enables writing of tape files protected by means of a retaining date or tape library management software.</li>
</ul>
<ul>
<li>OUPUT: The transfer fails in ABDEND 713 if the tape is write-protected by tape library management software, or an expiration date.</li>
</ul>
<blockquote>
<p><strong>Note:</strong></p>
<p>The delivered sample uses the value ‘TAPE=OUTPUT’.</p>
</blockquote>         </td>
      </tr>
      <tr>
         <td><p>[TSOEDIT = { <u>NO</u> | YES}]</p>         </td>
         <td><p>File support with sequence number in columns 73 to 80:</p>
<ul>
<li>YES: If the ISPF editor with the ‘NUMBER ON’ option creates them, then the input files read by CFTUTIL can contain an eight-digit sequence number in columns 73 to 80. This sequence number is then ignored by Transfer CFT z/OS.</li>
</ul>
<ul>
<li>NO: Input files are read without changes from CFTUTIL.</li>
</ul>
<blockquote>
<p><strong>Note:</strong></p>
<p>The delivered sample uses the value ‘TSOEDIT=YES’.</p>
</blockquote>         </td>
      </tr>
      <tr>
         <td>[VSAMSUFS = { <u>SHORT</u> | LONG }]         </td>
         <td><ul>
<li>SHORT: VSAM component suffixes are created with .D for KSDS and ESDS, and .I for KSDS.</li>
<li>LONG: VSAM component suffixes are created with .DATA for KSDS and ESDS, and .INDEX for KSDS.</li>
</ul>
<p>Alternatively, you can set this parameter using: <code>UCONFSET ID=cft.mvs.sginstal.vsamsufs,value=x</code></p>         </td>
      </tr>
   </tbody>
</table>

> **Note:**
>
> \*MCSOPT, SDSFOPT, EMCSOPT: A user id is added only to CFTUTIL commands. The z/OS PAUSE command is interpreted as a CFTUTIL SHUT FAST=YES command. Transfer CFT diagnosis commands are not associated with a used id, for example MODIFY cft or ECHO.

When you start Transfer CFT, all parameters are printed in the transfer CFT LOG, for example:



    CFTI18I+Installation options (macro SGINSTAL)               

    CFTI18I+   Macro date - 05/29/17 15.45  (MM/DD/YY hh.mm) (c)

    CFTI18I+   SHARECAT=NO                                      
    CFTI18I+   TAPE=UPDATE                                      
    CFTI18I+   BLKSIZE=27998                                    

    CFTI18I+   BLKPDS=200                                       
    CFTI18I+   HSMASYNC=YES 
    CFTI18I+   ALLPRIM=100,ALLSEC=10,VOLNUM=20,ALLONE=100,ALLNEX=100

    CFTI18I+   …

When Transfer CFT starts, the CFTI18I message and DATE macro display in one of four formats:

1.  CFTI18I and DATE macro - 06/16/17 14.10 (MM/DD/YY hh.mm) (c) SGINSTAL default model.  
    The SGINSTAL executable does not exist.  
    This was not configured with the cft.mvs.sginstal.xxxx variables.
2.  CFTI18I and DATE macro - 06/05/17 15.30 (MM/DD/YY hh.mm) (c) SGINSTAL load.  
    The SGINSTAL executable exists.  
    This was not configured with the cft.mvs.sginstal.xxxx variables.
3.  CFTI18I and DATE macro - 06/16/17 14.10 (MM/DD/YY hh.mm) (c) SGINSTAL default model modified by UCONF.  
    The SGINSTAL executable does not exist.  
    This was configured with a variable(s) of the cft.mvs.sginstal.xxxx type.
4.  CFTI18I and DATE macro - 06/05/17 15.30 (MM/DD/YY hh.mm) (c) SGINSTAL load modified by UCONF.  
    The SGINSTAL executable exists.  
    A variable of the type cft.mvs.sginstal.xxxx.

To generate parameters from the SGINSTAL executable as UCONF variables:



    //* STEP 1 : GENERATE
    //CFTSGIGN EXEC PGM=CFTSGIGN
    //STEPLIB   DD  DISP=SHR,DSN=&CFTLOAD     (LIBRARY contains SGINSTAL)
    //UCONFGEN  DD  UNIT=SYSDA,DISP=(NEW,PASS),
    //          DCB=(RECFM=VB,LRECL=256,BLKSIZE=2560),
    //          SPACE=(TRK,(1)),
    //          DSN=&&TMP
    //* STEP 2 : UPDATE UCONF
    //UCONF    EXEC PCFTUTL,PARM=''
    //CFTIN     DD  DISP=(OLD,DELETE),
    //          DSN=&&TMP
    Delivered JCL INSTALL(MIGRSGI) extract.

Related topics

[Customize JCL installation files](../installation_parameters_to_customize)
