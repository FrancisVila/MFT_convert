{
    "title": "Migration procedure",
    "linkTitle": "Migrate ",
    "weight": "230"
}This section describes the Transfer CFT z/OS migration procedure and the statements you use to complete the process.

## Prerequisites

Before you start, create a new Transfer CFT instance following the [installation procedure](../../overview_install_zos) in this guide. This is your target instance.

## Overview

Migration consists of extracting the configuration (CFTPARM, CFTPART, UCONF, PKI), the contents of the catalogs, the communication media files from the source instance (old installation), and importing them into the target instance (new installation).

All migration operations are from the target instance.

The following table lists and describes the MIGR\* members used in a Transfer CFT migration process. If you want to use the delivered procedure, as a first step you need to customize the MIGR$SET member.

<span class="autonumber"></span>Migration Job Control Language (JCL) Statements

<table>
   <th>
      <tr>
<th><p>Member name</p>         </th>
<th><p>Purpose</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>MIGR$SET</p>         </td>
         <td><p>JCL variables to customize</p>         </td>
      </tr>
      <tr>
         <td><p>MIGRCAT</p>         </td>
         <td><p>Migrate the catalog file</p>         </td>
      </tr>
      <tr>
         <td><p>MIGRCOM</p>         </td>
         <td><p>Migrate the communication file</p>         </td>
      </tr>
      <tr>
         <td><p>MIGRPARM</p>         </td>
         <td><p>Migrate the Managed File Transfer parameters file</p>         </td>
      </tr>
      <tr>
         <td><p>MIGRPART</p>         </td>
         <td><p>Migrate the Managed File Transfer partners file</p>         </td>
      </tr>
      <tr>
         <td><p>MIGRPKI1</p>         </td>
         <td><p>Export the keys and certificates</p>         </td>
      </tr>
      <tr>
         <td><p>MIGRPKI2</p>         </td>
         <td><p>Import the keys and certificates</p>         </td>
      </tr>
      <tr>
         <td><p>MIGRPTIN</p>         </td>
         <td><p>Sample - Include JCL called by MIGRPART</p>         </td>
      </tr>
      <tr>
         <td><p>MIGRPTCL</p>         </td>
         <td><p>Sample - CLIST updates partners extract file</p>         </td>
      </tr>
      <tr>
         <td><p>MIGRPMIN</p>         </td>
         <td><p>Sample - Include JCL called by MIGRPARM</p>         </td>
      </tr>
      <tr>
         <td><p>MIGRPMCL</p>         </td>
         <td><p>Sample - CLIST updates parameters extract file</p>         </td>
      </tr>
      <tr>
         <td><p>PMIGR2</p>         </td>
         <td><p>Common procedure to migrate PARM, PART, CATALOG and communication media file.</p>         </td>
      </tr>
   </tbody>
</table>

The MIGR$$$ file is located in the target.INSTALL library, and contains information about the JCL required for a Transfer CFT z/OS migration. Among the delivered JCL, MIGR$SET is used to customize variables used in the migration procedure. See the Migration Job Control Language (JCL) Statements table below for a description of the JCL and members to use.

The PMIGR2 procedure, is comprised of several steps:

-   Export the content of the source file in a sequential work file.
-   Optionally, activate a step to adapt this extracted file (Only for PART and PARM file)
-   Create (recreate) the target file (or no operation).
-   Import from the work file the data in the target file.
-   List the content of target file.

## Procedure

This section describes how to migrate the various configuration elements in a non-multi-node environment or in a multi-node environment. Except for the migration of catalogs and the media communication file in a multi node environment, which are described in a specific section *Procedure for mutli-node*.

1.  Customize the MIGR$SET file.  
    Edit the MIGR$SET and SET variables.
2.  Migrate the PARM file (MIGRPARM).

The following variables can be set in MIGR$SET file or/and in the PMIGR2 parameters.

<table>
   <th>
      <tr>
<th><p>Variable</p>         </th>
<th><p>Default value</p>         </th>
<th><p>Definition</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>OLDEXEC</p>         </td>
         <td><p> </p>         </td>
         <td><p>Executable library for the Transfer CFT version (source) to migrate.</p>         </td>
      </tr>
      <tr>
         <td><p>OLDPARM</p>         </td>
         <td><p> </p>         </td>
         <td><p>Transfer CFT PARM source file name.</p>         </td>
      </tr>
      <tr>
         <td><p>NEWPARM</p>         </td>
         <td><p> </p>         </td>
         <td><p>Transfer CFT PARM target file name.</p>         </td>
      </tr>
      <tr>
         <td><p>DISPPARM</p>         </td>
         <td><p>‘R’</p>         </td>
         <td><p>'R' for replace, 'A' for ADD:</p>
<p>‘R’ = Creates or recreates the Transfer CFT PARM file.</p>
<p>‘A’ = Only creates the Transfer CFT PARM file.</p>         </td>
      </tr>
      <tr>
         <td><p>TMPPARM</p>         </td>
         <td><p>&amp;CFTENV..MPARM</p>         </td>
         <td><p>Work file name.</p>         </td>
      </tr>
      <tr>
         <td><p>TMPSPARM</p>         </td>
         <td><p>'CYL,(10,2)'</p>         </td>
         <td><p>Size allocation for work file.</p>         </td>
      </tr>
      <tr>
         <td><p>CUSTOMPM</p>         </td>
         <td><p>DUMMYJ</p>
<p>(No customization)</p>         </td>
         <td><p>Include member to customize parameters extract file.</p>         </td>
      </tr>
   </tbody>
</table>

Submit the procedure ..INSTALL(MIGRPARM)

1.  Migrate the PART file. (MIGRPART)

The following variables can be set in MIGR$SET file or/and in the PMIGR2 parameters.

<table>
   <th>
      <tr>
<th><p>Variable</p>         </th>
<th><p>Default value</p>         </th>
<th><p>Definition</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>OLDPART</p>         </td>
         <td><p> </p>         </td>
         <td><p>Transfer CFT PART source file name.</p>         </td>
      </tr>
      <tr>
         <td><p>NEWPART</p>         </td>
         <td><p> </p>         </td>
         <td><p>Transfer CFT PART target file name.</p>         </td>
      </tr>
      <tr>
         <td><p>DISPPART</p>         </td>
         <td><p>'R'</p>         </td>
         <td><p>'R' for replace, 'A' for ADD:</p>
<p>‘R’ = Create or recreate Transfer CFT PART file.</p>
<p>‘A’ = Only creates the Transfer CFT PART file.</p>         </td>
      </tr>
      <tr>
         <td><p>TMPPART</p>         </td>
         <td><p>&amp;CFTENV..MPARM</p>         </td>
         <td><p>Work file name.</p>         </td>
      </tr>
      <tr>
         <td><p>TMPSPART</p>         </td>
         <td><p>'CYL,(30,5)'</p>         </td>
         <td><p>Size allocation for work file.</p>         </td>
      </tr>
      <tr>
         <td><p>CUSTOMPT</p>         </td>
         <td><p>DUMMYJ</p>
<p>(No customization)</p>         </td>
         <td><p>Include member to customize partners extract file.</p>         </td>
      </tr>
   </tbody>
</table>

Submit the procedure ..INSTALL(MIGRPART)

1.  Migrate the PKI file (MIGRPKIx).

<table>
   <th>
      <tr>
<th><p>Variable</p>         </th>
<th><p>Default value</p>         </th>
<th><p>Definition</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>OLDPKI</p>         </td>
         <td><p> </p>         </td>
         <td><p>Transfer CFT PKI source file name</p>         </td>
      </tr>
      <tr>
         <td><p>NEWPKI</p>         </td>
         <td><p> </p>         </td>
         <td><p>Transfer CFT PKItarget file name.</p>         </td>
      </tr>
   </tbody>
</table>

If the target version is lower than 3.4:

-   Submit the procedure ..INSTALL(MIGRPKI) (export + import)

If the target version is 3.4 or higher:

-   Submit the procedures ..INSTALL(MIGRPKI1) (export)
-   Submit the procedures ..INSTALL(MIGRPKI2) (import)

1.  Migrate the UCONF file parameters. (MIGRUCNF)

The JCL ..INSTALL(MIGRUCNF) must be customized to determine UCONF parameters to migrate.

Replace the line:


    CFTEXT ID=*,TYPE=UCONF,FOUT=$EXT

With the list of UCONF parameters to migrate. For example:


    CFTEXT ID=cft.mvs.sginstal.*,TYPE=UCONF,FOUT=$EXT
    CFTEXT ID=cg.*,TYPE=UCONF,FOUT=$EXT
    CFTEXT ID=cft.multi_node.*,TYPE=UCONF,FOUT=$EXT
    CFTEXT ID=cft.cftcat.default_size,TYPE=UCONF,FOUT=$EXT
    CFTEXT ID=cft.cftcom.default_size,TYPE=UCONF,FOUT=$EXT
    CFTEXT ID=cft.cftlog.fname.atts,TYPE=UCONF,FOUT=$EXT
    CFTEXT ID=cft.cftaccnt.fname.atts,TYPE=UCONF,FOUT=$EXT
    Etc.

<span class="span_1">Submit the procedure</span><span class="span_1"> ..</span><span class="span_1">INSTALL(MIGR</span><span class="span_1">UCNF</span><span class="span_1">)</span>

1.  Migrate the CATALOG file (MIGRCAT) for a non multi-node environment.

You can set the following variables in the MIGR$SET file and (or) in the PMIGR2 parameters:

<table>
   <th>
      <tr>
<th><p>Variable</p>         </th>
<th><p>Default value</p>         </th>
<th><p>Definition</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>OLDEXEC</p>         </td>
         <td><p> </p>         </td>
         <td><p>Executable library of the Transfer CFT version to migrate.</p>         </td>
      </tr>
      <tr>
         <td><p>OLDCAT</p>         </td>
         <td><p> </p>         </td>
         <td><p>Transfer CFT CATALOG source file name.</p>         </td>
      </tr>
      <tr>
         <td><p>NEWCAT</p>         </td>
         <td><p> </p>         </td>
         <td><p>Transfer CFT CATALOG target file name</p>         </td>
      </tr>
      <tr>
         <td><p>DISPCAT</p>         </td>
         <td><p>‘R’</p>         </td>
         <td><p>'R' for replace, 'A' for ADD:</p>
<p>‘R’ = Create or recreate CFT CATALOG file</p>
<p>‘A’ = Will only create a Transfer CFT CATALOG file.</p>         </td>
      </tr>
      <tr>
         <td><p>RECNBCAT</p>         </td>
         <td><p>50000</p>         </td>
         <td><p>Size in records if Catalog must be created.</p>         </td>
      </tr>
      <tr>
         <td><p>TMPCAT</p>         </td>
         <td><p>&amp;CFTENV..MCAT</p>         </td>
         <td><p>Work file name.</p>         </td>
      </tr>
      <tr>
         <td><p>TMPSCAT</p>         </td>
         <td><p>'CYL,(50,10)'</p>         </td>
         <td><p>Size allocation for work file.</p>
<p>Use 3 cylinders for every 1000 transfers to be migrated.</p>         </td>
      </tr>
   </tbody>
</table>

<span class="span_1">Submit the procedu</span>re ..INSTALL(MIGRCAT).

1.  Migrate the communication media file(s) (MIGRCOM)for a non mutli-node environment.

You can set the following variables in the MIGR$SET file or/and in the PMIGR2 parameters:

<table>
   <th>
      <tr>
<th><p>Variable</p>         </th>
<th><p>Default value</p>         </th>
<th><p>Definition</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>OLDEXEC</p>         </td>
         <td><p> </p>         </td>
         <td><p>Executable library of the Transfer CFT version to migrate.</p>         </td>
      </tr>
      <tr>
         <td><p>OLDCOM</p>         </td>
         <td><p> </p>         </td>
         <td><p>Transfer CFT communication source file name.</p>         </td>
      </tr>
      <tr>
         <td><p>NEWCOM</p>         </td>
         <td><p> </p>         </td>
         <td><p>Transfer CFT communication target file name.</p>         </td>
      </tr>
      <tr>
         <td><p>DISPCOM</p>         </td>
         <td><p>‘R’</p>         </td>
         <td><p>'R' for replace, 'A' for ADD:</p>
<p>‘R’ = Create or recreate a Transfer CFT communication file.</p>
<p>‘A’ = Will only create a Transfer CFT communication file.</p>         </td>
      </tr>
      <tr>
         <td><p>RECNBCOM</p>         </td>
         <td><p>5000</p>         </td>
         <td><p>Size in records if communication file must be created.</p>         </td>
      </tr>
      <tr>
         <td><p>TMPCOM</p>         </td>
         <td><p> </p>         </td>
         <td><p>Work file name.</p>         </td>
      </tr>
      <tr>
         <td><p>TMPSCOM</p>         </td>
         <td><p>'CYL,(10,10)'</p>         </td>
         <td><p>Size allocation for work file.</p>         </td>
      </tr>
   </tbody>
</table>

Submit the procedure ..INSTALL(MIGRCOM).