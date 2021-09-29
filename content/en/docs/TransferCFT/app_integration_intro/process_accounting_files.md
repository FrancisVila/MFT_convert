{
    "title": "Processing accounting files",
    "linkTitle": "Processing accounting files",
    "weight": "240"
}# Processing accounting files

You can write the statistical data for successful transfers to a file by defining the CFTACCNT type=file command as described in [Recording mode for statistical data](../../admin_intro/admin_config_commands/cftaccnt_concepts). You can then extract this data to use with other applications. The extracted data is available in C language for all platforms and in COBOL for z/OS and IBM i systems.

## Delivered files

### Include file

Transfer CFT provides an include file, cftcnt.h, that provides the account file record structure to be used by the program. Depending on the operating system, the file is located in:

-   UNIX, Windows, HP NonStop, and IBM i (IFS): &lt;installdir>/home/inc
-   z/OS: Distrib..H (CFTCNT)

### Sample source

Transfer CFT delivers a sample source written in C language called exacct.c as well as a compilation procedure, which is system dependent:

<table data-cellspacing="0">
<thead>
<tr class="header">
<th>System</th>
<th>File location</th>
<th>Build command</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>UNIX</td>
<td>&lt;install_dir&gt;/home/distrib/template/src/exit</td>
<td>makefile</td>
</tr>
<tr class="even">
<td>Windows</td>
<td>&lt;install_dir&gt;\home\distrib\template\src\exit</td>
<td>exit.mak</td>
</tr>
<tr class="odd" data-mc-conditions="">
<td>z/OS</td>
<td>Distrib..SAMPLEC(EXACCT)</td>
<td><p>Compilation: Runtime..INSTALL(I91APICP)</p>
<p>Link-edit: Runtime..INSTALL(I92APILK)</p></td>
</tr>
<tr class="even" data-mc-conditions="">
<td>IBM i (IFS)</td>
<td>&lt;install_dir&gt;/home/distrib/template/src/exit</td>
<td>gmake</td>
</tr>
<tr class="odd" data-mc-conditions="">
<td>HP NonStop</td>
<td>&lt;install_dir&gt;/home/distrib/template/src/exit</td>
<td>makefile</td>
</tr>
</tbody>
</table>

## Executing the sample file

You can use the following steps for all supported operating systems except z/OS:

To generate a sample file for example on UNIX:

1.  Copy the two files from &lt;install\_dir>/home/distrib/template/src/exit to &lt;install\_dir>/runtime/src/exit.
2.  Enter the system appropriate compile command.

The EXACCT executable file is automatically stored in:

-   UNIX, HP NonStop, IBM i (IFS): &lt;installdir>/runtime/bin/EXACCT &lt;account file name>
-   Windows: &lt;installdir>\\runtime\\bin\\EXACCT &lt;account file name>

Perform the following steps if you are running on a z/OS system.

1.  Copy the Runtime..SAMPLEC(EXACCT) to Distrib..SAMPLEC(EXACCT)
2.  Compile.
3.  Perform the link edit.

### UNIX, HP NonStop, and IBM i (IFS) example

Syntax

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td>EXACCT &lt;install_dir&gt;/runtime/accnt/cftaccnt</td>
</tr>
</tbody>
</table>

### Windows example

Syntax

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td>EXACCT &lt;install_dir&gt;\home\distrib\template\src\exit</td>
</tr>
</tbody>
</table>

### z/OS example

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>//S1 EXEC PGM=EXACCT,PARM='acount_file_name'</p>
<p>//SYSPRINT DD SYSOUT=*</p>
<p>//SYSOUT DD SYSOUT=*</p></td>
</tr>
</tbody>
</table>

## Results

All operating systems should have a resulting file similar to the following:

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>ACCOUNT FILE</p>
<p>------------</p>
<p>Transfer id. IDT</p>
<p>B2508304</p>
<p>Direct DIRECT = RECV</p>
<p>Mode MODE = REQUESTER</p>
<p>Type TYPE = FILE</p>
<p> </p>
<p>Item type DIFTYP = SINGLE</p>
<p> </p>
<p>Logic file identifier IDF = TEST</p>
<p>Logic file network id NIDF = TEST</p>
<p>Protocol identifier PROT = PESITSSL</p>
<p>File Name FNAME =</p>
<p>*recv/FTEST</p>
<p>...</p>
<p>*</p>
<p> </p>
<p>Receiver application RAPPL =</p>
<p>*</p>
<p>Record format FRECFM = U</p>
<p>length FLRECL = 04096</p>
<p>File compression NCOMP = 00</p>
<p>Bytes FCARS = 0000007104</p></td>
</tr>
</tbody>
</table>
