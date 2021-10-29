{
    "title": "Typographical  conventions",
    "linkTitle": "Typographical conventions",
    "weight": "180"
}The typographical conventions specify the
syntax to use in Transfer CFT commands, the
parameters and their values. These rules apply equally for any additional
parameter information, or information pertaining to the operating system
or the transfer protocols.

<table data-cellpadding="0" data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td data-valign="top">         </td>
         <td data-valign="top"><span><strong>Note</strong></span>         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">Use the <a href="transfercft/c_intro_userinterfaces/command_summary">Command
index</a> to help locate a command, and the <a href="parameter_intro">Parameter
index</a> for parameter details.         </td>
      </tr>
   </tbody>
</table>

## <span id="Command_description"></span>Command description

The description of each command is generally organized in parts:

-   Functional description
-   List indicating
    the general syntax of parameters passed with a command, grouped by categories

Example

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>CFTFILE [MODE = {CREATE
| DELETE},]<br />
FNAME = filename,<br />
TYPE = {PARM
| PART | CAT | LOG | ACCNT
| COM},         </td>
      </tr>
   </tbody>
</table>

-   Detailed description
    of parameters, in alphabetical order

FNAME =
filename (Name
of the file to which the command applies)

-   Generic example
    of parameter setting. Parameter setting examples are indicated in New
    Courier typeface.

Example of creating a parameter file:

CFTFILE TYPE = PARM,  
    MODE = CREATE,  
    FNAME = filename

### <span id="Parameter_description"></span>Parameter description

There are two types of parameters mandatory and optional:

-   Mandatory parameters
    are followed by the word (*Mandatory*)
    in italics
-   Optional parameters
    (placed between square brackets \[ \])

Each parameter description applies the following general syntax:

<table data-cellspacing="0">
   <thead>
      <tr class="header">
         <th>            <p>PARAMETER = value(s)</p></th>
         <th>            <p>Information</p></th>
         <th>            <p>SPECIFIC</p></th>
      </tr>
   </thead>
   <tbody>
      <tr class="odd" data-valign="middle">
         <td width="27.491%">            <p>Definition of the parameter</p>         </td>
         <td width="33.085%">            <p>Indication of any additional information available for
the value defined.</p>         </td>
         <td width="39.424%">            <p>Indication of the field of application and any usage restrictions
for the parameter</p>         </td>
      </tr>
   </tbody>
</table>

The information and specifics fields are optional.

Example

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>COPYFILE
OFNAME
= filename         </td>
      </tr>
   </tbody>
</table>

In this command, the OFNAME
parameter is mandatory. Its value corresponds to a filename.

Example

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>CFTSEND [NFNAME =
filename]       PeSIT
E CFT/CFT         </td>
      </tr>
   </tbody>
</table>

In this object, the NFNAME
parameter is:

-   Used to indicate
    a physical filename
-   Optional with no
    default value, the optional nature being indicated by square brackets
    \[ \]
-   Reserved for transfer
    cases in PeSIT E
    profile between two Transfer CFTs

### <span id="Parameter_value_notation_conventions"></span>Parameter value notation conventions

The notation conventions generally used to describe parameter values
are listed in the following table.

<table data-cellspacing="0">
   <thead>
      <tr class="header">
         <th>Description</th>
         <th>Notation</th>
         <th>Example</th>
      </tr>
   </thead>
   <tbody>
      <tr class="odd" data-valign="middle">
         <td data-valign="top" width="34.039%">            <p>List of possible values </p>         </td>
         <td data-valign="top" width="33.961%">            <p>{value, value} </p>         </td>
         <td data-valign="top" width="32%">            <p>{filename, string} </p>         </td>
      </tr>
      <tr class="even" data-valign="middle">
         <td data-valign="top" width="34.039%">            <p>Choice </p>         </td>
         <td data-valign="top" width="33.961%">            <p>{1 | 2} </p>         </td>
         <td data-valign="top" width="32%">            <p>{CREATE | DELETE} </p>         </td>
      </tr>
      <tr class="odd" data-valign="middle">
         <td data-valign="top" width="34.039%">            <p>Numeric field<br />
(value indicated between a and b) </p>         </td>
         <td data-valign="top" width="33.961%">            <p>{a..b} </p>         </td>
         <td data-valign="top" width="32%">            <p>{0..255}  </p>         </td>
      </tr>
      <tr class="even" data-valign="middle">
         <td data-valign="top" width="34.039%">            <p>Default value </p>         </td>
         <td data-valign="top" width="33.961%">            <p>underlined </p>         </td>
         <td data-valign="top" width="32%">            <p>{CREATE | DELETE} </p>         </td>
      </tr>
      <tr class="odd" data-valign="middle">
         <td data-valign="top" width="34.039%">            <p>Optional parameter </p>         </td>
         <td data-valign="top" width="33.961%">            <p>[PARAMETER] </p>         </td>
         <td data-valign="top" width="32%">            <p>[NFNAME
= filename] </p>         </td>
      </tr>
      <tr class="even" data-valign="middle">
         <td data-valign="top" width="34.039%">            <p>{value|text}
must be indicated </p>         </td>
         <td data-valign="top" width="33.961%">            <p>italic </p>         </td>
         <td data-valign="top" width="32%">            <p>filename </p>         </td>
      </tr>
      <tr class="odd" data-valign="middle">
         <td data-valign="top" width="34.039%">            <p>Mandatory parameter</p>         </td>
         <td data-valign="top" width="33.961%">            <p>(Mandatory)</p>         </td>
         <td data-valign="top" width="32%">            <p> </p>         </td>
      </tr>
   </tbody>
</table>

### <span id="Generic_type_parameter_values"></span>Generic-type parameter values

The conventions used for generic-type values are listed in the following
table.

<table data-cellspacing="0">
   <thead>
      <tr class="header">
         <th>Description</th>
         <th>Notation</th>
         <th>Example</th>
      </tr>
   </thead>
   <tbody>
      <tr class="odd">
         <td data-valign="top">            <p>Character type value: one single character </p>         </td>
         <td data-valign="top" width="22%">            <p>c</p>         </td>
         <td data-valign="top" width="30%">            <p>FTYPE
= c </p>         </td>
      </tr>
      <tr class="even">
         <td data-valign="top">            <p>Numeric type value: numeric character string </p>         </td>
         <td data-valign="top" width="22%">            <p>n</p>         </td>
         <td data-valign="top" width="30%">            <p>FLRECL
= n </p>         </td>
      </tr>
      <tr class="odd">
         <td data-valign="top">            <p>Character string value: series of alphanumeric characters
or series of characters between quotes </p>         </td>
         <td data-valign="top" width="22%">            <p>string</p>         </td>
         <td data-valign="top" width="30%">            <p>SAP = string </p>         </td>
      </tr>
      <tr class="even">
         <td data-valign="top">            <p>If the parameter is mandatory: string containing between
1 and n characters
inclusive</p>
            <p>If the parameter is optional: string containing between
0 and n characters </p>         </td>
         <td data-valign="top" width="22%">            <p>stringn</p>         </td>
         <td data-valign="top" width="30%">            <p>PUNAME
= string10<br />
String containing between 1 and 10 characters<br />
<br />
[COMMENT = string32]<br />
String containing between 0 and 32 characters </p>         </td>
      </tr>
      <tr class="odd">
         <td data-valign="top">            <p>String containing between n
and m characters</p>         </td>
         <td data-valign="top" width="22%">            <p>stringn..m </p>         </td>
         <td data-valign="top" width="30%">            <p>LUNAME
= string3..8<br />
String containing between 3 and 8 characters </p>         </td>
      </tr>
      <tr class="even">
         <td data-valign="top">            <p>String containing exactly n
characters</p>         </td>
         <td data-valign="top" width="22%">            <p>stringn </p>         </td>
         <td data-valign="top" width="30%">            <p>KEY = string21<br />
21-character string </p>         </td>
      </tr>
      <tr class="odd">
         <td data-valign="top">            <p>Constant-type value (preset) </p>         </td>
         <td data-valign="top" width="22%">            <p>VALUE </p>         </td>
         <td data-valign="top" width="30%">            <p>TYPE = PESIT </p>         </td>
      </tr>
      <tr class="even">
         <td data-valign="top">            <p>Password type value: string containing between n
and m characters</p>         </td>
         <td data-valign="top" width="22%">string         </td>
         <td data-valign="top" width="30%">          </td>
      </tr>
   </tbody>
</table>

The string notation is used generically, in lists indicating
the general parameter syntax for example. The stringn,
stringn..m
and stringn
notations are used in the detailed parameter descriptions.

### HELP command use and conventions

When using the CFTUTIL HELP command, as shown in the example below, the following rules apply to parameter values:

-   If STRING is in upper case, the parameter value is not case sensitive
-   If String is mixed case, the parameter value is case sensitive
-   If STRING or "String", the parameter value is only case sensitive when enclosed in quotes

Example

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>CFTUTIL help cmd=cftsend, content=detail</p>
            <p> </p>
            <p>COMMAND CFTSEND USAGE</p>
            <p> MODE STRING max_length=7 Action to do in the parameter or partner base &lt;REPLACE&gt;</p>
            <p> 'CREATE'</p>
<div>
            <p>   ...</p>
            <p> PRESTATE <strong>STRING</strong> max_length=0 The transfer phase step as it enters the A phase &lt; &gt; (' ','DISP','HOLD')</p>
            <p>   ...</p>
            <p> RAPPL <strong>STRING or "String"</strong> max_length=48 Identifier of the file receiver application</p>
            <p>  ...</p>
            <p> RPASSWD <strong>String</strong> max_length=32 Password for the user who is receiving the file</p>
</div>         </td>
      </tr>
   </tbody>
</table>

### Using single quotes and double quotes

The following conventions apply when using double quotes (hereafter referred to as quotes) " " and single quotes ' ' in CFTUTIL commands:

-   Enclosing in quotes " " keeps case sensitivity for applicable parameters as listed in the **Note** below.
-   Enclosing in a single quote ' ' keeps spaces in the value

<table data-cellpadding="0" data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td data-valign="top">         </td>
         <td data-valign="top"><span><strong>Note</strong></span>         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">Parameters affected by the quote sensitivity include: FLOWNAME, RAPPL, RUSER, SAPPL, SOURCEAPPL, SUSER, TARGETAPPL, NRPASSW, NSPART, NSPASSW.         </td>
      </tr>
   </tbody>
</table>

Lastly, to use the quote character in a parameter string you have to repeat it, for example:

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>PARM = 'xxx,''yyy'',zzz',</p>         </td>
      </tr>
   </tbody>
</table>

### <span id="Parameter_values_concerning_preset_categories"></span>Parameter values for preset categories

The conventions used for values concerning preset categories are listed
in the following table.

<table data-cellspacing="0">
   <thead>
      <tr class="header">
         <th>Description</th>
         <th>Notation</th>
      </tr>
   </thead>
   <tbody>
      <tr class="odd">
         <td data-valign="top" width="80%">            <p>Compression: numeric value between 0 and 15 indicating
the compression algorithm </p>         </td>
         <td data-valign="top" width="20%">            <p>cpr </p>         </td>
      </tr>
      <tr class="even">
         <td data-valign="top" width="80%">            <p>Date: 8-digit string</p>         </td>
         <td data-valign="top" width="20%">            <p>YYYYMMDD </p>         </td>
      </tr>
      <tr class="odd">
         <td data-valign="top" width="80%">            <p>File name: 512 characters including the drive, path, root, suffix, where limitations are imposed by file system or operating system  (such as list of unauthorized characters , length, case-sensitivity, etc.)</p>         </td>
         <td data-valign="top" width="20%">            <p>filename </p>         </td>
      </tr>
      <tr class="even">
         <td data-valign="top" width="80%">            <p>Identifier: alphanumeric string of 1 to 32 alphanumeric characters and additional characters:</p>
            <p>@ # &amp; % ! : - _ + \ / | ? { } [ ] ; * &lt; &gt; ~ ^</p>         </td>
         <td data-valign="top" width="20%">            <p>identifier </p>         </td>
      </tr>
      <tr class="odd">
         <td data-valign="top" width="80%">            <p>Mask: string containing wildcard characters (* and ?) :</p>
            <p>When referring to ReGEX expressions, other value are possible.</p>         </td>
         <td data-valign="top" width="20%">            <p>mask </p>         </td>
      </tr>
      <tr class="even">
         <td data-valign="top" width="80%">            <p>Time: string containing 2 to 8 digits </p>         </td>
         <td data-valign="top" width="20%">            <p>HHMMSSSS</p>         </td>
      </tr>
      <tr class="odd">
         <td data-valign="top" width="80%">            <p>Transfer identifier assigned by <span>Transfer CFT</span> </p>         </td>
         <td data-valign="top" width="20%">            <p>transid </p>         </td>
      </tr>
   </tbody>
</table>

### <span id="OS_specificities"></span>OS specificity

In the parameter syntax listings, values that are OS specific indicated
as follows: OS

Example: ACCID
= n                              OS

In the detailed description of a parameter, the operating system(s)
for which this parameter is pertinent is (are) indicated in detail, for
the operating system concerned.

Example: ACCID
=n           
                           
MVS

The default value of a parameter may differ from one system to another;
this is indicated as follows: Dft: OS

Example: \[FCODE    
= {BINARY | EBCDIC | ASCII}          Dft:
OS

### <span id="Protocol_dependent_parameters"></span>Protocol dependent parameters

In the parameter syntax listings, the parameter values that are dependent
on one or more protocols are indicated as follows: PROTOCOL

Example

\[NSPACE    
= n,\]               PROTOCOL

In the parameter description, the protocol concerned is
indicated explicitly. This notation is used, for example, in the following
cases:

-   Associated parameter
    is only defined for certain protocols

Example: \[NSPACE = {value of FSPACE
| n},\]           ODETTE,
PeSIT

-   Length of the value
    of the associated parameter differs from one protocol to another.

Example  

\[NSPASSW = string\]  
string8     
PeSIT  
string8       ODETTE  
string22

The default value of a parameter may differ from one protocol to another;
this is indicated as follows: Dft: PROTOCOL

Example

\[NCODE = {see the comment
| BINARY | EBCDIC | ASCII}\]      Dft: PROTOCOL

The default value of a parameter may differ from one PeSIT protocol
profile to another; this specificity is indicated as follows: Dft:
PROFILE

Example

\[DISCTS     = n\]                        
Dft: PROFILE    

If the parameter in the command, in this case CFTPROT TYPE=PeSIT, is
not defined, the default value of the profile is used.

### <span id="Protocol_variants"></span>Protocol variants

Specificity concerning the PeSIT protocol. A protocol dependent parameter may involve one or more of the PeSIT
protocol variants, indicated as follows:

<table data-cellspacing="0">
   <thead>
      <tr class="header">
         <th>Protocol</th>
         <th>Description</th>
      </tr>
   </thead>
   <tbody>
      <tr class="odd">
         <td>            <p>PeSIT</p>         </td>
         <td>            <p>PeSIT protocol (standard)</p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>PeSIT CFT/CFT</p>         </td>
         <td>            <p>PeSIT protocol used between two <span>Transfer CFT</span>s</p>         </td>
      </tr>
   </tbody>
</table>

### <span id="Command_syntax"></span>Command syntax

The parameter setting commands are presented in the following format:

<table data-cellspacing="0">
   <thead>
      <tr class="header">
         <th>            <p>Syntax</p></th>
         <th>            <p>Command syntax listed here [see
parameters below]</p></th>
      </tr>
   </thead>
   <tbody>
      <tr class="odd">
         <td>            <p>Description</p>         </td>
         <td>            <p>Each parameter setting command generates one or more binary
records in the PARAMETER or PARTNER file.</p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>Parameters</p>         </td>
         <td>            <p>Parameter name and abbreviation</p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p>id</p>         </td>
         <td>            <p>identifier {0..32768}</p>
            <p>Identifies the object
described by the parameter setting command.</p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>mode</p>         </td>
         <td>            <p>Describes the operation to be performed on the PARAMETER
or PARTNER files.</p>
            <ul>
               <li>REPLACE
(default): modify the associated record or records, or create them if
they do not exist; this is the default value (default)               </li>
               <li>CREATE: add one or more records               </li>
               <li>DELETE: delete one or more records               </li>
            </ul>         </td>
      </tr>
      <tr class="odd">
         <td>            <p>Usage rules</p>         </td>
         <td>            <p>All the parameters required to identify the file must be
specified, except in the case of DELETE where the ID parameter is sufficient.</p>
            <p>When you select REPLACE the following occurs:</p>
            <ul>
               <li>If the
CLASS parameter is modified a new record is created               </li>
               <li>If the
CLASS parameter is not modified the new record overwrites the existing
one               </li>
            </ul>
            <p>Only the parameters specified in the command are taken
into account. Default value are used for unspecified parameters.</p>
            <p>The comment for the MODE parameter is common to all the
parameter setting commands and is not repeated on the following pages.</p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>Example</p>         </td>
         <td>            <p>When available, an example is listed here.</p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p>Syntax</p>         </td>
         <td>            <p>Command syntax listed here [see
parameters below]</p>         </td>
      </tr>
   </tbody>
</table>

### <span id="Command_reply_format"></span>Command reply format

Example

The report `CFTU94I   SHUT _Correct `indicates that the SHUT command was correctly entered
in CFTUTIL.

### Referencing environment variables

You can reference a environment variable in the Transfer CFT configuration using the `%env:<variable>%`, for example, `FNAME=%env:CFTDIRPUB%/FTEST`, which is resolved when you create or modify the associated object.

### Referencing UCONF parameters

You can reference a UCONF parameter in the Transfer CFT configuration using the `%uconf:<parameter>%`, for example, `PART=%uconf:cft.instance_id%`, which is resolved when you create or modify the associated object.
