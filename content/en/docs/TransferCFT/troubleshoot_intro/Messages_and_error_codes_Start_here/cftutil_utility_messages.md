{
    "title": "CFTUTIL  utility output messages: CFTunnx",
    "linkTitle": "CFTUTIL utility messages",
    "weight": "410"
}<span id="Messages_from_the_CFTUTIL_utility"></span>You can find the utility output in either the standard output or the redirection file.

<table>
   <tbody>
      <tr>
         <td><p>Error</p>         </td>
         <td><p><span id="CFTU00I"></span>CFTU00I: &amp;Cmd _
Correct (&amp;str)</p>         </td>
      </tr>
      <tr>
         <td><p>Information</p>         </td>
         <td><p>The &amp;Cmd command is executed correctly. The &amp;str
string represents the parameters passed with this command (up to 50 characters).</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
   <tbody>
      <tr>
         <td><p>Error</p>         </td>
         <td><p><span id="CFTU01E"></span>CFTU01E: storage allocation
error</p>         </td>
      </tr>
      <tr>
         <td><p>Explanation</p>         </td>
         <td><p>The communication utility could not acquire the memory
required to run.</p>         </td>
      </tr>
      <tr>
         <td><p>Consequence</p>         </td>
         <td><p>Immediate shutdown of the communication utility.</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Inform Product Support.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
   <tbody>
      <tr>
         <td><p>Error</p>         </td>
         <td><p><span id="CFTU02E"></span>CFTU02E: unable to allocate
file &amp;Fname</p>         </td>
      </tr>
      <tr>
         <td><p>Explanation</p>         </td>
         <td><p>Problem allocating the file containing the parameter setting
commands.</p>         </td>
      </tr>
      <tr>
         <td><p>Consequence</p>         </td>
         <td><p>Immediate shutdown of the communication utility.</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check the existence and state of the file, correct the
error and then restart the communication utility.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
   <tbody>
      <tr>
         <td><p>Error</p>         </td>
         <td><p><span id="CFTU03E"></span>CFTU03E: unable to open
file &amp;Fname</p>         </td>
      </tr>
      <tr>
         <td><p>Explanation</p>         </td>
         <td><p>Problem opening the file containing the parameter setting
commands.</p>         </td>
      </tr>
      <tr>
         <td><p>Consequence</p>         </td>
         <td><p>Immediate shutdown of the communication utility.</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check the characteristics of the file to be opened and
inform Product Support if necessary.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
   <tbody>
      <tr>
         <td><p>Error</p>         </td>
         <td><p><span id="CFTU04E"></span>CFTU04E: error reading
input file &amp;Fname</p>         </td>
      </tr>
      <tr>
         <td><p>Explanation</p>         </td>
         <td><p>Problem reading the file containing the parameter setting
commands.</p>         </td>
      </tr>
      <tr>
         <td><p>Consequence</p>         </td>
         <td><p>Immediate shutdown of the communication utility.</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check the characteristics of the file to be opened and
inform Product Support if necessary.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
   <tbody>
      <tr>
         <td><p>Error</p>         </td>
         <td><p><span id="CFTU05E"></span>CFTU05E: &amp;Cmd Failed
_ Unexpected end of file (command)</p>         </td>
      </tr>
      <tr>
         <td><p>Explanation</p>         </td>
         <td><p>The end of the file was reached before the end of the command
(the last character of the command line may be a comma).</p>         </td>
      </tr>
      <tr>
         <td><p>Consequence</p>         </td>
         <td><p>Immediate shutdown of the communication utility.</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Review the command syntax, correct the error and then restart
the communication utility.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
   <tbody>
      <tr>
         <td><p>Error</p>         </td>
         <td><p><span id="CFTU06E"></span>CFTU06E: unexpected
end of file before new command</p>         </td>
      </tr>
      <tr>
         <td><p>Explanation</p>         </td>
         <td><p>The end of the file was reached before the start of a new
command (a comment in the file read may not be closed).</p>         </td>
      </tr>
      <tr>
         <td><p>Consequence</p>         </td>
         <td><p>Immediate shutdown of the communication utility.</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Add an end of comment marker (*/) to the file and then
restart the communication utility.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
   <tbody>
      <tr>
         <td><p>Error</p>         </td>
         <td><p><span id="CFTU07E"></span>CFTU07E: &amp;Cmd Failed
_ unexpected end of file (comments)</p>         </td>
      </tr>
      <tr>
         <td><p>Explanation</p>         </td>
         <td><p>The end of the file was reached before the end of the command
(a comment inside the command may not be closed).</p>         </td>
      </tr>
      <tr>
         <td><p>Consequence</p>         </td>
         <td><p>Immediate shutdown of the communication utility.</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Add an end of comment marker (*/) in the command and then
restart the communication utility.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
   <tbody>
      <tr>
         <td><p>Error</p>         </td>
         <td><p><span id="CFTU08E"></span>CFTU08E: &amp;Cmd Failed
_ missing parenthesis</p>         </td>
      </tr>
      <tr>
         <td><p>Explanation</p>         </td>
         <td><p>An opening or closing parenthesis is missing in the command
syntax.</p>         </td>
      </tr>
      <tr>
         <td><p>Consequence</p>         </td>
         <td><p>Immediate shutdown of the communication utility.</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Review the command syntax, correct the error and then restart
the communication utility.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
   <tbody>
      <tr>
         <td><p>Error</p>         </td>
         <td><p><span id="CFTU09E"></span>CFTU09E: &amp;Cmd Failed
_ command size too large</p>         </td>
      </tr>
      <tr>
         <td><p>Explanation</p>         </td>
         <td><p>The length of the command name is greater than 8.</p>         </td>
      </tr>
      <tr>
         <td><p>Consequence</p>         </td>
         <td><p>Immediate shutdown of the communication utility.</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check the command syntax, correct the error and then restart
the communication utility.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
   <tbody>
      <tr>
         <td><p>Error</p>         </td>
         <td><p><span id="CFTU10E"></span>CFTU10E: &amp;Cmd Failed
_ unknown command</p>         </td>
      </tr>
      <tr>
         <td><p>Explanation</p>         </td>
         <td><p>The command is unknown.</p>         </td>
      </tr>
      <tr>
         <td><p>Consequence</p>         </td>
         <td><p>Immediate shutdown of the communication utility.</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check the <a href="../../../c_intro_userinterfaces/command_summary">command syntax</a> in the <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> Online documentation.
Correct the error and restart the communication utility.</p>
<p>Check the command syntax in the <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> Online documentation.
Correct the error and restart the communication utility.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
   <tbody>
      <tr>
         <td><p>Error</p>         </td>
         <td><p><span id="CFTU11E"></span>CFTU11E: &amp;Cmd Failed
_ keyword &amp;Keyw too large</p>         </td>
      </tr>
      <tr>
         <td><p>Explanation</p>         </td>
         <td><p>The length of the &amp;Keyw keyword is greater than 8.</p>         </td>
      </tr>
      <tr>
         <td><p>Consequence</p>         </td>
         <td><p>Immediate shutdown of the communication utility.</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check the description of this parameter in the Transfer
CFT <a href="../../../c_intro_userinterfaces/command_summary/parameter_intro">parameter index</a>, correct the error and then restart the communication
utility.</p>
<p>Check the description of this parameter in the Transfer
CFT parameter index, correct the error and then restart the communication
utility.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
   <tbody>
      <tr>
         <td><p>Error</p>         </td>
         <td><p><span id="CFTU12E"></span>CFTU12E: &amp;Cmd Failed
_ illegal separator for keyword &amp;Keyw</p>         </td>
      </tr>
      <tr>
         <td><p>Explanation</p>         </td>
         <td><p>A parameter separator in the &amp;Cmd command is invalid.</p>         </td>
      </tr>
      <tr>
         <td><p>Consequence</p>         </td>
         <td><p>Immediate shutdown of the communication utility.</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check the <a href="../../../c_intro_userinterfaces/command_summary">command syntax</a> being sure that the separator is a comma. Correct the error and then restart the communication utility.</p>
<p>Check the command syntax being sure that the separator is a comma. Correct the error and then restart the communication utility.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
   <tbody>
      <tr>
         <td><p>Error</p>         </td>
         <td><p><span id="CFTU13E"></span>CFTU13E: &amp;Cmd Failed_missing
quote</p>         </td>
      </tr>
      <tr>
         <td><p>Explanation</p>         </td>
         <td><p>A closing quote (') is missing in the value assigned to
a command parameter.</p>         </td>
      </tr>
      <tr>
         <td><p>Consequence</p>         </td>
         <td><p>Immediate shutdown of the communication utility.</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check the invalid parameter; correct the error and then
restart the communication utility.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
   <tbody>
      <tr>
         <td><p>Error</p>         </td>
         <td><p><span id="CFTU14E"></span>CFTU14E: &amp;Cmd Failed
_ too many keywords</p>         </td>
      </tr>
      <tr>
         <td><p>Explanation</p>         </td>
         <td><p>There are too many keywords for this command.</p>         </td>
      </tr>
      <tr>
         <td><p>Consequence</p>         </td>
         <td><p>Immediate shutdown of the communication utility.</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check the <a href="../../../c_intro_userinterfaces/command_summary">command syntax</a>. Correct the error and then restart
the communication utility.</p>
<p>Check the command syntax. Correct the error and then restart
the communication utility.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
   <tbody>
      <tr>
         <td><p>Error</p>         </td>
         <td><p><span id="CFTU15E"></span>CFTU15E: &amp;Cmd Failed
_ keyword &amp;Keyw unknown or duplicate</p>         </td>
      </tr>
      <tr>
         <td><p>Explanation</p>         </td>
         <td><p>The &amp;Keyw keyword is unknown or appears twice in the
command.</p>         </td>
      </tr>
      <tr>
         <td><p>Consequence</p>         </td>
         <td><p>Immediate shutdown of the communication utility.</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check the <a href="../../../c_intro_userinterfaces/command_summary">command syntax</a>. Correct the error and then restart
the communication utility.</p>
<p>Check the command syntax. Correct the error and then restart
the communication utility.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
   <tbody>
      <tr>
         <td><p>Error</p>         </td>
         <td><p><span id="CFTU16E"></span>CFTU16E: &amp;Cmd Failed
_ keyword &amp;Keyw missing</p>         </td>
      </tr>
      <tr>
         <td><p>Explanation</p>         </td>
         <td><p>The &amp;Keyw keyword, which is mandatory for the command,
is missing.</p>         </td>
      </tr>
      <tr>
         <td><p>Consequence</p>         </td>
         <td><p>Immediate shutdown of the communication utility.</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check the command syntax, correct the error and then restart
the communication utility.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
   <tbody>
      <tr>
         <td><p>Error</p>         </td>
         <td><p><span id="CFTU17E"></span>CFTU17E: &amp;Cmd Failed
_ keyword &amp;Keyw value out of bounds</p>         </td>
      </tr>
      <tr>
         <td><p>Explanation</p>         </td>
         <td><p>The &amp;Keyw keyword of the &amp;Cmd command is numeric
and its value has exceeded the authorized limits.</p>         </td>
      </tr>
      <tr>
         <td><p>Consequence</p>         </td>
         <td><p>Immediate shutdown of the communication utility.</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check the possible values for this parameter, correct the
error and then restart the communication utility.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
   <tbody>
      <tr>
         <td><p>Error</p>         </td>
         <td><p><span id="CFTU18E"></span>CFTU18E: &amp;Cmd Failed
_ invalid value for keyword &amp;Keyw</p>         </td>
      </tr>
      <tr>
         <td><p>Explanation</p>         </td>
         <td><p>The value of the &amp;Keyw keyword of the &amp;Cmd command
is not authorized (numeric value for an alphabetic parameter for example).</p>         </td>
      </tr>
      <tr>
         <td><p>Consequence</p>         </td>
         <td><p>Immediate shutdown of the communication utility.</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check the possible values for this <a href="../../../c_intro_userinterfaces/command_summary/parameter_intro">parameter</a>. Correct the
error and then restart the communication utility.</p>
<p>Check the possible values for this parameter. Correct the
error and then restart the communication utility.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
   <tbody>
      <tr>
         <td><p>Error</p>         </td>
         <td><p><span id="CFTU19E"></span>CFTU19E: CFTDEST Failed
_ keywords FNAME and &amp;str are mutually exclusive</p>         </td>
      </tr>
      <tr>
         <td><p>Explanation</p>         </td>
         <td><p>If &amp;str=PART</p>
<p>The components of a broadcast list can either be described
within the command (PART = parameter) or in an external file (FNAME =
parameter). These two parameters are mutually exclusive.</p>
<p>If &amp;str=IDF</p>
<p>The IDENTIFIERS authorized in the CFTAUTH command can either
be described within the command (IDF = parameter) or in an external file
(FNAME = parameter). These two parameters are mutually exclusive.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
   <tbody>
      <tr>
         <td><p>Error</p>         </td>
         <td><p><span id="CFTU20I"></span>CFTU20I: &amp;str</p>         </td>
      </tr>
      <tr>
         <td><p>Explanation</p>         </td>
         <td><p>CFTUTIL command interpreter information messages.</p>
<p>The &amp;str is self-explanatory and can be of several
types:</p>
<ul>
<li>Execution header: Information messages indicating the product,
release, copyright and execution start date and time</li>
<li>Execution report: Information messages indicating the number
of commands interpreted, the number of errors detected and the execution
end date and time</li>
<li>Dynamic modification of a <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> partner state: Part
= &amp;part : &amp;str1</li>
</ul>
<p>The ACT or INACT command has been executed correctly (&amp;str1
indicates the change of state for the &amp;part partner: initial state
-&gt; final state). There are four possible states for
a partner:</p>
<ul>
<li>ACTIVEBOTH: Partner
active in both modes (requester and server)</li>
<li>NOACTIVE:
Partner inactive in both modes</li>
<li>ACTIVEREQ:
Partner active in the requester mode</li>
<li>ACTIVESERV:
Partner active in the server mode</li>
</ul>         </td>
      </tr>
   </tbody>
</table>

 

<table>
   <tbody>
      <tr>
         <td><p>Error</p>         </td>
         <td><p><span id="CFTU24W"></span>CFTU24W : &amp;Cmd _
Warning (&amp;str)</p>         </td>
      </tr>
      <tr>
         <td><p>Explanation</p>         </td>
         <td><p>A CFTUTIL command was correctly interpreted but no information
was given; the &amp;str field specifies the reason.</p>
<p>Example: a CFTUTIL LISTCAT command on an empty Transfer
CFT catalog causes the following message to be displayed:</p>
<p><span id="CFTU24W1"></span>CFTU24W : LISTCAT Warning (no record
found). </p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
   <tbody>
      <tr>
         <td><p>Error</p>         </td>
         <td><p><span id="CFTU26E"></span>CFTU26E : &amp;Cmd _
Error (&amp;str)</p>         </td>
      </tr>
      <tr>
         <td><p>Explanation</p>         </td>
         <td><p>When executing the command, an error was detected. The
&amp;str field can be set to one of the following values. Note that the
following list is not exhaustive, as the &amp;str field is relatively self-explanatory:</p>
<ul>
<li>Parameter file opening error: Execution of the &amp;Cmd command
(LISTPARM for example) resulted in an error when opening the parameter
file.</li>
<li>Partners file opening error: Execution of the &amp;Cmd command
(LISTPART for example) resulted in an error when opening the partner file.</li>
<li>Catalog file opening error: Execution of the &amp;Cmd command
(LISTCAT for example) resulted in an error when opening the catalog file.</li>
<li>Media communication file opening error: Execution of the &amp;Cmd
command (LISTCOM for example) resulted in an error when opening the communication
file.</li>
<li>File creation error: An error was detected when creating and
formatting the <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> internal datafile (CFTUTIL CFTFILE TYPE=CAT/LOG/PARM/PART/
command).</li>
<li>File delete error: An error was detected when executing a request
to delete a <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> internal datafile (CFTUTIL CFTFILE TYPE= ,MODE=DELETE
command).</li>
<li>Output file creating error cs=&amp;scs: Execution of the &amp;Cmd
command (COPYFILE for example) resulted in an error when creating the
output file.</li>
<li>Input file opening error cs=&amp;scs: Execution of the &amp;Cmd
command (COPYFILE for example) resulted in an error when opening the input
file.</li>
<li>&amp;id: Partner record already exists: Command execution, e.g. writing information to the <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> partner file, resulted in
an attempt to add a record that already existed in the file (the &amp;Cmd
command requested is designated by &amp;Id).</li>
<li>&amp;id: Partner record &amp;str error (&amp;str=writing/reading/selecting):
Command execution resulted in a write/read/article selection error
in the file (the &amp;Cmd command requested is designated by &amp;Id).</li>
<li>&amp;id: Parameter record already exists: Command
execution, writing information to the <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> parameter file, resulted in
an attempt to add a record that already existed in the file (&amp;Id being
the command identifier).</li>
<li>&amp;id: Invalid value for NRPART paramete:r Executing the CFTPART
command, writing information to the <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> partner file, resulted
in an attempt to add a record that already existed in the file (&amp;Id
being the CFTPART command identifier). In this case, the NRPART parameter
is already assigned to an existing CFTPART command.</li>
<li>&amp;id: Non bijective table: The conversion table specified
in the file referenced by the CFTXLATE DIRECT=BOTH command is not bijective
(&amp;Id being the command identifier). Check that the conversion table
specified is bijective or create one command for each transfer direction
(DIRECT=SEND or DIRECT=RECV).</li>
<li>No partner found: A partner activation or deactivation command
(ACT or INACT) resulted in an error. The identifier indicated (ACT ID=&amp;Part)
does not correspond to an existing partner identifier (CFTPART ID=&amp;Part).</li>
<li>Media communication is full: A transfer command (SEND or RECV)
could not be written to the <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> communication file. The maximum
number of requests in the communication file that have not yet been processed
by the <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> has been reached (<a href="../../../c_intro_userinterfaces/command_summary/parameter_intro/recnb">RECNB</a> parameter in the CFTFILE
TYPE=COM command).</li>
<li><p>Incompatible compression parameters: Execution of the COPYFILE
command resulted in an error when checking the attributes (record length
or format, compression code or state).</p>
<p><a href="../../../admin_intro/admin_commands_intro/copyfile_command" class="MCXref xref">COPYFILE
- Copy files off-line</a></p></li>
<li><p>Compression error: Executing the COPYFILE command resulted
in an error during the compression process.</p>
<p><a href="../../../admin_intro/admin_commands_intro/copyfile_command" class="MCXref xref">COPYFILE
- Copy files off-line</a></p></li>
<li><p>Decompression error: Executing the <a href="../../../admin_intro/admin_commands_intro/copyfile_command">COPYFILE</a> command resulted
in an error during the decompression process. Executing the COPYFILE command resulted
in an error during the decompression process.</p>
<p><a href="../../../admin_intro/admin_commands_intro/copyfile_command" class="MCXref xref">COPYFILE
- Copy files off-line</a></p></li>
<li>&amp;id: command not authorized: The command specified by the
user is not authorized by the <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> security system (&amp;id being
the command identifier)</li>
<li>Habilitation opening error: An error was detected when initializing
the <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> security system; a file required by the system could
not be opened correctly. Check that the initialization file exists and
is valid (contains the operating rules and indirections pointing to the
object and action dictionaries) and ensure that the security system dictionary
files exist.</li>
<li>Create channel failed: An error was detected when creating the <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> synchronous communication media. Check that you have enough memory.</li>
<li>Open channel failed: An error was detected when opening the <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> synchronous communication media. Check that the synchronous communication process is launched.</li>
<li>Channel read error: An error was detected when reading the <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> synchronous communication media. Check that the synchronous communication process is launched.</li>
<li>Channel write error: An error was detected when writing in the <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> synchronous communication media. Check that the synchronous communication process is launched.</li>
<li>Close channel failed: An error was detected when closing the <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> synchronous communication media. Check that the communication media is not already closed.</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Consequence</p>         </td>
         <td><p>The command is ignored.</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check the parameter settings, analyze the &amp;scs code
if it is set and, if necessary, inform Product Support.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
   <tbody>
      <tr>
         <td><p>Error</p>         </td>
         <td><p><span id="CFTU30E"></span>CFTU30E : &amp;Cmd Failed
_ Unable to create file &amp;Fname</p>         </td>
      </tr>
      <tr>
         <td><p>Explanation</p>         </td>
         <td><p>Execution of the &amp;Cmd command resulted in an error
during the file create process.</p>
<p>Example: redirection of CFTUTIL information messages to
an invalid report file (CONFIG TYPE=OUTPUT,FNAME=&amp;Fname command).</p>         </td>
      </tr>
      <tr>
         <td><p>Consequence</p>         </td>
         <td><p>The command is ignored.</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check the validity of the file name and, if necessary,
inform Product Support.</p>         </td>
      </tr>
   </tbody>
</table>
