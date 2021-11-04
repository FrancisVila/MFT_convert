{
    "title": "Upload and restore the installation files",
    "linkTitle": "Upload and restore installation files",
    "weight": "180"
}This section describes the upload and restore options available for Transfer CFT <span class="mc-variable axway_variables.Release_Number variable">3.9</span> for the IBM i platform to perform prior to installation, using FTP and the RSTLIB command.

Before starting a Transfer CFT session, you must add the value \*none in the initial program call to call a screen menu directly. Otherwise the session cannot start.

<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Note</strong></span>         </td>
         <td>CFTPGM is the standard name for the programs library.         </td>
      </tr>
   </tbody>
</table>

Begin the installation process by uploading the Transfer CFT installation package, in binary mode, to the IBM i system:

1.  Log in with the <span class="bold_in_para">CFTINST </span>user.

2.  Create a temporary library:  


        CRTLIB CFTTMP

3.  Create a SAVF file:  


        CRTSAVF FILE(CFTTMP/CFT37)

4.  Upload the installation package to the SAVF in binary mode using FTP:  



        binary
        cd CFTTMP
        put Transfer_CFT_os400.bin CFT37

<!-- -->

1.  Restore the SAVF file:  


        RSTLIB SAVLIB(CFTPG) DEV(*SAVF) SAVF(CFTTMP/CFT37) OPTION(*NEW) RSTLIB(CFTTMP)