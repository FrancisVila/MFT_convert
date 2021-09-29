{
    "title": "CFTUTIL\u00a0in a z/OS\u00a0environment",
    "linkTitle": "CFTUTIL\u00a0in a z/OS\u00a0environment",
    "weight": "270"
}CFTUTIL is the primary utility for Transfer CFT. This section details some functionally related specifically to z/OS. The CFTUTIL utility is called through two procedures: PCFTUTIL and PCFTUTL.

<table data-cellpadding="0" data-cellspacing="0">
<tbody>
<tr class="odd">
<td data-valign="top"></td>
<td data-valign="top"><span><strong>Note</strong></span></td>
<td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">There have been updates to this utility in versions 3.2.4 and 3.2.4 SP1.</td>
</tr>
</tbody>
</table>

## CFTIN: Concatenate regular sequential data sets and in-stream data sets

<table data-cellpadding="0" data-cellspacing="0">
<tbody>
<tr class="odd">
<td data-valign="top"></td>
<td data-valign="top"><span><strong>Note</strong></span></td>
<td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">MY.FB80.PARM -&gt; RECFM=FB , LRECL=80</td>
</tr>
</tbody>
</table>

### Regular data set defined first

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>//CFTUTIL EXEC PCFTUTIL,PARM=''</p>
<p>//CFTIN DD DISP=SHR,DSN=MY.FB80.PARM(CMDUTI)</p>
<p>// DD *</p>
<p>ABOUT</p>
<p>/*</p></td>
</tr>
</tbody>
</table>

### In-stream data set defined first

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>//CFTUTIL EXEC PCFTUTIL,PARM=''</p>
<p>//CFTIN DD *</p>
<p>ABOUT</p>
<p>/*</p>
<p>//      DD DISP=SHR,DSN=MY.FB80.PARM(CMDUTI)</p></td>
</tr>
</tbody>
</table>

For data set concatenation on Transfer CFT 3.2.4 and higher:

-   For PDSs concatenation, as specified in the IBM documentation, the data set with the largest block size must appear first in the concatenation.
-   You cannot concatenate PDSs that have different record lengths when RECFM=FB.

## CFTIN: Working with UNIX files

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>//CFTUTIL EXEC PCFTUTIL,PARM=''</p>
<p>//CFTIN DD PATHOPTS=ORDONLY,</p>
<p>// PATH='/home/user/cft_cmd.txt'</p></td>
</tr>
</tbody>
</table>

-   File concatenation does not work.
-   cft\_cmd.txt is a EBCDIC text file.

## CFTIN: CFTIN is missing

When no command is specified in the JCL PARM parameter, and if the DD CFTIN is not defined in the JCL:

-   The CFTUTIL return code is: 8
-   The following WTO is performed:

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td>+CFTUZ1E ** CFTIN/VFMIN DD STATEMENT MISSING **</td>
</tr>
</tbody>
</table>

## CFTPARM dummy

When using the PCFTUTIL procedure and there is no data used from CFTPARM, we recommend specifying DUMMY as the DD CFTPARM to decrease EXCP and CPU consumption, for example in END-TRANSFER procedures.

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>//CFTUTIL EXEC PCFTUTIL,PARM=''</p>
<p>//CFTPARM DD DUMMY</p></td>
</tr>
</tbody>
</table>
