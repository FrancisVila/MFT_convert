{
    "title": "Upload and restore installation files",
    "linkTitle": "Upload and restore installation files",
    "weight": "180"
}This section describes the upload and restore options available for Transfer CFT 3.9 for the IBM i platform to perform prior to installation, using FTP and the RSTLIB command.

Before starting a Transfer CFT session, you must add the value \*none in the initial program call to call a screen menu directly. Otherwise the session cannot start.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">CFTPGM is the standard name for the programs library.         </td>
      </tr>
</table>

Begin the installation process by uploading the Transfer CFT installation package, in binary mode, to the IBM i system:

1.  Log in with the CFTINST user.

2.  Create a temporary library:  
    

    <table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>CRTLIB CFTTMP         </td>
      </tr>
   </tbody>
</table>

3.  Create a SAVF file:   
    

    <table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>CRTSAVF FILE(CFTTMP/CFT37)         </td>
      </tr>
   </tbody>
</table>

4.  Upload the installation package to the SAVF in binary mode using FTP:  
    

    <table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>binary</p>
            <p>cd CFTTMP</p>
            <p>put Transfer_CFT_os400.bin CFT37</p>
         </td>
      </tr>
   </tbody>
</table>

<!-- -->

1.  Restore the SAVF file:  
    

    <table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>RSTLIB SAVLIB(CFTPG) DEV(*SAVF) SAVF(CFTTMP/CFT37) OPTION(*NEW) RSTLIB(CFTTMP)         </td>
      </tr>
   </tbody>
</table>
