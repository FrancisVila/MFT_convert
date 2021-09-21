{
    "title": "Roll back an upgrade",
    "linkTitle": "Roll back an upgrade",
    "weight": "240"
}In the event that after upgrading a version you need to revert back to the previous version, you can perform the steps in this section using either the [automatic](#automati) procedure or the [manual](#manually) roll back and restore catalog procedure.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">If you executed transfers in <span>Transfer CFT</span> the new version that use parameters or metadata not available in the previous version, when you rollback the new metadata is lost.         </td>
      </tr>
</table>

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Tip  </b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Tip  &lt;/b&gt;" valign="top">CFTPGM is the standard name for the program library, and CFTPROD is the standard name for the library where the configuration files are usually located.         </td>
      </tr>
</table>

## Before you start

Before beginning the rollback procedure:

-   Check that you can access the Transfer CFT installation or upgrade packages for download from Axway at [support.axway.com](https://support.axway.com/).
-   Stop the Transfer CFT server and the Transfer CFT Copilot (UI) server. Enter:

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>CFTSTOP</p>
            <p>COPSTOP</p>
         </td>
      </tr>
   </tbody>
</table>

Optionally, you can use the display command to check the version or product details prior to upgrading.

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>CFTUTIL about         </td>
      </tr>
   </tbody>
</table>

## <span id="Automati"></span>Automatically roll back

### Uploading the installation package

Start the rollback process by uploading the Transfer CFT installation package in binary mode to the IBM i system:

1.  Log in with the `CFTINST `user.

2.  Create a temporary library: `CRTLIB CFTTMP`

3.  Create a SAVF file: `CRTSAVF FILE(CFTTMP/CFT37)`

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

1.  Restore the SAVF file in the temporary library:  
    

    <table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>RSTLIB SAVLIB(CFTPG) DEV(*SAVF) SAVF(CFTTMP/CFT37) OPTION(*NEW) RSTLIB(CFTTMP)         </td>
      </tr>
   </tbody>
</table>

<!-- -->

1.  After restoring the SAVF, you must add the library name in the first position of the library list for the user profile. Execute the command:  
    

    <table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>ADDLIBLE LIB(CFTTMP) POSITION(*FIRST)</p>
         </td>
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
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">The  user performing the upgrade requires the same rights as for a regular installation or update (*JOBCTL, *SPLCTL, and *ALLOBJ).         </td>
      </tr>
</table>

1.  Call the UPGRADE command for your Transfer CFT. Applying an UPGRADE of a version older than the version of your Transfer CFT rolls it back to this older version, but keeps your configuration.

In rollback mode, the UPGRADE command prompt resembles the following screen:

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>UPGRADE CFT (UPGRADE)</p>
            <p>Extract lib for the CFT  . . . . CFTEXTLIB      __________ </p>
            <p>CFT Program Library  . . . . . . CFTPGM         __________</p>
            <p>CFT Production Library . . . . . CFTPROD        __________</p>
            <p>Are you rolling back? . . . . . .ROLLBACK       '1'    </p>
            <p>Lib of the SAVF  . . . . . . . . LIBSAVF        '*LIBL'   </p>
            <p>SAVF of the version to apply . . SAVF           CFT37X       </p>
         </td>
      </tr>
   </tbody>
</table>

The following fields are mandatory; you should complete as per your system details:

-   CFTEXTLIB: Enter the name of the temporary library used to process the upgrade. This can be existing or non-existent library, but its content is cleared during the process.
-   CFTPGM: Enter the name of the library containing the binaries of your Transfer CFT to upgrade.
-   CFTPROD: Enter the name of the library containing the working files of your Transfer CFT to upgrade.
-   ROLLBACK: '1': Enables the rollback mode (YES).  
    ‘2’: Indicates that you are NOT rolling back to a previous Transfer CFT version (NO).
-   SAVF: This field only displays when you enter '1' in the ROLLBACK field. In this case, enter the name of the SAVF for the version you want to apply. The default value is the name of SAVF for the version that you downloaded.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Caution  </b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Caution  &lt;/b&gt;" valign="top">When performing a rollback, the default value of the SAVF field MUST match the version you want to roll back to. Please determine the name of the SAVF corresponding to the version you want to roll back to, as shown below:         </td>
      </tr>
</table>

<table cellspacing="0">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>
            <p>Transfer CFT version</p>
</th>
         <th>
            <p>SAVF name</p>
</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>
            <p>3.1.3</p>
         </td>
         <td>
            <p>CFT31X</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>3.2.4</p>
         </td>
         <td>
            <p>CFT32X</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>3.3.2</p>
         </td>
         <td>
            <p>CFT33X</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>3.6</p>
         </td>
         <td>
            <p>CFT36X</p>
         </td>
      </tr>
   </tbody>
</table>

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Tip  </b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Tip  &lt;/b&gt;" valign="top">The UPGRADE command is available as of  Transfer CFT 3.7.         </td>
      </tr>
</table>

## Roll back to a version that predates the UPGRADE command

The UPGRADE command was not available in Transfer CFT 3.6 and lower; however you can still execute the UPGRADE command to roll back to those versions. Use FTP in binary mode for the various upload steps to your system.

To roll back to version 3.6 or lower:

1.  Follow the [Upload instructions](#upload) to upload the rollback version SAVF to a temporary library, for example CFTTMP.
2.  Restore the SAVF in CFTTMP.
3.  Repeat the [Upload instructions](#upload) to upload the most recent Transfer CFT version SAVF to a second temporary library, for example CFTTMP2.
4.  Add the CFTTMP2 temporary library in the first position of your library list.

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>ADDLIBLE LIB(CFTTMP2) POSITION(*FIRST)</p>
         </td>
      </tr>
   </tbody>
</table>

1.  Call the UPGRADE command, and then press F4 to fill the fields. Remember to enable the rollback mode by changing the ROLLBACK value. The command to execute, again for example for version 3.6, should resemble the following:

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>UPGRADE CFTEXTLIB(CFTEXTLIB) CFTPGM(CFTPGM) CFTPROD(CFTPROD) ROLLBACK('1') LIBSAVF(CFTTMP) SAVF(CFT36X)           </td>
      </tr>
   </tbody>
</table>

## <span id="Manually"></span>Manually roll back

### Prerequisites

-   Save all the CFTPGM and CFTPROD before installing Transfer CFT 3.9.
-   Install to upgrade from Transfer CFT 3.4, 3.5, 3.6 (3.x) to Transfer CFT 3.9.

### Manual procedure

Perform the following tasks (we use 3.x in this example step procedure to indicate the version to roll back to):

1.  Migrate the Transfer CFT catalog file. On the IBM i system: 

    CALL PGM(CFTMI) PARM(‘MIGR’ ‘type=CAT, direct=FROMCAT, ifname=CFTPROD/CAT, ofname=CFTUPGLIB/CAT35’)

    Where CFTUPGLIB is a temporary backup library.

2.  Downgrade from Transfer CFT 3.6 to Transfer CFT 3.x version:
    1.  Rename CFTPGM and CFTPROD.
    2.  Install Transfer CFT3.x.

3.  Restore your EXEC procedures and the CFTPROD library template.

4.  Create a new Transfer CFT catalog file.

5.  Import the saved cftcat\_35 to the new Transfer CFT catalog file:

    CFTMI migr type=cat,direct=tocat,ifname=cftcat\_35,ofname=$CFTCATA

6.  On the IBM i system:

    CALL PGM(CFTMI) PARM(‘MIGR’ ‘type=CAT, direct=TOCAT, ifname=CFTUPGLIB/CAT35, ofname=CFTPROD/CAT’)