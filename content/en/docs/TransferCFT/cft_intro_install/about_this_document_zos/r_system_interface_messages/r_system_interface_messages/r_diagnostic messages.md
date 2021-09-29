{
    "title": "Diagnostic messages",
    "linkTitle": "Diagnostic messages",
    "weight": "260"
}This section describes the diagnostic messages for Transfer CFT in a z/OS environment:

-   DIAGP field format
-   Complementary file error diagnostics

The file error codes have the same form as:

-   Transfer CFT messages
-   The DIAGP field of the Transfer CFT catalog

## DIAGP field format

The typical file error code format is: SFRRNNNN.

-   S: The environment code

### Environment code

#### Code definition

S=0 MVS/DFP returned error

S=4 Read/write error

S=8 Read/write abnormal end

S=9 DYNALLOC returned error

S=C VSAM read/write error

S=F File processing parameter error

-   F: The F function code indicates the processing requested on the file.

The F function code values are:

<table data-cellspacing="0">
<thead>
<tr class="header">
<th>F code</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>F=0</p></td>
<td><p>File creation</p></td>
</tr>
<tr class="even">
<td><p>F=1</p></td>
<td><p>File deletion</p></td>
</tr>
<tr class="odd">
<td><p>F=2</p></td>
<td><p>File characteristics query</p></td>
</tr>
<tr class="even">
<td><p>F=3</p></td>
<td><p>File rename</p></td>
</tr>
<tr class="odd">
<td><p>F=4</p></td>
<td><p>Allocate a file by DSNAME</p></td>
</tr>
<tr class="even">
<td><p>F=5</p></td>
<td><p>De-allocate the file</p></td>
</tr>
<tr class="odd">
<td><p>F=6</p></td>
<td><p>Allocate by DDNAME</p></td>
</tr>
<tr class="even">
<td><p>F=7</p></td>
<td><p>Submission of a CFT procedure to the INTERNAL READER</p></td>
</tr>
<tr class="odd">
<td colspan="2"><p>Other values are then detailed.</p></td>
</tr>
</tbody>
</table>

-   RR: The RR code designates the requested z/OS function.

<table data-cellspacing="0">
<thead>
<tr class="header">
<th>RR code</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RR=F0</p></td>
<td><p>Call to CAMLST LOCATE</p></td>
</tr>
<tr class="even">
<td><p>RR=F1</p></td>
<td><p>Call to CAMLST SCRATCH</p></td>
</tr>
<tr class="odd">
<td><p>RR=F2</p></td>
<td><p>Call to CAMLST RENAME</p></td>
</tr>
<tr class="even">
<td><p>RR=F3</p></td>
<td><p>Call to CAMLST OBTAIN/SHOWCB if VSAM</p></td>
</tr>
<tr class="odd">
<td><p>RR=F4</p></td>
<td><p>Call to function RACROUTE</p></td>
</tr>
<tr class="even">
<td><p>RR=F5</p></td>
<td><p>Call to function SFMWTM</p></td>
</tr>
<tr class="odd">
<td><p>RR=F6</p></td>
<td><p>Dynamic call to IDCAMS</p></td>
</tr>
<tr class="even">
<td><p>RR=DC</p></td>
<td><p>Dynamic call to IDCAMS, message IDC 3nnn in return</p></td>
</tr>
<tr class="odd">
<td colspan="2"><p>Other values are then detailed.</p></td>
</tr>
</tbody>
</table>

-   NNNN: The data code completing the return code

NNNN is the z/OS or OPEN VSAM return code, or one of the following codes:

for RR=DC, NNNN is the IDCAMS IDCnnnn message number

Example:

00DC3203 corresponds to the message IDC32031 ITEM ”-” DOES NOT ADHERE TO RESTRICTIONS.

### NNNN file error codes

Specific codes:

-   00F000B37: No space in an HFS File System

<!-- -->

-   0x0y00E37: Multi-volume file creation not supported on volume 'x'  in 'y'

<!-- -->

-   91300038 or 80000913: Read/write operation requested by user is not allowed by RACF

#### NNNN Code Table for S=0

NNNN code table for S=0

<table data-cellspacing="0">
<thead>
<tr class="header">
<th>NNNN code</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>0005</p></td>
<td><p>No DD card</p></td>
</tr>
<tr class="even">
<td><p>0017</p></td>
<td><p>Multi-volume file not supported</p></td>
</tr>
<tr class="odd">
<td><p>0019</p></td>
<td><p>VOLUME discrepancy with catalog</p></td>
</tr>
<tr class="even">
<td><p>001A</p></td>
<td><p>DSNAME error or access via an ALIAS</p></td>
</tr>
<tr class="odd">
<td><p>001B</p></td>
<td><p>UCB not found or access generated in DRM</p></td>
</tr>
<tr class="even">
<td><p>001C</p></td>
<td><p>File not found in VTOC</p></td>
</tr>
<tr class="odd">
<td><p>001E</p></td>
<td><p>Concatenated files not supported</p></td>
</tr>
<tr class="even">
<td><p>0028</p></td>
<td><p>File not found in catalog</p></td>
</tr>
<tr class="odd">
<td><p>0030</p></td>
<td><p>File not found in catalog</p></td>
</tr>
<tr class="even">
<td><p>0040</p></td>
<td><p>DSNAME missing</p></td>
</tr>
<tr class="odd">
<td><p>0048</p></td>
<td><p>File root in GDG without version number</p></td>
</tr>
<tr class="even">
<td><p>0050</p></td>
<td><p>DSNAME does not conform with z/OS rules</p></td>
</tr>
<tr class="odd">
<td><p>03DE</p></td>
<td><p>File not deleted/renamed, member of PDS</p></td>
</tr>
<tr class="even">
<td><p>03DF</p></td>
<td><p>File not deleted/renamed, ENQ OLD not possible</p></td>
</tr>
<tr class="odd">
<td><p>03E0</p></td>
<td><p>Shared file not available, allocated by another task</p></td>
</tr>
<tr class="even">
<td><p>03E1</p></td>
<td><p>Allocate of a PDS file without member name</p></td>
</tr>
<tr class="odd">
<td><p>03E2</p></td>
<td><p>Allocate of a GDG without BLDG</p></td>
</tr>
<tr class="even">
<td><p>03E3</p></td>
<td><p>Allocate of a GDG in version +1</p></td>
</tr>
<tr class="odd">
<td><p>03E4</p></td>
<td><p>File not deleted/renamed, does not exist</p></td>
</tr>
<tr class="even">
<td><p>03E5</p></td>
<td><p>File not created; file already exists</p></td>
</tr>
<tr class="odd">
<td><p>03E6</p></td>
<td><p>File not deleted/renamed, on tape</p></td>
</tr>
<tr class="even">
<td><p>03E7</p></td>
<td><p>Creation of a file with a logical name (DDNAME)</p></td>
</tr>
<tr class="odd">
<td><p>0051</p></td>
<td><p>RENAME, GDG(+1) mandatory</p></td>
</tr>
<tr class="even">
<td><p>0052</p></td>
<td><p>RENAME, temporary file cannot be GDG</p></td>
</tr>
<tr class="odd">
<td><p>0053</p></td>
<td><p>RENAME, CAMLST RENAME error</p></td>
</tr>
<tr class="even">
<td><p>0054</p></td>
<td><p>RENAME, CAMLST CATALOG error</p></td>
</tr>
<tr class="odd">
<td><p>0055</p></td>
<td><p>RENAME, temporary file cannot be GDG(+1)</p></td>
</tr>
<tr class="even">
<td><p>0056</p></td>
<td><p>RENAME, duplicate file on 1 volume</p></td>
</tr>
<tr class="odd">
<td><p>0057</p></td>
<td><p>SCRATCH, file not found</p></td>
</tr>
<tr class="even">
<td><p>0058</p></td>
<td><p>SCRATCH, CAMLST SCRATCH error</p></td>
</tr>
<tr class="odd">
<td><p>0059</p></td>
<td><p>SCRATCH, volume not mounted</p></td>
</tr>
<tr class="even">
<td><p>005A</p></td>
<td><p>SCRATCH, CAMLST UNCAT outside SMS</p></td>
</tr>
<tr class="odd">
<td><p>005F</p></td>
<td><p>RENAME, member of PDS file</p></td>
</tr>
</tbody>
</table>

**Example**

’04F003E0’: allocate by DSNAME, file already allocated to another transfer by CFT.

’04F00028’: allocated by DSNAME, file not found in the catalog.

#### NNNN Code for S=4 (Read/Write Error)

F and RR have no significance.

NNNN takes on the following values:

NNNN code for S=4

<table data-cellspacing="0">
<thead>
<tr class="header">
<th>Code</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>00D4</p></td>
<td><p>OPEN, LRECL/BLKSIZE incorrect</p></td>
</tr>
<tr class="even">
<td><p>00D8</p></td>
<td><p>OPEN, no parameter delimiter</p></td>
</tr>
<tr class="odd">
<td><p>00E4</p></td>
<td><p>OPEN, DDNAME incorrect</p></td>
</tr>
<tr class="even">
<td><p>00E8</p></td>
<td><p>OPEN, DDNAME missing</p></td>
</tr>
<tr class="odd">
<td><p>00EC</p></td>
<td><p>OPEN, no more memory for buffers</p></td>
</tr>
<tr class="even">
<td><p>00F0</p></td>
<td><p>OPEN, parameters missing</p></td>
</tr>
<tr class="odd">
<td><p>00F4</p></td>
<td><p>FCB reference incorrect</p></td>
</tr>
<tr class="even">
<td><p>00F8</p></td>
<td><p>Invalid SGF function code</p></td>
</tr>
<tr class="odd">
<td><p>00FC</p></td>
<td><p>Non-authorized function code</p></td>
</tr>
<tr class="even">
<td><p>00FD</p></td>
<td><p>OPEN, non-0 return code</p></td>
</tr>
<tr class="odd">
<td><p>0FFF</p></td>
<td><p>BSAM, read/write/POINT error</p></td>
</tr>
</tbody>
</table>

The error is accompanied by Transfer CFT and possibly a z/OS messages depending on the following criteria, but is displayed uniquely on the z/OS console:

-   CFT ‘POINT ERROR’ message in the case of repositioning on a file that does not support it

<!-- -->

-   CFT ‘SYNA01E:’ message accompanied by the z/OS‘SYNADAF’ message text. This message is only displayed on the z/OS console

<!-- -->

-   z/OSIEA000 or IECxxx message

#### NNNN Code for S=8 (ABEND during a Read/Write)

F and RR have no significance

NNNN has the ABEND code intercepted by CFT

Examples: 0B37, 0013.

**Example**

’80000913’: AbendS913 at file opening, CFT/z/OS does not have the right to read/write.

#### NNNN Code for S=C (VSAM Read/Write Error)

F has no significance

RR is the VSAM RETURN-CODE

NNNN is the VSAM FDBK

The VSAM RTNCD/FDBK codes are explained in the VSAM documentation.

**Example**

’C004001C’: no more space in the file

#### NNNN Code for S=F (File Parameter Error)

RR and NNNN have no significance

NNNN code table for S=F

**Code definition**

<table data-cellspacing="0">
<thead>
<tr class="header">
<th>Code</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>F = 4</p></td>
<td><p>Function not allowed</p></td>
</tr>
<tr class="even">
<td><p>F = 7</p></td>
<td><p>Function unknown</p></td>
</tr>
<tr class="odd">
<td><p>F = C</p></td>
<td><p>File reference incorrect</p></td>
</tr>
</tbody>
</table>

These codes must be submitted to the Transfer CFT Technical Support.

####  DYNALLOC Error Codes S=9

The DYNALLOC errors are explained in the IBM brochure “IBM SPL system macros & facilities”.

 Value of F for the DYNALLOC function

<table data-cellspacing="0">
<thead>
<tr class="header">
<th><p>Code</p></th>
<th><p>Definition</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>F=1</p></td>
<td><p>Allocate</p></td>
</tr>
<tr class="even">
<td><p>F=2</p></td>
<td><p>De-allocate</p></td>
</tr>
</tbody>
</table>

Value of RR for DYNALLOC:

-   RR is the DYNALLOC return code. It can take on values 04, 08, 0C

Value of NNNN for DYNALLOC:

-   NNNN is the DYNALLOC REASON CODE

Example of a DYNALLOC error code:

‘9104970C’ error: no more space to create the file.

The "IKJnnnnnI" and "IGDnnnnnI" error messages returned by DYNALLOC (under SMS) are displayed on the z/OS console:

-   IKJ56893I DATA SET NOT ALLOCATED+

<!-- -->

-   IGD17273I ALLOCATION HAS FAILED FOR ALL VOLUMES SELECTED FOR DATA SET

The ‘nnnn’ hexadecimal value converted to decimal gives the SMS IGD message number. For example, the X’4379’ value corresponds to the IGD172731 message.

## Complementary file error diagnostics

The following complementary diagnostics are available on request by Transfer CFT support, through the SGTRACE tool:

-   SGTRACE 4:

Traces the file read/write actions. This value must be used for codes S=0 and S=9

-   SGTRACE 8:

Traces the file read/write actions. This value must be used for codes S=4, 8, C, F

-   SGTRACE 2: traces the errors

<!-- -->

-   SGTRACE 128: traces the module calls and returns

The modules concerned are:

-   S=0: SGF3ACC, SGF3STAT, SIFM, SGF3VSAM, SGF3REN

<!-- -->

-   S=9: SGF3SV99

<!-- -->

-   S=4, 8, C, F: SGF3C, SIDM

Related topics

[About the operator interface commands](../../../t_start_servers_jobs_zos/t_system_environment_zos/r_about_operator_interface_commands)

[Diagnostic commands](../../../t_start_servers_jobs_zos/t_system_environment_zos/c_diagnostic_commands)
