{
    "title": "Create an Express Package",
    "linkTitle": "Create an Express Package",
    "weight": "180"
}A product deployment package in Transfer CFT is called an Express Package. For the iSeries platform, you can create a deployment package for Transfer CFTs to be used with Central Governance, or for standalone Transfer CFTs.

This section describes how to create a reusable and distributable Transfer CFT package to simplify and ease the task of installing and configuring Transfer CFTs on multiple servers of the same architecture.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">You can only install a Transfer CFT Express Package on the same platform as the one on which it was generated.          </td>
      </tr>
</table>

## Create a deployment package for Transfer CFTs used with Central Governance

Perform the following steps:

1.  Create a user profile using the command: CRTUSRPRF

2.  Create a temporary library, for example:  
    

    <table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>CRTLIB CFTTMP         </td>
      </tr>
   </tbody>
</table>

3.  Create a save file (\*SAVF) in the CFTTMP library, for example:  
    

    <table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>CRTSAVF FILE(CFTTMP/CFT32XL) TEXT('Transfer CFT Distribution save file')</p>
         </td>
      </tr>
   </tbody>
</table>

4.  Use FTP in binary mode to send the save file to an iSeries system. Open an FTP session, and enter:  
    

    <table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>Set Transfer Mode to bin</p>
            <p>cd CFTTMP</p>
            <p>put Transfer_CFT_os400.bin CFT32XL</p>
            <p>quit</p>
         </td>
      </tr>
   </tbody>
</table>

5.  Restore the Transfer CFT save file, for example:  
    

    <table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>RSTLIB SAVLIB(CFTPG) DEV(*SAVF) SAVF(CFTTMP/CFT32XL) RSTLIB(CFTTMP)</p>
         </td>
      </tr>
   </tbody>
</table>

6.  Install a Transfer CFT 3.2.4 with Central Governance (you must use this command for all iSeries Transfer CFT deployments).

-   See the example and options described in the INSTALL section and customize to suit your business needs. Details on [Silent installation](../install_intro_ibmi/perform_auto_installation).

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">If you want to add or modify the installation parameters, you must run the INSTALL command after selecting F4. Answer the prompted questions  to configure the product for your production. At the end of your first installation, press F9 to execute the recall command. This command must be used for all your deployments.         </td>
      </tr>
</table>

1.  Use Central Governance to deploy and configure your Transfer CFTs as needed.

## Create a Transfer CFT deployment package for standalone usage

In this procedure, you must first create a SAVF file that contains all of your necessary configurations for your deployment including:

-   Static configuration, such as protocols (CFTPROT), networks (CFTNET), UCONF parameters, and so on
-   Partners (CFTPART, CFTTCP)

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">If you create partners to export, DO NOT use the NSPART parameter in the CFTPART definition. The target Transfer CFT instead uses the CFTPARM PART/NPART values.         </td>
      </tr>
</table>

-   Flows (CFTSEND and CFTRECV)
-   SSL certificates
-   Processing scripts and EXITs
-   Additional Axway components that you use with Transfer CFT such as Sentinel, PassPort, etc.

### Procedure

On the local machine where you have Transfer CFT installed:

1.  Create a temporary library that will contain all the items you want to deploy, for example:  
    

    <table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>CRTLIB CFTCONF         </td>
      </tr>
   </tbody>
</table>

2.  Copy all the configuration elements you want to deploy into this library, for example:  
    

    <table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>CPYF FROMFILE(CFTPROD/UTIN) TOFILE(CFTCONF/UTIN) FROMMBR(CGPARAM) TOMBR(TCPPARAM)         </td>
      </tr>
   </tbody>
</table>

3.  Create a backup for your library CFTCONF, for example:  
    

    <table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>1.	CRTSAVF FILE(CFTCONF/CFTCONFSVF)</p>
            <p>2.	SAVLIB LIB(CFTCONF) DEV(*SAVF) SAVF(CFTCONF/CFTCONFSVF)</p>
            <p>3.	Get the CFTCONFSVF.savf (in binary mode)</p>
         </td>
      </tr>
   </tbody>
</table>

On the other machines, where you want to deploy Transfer CFT:

1.  Create a temporary library, for example:  
    

    <table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>CRTLIB CFTTMP         </td>
      </tr>
   </tbody>
</table>

2.  Create two save file (\*SAVF) in the CFTTMP library, for example:  
    

    <table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>1.	CRTSAVF FILE(CFTTMP/CFT32XL) TEXT('Transfer CFT Distribution')</p>
            <p>2.	CRTSAVF FILE(CFTTMP/CFTCONFSVF) TEXT('CFT configuration')</p>
         </td>
      </tr>
   </tbody>
</table>

3.  Use FTP in binary mode to send the save file to an Iserie system. Open an FTP session, and enter:  
    

    <table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>Set Transfer Mode to bin</p>
            <p>cd CFTTMP</p>
            <p>put Transfer_CFT_os400.bin CFT32XL (SAVF with Transfer CFT)</p>
            <p>put CFTCONFSVF.savf CFTCONFSVF (SAVF with CFT configuration)</p>
            <p>quit</p>
         </td>
      </tr>
   </tbody>
</table>

4.  Restore the Transfer CFT save file, for example:  
    

    <table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>RSTLIB SAVLIB(CFTPG) DEV(*SAVF) SAVF(CFTTMP/CFT32XL) RSTLIB(CFTTMP)         </td>
      </tr>
   </tbody>
</table>

5.  Installing a Transfer CFT 3.2.4 without Central Governance  
    

    <table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>INSTALL         </td>
      </tr>
   </tbody>
</table>

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">When you run INSTALL without parameters, you run the default installation with the CFTPGM and CFTPROD libraries.         </td>
      </tr>
</table>

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">As of <span>Transfer CFT</span> 3.3.2, you can define the user for the  <span>Transfer CFT</span> installation. This user can be different from the current user. From the INSTALL command, select F4 (Prompt) and modify the USERINST value. This user must exist on the machine; if it does not, you can use the CRTUSRPRF command to create it.         </td>
      </tr>
</table>

1.  Restore the Transfer CFT configuration save file, for example:  
    

    <table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>RSTLIB SAVLIB(CFTCONF) DEV(*SAVF) SAVF(CFTTMP/CFTCONFSVF) RSTLIB(CFTPROD)         </td>
      </tr>
   </tbody>
</table>

2.  Apply your configuration to your new environment, for example:  
    

    <table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>1.	CFTUTIL PARAM('#CFTPROD/&lt;CFTCONF&gt;)</p>
            <p>2.	PKIUTIL PARAM('#CFTPROD/&lt;PKICONF&gt;')</p>
         </td>
      </tr>
   </tbody>
</table>

## Limitations

-   Transfer CFT Express Package does not support cluster mode installations.
-   Transfer CFT Express Package cannot embed a Transfer CFT upgrade pack.
