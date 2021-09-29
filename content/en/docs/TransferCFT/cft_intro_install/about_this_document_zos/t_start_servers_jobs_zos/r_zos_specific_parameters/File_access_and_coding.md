{
    "title": "Code filenames",
    "linkTitle": "Code filenames",
    "weight": "280"
}Working with files and coding

This section describes file properties and how to code Transfer CFT filenames.

-   [File access overview](#file%20access%20overview)
-   [About coding filenames](#coding%20file%20names%20zos)
-   [Filename forms](#filename)
-   [Code filenames with DDNAME ](#coding%20filenames%20with%20ddname)
-   [Coding PDS filenames](#coding%20pds%20filenames)
-   [Code GDG filenames](#coding%20gdg%20filenames)

## <span id="File access overview"></span>File access overview

Transfer CFT z/OS has read or write access to the following files:

-   Disk sequential files
-   Multi-volume disk sequential files
-   PDS files
-   Files in GENERATION DATA GROUP (GDG)
-   VSAM KSDS files
-   VSAM ESDS files
-   HFS hierarchical files

Transfer CFT z/OS creates, deletes, and renames the following files by calling IDCAMS:

-   VSAM KSDS files
-   VSAM ESDS files

Transfer CFT z/OS cannot transfer the following files:

-   VSAM RRDS files
-   VSAM LINEAR files
-   Concatenated files
-   Files on magnetic tapes
-   File for which the LRECL is higher than 32760 (lrecl=x)

## <span id="Coding file names zOS"></span>About coding filenames

Transfer CFT z/OS uses the following coding to handle files:

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>FNAME=VOLUME%UNIT%NAME1.NAME2.NAMEX</p></td>
</tr>
</tbody>
</table>

Where:

-   VOLUME has the following characteristics:

    > -   Indicates the name of the disk volume where the file will be created or searched
    > -   Is optional, but useful for requesting Transfer CFT to create a VSAM file or other file, except for SMS managed volumes
    > -   Corresponds to the VOLUME parameter of the DEFINE CLUSTER VSAM or VOL=SER= of the JCL
    > -   Should not be used with DF/SMS

-   UNIT has the following characteristics:

> -   Indicates the UNITNAME used
>
> <!-- -->
>
> -   Is optional but useful for a tape or disk SAM file
>
> <!-- -->
>
> -   Corresponds to the parameter UNIT= of the JCL
>
> <!-- -->
>
> -   By default, the value SYSALLDA or the value imposed by your DYNALLOC EXIT will be used

-   NAME1.NAME2.NAMEx have the following characteristics:

> -   Defines the filename
>
> <!-- -->
>
> -   Mandatory
>
> <!-- -->
>
> -   The initial character in HFS filenames is the slash: ( / )

**Example**

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>CFTVOL%%FILENAME</p>
<p>%3390%FILENAME</p>
<p>%%FILENAME</p>
<p>FILENAME</p>
<p>/path/file.extension</p></td>
</tr>
</tbody>
</table>

<table data-cellpadding="0" data-cellspacing="0">
<tbody>
<tr class="odd">
<td data-valign="top"></td>
<td data-valign="top"><span><strong>Note</strong></span></td>
<td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">The two % signs are mandatory only if the VOLUME parameter or the UNIT parameter has been specified.</td>
</tr>
</tbody>
</table>

## <span id="Filename"></span>Filename forms

A filename can have different forms:

-   A DSNAME or a string coded in form ‘VOLUME%UNIT%DSNAME’ (VOLUME and UNIT are often optional).
-   A logical name, associated with a DD card \[ JCL \] or with an ALLOC \[ CLIST \].
-   PDS member name, which is also by completing with the member name between brackets.

Example 

A DSNAME or a string to request that a file be sent:

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td>SEND FNAME=‘CFT.SEND.FILE’</td>
</tr>
</tbody>
</table>

Search the catalog for the file:

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td>SEND FNAME=‘CFTRES%3480%CFT.SEND.FILE’</td>
</tr>
</tbody>
</table>

Look for the file on the volume CFTRES, unit 3480:

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td>SEND FNAME=‘%3480%CFT.SEND.FILE’</td>
</tr>
</tbody>
</table>

Look for the file in the catalog (unit type imposed):

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td>SEND FNAME=‘CFTRES%%CFT.SEND.FILE’</td>
</tr>
</tbody>
</table>

Look for the file on the disk CFTRES:

Using parameters ‘VOLUME’ and/or ‘UNIT’ may conflict with DF/SMS file management.

Example

PDS member name to request sending of a member with the file searched for in the catalog:

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td>SEND FNAME=‘CFT.SEND.FILE(MEMBER)’</td>
</tr>
</tbody>
</table>

Example

A logical name to select a PARTNERS file:

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>CFTPARM PARTFNAM=$CFTPART</p></td>
</tr>
</tbody>
</table>

This file is indicated in the JCL that starts Transfer CFT, by:

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>//CFTPART DD DISP=SHR,DSN=... ,</p></td>
</tr>
</tbody>
</table>

Or under TSO:

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>ALLOC FI(CFTPART) SHR DA(’...’) .</p></td>
</tr>
</tbody>
</table>

Transfer CFT and the associated utilities set aside the use of “DD names” beginning with ‘FIL’ for dynamic allocations.

### Coding SMS parameters

Transfer CFT z/OS allows limited coding of certain SMS parameters in the UNIT parameter.

The following values allow you to:

-   &gt;STORCLA: specify a value for STORAGE-CLASS

<!-- -->

-   &lt;DATACLA: specify a value for DATA CLASS
-   \*MGTCLAS: specify a value for MANAGEMENT CLASS

An alternate way to specify full-length DF/SMS parameters is described in [DF/SMS large file support](../t_dynamically_create_files).

## <span id="Coding filenames with DDNAME"></span>Code filenames with DDNAME 

Transfer CFT z/OS uses the following coding to refer to a DDNAME declared in the JCL:

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>FNAME=$DDNAME</p></td>
</tr>
</tbody>
</table>

Example

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>FNAME=$CFTCAT</p></td>
</tr>
</tbody>
</table>

## <span id="Coding PDS filenames"></span>Coding PDS filenames

Transfer CFT z/OS handles PDS files one member at a time. Transfer CFT z/OS processes PDS files:

-   Member by member in sequence

<!-- -->

-   By calling IEBCOPY UNLOAD

<!-- -->

-   For the entire PDS, by setting FNAME=#DSNAME or #DSNAME(\*)

<table data-cellpadding="0" data-cellspacing="0">
<tbody>
<tr class="odd">
<td data-valign="top"></td>
<td data-valign="top"><span><strong>Note</strong></span></td>
<td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">The second syntax is recommended as it is the syntax to use for heterogeneous transfers.</td>
</tr>
</tbody>
</table>

-   For a selected subset of members, using the ’\*’ character to replace a character string or ’?’ to replace one character and by setting FNAME=#DSNAME(ME?BER\*)

A PDS file is coded as:

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>FNAME=NAME1.NAMEX(MEMBER)</p></td>
</tr>
</tbody>
</table>

Delivered template:

-   ..SAMPLE(CFTPDS)

## <span id="Coding GDG filenames"></span>Code GDG filenames

A GDG filename is coded as:

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>FNAME=NAME1.NAMEX(0)</p>
<p>FNAME=NAME1.NAMEX(-n)</p>
<p>FNAME=NAME1.NAMEX(+n)</p></td>
</tr>
</tbody>
</table>

<table data-cellpadding="0" data-cellspacing="0">
<tbody>
<tr class="odd">
<td data-valign="top"></td>
<td data-valign="top"><span><strong>Note</strong></span></td>
<td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">Transfer CFT z/OS does not allow the concatenation of all versions of a GDG file.</td>
</tr>
</tbody>
</table>

Delivered templates:

-   ..SAMPLE(CFTGDGS) (send GDG)
-   ..SAMPLE(CFTGDGR) (receive GDG)

Related topics

-   [Delete rename and share files](../t_delete_and_rename_files_zos)
-   [Dynamically create files](../t_dynamically_create_files)
-   [HFS hierarchical files](../c_hfs_hierarchical_files_zos)
