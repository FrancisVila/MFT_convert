{
    "title": "Create an Express Package",
    "linkTitle": "Create an Express Package",
    "weight": "180"
}A product deployment package in Transfer CFT is called an Express Package. For the iSeries platform, you can create a deployment package for Transfer CFTs to be used with <span class="mc-variable suite_variables.Central_GovernanceName variable">Central Governance</span>, or for standalone Transfer CFTs.

This section describes how to create a reusable and distributable <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> package to simplify and ease the task of installing and configuring <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span>s on multiple servers of the same architecture.

<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Note</strong></span>         </td>
         <td>You can only install a Transfer CFT Express Package on the same platform as the one on which it was generated.         </td>
      </tr>
   </tbody>
</table>

## Create a deployment package for <span class="mc-variable suite_variables.TransferCFTName variable">Transfer CFT</span>s used with Central Governance

Perform the following steps:

1.  Create a user profile using the command: <span class="code">CRTUSRPRF</span>

2.  Create a temporary library, for example:  


        CRTLIB CFTTMP

3.  Create a save file (\*SAVF) in the CFTTMP library, for example:  



        CRTSAVF FILE(CFTTMP/CFT32XL) TEXT('Transfer CFT Distribution save file')

4.  Use FTP in binary mode to send the save file to an iSeries system. Open an FTP session, and enter:  



        Set Transfer Mode to bin
        cd CFTTMP
        put Transfer_CFT_os400.bin CFT32XL
        quit

5.  Restore the Transfer CFT save file, for example:  



        RSTLIB SAVLIB(CFTPG) DEV(*SAVF) SAVF(CFTTMP/CFT32XL) RSTLIB(CFTTMP)

6.  Install a Transfer CFT 3.2.4 with Central Governance (you must use this command for all iSeries Transfer CFT deployments).

-   See the example and options described in the INSTALL section and customize to suit your business needs. Details on <a href="../install_intro_ibmi/perform_auto_installation" class="MCXref xref">Silent installation</a>.

<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Note</strong></span>         </td>
         <td>If you want to add or modify the installation parameters, you must run the INSTALL command after selecting F4. Answer the prompted questions to configure the product for your production. At the end of your first installation, press F9 to execute the recall command. This command must be used for all your deployments.         </td>
      </tr>
   </tbody>
</table>

1.  Use Central Governance to deploy and configure your Transfer CFTs as needed.

## Create a <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> deployment package for standalone usage

In this procedure, you must first create a SAVF file that contains all of your necessary configurations for your deployment including:

-   Static configuration, such as protocols (CFTPROT), networks (CFTNET), UCONF parameters, and so on
-   Partners (CFTPART, CFTTCP)

<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Note</strong></span>         </td>
         <td>If you create partners to export, DO NOT use the NSPART parameter in the CFTPART definition. The target Transfer CFT instead uses the CFTPARM PART/NPART values.         </td>
      </tr>
   </tbody>
</table>

-   Flows (CFTSEND and CFTRECV)
-   SSL certificates
-   Processing scripts and EXITs
-   Additional Axway components that you use with Transfer CFT such as Sentinel, PassPort, etc.

### Procedure

On the local machine where you have <span class="mc-variable suite_variables.TransferCFTName variable">Transfer CFT</span> installed:

1.  Create a temporary library that will contain all the items you want to deploy, for example:  


        CRTLIB CFTCONF

2.  Copy all the configuration elements you want to deploy into this library, for example:  


        CPYF FROMFILE(CFTPROD/UTIN) TOFILE(CFTCONF/UTIN) FROMMBR(CGPARAM) TOMBR(TCPPARAM)

3.  Create a backup for your library CFTCONF, for example:  



        1.  CRTSAVF FILE(CFTCONF/CFTCONFSVF)
        2.  SAVLIB LIB(CFTCONF) DEV(*SAVF) SAVF(CFTCONF/CFTCONFSVF)
        3.  Get the CFTCONFSVF.savf (in binary mode)

On the other machines, where you want to deploy <span class="mc-variable suite_variables.TransferCFTName variable">Transfer CFT</span>:

1.  Create a temporary library, for example:  


        CRTLIB CFTTMP

2.  Create two save file (\*SAVF) in the CFTTMP library, for example:  



        1.  CRTSAVF FILE(CFTTMP/CFT32XL) TEXT('Transfer CFT Distribution')
        2.  CRTSAVF FILE(CFTTMP/CFTCONFSVF) TEXT('CFT configuration')

3.  Use FTP in binary mode to send the save file to an Iserie system. Open an FTP session, and enter:  



        Set Transfer Mode to bin
        cd CFTTMP
        put Transfer_CFT_os400.bin CFT32XL (SAVF with Transfer CFT)
        put CFTCONFSVF.savf CFTCONFSVF (SAVF with CFT configuration)
        quit

4.  Restore the Transfer CFT save file, for example:  


        RSTLIB SAVLIB(CFTPG) DEV(*SAVF) SAVF(CFTTMP/CFT32XL) RSTLIB(CFTTMP)

5.  Installing a Transfer CFT 3.2.4 without Central Governance  


        INSTALL

<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Note</strong></span>         </td>
         <td>When you run INSTALL without parameters, you run the default installation with the CFTPGM and CFTPROD libraries.         </td>
      </tr>
   </tbody>
</table>

<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Note</strong></span>         </td>
         <td>As of <span class="mc-variable suite_variables.TransferCFTName variable">Transfer CFT</span> 3.3.2, you can define the user for the <span class="mc-variable suite_variables.TransferCFTName variable">Transfer CFT</span> installation. This user can be different from the current user. From the INSTALL command, select F4 (Prompt) and modify the USERINST value. This user must exist on the machine; if it does not, you can use the CRTUSRPRF command to create it.         </td>
      </tr>
   </tbody>
</table>

1.  Restore the Transfer CFT configuration save file, for example:  


        RSTLIB SAVLIB(CFTCONF) DEV(*SAVF) SAVF(CFTTMP/CFTCONFSVF) RSTLIB(CFTPROD)

2.  Apply your configuration to your new environment, for example:  



        1.  CFTUTIL PARAM('#CFTPROD/<CFTCONF>)
        2.  PKIUTIL PARAM('#CFTPROD/<PKICONF>')

## Limitations

-   Transfer CFT Express Package does not support cluster mode installations.
-   Transfer CFT Express Package cannot embed a Transfer CFT upgrade pack.