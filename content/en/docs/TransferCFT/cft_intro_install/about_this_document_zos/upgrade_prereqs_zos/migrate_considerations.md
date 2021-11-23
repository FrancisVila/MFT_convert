{
    "title": "Migrate and upgrade considerations",
    "linkTitle": "Migrate/upgrade considerations",
    "weight": "200"
}This section summarizes the migration and upgrade procedures for each type of object and provides related recommendations.

**Transfer CFT file IDs**

<table>
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">File ID         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1">Migrate or upgrade procedures         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>PARM         </td>
         <td>MIGRPARM         </td>
      </tr>
      <tr>
         <td>PART         </td>
         <td>MIGRPART         </td>
      </tr>
      <tr>
         <td>CATALOG         </td>
         <td>MIGRCAT         </td>
      </tr>
      <tr>
         <td>COM         </td>
         <td>MIGRCOM         </td>
      </tr>
      <tr>
         <td>LOG         </td>
         <td>No migration step; you must create the file if you migrated.         </td>
      </tr>
      <tr>
         <td>ACCNT         </td>
         <td><p>No migration step; you must create the file if you migrated.</p>
<p>For format=V24, some field lengths were modified, but the total size of record remains the same.</p>         </td>
      </tr>
      <tr>
         <td>UCONF, unified configuration file         </td>
         <td>MIGRUCNF.         </td>
      </tr>
      <tr>
         <td>PKI file         </td>
         <td>As of Transfer CFT 3.4, MIGRPKI was split into 2 procedures, MIGRPKI1 and MIGRPKI2.         </td>
      </tr>
      <tr>
         <td>Exits/API         </td>
         <td>The use of DLL mode is mandatory (otherwise you must rework the Exits and API).
In any case, you must compile and link the exits and API.         </td>
      </tr>
   </tbody>
</table>

**Recommendations**

-   The delivered examples to create the files LOG and ACCOUNT (D40INIT..) have a `format=V24` definition. Ensure that the FORMAT parameter in the CFTLOG and CFTACCNT commands are consistent.
-   For Copilot usage, verify that the uconf cft.install\_dir and copilot.HTTP.HttpRootDir parameters are correctly configured - that is, consistent with the variable values in the A03PARM and ..UPARM (COPCFG) file.
-   As of Transfer CFT 3.1.3:
    -   A new UCONFRUN file was added in JCL/STC/Procedures (CFTMAIN, COPRUN, PCFTUTIL, PCFTUTL, MNRMAIN, MNRMNG). We recommend adding the definition of this file in your JCL containing EXEC PGM=CFTUTIL, and in JCLs that are running Transfer CFT APIs.

    -   The product comes with components:

        -   CFTINC and CFTENV include JCL

        -   PCFTUTIL and PCFTUTL procedures

    -   Integrating these components where possible into your existing JCLs, simplifies migration.

<!-- -->


    //UCONFRUN DD DISP=SHR,DSN=&QUAL..UCONFRUN

As of {{< TransferCFT/componentlongname  >}} 3.3.2:

-   SGINSTAL is optional and can be replaced by UCONF variables.
-   A USER.LOAD library can contain API(s), EXIT(s), and SGINSTAL(optional). If you define a USER.LOAD, you must add this load in STEPLIB/JOBLIB in your JCL or STC, and it must be an APF.
