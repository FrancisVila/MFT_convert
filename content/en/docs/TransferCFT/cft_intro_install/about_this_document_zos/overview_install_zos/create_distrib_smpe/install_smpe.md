{
    "title": "Create a Transfer CFT instance ",
    "linkTitle": "Create a Transfer CFT instance",
    "weight": "180"
}## SMP/E FMIDs list

The Transfer CFT software has a SYSMOD FMID (Function Module ID) that identifies the software and its release number. For example, FMID TCF0300 identifies the Transfer CFT 3.3.2 release.

<table>
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1"><p>FMID</p>         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1"><p>Format</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>TCF0100</p>         </td>
         <td><ul>
</ul>         </td>
      </tr>
   </tbody>
</table>

## Upload the SMP/E package to the mainframe

1.  Unzip the package file, for example Transfer\_CFT\_3.3.2\_install\_mvs\_BNnnnnnnnn.smpe.zip.
2.  Run the setup.bat (Windows) or setup.sh (Unix).
3.  Enter the following parameters in the console. Upon completion you require an FTP client.

<table>
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1"><p>Question</p>         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1"><p>Default value</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Dataset name for the product SMPE samples</p>         </td>
         <td><p>AXWAY.SMPE.CFT332.SMPCNTL</p>         </td>
      </tr>
      <tr>
         <td><p>USS SMP/E Network Temporary Store</p>         </td>
         <td><p>/home/AXWAY/smpnts</p>         </td>
      </tr>
      <tr>
         <td><p>USS package subdirectory</p>         </td>
         <td><p>CFT332</p>         </td>
      </tr>
      <tr>
         <td><p>Hostname mainframe address</p>
<p>Login user</p>
<p>Login password</p>         </td>
         <td><p> </p>
<p> </p>         </td>
      </tr>
   </tbody>
</table>

-   The setup procedure allocates the destination library dataset (default is AXWAY.SMPE.CFT332.SMPCNTL),  
    with the attributes recfm=fb,lrecl=80,blksize=27920,space=(cyl,(1,5)).
    -   To add a volume or device name, edit the &vol= or &unit= field in the silent\_smpe\_install.conf file.
-   The sample member $C\* is transferred to the dataset using FTP in text mode.
-   The setup procedure creates the destination USS directory (default is /home/AXWAY/smpnts), and subdirectory (default is CFT332).
-   The Transfer\_CFT\_mvs.pax.Z SMP/E package file is transferred to the subdirectory using FTP in binary mode, and renamed to CFT332.pax.Z  (approximately 150 Mbytes).

### Silent mode

You can run the setup procedure in silent mode, `setup –s`. In this case, you do not have to enter parameters in the console, but prior to starting you must update the s`ilent_smpe_install.conf` file located in the install directory.

## Create a new Transfer CFT SMP/E environment

The user ID you use must have read access to the SAF facility class resources GIM.CMD.command and GIM.PGM.program, for example PERMIT GIM.\* CLASS(FACILITY) ID(user ID) ACCESS(READ).

1.  Edit the sample jobs in the following table, modifying as necessary; supply a valid JOB JCL card statement, select and modify the dataset qualifier &HLQ&, and the optional device &UNIT& and volume &VOLUME&.  
    <table>
       <thead>
          <tr>
    <th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1"><p>Member Name</p>         </th>
    <th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1"><p>Description</p>         </th>
          </tr>
       </thead>
       <tbody>
          <tr>
             <td><p>$C01DCSI</p>         </td>
             <td><p>Allocate the SMP/E CSI, and the operational and work data sets used by SMP/E.</p>         </td>
          </tr>
          <tr>
             <td><p>$C02DZON</p>         </td>
             <td><p>Define the SMP/E distribution and target zones.</p>         </td>
          </tr>
       </tbody>
    </table>
2.  Submit the jobs in the order listed.

## Receive the Transfer CFT SMP/E product

1.  Edit the sample job listed in the following table, modifying as necessary; supply a valid JOB JCL card statement, select and modify the dataset qualifier &HLQ&.  
    <table>
       <thead>
          <tr>
    <th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1"><p>Member name</p>         </th>
    <th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1"><p>Description</p>         </th>
          </tr>
       </thead>
       <tbody>
          <tr>
             <td><p>$C10RECV</p>         </td>
             <td><p>UNPAX the archive package and RECEIVE the FMIDs functions.</p>         </td>
          </tr>
       </tbody>
    </table>
2.  Submit the job.  
    The following data sets (approximately 300 cylinders) are created and suffixed by their corresponding FMID identifier (TCF0nnn) and RELFILEs number (Fn).  
    <table>
       <thead>
          <tr>
    <th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1"><p>File Number</p>         </th>
    <th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1"><p>Data Set Suffix</p>         </th>
    <th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1"><p>Description</p>         </th>
          </tr>
       </thead>
       <tbody>
          <tr>
             <td><p>  1</p>         </td>
             <td><p>TCF0nnn.F1</p>         </td>
             <td><p>HFS pax files</p>         </td>
          </tr>
          <tr>
             <td><p>  2</p>         </td>
             <td><p>TCF0nnn.F2</p>         </td>
             <td><p>Transfer CFT XML files</p>         </td>
          </tr>
          <tr>
             <td><p>  3</p>         </td>
             <td><p>TCF0nnn.F3</p>         </td>
             <td><p>Transfer CFT exec procedures </p>         </td>
          </tr>
          <tr>
             <td><p>  4</p>         </td>
             <td><p>TCF0nnn.F4</p>         </td>
             <td><p>Transfer CFT JCLs</p>         </td>
          </tr>
          <tr>
             <td><p>  5</p>         </td>
             <td><p>TCF0nnn.F5</p>         </td>
             <td><p>Trusted File messages</p>         </td>
          </tr>
          <tr>
             <td><p>  6</p>         </td>
             <td><p>TCF0nnn.F6</p>         </td>
             <td><p>Transfer CFT parameter and JCL samples</p>         </td>
          </tr>
          <tr>
             <td><p>  7</p>         </td>
             <td><p>TCF0nnn.F7</p>         </td>
             <td><p>Transfer CFT general parameters</p>         </td>
          </tr>
          <tr>
             <td><p>  8</p>         </td>
             <td><p>TCF0nnn.F8</p>         </td>
             <td><p>Link-edit maps</p>         </td>
          </tr>
          <tr>
             <td><p>  9</p>         </td>
             <td><p>TCF0nnn.F9</p>         </td>
             <td><p>Transfer CFT load modules</p>         </td>
          </tr>
          <tr>
             <td><p>10</p>         </td>
             <td><p>TCF0nnn.F10</p>         </td>
             <td><p>Copy COBOL</p>         </td>
          </tr>
          <tr>
             <td><p>11</p>         </td>
             <td><p>TCF0nnn.F11</p>         </td>
             <td><p>H headers</p>         </td>
          </tr>
          <tr>
             <td><p>12</p>         </td>
             <td><p>TCF0nnn.F12</p>         </td>
             <td><p>Assembler macros</p>         </td>
          </tr>
          <tr>
             <td><p>13</p>         </td>
             <td><p>TCF0nnn.F13</p>         </td>
             <td><p>Assembler samples</p>         </td>
          </tr>
          <tr>
             <td><p>14</p>         </td>
             <td><p>TCF0nnn.F14</p>         </td>
             <td><p>C samples</p>         </td>
          </tr>
          <tr>
             <td><p>15</p>         </td>
             <td><p>TCF0nnn.F15</p>         </td>
             <td><p>COBOL samples</p>         </td>
          </tr>
       </tbody>
    </table>

## Install the target libraries with SMP/E

1.  Edit the sample jobs that are listed in the following table, modifying as necessary; supply a valid JOB JCL card statement, select and modify the dataset qualifier &HLQ& and the optional device &UNIT& and volume &VOLUME&.  
    <table>
       <thead>
          <tr>
    <th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1"><p>Member name</p>         </th>
    <th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1"><p>Description</p>         </th>
          </tr>
       </thead>
       <tbody>
          <tr>
             <td><p>$C20ALLT</p>         </td>
             <td><p>Allocate the Target libraries.</p>         </td>
          </tr>
          <tr>
             <td><p>$C30FAPP</p>         </td>
             <td><p>Perform an APPLY (with the CHECK operand) to install the SYSMOD functions in the target zone and libraries.</p>         </td>
          </tr>
       </tbody>
    </table>

2.  Submit the jobs in the order listed.  
    If the $C30FAPP return code equals zero, edit $C30FAPP, remove the CHECK command, and resubmit the job.  
    The $C20ALLT job creates, and the $C30FAPP job updates, the following data sets (approximately 300 cylinders).  

    <table>
       <thead>
          <tr>
    <th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1"><p>Data Set Suffix</p>         </th>
    <th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1"><p>File Type</p>         </th>
    <th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1"><p>Description</p>         </th>
          </tr>
       </thead>
       <tbody>
          <tr>
             <td><p>CF0nnnnn.SCR          </p>         </td>
             <td><p>PDSE / VB</p>         </td>
             <td><p>HFS pax files</p>         </td>
          </tr>
          <tr>
             <td><p>CF0nnnnn.XMLLIB         </p>         </td>
             <td><p>PDSE / VB</p>         </td>
             <td><p>Transfer CFT XML files</p>         </td>
          </tr>
          <tr>
             <td><p>CF0nnnnn.EXEC        </p>         </td>
             <td><p>PDS / FB</p>         </td>
             <td><p>Transfer CFT exec procedures </p>         </td>
          </tr>
          <tr>
             <td><p>CF0nnnnn.INSTALL  </p>         </td>
             <td><p>PDS / FB</p>         </td>
             <td><p>Transfer CFT JCLs</p>         </td>
          </tr>
          <tr>
             <td><p>CF0nnnnn.PKIMSG  </p>         </td>
             <td><p>PDSE / VB</p>         </td>
             <td><p>Trusted Files messages</p>         </td>
          </tr>
          <tr>
             <td><p>CF0nnnnn.SAMPLE  </p>         </td>
             <td><p>PDS / FB</p>         </td>
             <td><p>Transfer CFT parameter and JCL samples</p>         </td>
          </tr>
          <tr>
             <td><p>CF0nnnnn.UPARM    </p>         </td>
             <td><p>PDS / VB</p>         </td>
             <td><p>Transfer CFT general parameters</p>         </td>
          </tr>
          <tr>
             <td><p>CF0nnnnn.CNTL         </p>         </td>
             <td><p>PDSE/ FB</p>         </td>
             <td><p>Link-edit maps</p>         </td>
          </tr>
          <tr>
             <td><p>CF0nnnnn.LOAD          </p>         </td>
             <td><p>PDSE / U</p>         </td>
             <td><p>Transfer CFT load modules</p>         </td>
          </tr>
          <tr>
             <td><p>CF0nnnnn.COPY       </p>         </td>
             <td><p>PDSE/ FB</p>         </td>
             <td><p>Copy COBOL</p>         </td>
          </tr>
          <tr>
             <td><p>CF0nnnnn.H               </p>         </td>
             <td><p>PDSE / VB</p>         </td>
             <td><p>H headers</p>         </td>
          </tr>
          <tr>
             <td><p>CF0nnnnn.MAC          </p>         </td>
             <td><p>PDSE / FB</p>         </td>
             <td><p>Assembler macros</p>         </td>
          </tr>
          <tr>
             <td><p>CF0nnnnn.SAMPLEA </p>         </td>
             <td><p>PDSE / FB</p>         </td>
             <td><p>Assembler samples</p>         </td>
          </tr>
          <tr>
             <td><p>CF0nnnnn.SAMPLEC </p>         </td>
             <td><p>PDSE / VB</p>         </td>
             <td><p>C samples</p>         </td>
          </tr>
          <tr>
             <td><p>CF0nnnnn.SAMPLEO </p>         </td>
             <td><p>PDSE / FB</p>         </td>
             <td><p>COBOL samples</p>         </td>
          </tr>
       </tbody>
    </table>

    ## Create the Transfer CFT instance files

    Edit the sample job listed below, modifying as necessary: supply a valid JOB JCL card statement, choose and modify the dataset qualifier &HLQ& of the SMP/E target libraries, and select the appropriate Transfer CFT instance qualifier &CFT& and Transfer CFT instance device &UNIT& and volume &VOLUME&.

    <table>
       <thead>
          <tr>
    <th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1"><p>Member Name</p>         </th>
    <th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1"><p>Description</p>         </th>
          </tr>
       </thead>
       <tbody>
          <tr>
             <td><p>$C40ICFT</p>         </td>
             <td><p>Creates the Transfer CFT instance files.</p>         </td>
          </tr>
       </tbody>
    </table>

    Submit the job.

    > **Note:**
    >
    > The Transfer CFT dataset files, the instance customization, and build steps are described in the COMMON INSTALLATION chapter.

    ### Additional SMP/E sample jobs

    The following table lists additional sample jobs.

    <table>
       <thead>
          <tr>
    <th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1"><p>Member Name</p>         </th>
    <th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1"><p>Description</p>         </th>
          </tr>
       </thead>
       <tbody>
          <tr>
             <td><p>$C10REJT</p>         </td>
             <td><p>Performs a REJECT of the SYSMODs in the SMP/E global zone.</p>         </td>
          </tr>
          <tr>
             <td><p>$C50ALLD</p>         </td>
             <td><p>Allocates the distribution libraries.</p>         </td>
          </tr>
          <tr>
             <td><p>$C60FACC</p>         </td>
             <td><p>Performs an ACCEPT (with the CHECK operand) the SYSMOD functions in the distribution zone and libraries.</p>         </td>
          </tr>
       </tbody>
    </table>
