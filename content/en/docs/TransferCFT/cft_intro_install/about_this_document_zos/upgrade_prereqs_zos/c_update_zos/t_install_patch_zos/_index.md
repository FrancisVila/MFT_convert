{
    "title": "Transfer CFT maintenance (non-SMP/E)",
    "linkTitle": "Transfer CFT maintenance (non-SMP/E)",
    "weight": "240"
}## Update or apply a service pack (non-SMP/E)

This section describes how to install a patch or service pack on your z/OS Transfer CFT using the non-SMP/E method.

Information includes:

-   [Install update libraries (PTF)](#Install%20update%20libraries%20(PTF))
-   [Transfer the PTF file to the host machine](#Transfer%20the%20PTF%20file%20to%20the%20host%20machine)
-   [Integrate PTF elements using A13PTFLD](#Integrate%20PTF%20elements%C2%A0using%20A13PTFLD) 
-   [Apply a PTF using A13PTFLK](#Apply%20a%20PTF%C2%A0using%20A13PTFLK) 

<span id="Install update libraries (PTF)"></span>

## Install update libraries

A PTF file results from the fixed formatting (80) of an ADRDSSU-type file containing the update libraries. The PTF format is used by all delivery and distribution modes. The PTF files are available at [support.axway.com](http://support.axway.com/).

> **Note:**
>
> PTF files are cumulative. A basic Transfer CFT z/OS installation can integrate PTFs. If you use this method, apply the PTFs one at a time.

<span class="autonumber"></span>Libraries taken into account during a DUMP ADRDSSU

<table>
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Libraries         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1">Contents         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>INSTALL</p>         </td>
         <td><p>Update the installation JCLs</p>         </td>
      </tr>
      <tr>
         <td><p>SAMPLE</p>         </td>
         <td><p>Update the SAMPLES</p>         </td>
      </tr>
      <tr>
         <td><p>SAMPLEO</p>         </td>
         <td><p>Update the COBOL samples</p>         </td>
      </tr>
      <tr>
         <td><p>SAMPLEC</p>         </td>
         <td><p>Update the C samples</p>         </td>
      </tr>
      <tr>
         <td>SAMPLEA         </td>
         <td>Update the ASM samples         </td>
      </tr>
      <tr>
         <td><p>PFTOBJ</p>         </td>
         <td><p>Update OBJECT modules</p>         </td>
      </tr>
      <tr>
         <td><p>DOC</p>         </td>
         <td><p>Update documentation</p>         </td>
      </tr>
      <tr>
         <td><p>CNTL</p>         </td>
         <td><p>Control files</p>         </td>
      </tr>
      <tr>
         <td><p>MAC</p>         </td>
         <td><p>Macros</p>         </td>
      </tr>
      <tr>
         <td><p>SCR</p>         </td>
         <td><p>Update components for interactive functions, messages, sample SSL</p>         </td>
      </tr>
      <tr>
         <td><p>UPARM</p>         </td>
         <td><p>Update unified configuration parameters definition.</p>         </td>
      </tr>
      <tr>
         <td>OBJ         </td>
         <td>Update NEW OBJECT modules.         </td>
      </tr>
      <tr>
         <td>COPY         </td>
         <td>Update Cobol copybook.         </td>
      </tr>
      <tr>
         <td>H         </td>
         <td>Update ‘header’ C.         </td>
      </tr>
      <tr>
         <td>XMLLIB         </td>
         <td>Update XML components.         </td>
      </tr>
      <tr>
         <td>EXEC         </td>
         <td>Update Transfer CFT procedures.         </td>
      </tr>
   </tbody>
</table>

<span id="Transfer the PTF file to the host machine"></span>

## Transfer the PTF file to the host machine

You can transfer a given PTF file from either the workstation or the host, in binary form, to the central site **distlib.UPLIB** library.

<span id="Transfer file using FTP"></span>

### Transfer file using FTP

The following is an example of commands for the binary transfer of the PTF file from the workstation to the host:


    open hostname 
    userid  
                            
    userpsw 
                            
    binary 
                            
    put c:\mycftpatchs\patch_from Axway support website 'distlib.UPLIB(CFxxxxxx)'   
                            

Where:

-   xxxxxx identifies the PTF number

<!-- -->

-   distlib indicates the distribution environment

<!-- -->

-   distlib.UPLIB library is created during the product installation

<span id="Retrieve file using FTP A13PTFFT"></span>

### Retrieve file using FTP A13PTFFT

If an FTP server is configured on the workstation, you can use the sample JCL, A13PTFFT in target.INSTALL library, to transfer the PTF file in binary format via FTP. In the JCL, specify the address of the workstation and the PTF identifier.

### A13\* JCL descriptions

All of the A13\* JCLs are used to update or apply a Service Pack to Transfer CFT as described here.

<table>
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">JCL         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>A13AUTO         </td>
         <td>To automatically apply fixes.         </td>
      </tr>
      <tr>
         <td>A13PTFFT         </td>
         <td>To transfer a patch to the distlib.UPLIB in binary mode (using FTP - mode GET).         </td>
      </tr>
      <tr>
         <td>A13PTFLD         </td>
         <td>To update the distribution libraries. (ADRDSSU)         </td>
      </tr>
      <tr>
         <td>A13PTFLI         </td>
         <td>To update the distribution libraries. (XMIT)         </td>
      </tr>
      <tr>
         <td>A13PTFLK         </td>
         <td>To apply a patch in the Transfer CFT loadlib (create a save library/link-edit).         </td>
      </tr>
      <tr>
         <td>A13RSTOR         </td>
         <td>To restore the loadlib from a save library.         </td>
      </tr>
      <tr>
         <td>A13SDEL         </td>
         <td>To delete a save-load library when a patch is validated, or if the loadlib is restored to reapply a patch.         </td>
      </tr>
      <tr>
         <td>  Transfer CFT Copilot update         </td>
      </tr>
      <tr>
         <td>A13UCOPA         </td>
         <td>To apply a patch to Transfer CFT Copilot (Create a save file).         </td>
      </tr>
      <tr>
         <td>A13UCOPR         </td>
         <td>To restore the Transfer CFT Navigator environment from a save file in USS environment.         </td>
      </tr>
      <tr>
         <td>A13UCOPD         </td>
         <td>To delete a save file when a patch is validated.         </td>
      </tr>
      <tr>
         <td>  Transfer CFT - Secure Relay - Master Agent update         </td>
      </tr>
      <tr>
         <td>A13UXSRA         </td>
         <td>To apply a patch to Secure Relay - Master Agent (creates a save file).         </td>
      </tr>
      <tr>
         <td>A13UXSRR         </td>
         <td>To restore the Transfer CFT <span class="mc-variable suite_variables.SecureRelayName variable">Secure Relay</span> environment from a save file in USS environment.         </td>
      </tr>
      <tr>
         <td>A13UXSRD         </td>
         <td>To delete a save file when a patch is validated.         </td>
      </tr>
      <tr>
         <td>  Other JCL         </td>
      </tr>
      <tr>
         <td>A13JCL         </td>
         <td>To customize the patched JCL.         </td>
      </tr>
      <tr>
         <td>A13UCONF         </td>
         <td>To update the unified configuration parameter definitions.         </td>
      </tr>
      <tr>
         <td>A13XML         </td>
         <td>To update the XML library.         </td>
      </tr>
      <tr>
         <td>A13WDEL         </td>
         <td><p>To delete work files.</p>         </td>
      </tr>
      <tr>
         <td>A13RBACK         </td>
         <td>To automatically execute the three jobs A13RSTOR, A13UCOPR, and A13UXSRR.         </td>
      </tr>
   </tbody>
</table>

<span id="Integrate PTF elements using A13PTFLD"></span>

## Integrate PTF elements using A13PTFLD

After loading PTF files, you must integrate the composing elements of the PTF files into the distribution libraries. Only perform this operation though from one of the Transfer CFT instances environments. 

The JCLs used are found in the target.INSTALL libraries below.

Before you submit the JOB, specify the PTF identifier in the EXEC card:

A13PTFLD: PTF integration in distribution libraries

//LOADPTF  EXEC PLOADPU,ID=’xxxxxx’, …   

This JOB takes place in several stages:

1.  Deletes the PTF temporary libraries.
2.  Formats the ADRDSSU of the PTF (IKJEFT01).
3.  Extracts temporary PTF libraries (ADRDSSU, or IKJEFT01).
4.  Copies (with replace) PTF components in the distribution libraries.
5.  Deletes the PTF temporary libraries.

> **Note:**
>
> This operation is displayed in the file distlib.LOG.

For more information, you can consult the patch documentation located in the distlib.DOC library and named DCxxxxxx (xxxxxx are the patch identifiers). These documents describe known incidents, corrections and PTF specifics (exits, and so on). Additionally the library, PTFINFO member, lists all corrected incidents.

<span id="Apply a PTF using A13PTFLK"></span>

## Apply a PTF using A13PTFLK

Usually a patch is applied through a LINK-EDIT. The JCL A13PTFLK is found in the target.INSTALL library.

Before submitting the JOB, specify the LINK EDIT identifier in the EXEC card:


    //APPLY  EXEC PAPPLY,ID=’xxxxxx’

Where:

-   xxxxxx: patch identifier

This JOB runs in several phases:

-   Backup of LOAD libraries, of which one of the qualifiers is the PTF identifier

<!-- -->

-   LINK-EDIT

> **Note:**
>
> This operation is displayed in the file distlib.LOG.

## Deleting a backup file version

**A13SDEL**

Use this JOB to delete a backup file after you have validated the application of a PTF. Each backup requires about 130 cylinders of the available 3390. Before submitting the JOB, specify the patch identifier on the EXEC card:

//DELSAV EXEC PDELSAV,ID=’xxxxxx’

> **Note:**
>
> This operation is displayed in the file distlib.LOG.

## Updating the Copilot server

When you apply a patch to the Transfer CFT Copilot server, the update is not automatic.

> **Note:**
>
> The user applying the PTFs should have write access rights for the ‘cftroot\\wwwroot’ \* directory. The \* cftroot is a customizable parameter (A03PARM member in the target.INSTALL library).

The following three JCLs mange the PTFs for Copilot:

-   A13UCOPA: Saves all files (\*) and PTF application (in a sequential file)
-   A13UCOPD: Deletes the save file that is associated with a PTF application
-   A13UCOPR: Restores files from the save file

> **Note:**
>
> All of these operations are displayed in the file distlib.LOG.

Before submitting the JCL, modify the value associated with the ID=, where xxxxxx is the identifier of the PTF to apply:



    //   SET ID='xxxxxx'  (JCL A13UPTFA)
    //DELSAV EXEC PCDELSAV,ID=’xxxxxx’ (JCL A13UPFTD)
    //   SET ID='xxxxxx'  (JCL A13UPTFR)

### Updating the unified configuration definitions A13UCONF

This JOB updates the member DEFAULT in target.UPARM.

## Automatically applying fixes A13AUTO

The use of this JCL is optional. It allows you to submit JOB 'A13\*', which runs as described in the patch readme (Distlib..doc(..)). Check the information concerning the application of the patch or service pack's in the associated readme.

You must configure the following JCLs in automatic mode.

> ..INSTALL(A13PTFLD) &gt;&gt; ID='AUTO'
>
> ..INSTALL(A13PTFLK) &gt;&gt; ID='AUTO'
>
> ..INSTALL(A13UCOPA) &gt;&gt; ID='AUTO' or ID='NONE'
>
> ..INSTALL(A13UXSRA) &gt;&gt; ID='AUTO' or ID='NONE'

If ID='NONE', this JCL is not submitted.

Related topics

-   About migrating Transfer CFT z/OS
