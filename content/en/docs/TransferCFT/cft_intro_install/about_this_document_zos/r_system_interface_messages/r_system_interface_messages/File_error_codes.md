{
    "title": "File error codes in z/OS",
    "linkTitle": "File error codes in z/OS",
    "weight": "240"
}This section lists the codes that define the Transfer CFT performance on z/OS. The file error codes have the same form as:

-   Transfer CFT messages

<!-- -->

-   The DIAGP field of the Transfer CFT catalog

## DIAGP field format

The usual format of file error codes is as follows: SFRRNNNN.

-   S: The environment code

S Environment code

**Code definition**

S=0 MVS/DFP returned error

S=4 Read/write error

S=8 Read/write abnormal end

S=9 DYNALLOC returned error

S=C VSAM read/write error

S=F File processing parameter error

-   F: The F function code indicates the processing requested on the file

F Function code

**Code definition**

F=0 File creation

F=1 File deletion

F=2 File characteristics query

F=3 File rename

F=4 Allocate a file by DSNAME

F=5 De-allocate the file

F=6 Allocate by DDNAME

F=7 Submission of a Transfer CFT procedure to the INTERNAL READER

Other values are then detailed.

-   RR: The RR code designates the requested z/OS function

RR Requested function code

**Code definition**

RR=F0 Call to CAMLST LOCATE

RR=F1 Call to CAMLST SCRATCH

RR=F2 Call to CAMLST RENAME

RR=F3 Call to CAMLST OBTAIN/SHOWCB if VSAM

RR=F4 Call to function RACROUTE

RR=F5 Call to function SFMWTM

RR=F6 Dynamic call to IDCAMS

RR=DC Dynamic call to IDCAMS, message IDC 3nnn in return

Other values are then detailed.

-   NNNN: The data code completing the return code

NNNN: The data code

NNNN is the z/OS or OPEN VSAM return code, or one of the following codes:

for RR=DC, NNNN is the IDCAMS IDCnnnn message number

**Example**

00DC3203 corresponds to the message IDC32031 ITEM ”-” DOES NOT ADHERE TO RESTRICTIONS.

 NNNN file error code table

Specific codes:

-   00F000B37 : No space in an HFS File System

<!-- -->

-   0x0y00E37 : Multi-volume file creation not supported on volume 'x'  in 'y'

<!-- -->

-   91300038 or 80000913 : Read/write operation requested by user is not allowed by RACF

NNNN code for S=0

**Code definition**

0005 No DD card

0017 Multi-volume file not supported

0019 VOLUME discrepancy with catalog

001A DSNAME error or access via an ALIAS

001B UCB not found or access generated in DRM

001C File not found in VTOC

001E Concatenated files not supported

0028 File not found in catalog

0030 File not found in catalog

0040 DSNAME missing

0048 File root in GDG without version number

0050 DSNAME not conform with z/OS rules

0201 Invalid information in DSCB (for example, a corrupted "used space" definition)

03DE File not deleted/renamed, member of PDS

03DF File not deleted/renamed, ENQ OLD impossible

03E0 Shared file not available, allocated by another task

03E1 Allocate of a PDS file without member name

03E2 Allocate of a GDG without BLDG

03E3 Allocate of a GDG in version +1

03E4 File not deleted/renamed, does not exist

03E5 File not created; file already exists

03E6 File not deleted/renamed, on tape

03E7 Creation of a file with a logical name (DDNAME)

0051 RENAME, GDG(+1) mandatory

0052 RENAME, temporary file cannot be GDG

0053 RENAME, CAMLST RENAME error

0054 RENAME, CAMLST CATALOG error

0055 RENAME, temporary file cannot be GDG(+1)

0056 RENAME, duplicate file on 1 volume

0057 SCRATCH, file not found

0058 SCRATCH, CAMLST SCRATCH error

0059 SCRATCH, volume not mounted

005A SCRATCH, CAMLST UNCAT outside SMS

005F RENAME, member of PDS file

**Example**

’04F003E0’: allocate by DSNAME, file already allocated to another transfer by Transfer CFT.

’04F00028’: allocated by DSNAME, file not found in the catalog.

<span id="_Toc236186759"></span>NNNN Code for S=4 (Read/Write Error)

F and RR have no significance

NNNN takes on the following values:

**Code definition**

00D4 OPEN, LRECL/BLKSIZE incorrect

00D8 OPEN, no parameter delimiter

00E4 OPEN, DDNAME incorrect

00E8 OPEN, DDNAME missing

00EC OPEN, no more memory for buffers

00F0 OPEN, parameters missing

00F4 FCB reference incorrect

00F8 Invalid SGF function code

00FC Non-authorized function code

00FD OPEN, non-0 return code

0FFF BSAM, read/write/POINT error

This error is accompanied by Transfer CFT and/or z/OS messages depending on whether:

-   Transfer CFT ‘POINT ERROR’ message in the case of repositioning on a file that does not support it.

<!-- -->

-   Transfer CFT ‘SYNA01E:’ message accompanied by the z/OS ‘SYNADAF’ message text.

This message is only displayed on the z/OS console

-   z/OSIEA000 or IECxxx message

These messages are only displayed on the z/OS console

NNNN Code Table for S=8 (ABEND during a Read/Write)

F and RR have no significance

NNNN has the ABEND code intercepted by Transfer CFT

**Example**

0B37, 0013

**Example**

’80000913’: AbendS913 at file opening, Transfer CFT does not have the right to read/write.

NNNN Code Table for S=C (VSAM Read/Write Error)

F has no significance

RR is the VSAM RETURN-CODE

NNNN is the VSAM FDBK

The VSAM RTNCD/FDBK codes are explained in the VSAM documentation.

**Example**

’C004001C’: no more space in the file.

NNNN Code table for S=F (File Parameter Error)

RR and NNNN have no significance

NNNN code table for S=F

Code Definition

F = 4 Function not allowed

F = 7 Function unknown

F = C File reference incorrect

Submit these to Axway Technical Support.

DYNALLOC Error Codes S=9

The DYNALLOC errors are explained in the IBM brochure Z/OS Vx MVS Authorized Assembler Services Guide.

Value of F for the DYNALLOC function:

**Code definition**

F=1 Allocate

F=2 De-allocate

Value of RR for DYNALLOC:

-   RR is the DYNALLOC return code. It can take on values 04, 08, 0C

Value of NNNN for DYNALLOC:

-   NNNN is the DYNALLOC REASON CODE

**Example of a DYNALLOC error code**

‘9104970C’ error: no more space to create the file.

The "IKJnnnnnI" and "IGDnnnnnI" error messages returned by DYNALLOC (under SMS) are displayed on the z/OS console:

-   IKJ56893I DATA SET NOT ALLOCATED+  

<!-- -->

-   IGD17273I ALLOCATION HAS FAILED FOR ALL VOLUMES SELECTED FOR DATA SET

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">The ‘nnnn’ hexadecimal value converted to decimal gives the SMS IGD message number. For example, the X’4379’ value corresponds to the IGD172731 message.          </td>
      </tr>
</table>

## Diagnostics for file errors

The following complementary diagnostics are available on request by Axway support, through the SGTRACE tool:

-   SGTRACE 4: Traces the file read/write actions. This value must be used for codes S=0 and S=9

<!-- -->

-   SGTRACE 8: Traces the file read/write actions. This value must be used for codes S=4, 8, C, F

<!-- -->

-   SGTRACE 2: traces the errors

<!-- -->

-   SGTRACE 128: traces the module calls and returns

The modules concerned are:

-   S=0: SGF3ACC, SGF3STAT, SIFM, SGF3VSAM, SGF3REN

<!-- -->

-   S=9: SGF3SV99

<!-- -->

-   S=4, 8, C, F: SGF3C, SIDM
