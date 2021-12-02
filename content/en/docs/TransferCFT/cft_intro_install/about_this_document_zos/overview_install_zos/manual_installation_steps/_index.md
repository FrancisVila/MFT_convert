{
    "title": "Advanced installation",
    "linkTitle": "Advanced installation ",
    "weight": "220"
}## Manually install or modify installation

The following JCLs are contained in the INSTALL library. Execute the JCLs in the order listed in the following table.

<table>
   <thead>
      <tr>
<th >Step         </th>
<th >JCL         </th>
<th >Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>Target customization         </td>
      </tr>
      <tr>
         <td>1         </td>
         <td><p><a href="../t_customize_instance_zos#Modifying_A03PARM">A03PARM</a></p>         </td>
         <td><p>Customize file parameters</p>         </td>
      </tr>
      <tr>
         <td>2         </td>
         <td><p><a href="../installation_parameters_to_customize">A00CUSTO</a></p>         </td>
         <td><p>Customize JOBs installation</p>         </td>
      </tr>
      <tr>
         <td>3         </td>
         <td>A06FILES         </td>
         <td>Create and initialize instance files         </td>
      </tr>
      <tr>
         <td>4         </td>
         <td><p>A12OPTS</p>         </td>
         <td><p>Select options for Transfer CFT operations</p>
<p><em>Optional step</em></p>         </td>
      </tr>
      <tr>
         <td>After performing Steps 1 -4, you can either continue with the following step-by-step instructions, or start the JOB A05ALL, which uses the customized settings in the A03PARM file to run.         </td>
      </tr>
      <tr>
         <td>5         </td>
         <td><p>B20LINK</p>         </td>
         <td><p>General LINK-EDIT of Transfer CFT modules. Submit for non-SMP/E installations.</p>         </td>
      </tr>
      <tr>
         <td>6         </td>
         <td>CFTGNKEY         </td>
         <td>Generate an encryption key. See also <a href="../t_customize_instance_zos#Password">Password encryption</a>.         </td>
      </tr>
      <tr>
         <td>7         </td>
         <td><p>COPA010</p>         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>Transfer CFT installation customization         </td>
      </tr>
      <tr>
         <td>8         </td>
         <td><p><a href="../zos_auto_install_a05all/t_customize_install_zos#JOB%C2%A0H80EXEC">CFT$SET</a></p>
<p>CFT$SETC </p>         </td>
         <td><p>Select one of the two options available for this step to set the UCONF variables and create Transfer CFT parameters from a template.</p>
<ul>
<li>CFT$SET: When not using Central Governance.</li>
<li>CFT$SETC: When using Central Governance.</li>
</ul>
<p> </p>         </td>
      </tr>
      <tr>
         <td>9         </td>
         <td><p><a href="../zos_auto_install_a05all/t_customize_install_zos#D40INIT">D40INIT</a></p>         </td>
         <td><p>Format the Transfer CFT work files</p>         </td>
      </tr>
      <tr>
         <td>10         </td>
         <td><a href="../t_customize_instance_zos">E50PARM</a>         </td>
         <td>CFTPARM configuration example         </td>
      </tr>
      <tr>
         <td>11         </td>
         <td><p><a href="t_configure_navigator_server_zos">COPA020</a></p>         </td>
         <td><p><a href="t_configure_navigator_server_zos">Configure Transfer CFT Copilot server</a></p>         </td>
      </tr>
      <tr>
         <td>Optional steps         </td>
      </tr>
      <tr>
         <td>12         </td>
         <td><p>C32XMEM</p>         </td>
         <td><p>Communication server</p>         </td>
      </tr>
      <tr>
         <td>13         </td>
         <td><p><a href="t_configure_optional_features_zos#Create%20a%20Transfer%20CFT%20PKI%20file%C2%A0D43PKI">D43PKI</a></p>
<p><a href="t_configure_optional_features_zos#Connect%20with%20PassPort%C2%A0D44PASS">D44PASS</a></p>
<p><a href="t_configure_optional_features_zos">D47SYST</a></p>         </td>
         <td><p>Select one of the options listed for Step 12:</p>
<ul>
<li>D43PKI: Create internal datafile for PKI data</li>
<li>D44PASS: Declare link to PassPort server</li>
<li>D47SYST: Enable use of system PKI</li>
</ul>         </td>
      </tr>
      <tr>
         <td>14         </td>
         <td><p><a href="t_install_sentinel_zos">SN05CONF</a></p>         </td>
         <td><p><a href="t_install_sentinel_zos">Customize Sentinel</a> configuration file</p>         </td>
      </tr>
      <tr>
         <td>15         </td>
         <td>CFTHEART         </td>
         <td>Activate Transfer CFT Heartbeats for Sentinel Dashboards         </td>
      </tr>
      <tr>
         <td>16         </td>
         <td>CFTCGREG         </td>
         <td>Register {{< TransferCFT/transfercftname  >}} with         </td>
      </tr>
      <tr>
         <td>17         </td>
         <td>CFTCGPKI         </td>
         <td>Used to register {{< TransferCFT/transfercftname  >}} with         </td>
      </tr>
      <tr>
         <td>18         </td>
         <td>XSRRUN         </td>
         <td><p>Launches the Java virtual machine (JVM).</p>
<blockquote>
<p><strong>Note:</strong></p>
<p>Customize JOB card.</p>
</blockquote>         </td>
      </tr>
      <tr>
         <td>19         </td>
         <td>XSRA010         </td>
         <td>Install files for the Secure Relay Master Agent
on the USS environment.         </td>
      </tr>
      <tr>
         <td>20         </td>
         <td>XSRA015         </td>
         <td>Create the Runtime directory for the Transfer CFT Secure Relay Master Agent.         </td>
      </tr>
      <tr>
         <td>21         </td>
         <td>XSRA020         </td>
         <td>Update the Secure Relay parameters for UCONF.         </td>
      </tr>
      <tr>
         <td>22         </td>
         <td>XSRA050         </td>
         <td>Update the Transfer CFT parameters samples.         </td>
      </tr>
      <tr>
         <td>23         </td>
         <td>RESTCFG         </td>
         <td>REST API configuration.         </td>
      </tr>
   </tbody>
</table>

To manually install, you can run the following JOBs.

<span id="JOB B20LINK LINK-EDIT Transfer CFT "></span><span id="kanchor4"></span>

## LINK-EDIT Transfer CFT using JOB B20LINK

You should only use this JCL for non-SMP/E installations.

The B20LINK JOB does a LINK-EDIT of Transfer CFT z/OS modules. Programs that are created in this step use the DLL mechanism.

Before beginning it is recommended that you save the execution listing for this JOB.

The CFTMAIN/CFTMA31 programs are copied in an authorized APF library for the cases in which Transfer CFT:

-   Writes ACCOUNT records to SMF.

<!-- -->

-   Uses the RACF options.

<!-- -->

-   Sends messages to TSO users.

<!-- -->

-   Uses dynamic UCBs (DRM) or UCBs that are defined in 31 bits in IODF.

<!-- -->

-   Uses the ARM services.
-   Uses a shared catalog cache.
-   Frees unused space for received files.

> **Note:**
>
> The return code generated by the LINK-EDIT must be 0.

> **Note:**
>
> IMPORTANT - If you have applied a patch, resubmitting the JCL B20LINK resets all the executable files generated by this procedure to their original versions and therefore cancels any and all applied patches.

<span id="JOB B25LKWS LINK-EDIT Web services "></span>

## 

<span id="COPA010 Setting up the CFT Navigator server files in USS "></span><span id="kanchor5"></span>

## Set up Copilot server files in USS using COPA010

The files that are used by the Transfer CFT Copilot server are located in the USS environment. The implementation directory for these files is partially customizable. This directory is composed of two parameter setting sections. The first section is defined by cftroot in the customization file (A03PARM in the INSTALL library, e.g. /home/AXWAY/CFT&lt;version>). The second section is a set, non-modifiable parameter /wwwroot, which corresponds to the Transfer CFT Copilot component.

Prerequisites

-   Authorization to create the directory: cftroot/wwwroot

<!-- -->

-   Available disk space: 25,000 K

**Procedure**

You can use the JCL COPA010 to set up the Transfer CFT Copilot files in USS.

1.  Extract the Transfer CFT Copilot package from the distribution libraries in a temporary sequential file with a fixed format.
2.  Transfer and install the files that are used by Transfer CFT Copilot. Use the pax command via a REXX procedure to perform this task. 
3.  Execute the command: pax -rvf "//'tempory.seq.fix’" -o saveext

> **Note:**
>
> The file access rights are Read only for Group and others. Users must have rights to read the file system where the Transfer CFT Copilot USS files are installed. To get the file system name, enter the command: df .

**Example**

```
/home/AXWAY/CFT<version>/wwwroot/applets: #df .
Mounted on Filesystem Avail/Total Files Status
/home/AXWAY (xxxxxx.yyyyy.HFSAXWAY) 235680/1872000 4294927912 Available
```

Related topics

-   [Create a Transfer CFT instance](../distribution_environment_installation/t_install_instance_envr_zos)
-   [Customize the JCL installation files](../installation_parameters_to_customize)
