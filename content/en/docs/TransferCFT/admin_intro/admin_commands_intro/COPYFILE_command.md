{
    "title": "COPYFILE - Copy files off-line",
    "linkTitle": "COPYFILE - Copy files off-line",
    "weight": "300"
}# <span id="kanchor23"></span><span id="COPYFILE___Copy_files_off_line"></span>COPYFILE - Copy files off-line



The COPYFILE command is used

to copy a sequential file performing the following operations:



-   Compression/decompression: the compressed file must always have a

    variable format







-   Record format or

    file type modification



Use the COPYFILE command to copy a sequential file. The COPYFILE command enables a file to compressed offline, before being

sent by Transfer CFT and a file to be decompressed after being received.



Syntax



[OFN<span>A</span>ME](../Parameter_index/ofname.htm)

= filename



\[ [CREATE](../Parameter_index/create.htm)

= { <span>‘

‘</span> | YES | NO } \]



\[ [IBLKSIZE](../Parameter_index/iblksize.htm)

= { <span>0</span>

| n } \]



\[ [ICHARSET](../Parameter_index/icharset.htm) = string \]



\[ [ICODE](../Parameter_index/icode.htm)

= { ASCII | EBCDIC } \]



\[ [ICOMP](../Parameter_index/icomp.htm)

= { <span>0</span>

| 15 } \]



\[ [ICT](../Parameter_index/ict.htm)

=  { <span>H</span>

| C } \]



\[ [ILRECL](../Parameter_index/ilrecl.htm)

= { <span>0</span>

| n } \]



\[ [IRECFM](../Parameter_index/irecfm.htm)

= { F | V | U } \]



\[ [ITYPE](../Parameter_index/itype.htm)

= { ‘ ‘ | character } \]



\[ [OBLKSIZE](../Parameter_index/oblksize.htm)

= { 0 |n  }

\]



\[ [OCHARSET ](../Parameter_index/ocharset.htm)= string \]



\[ [OCODE](../Parameter_index/ocode.htm)

= { ASCII | EBCDIC } \]



\[ [OCOMP](../Parameter_index/ocomp.htm)

= { <span>0</span>

| 15 } \]



\[ [OCT](../Parameter_index/oct.htm)

= { H | C } \]



\[ [OLRECL](../Parameter_index/olrecl.htm)

= { <span>0</span>

|n } \]



\[ [ORECFM](../Parameter_index/orecfm.htm)

= { <span>IRECFM

value</span> | F | V| U } \]



\[ [OSPACE](../Parameter_index/ospace.htm)

= { <span>0</span>

| n } \]



\[ [OTYPE](../Parameter_index/otype.htm)

= { <span>‘

‘</span> | character } \]



\[ [XLATE](../Parameter_index/xlate.htm) = string \]



Limitation



When using ICHARSET and OCHARSET, all file types are supported except Binary (B) and Variable (V).



<table data-cellspacing="0">
<thead>
<tr>
<th>Parameter</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td><p><a href="../../../c_intro_userinterfaces/command_summary/parameter_intro/create">CREATE</a></p></td>
<td><p>Output file creation option.</p></td>
</tr>
<tr>
<td><p><a href="../../../c_intro_userinterfaces/command_summary/parameter_intro/iblksize">IBLKSIZE</a> </p></td>
<td><p>Defines the block size of the input file, in bytes.</p>
<p> </p></td>
</tr>
<tr>
<td><a href="icharset.htm">ICHARSET</a></td>
<td>Defines the input file encoding.</td>
</tr>
<tr>
<td><p><a href="../../../c_intro_userinterfaces/command_summary/parameter_intro/icode">ICODE</a> </p></td>
<td><p>Codes the input file data. Internal

code managed by the system, either

ASCII, or EBCDIC.</p></td>
</tr>
<tr>
<td><p><a href="../../../c_intro_userinterfaces/command_summary/parameter_intro/icomp">ICOMP</a> </p></td>
<td><p>Compresses the input file data.</p>
<p>The value 0 means that there is no compression. The possible

values (cpr) are indicated in <a href="../../../c_intro_userinterfaces/command_summary/parameter_intro/compression">Compression</a>.</p></td>
</tr>
<tr>
<td><p><a href="../../../c_intro_userinterfaces/command_summary/parameter_intro/ict">ICT</a> </p></td>
<td><p>Type of input file data compression. The value of ICOMP

must be compatible with the compression type.</p></td>
</tr>
<tr>
<td><p><a href="../../../c_intro_userinterfaces/command_summary/parameter_intro/ifname">IFNAME</a> </p></td>
<td><p>Name of the input file to be copied.</p></td>
</tr>
<tr>
<td><p><a href="../../../c_intro_userinterfaces/command_summary/parameter_intro/ilrecl">ILRECL</a></p>
<p><a href="../../../c_intro_userinterfaces/command_summary/parameter_intro/ilrecl">see

comments</a></p>
<p> </p></td>
<td><p>For records of:</p>
<ul>
<li>Fixed

format (IFRECFM = F): input file record size</li>
<li>Variable

format (IFRECFM = V): maximum record size</li>
</ul></td>
</tr>
<tr>
<td><p><a href="../../../c_intro_userinterfaces/command_summary/parameter_intro/irecfm">IRECFM</a></p>
<p>see

the specific Operations Guide</p></td>
<td><p>Input file record format:</p>
<ul>
<li>F: fixed</li>
<li>V: variable</li>
<li>U: undefined</li>
</ul></td>
</tr>
<tr>
<td><p><a href="../../../c_intro_userinterfaces/command_summary/parameter_intro/itype">ITYPE</a></p></td>
<td><p>Input file type.</p>
<p>Refer to the Operations

Guide corresponding to your OS.  </p></td>
</tr>
<tr>
<td><p><a href="../../../c_intro_userinterfaces/command_summary/parameter_intro/oblksize">OBLKSIZE</a>

   OS</p></td>
<td><p>Output file block size (in bytes). The value indicated

must be greater than the value of the OLRECL parameter.</p></td>
</tr>
<tr>
<td><a href="ocharset.htm">OCHARSET</a></td>
<td>Defines the output file encoding.</td>
</tr>
<tr>
<td><p><a href="../../../c_intro_userinterfaces/command_summary/parameter_intro/ocode">OCODE</a></p></td>
<td><p>Codes the output file data.</p></td>
</tr>
<tr>
<td><p><a href="../../../c_intro_userinterfaces/command_summary/parameter_intro/ocomp">OCOMP</a> </p></td>
<td><p>Compresses the output file data.</p></td>
</tr>
<tr>
<td><p><a href="../../../c_intro_userinterfaces/command_summary/parameter_intro/oct">OCT</a></p></td>
<td><p>Type of output file data compression. The value of OCOMP

must be compatible with the compression type.</p></td>
</tr>
<tr>
<td><p><a href="../../../c_intro_userinterfaces/command_summary/parameter_intro/ofname">OFNAME </a></p></td>
<td><p>Output file name.</p></td>
</tr>
<tr>
<td><p><a href="../../../c_intro_userinterfaces/command_summary/parameter_intro/olrecl">OLRECL</a></p></td>
<td><p>Record formats, expressed in bytes.</p></td>
</tr>
<tr>
<td><p><a href="../../../c_intro_userinterfaces/command_summary/parameter_intro/orecfm">ORECFM</a> </p></td>
<td><p>Output record format.</p></td>
</tr>
<tr>
<td><p><a href="../../../c_intro_userinterfaces/command_summary/parameter_intro/ospace">OSPACE</a></p></td>
<td><p>Space to be reserved for the output file, in K-bytes (1

K-byte = 1024 bytes).</p></td>
</tr>
<tr>
<td><p><a href="../../../c_intro_userinterfaces/command_summary/parameter_intro/otype">OTYPE</a>   

    </p></td>
<td><p>Output file type.</p></td>
</tr>
<tr>
<td><a href="../../../c_intro_userinterfaces/command_summary/parameter_intro/xlate">XLATE</a></td>
<td>Defines the translation table used

for the copyfile.</td>
</tr>
<tr>
<td> </td>
<td> </td>
</tr>
</tbody>
</table>



### Input and output parameter categories



Parameters beginning with I refer to input files.



Parameters beginning with O refer to the output files.



These two parameters may be classified into 5 sub-categories, as shown

in the following table.



<table data-cellspacing="0">
<thead>
<tr>
<th>Parameter category</th>
<th>Parameter concerned</th>
</tr>
</thead>
<tbody>
<tr>
<td><p>Execution control parameters </p></td>
<td><p>CREATE </p></td>
</tr>
<tr>
<td><p>Input data processing parameters </p></td>
<td><p>ICT, ICOMP, ICODE, ICHARSET, XLATE</p></td>
</tr>
<tr>
<td><p>Parameters associated with the input file:</p>
<ul>
<li>physical

name</li>
<li>physical

characteristics (global file)</li>
<li>physical

characteristics (records)</li>
</ul></td>
<td><p> </p>
<p> </p>
<p>IFNAME</p>
<p>ITYPE</p>
<p>IRECFM, ILRECL, IBLKSIZE </p></td>
</tr>
<tr>
<td><p>Output data processing parameters </p></td>
<td><p>OCT, OCOMP, OCODE, OCHARSET</p></td>
</tr>
<tr>
<td><p>Parameters associated with the output file:</p>
<ul>
<li>physical

name</li>
<li>physical

characteristics (global file)</li>
<li>physical

characteristics (records)</li>
</ul></td>
<td><p> </p>
<p> </p>
<p>OFNAME</p>
<p>OSPACE, OTYPE</p>
<p>ORECFM, OLRECL, OBLKSIZE </p></td>
</tr>
</tbody>
</table>



## <span id="Statistics"></span>Statistics



The utility prints out execution statistics.



The following table indicates the heading contents.



<table data-cellspacing="0">
<thead>
<tr>
<th>Heading number</th>
<th>Contents</th>
</tr>
</thead>
<tbody>
<tr>
<td><p>1 </p></td>
<td><p>Complete name of the input file </p></td>
</tr>
<tr>
<td><p>2 </p></td>
<td><p>Coding of the input file data </p></td>
</tr>
<tr>
<td><p>3 </p></td>
<td><p>Input file compression type:</p>
<ul>
<li>EXT (PeSIT

non-SIT)</li>
<li>CFT (PeSIT

CFT to CFT)</li>
</ul></td>
</tr>
<tr>
<td><p>4 </p></td>
<td><p>Input file compression value </p></td>
</tr>
<tr>
<td><p>5 </p></td>
<td><p>Number of records to be copied (input file) </p></td>
</tr>
<tr>
<td><p>6 </p></td>
<td><p>Input file size in K bytes (1) </p></td>
</tr>
<tr>
<td><p>6b </p></td>
<td><p>Input file size in K bytes, if ILRECL is less than the

actual size of the record (2) </p></td>
</tr>
<tr>
<td><p>7 </p></td>
<td><p>Complete name of the output file </p></td>
</tr>
<tr>
<td><p>8 </p></td>
<td><p>Coding of the output file data </p></td>
</tr>
<tr>
<td><p>9 </p></td>
<td><p>Compression type:</p>
<ul>
<li>EXT (PeSIT

non-SIT)</li>
<li>CFT (PeSIT

CFT to CFT)</li>
</ul></td>
</tr>
<tr>
<td><p>10 </p></td>
<td><p>Output file compression value </p></td>
</tr>
<tr>
<td><p>11 </p></td>
<td><p>Output file size in K bytes </p></td>
</tr>
<tr>
<td><p>11b </p></td>
<td><p>Output file size in K bytes, if padding (OLRECL &gt; ILRECL) </p></td>
</tr>
<tr>
<td><p>12 </p></td>
<td><p>Compression rate performed when copying the file </p></td>
</tr>
<tr>
<td><p>12b </p></td>
<td><p>Expansion rate performed when copying the file </p></td>
</tr>
</tbody>
</table>



\(1\) (2): Headings 6 and 6b are mutually

exclusive. If heading 6b is displayed, heading 6 is not and vice versa.

