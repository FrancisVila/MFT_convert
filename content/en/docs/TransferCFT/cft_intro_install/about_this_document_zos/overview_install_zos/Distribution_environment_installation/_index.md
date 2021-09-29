{
    "title": "Non-SMP/E: create distribution environment",
    "linkTitle": "Non-SMP/E: create distribution environment",
    "weight": "170"
}This section describes how to install the **<span id="kanchor56"></span>distribution** **environment**. After installing the distribution environment, you should not need to modify it. Later you will use the installed distribution environment to create a Transfer CFT <span id="kanchor57"></span>[*instance* *environment*](t_install_instance_envr_zos) (runtime). The term instance replaces the former notion of a *target* environment in Transfer CFT.

When you install the Transfer CFT you can create the following environments in a single step:

-   Distribution environment
-   Transfer CFT run-time instance environment

## Define a Transfer CFT <span id="kanchor58"></span>alias

You can create a Transfer CFT ALIAS in the USER CATALOG if the file names mentioned in the installation JOBs are reserved for operation.

To define an alias, adapt the parameters in bold to suit your environment. Enter:

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><code>//DEFALIAS EXEC PGM=IDCAMS   </code><br />
<code>//SYSPRINT DD SYSOUT=sysout</code><br />
<code>//SYSIN    DD *      </code><br />
<code>   DEFINE ALIAS(NAME(CFTV2) RELATE(USER.CATALOG))   ...................</code><br />
<code>/*     </code><br />
</td>
</tr>
</tbody>
</table>

## Download the installation library from ESD 

### Required configuration

-   An FTP client that permits the transfer of files to the z/OS host
-   Download the ESD file from Axway Support at [https://support.axway.com](https://support.axway.com/)

<table data-cellpadding="0" data-cellspacing="0">
<tbody>
<tr class="odd">
<td data-valign="top"></td>
<td data-valign="top"><span><strong>Note</strong></span></td>
<td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">ISO files were deprecated in version 3.0.1.</td>
</tr>
</tbody>
</table>

To install the Transfer CFT z/OS product, you need approximately:

-   200 cylinders 3390 of disk space on z/OS to transfer the delivery files from another system using FTP

<!-- -->

-   450 additional cylinders of disk space to unpack the installation files

## <span id="Installa"></span><span id="kanchor59"></span>Installation files 

The installation package is a zip archive that contains the product and installer program files.

### Installation modes

Once you unzip the files, locate and run the setup file in the root folder of the installation package. Two installation modes are available:

-   Installation (console mode)
    -   UNIX/Linux: setup.sh
    -   Windows: setup.bat
-   Silent installation
    -   UNIX/Linux: setup.sh --silent
    -   Windows: setup.bat --silent

## Upload Transfer CFT z/OS using the installer

This section describes how to prepare the distribution environment necessary to create a target environment. The procedure consists of:

-   Installing the product
-   Creating the distribution environment

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>Unix Installation example:</p>
<p>./setup.sh</p>
<p> </p>
<p>/home/cft/Transfer_CFT_3.3.2_Install_mvs_BN10687000/bin/axwaykit_linux Version 1.0 ===</p>
<p>-------------------------------------------------------</p>
<p>&gt;&gt; Start the configuration installation - Transfer CFT ZOS with /home/cft/Transfer_CFT_3.3.2_Install_mvs_BN10687000/bin/axwaykit_linux on Fri Apr 06 13:40:41 2018</p>
<p>-------------------------------------------------------</p>
<p>&gt;Enter the local working directory where you want to save the configuration [Default:/home/cft/Transfer_CFT_3.3.2_Install_mvs_BN10687000/bin][Mandatory]</p>
<p>--------------------------------</p>
<p>&gt;Enter the dataset name for the product installation (4 qualifiers min.)</p>
<p>[Default:AXWAY.XFB.D332.CF030000][Mandatory]</p>
<p>Number of qualifiers=4</p>
<p>&gt;Enter File Format ADRDSSU(A) or XMIT(X):</p>
<p>[Default:A][Mandatory]</p>
<p> </p>
<p> </p>
<p>Installation runtime:</p>
<p>--------------------------------</p>
<p>&gt;Enter the dataset name for the runtime environment (as either a value or NO). [Default:AXWAY.V332][Mandatory]</p>
<p> </p>
<p>Mainframe address (for FTP):</p>
<p>--------------------------------</p>
<p>&gt;Enter hostname address: [No default][Mandatory]</p>
<p>axway.hostname.mvs</p>
<p> </p>
<p>&gt;Enter login TSO: [No default][Mandatory]</p>
<p>TSOUSER</p>
<p> </p>
<p>&gt;Enter password: [******][Mandatory]</p>
<p>****</p>
<p> </p>
<p>&gt;Enter Y if you want to change the user and password? (Y/N) [Default:N][Mandatory]</p>
<p>****</p>
<p> </p>
<p>&gt;Enter Y if you want to change the user and password? (Y/N) [Default:N][Mandatory]</p>
<p> </p>
<p>&gt;Enter Y/N to define if you want submit the JCL(Note: JESINTERFACELEVEL should be set to 2) [Default:Y]</p>
<p> </p>
<p>&gt;Enter the execution class (JCL) [Default:A][Mandatory]</p>
<p> </p>
<p>&gt;Enter the account parameter (JCL) [Default:()]</p>
<p>Configuration summary: ---------------------</p>
<p>Local parameters ----------------</p>
<p>Local work PATH : /home/cft/Transfer_CFT_3.3.2_Install_mvs_BN10687000/bin</p>
<p>Installation PATH : /home/cft/Transfer_CFT_3.3.2_Install_mvs_BN10687000/bin</p>
<p> </p>
<p> </p>
<p>Host parameters</p>
<p>---------------</p>
<p>Host IP address : axway.hostname.mvs</p>
<p>User : TSOUSER</p>
<p>Upload library : AXWAY.XFB.D332.CF030000.UPLIB</p>
<p>&gt;&gt; this library will be created</p>
<p>&gt;&gt; member : CFT332A</p>
<p>Transfer CFT runtime envir.: AXWAY.V332</p>
<p>JCL to be submitted : J1IDISTA</p>
<p>jobname : TSOUSERI</p>
<p> </p>
<p>&gt;Enter Y if you agree with these parameters, or N to Exit installation (Y/N)</p>
<p>[No default][Mandatory]</p></td>
</tr>
</tbody>
</table>

## Silent installation

Silent mode enables you to perform an installation or configuration in a non-interactive mode. You do not have to enter any parameters in the console. To use this mode, you must install the product or run the installer program and perform the configuration until just before you execute setup.sh or setup.bat.

Before you start the silent installation you must update the silent\_install.conf installation file located in the install directory.

<table data-cellspacing="0">
<thead>
<tr class="header">
<th>Value</th>
<th>Default value</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>&amp;cftinstall</p></td>
<td>AXWAY.XFB.D332</td>
<td>Library prefix qualifiers for distribution environment</td>
</tr>
<tr class="even">
<td><p>&amp;distlev</p></td>
<td>CF030000</td>
<td>Distribution prefix level</td>
</tr>
<tr class="odd">
<td><p>&amp;hostuplib</p></td>
<td><p>AXWAY.XFB.D332.CF030000.UPLIB</p></td>
<td>Library prefix to upload product</td>
</tr>
<tr class="even">
<td><p>&amp;cftruntime</p></td>
<td>AXWAY.V332</td>
<td>Library for the runtime creation of the target environment</td>
</tr>
<tr class="odd">
<td><p>&amp;patch</p></td>
<td>N/A</td>
<td>Information about last patch applied</td>
</tr>
<tr class="even">
<td><p>&amp;format</p></td>
<td>A</td>
<td><p>Type of restoration product:</p>
<ul>
<li>A (ADRDSSU)</li>
<li>X (XMIT)</li>
</ul></td>
</tr>
<tr class="odd">
<td><p>&amp;hostname</p></td>
<td>N/A</td>
<td>z/OS hostname</td>
</tr>
<tr class="even">
<td><p>&amp;user</p></td>
<td>N/A</td>
<td>z/OS user</td>
</tr>
<tr class="odd">
<td><p>&amp;password</p></td>
<td>N/A</td>
<td>z/OS password</td>
</tr>
<tr class="even">
<td><p>&amp;installvol</p></td>
<td>N/A</td>
<td>Volume Serial for distribution environment</td>
</tr>
<tr class="odd">
<td><p>&amp;runtimevol</p></td>
<td>N/A</td>
<td>Volume Serial for runtime environment</td>
</tr>
<tr class="even">
<td><p>&amp;account</p></td>
<td>()</td>
<td>Accounting</td>
</tr>
<tr class="odd">
<td><p>&amp;class</p></td>
<td>A</td>
<td>Class</td>
</tr>
<tr class="even">
<td><p>&amp;unit</p></td>
<td>3390</td>
<td>Unit</td>
</tr>
<tr class="odd">
<td><p>&amp;submit</p></td>
<td>Y</td>
<td>Submit JCL for the runtime creation</td>
</tr>
</tbody>
</table>

Once you have configured and saved the file for silent installation, run the following command to start the installation:

-   UNIX/Linux: setup.sh --silent
-   Windows: setup.bat --silent

## Decompress the installation files

Use one of the following methods to unpack the installation files:

-   Decompress using the ADRDSSU format, *or*
-   Decompress using double Xmit format

### Decompress using the <span id="kanchor60"></span>ADRDSSU format

From the transferred distlib.UPLIB library, customize and submit the J1IDISTA JCL. Refer to the Note below for details.

This procedure:

-   Transforms the product file into an ADRDSSU file type (via IKJEFT01)

<!-- -->

-   Restores the Transfer CFT distribution files via ADRDSSU

<!-- -->

-   Creates a distribution environment

<!-- -->

-   Creates a Transfer CFT instance environment (if required)

To customize the JCL, apply a `change all` command on the following parameters:

-   distlib: distribution environment prefix

<!-- -->

-   volser: volume serial number, used to override the default value. If used, the statement marked as comment must be activated

<!-- -->

-   storclass: SMS Storage class, used to override the default value. If used, the statement marked as a comment must be activated

<table data-cellpadding="0" data-cellspacing="0">
<tbody>
<tr class="odd">
<td data-valign="top"></td>
<td data-valign="top"><span><strong>Note</strong></span></td>
<td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">The distribution files are restored with 5 qualifiers (ADRDSSU). You can modify 4 of these qualifiers, for example AXWAY.XFB.CFT332.CF030000, using the ADRDSSU parameter, step ADRD020 in J1IDISTA, but the fifth qualifier is hard coded.</td>
</tr>
</tbody>
</table>

### Decompress using <span id="kanchor61"></span>double Xmit

From the transferred distlib.UPLIB library, customize and submit the J1IDISTX JCL.

This procedure:

-   Performs two successive orders RECEIVE (via IKJEFT01)
-   Creates a distribution environment
-   Creates a Transfer CFT instance environment (if needed)
-   Creates a Composer connector environment for Transfer CFT (if needed)

To customize the JCL, apply a change all command to the following parameters:

-   distlib: distribution environment prefix
-   Volse: volume serial number, used to override the default value. If used, the statement marked as comment must be activated
