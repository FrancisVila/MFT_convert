{
    "title": "CFTEXT  - Extract file data ",
    "linkTitle": "CFTEXT &#45; Extracting data",
    "weight": "340"
}You can use the <span id="About_the_CFTEXT_Command"></span>**CFTEXT**
object to extract Parameter and Partner file data. CFTEXT generates, as output, a configuration command text used to reconstitute
the data of these files.

The resulting configuration
file is then submitted to CFTUTIL to:

-   Rebuild a lost
    or damaged configuration
-   Facilitate the
    exporting of a <span class="mc-variable axway_variables.Component_Long_Name variable">Transfer CFT</span> configuration to another computer
-   Upgrade the Transfer
    CFT software when such an upgrade incorporates a file structure modification

The configuration command text generated is written to the CFTUTIL output
medium. To recover a CFTUTIL output, you can either redirect the standard
output or else redefine the output medium via the command CONFIG TYPE
= OUTPUT.

All parameter values are in UPPER CASE letters.

Command syntax: <span style="font-weight: bold;">[CFTEXT](../../../command_summary#CFTEXT)</span>

<table>
         
         
         
   
   <thead>
      <tr>
<th >Parameters         </th>
<th >Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td colspan="2" ><p>Use this command to extract all or part of the data from
the parameter and partner files.</p>         </td>
      </tr>
      <tr>
         <td ><p><a href="../../../command_summary/parameter_intro/id">ID</a> </p>         </td>
         <td   width="49.916%"><p>Identifier of the parameter to be extracted.</p>
<p>The value of this identifier is the value of the ID of
the command CFTxxxx corresponding to the TYPE parameter; this allows the
extraction to be limited:</p>
<ul>
<li>To an
explicitly indicated value (identifier)</li>
<li>Or to
a group of values designated through the use of a mask using "wildcard"
characters</li>
</ul>
<p>When this parameter is not defined, all the occurrences
of the parameter type (defined by TYPE) are extracted.</p>         </td>
      </tr>
      <tr>
         <td ><a href="../../../command_summary/parameter_intro/content">CONTENT</a>         </td>
         <td   width="49.916%"><p>Level of content included in output:</p>
<ul>
<li>BRIEF = Empty or default value parameters are omitted</li>
<li>FULL = All parameters are included</li>
</ul>         </td>
      </tr>
      <tr>
         <td ><p><a href="../../../command_summary/parameter_intro/fout">FOUT</a> </p>         </td>
         <td   width="49.916%"><p>Name of the file to which the command’s standard output
will be redirected.</p>
<p>This generated file can then be interpreted directly by
CFTUTIL.</p>
<p>When this parameter is not filled, all occurrences of the
type parameter (defined in the TYPE parameter) are extracted.</p>         </td>
      </tr>
      <tr>
         <td ><p><a href="../../../command_summary/parameter_intro/fparm">FPARM</a></p>
<p>{see the comment |
filename} </p>
<p>Except for TYPE = PART</p>         </td>
         <td   width="49.916%"><p>Name of the Parameter input file.</p>
<p>Default value: default name of the Parameter file defined
for CFTUTIL for the system concerned. Refer to the Transfer CFT <em>Operations
Guide</em> that corresponds with your OS.</p>         </td>
      </tr>
      <tr>
         <td ><p><a href="../../../command_summary/parameter_intro/fpart">FPART</a> </p>
<p>{see the
comment | filename}]</p>
<p>For TYPE = {ALL | PART}</p>         </td>
         <td   width="49.916%"><p>Name of the Partner input file.</p>
<p>Default value: default
name of the Partner file defined for CFTUTIL for the system concerned.
Refer to the Transfer CFT <span >Operations Guide</span> that corresponds with
your OS.</p>         </td>
      </tr>
      <tr>
         <td ><p><a href="../../../command_summary/parameter_intro/type">TYPE</a> </p>         </td>
         <td   width="49.916%"><p>This parameter defines the parameter type to be extracted.</p>         </td>
      </tr>
   </tbody>
</table>

Example 1

```
CFTEXT
```

Extraction of all data from the CFTPARM parameter and CFTPART
partner files.

Example 2

```
CFTEXT     TYPE    
=     SEND,
     ID     =    
FACT,
     FPARM     =    
mycftparm
```

Extraction of data concerning the model file to be sent
(CFTSEND command) with an IDF = FACT, from the file mycftparm.

Example 3

```
CFTEXT
TYPE = RECV,
ID = FACT\*
```

Extraction of the data concerning the model files to be
received (CFTRECV command) whose IDF value begins with the four letters
"FACT". The name of the Parameter file is the default name indicated.
Refer to the Transfer CFT Operations Guide that corresponds with
your OS.

Example 4

```
CFTEXT
TYPE = PART,
ID = MAGA\*
```

Extraction of the partner data corresponding to the CFTPART
commands, the identifier of which begins with the four letters "MAGA".
The Partner file name is the default name indicated. Refer to the Transfer
CFT Operations Guide that corresponds with your OS.

Example 5

Transfer
CFT application definition:

```
CFTEXT TYPE = APPL,
```
