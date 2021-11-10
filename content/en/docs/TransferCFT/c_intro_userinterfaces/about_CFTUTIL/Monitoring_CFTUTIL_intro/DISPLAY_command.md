{
    "title": "DISPLAY - Catalog output display model",
    "linkTitle": "DISPLAY - Catalog output display model",
    "weight": "290"
}The <span id="DISPLAY"></span>DISPLAY
command is an enhanced version of the LISTCAT command and displays
the catalog transfer field values. The output can be organized
by columns when the mode is column,
or by lines when the mode is line.

Display uses an external
XML file that lists and describes the format for customized models. This means the Display command can call an XML document as a fmodel parameter.

In column mode, an adjustable title bar is displayed at the top of
the catalog content to improve readability. In line mode, every line is presented horizontally
in the form FIELD\_NAME = FIELD\_VALUE. Several customizing options are
available in both modes to control the display format for field values such
as prefix, suffix, length, and alignment. The line output can also be customized by prefix and suffix.

DISPLAY uses the same parameters as the [LISTCAT](../listcat_command) command and, with the exception of the CONTENT parameter, all common parameters use the
same semantics. However,
there are certain parameters that are applicable only for the DISPLAY
command, as described later in this topic.

The use of the DISPLAY command overrides all other global model
options. Parameters that are affected by this command are MODE, NA and
EMPTY.

See also, [LISTCAT/DISPLAY - Statistical variables](../listcat_filter_variables).

## About XML

The XML formatting must comply with certain conventions:

-   The file must begin with the header: &lt;?xml content='ascii'?>
-   Every tag &lt;tag> must be closed &lt;/tag>
-   Using a tag in the format &lt;tag/> is accepted but not recommended and should be empty

For more information, refer to an XML standards reference such as <http://www.w3.org/TR/REC-xml/>. Additionally, you can reference the sample template delivered with your Transfer CFT, which is located in the OS-specific distribution package:

-   UNIX, Windows: DSPCNF.XML in runtime/conf
-   z/OS (MVS): distlib.XMLLIB(DSPCNF) and instance.XMLLIB(DSPCNF)
-   IBM i (OS/400): CFTPGM1/DSPCNF

Details

Fmodel structure



    <?xml content='ascii'?>
    <CFTDisplayFilter>
    <Fields>
    <Field>
    <Field>
    [...]
    </Fields>
    </CFTDisplayFilter>

Attributes for the &lt;CFTDisplayFilter>

<table>
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Parameter         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>id='string'         </td>
         <td>Model ID, call within the DISPLAY command with the content parameter         </td>
      </tr>
      <tr>
         <td>mode = 'column | line'         </td>
         <td>Output orientation (line or column)         </td>
      </tr>
      <tr>
         <td>title_size = '-1 | NUM'         </td>
         <td>Title size, only in column mode (undefined or number)         </td>
      </tr>
      <tr>
         <td>title_align = 'left | center | right'         </td>
         <td>Title alignment (column mode only)         </td>
      </tr>
      <tr>
         <td>line_prefix = '&lt;LF&gt;|STR'         </td>
         <td>Prefix in line mode (empty or string)         </td>
      </tr>
      <tr>
         <td>line_suffix = '| STR'         </td>
         <td>Suffix in line mode (empty or string)         </td>
      </tr>
      <tr>
         <td>default_prefix = '| STR'         </td>
         <td>Default prefix (empty or string)         </td>
      </tr>
      <tr>
         <td>default_suffix = ' | STR'         </td>
         <td>Default suffix ('' in column mode and 'Line Feed' in line mode) (empty or string)         </td>
      </tr>
      <tr>
         <td>default_empty = '| STR'         </td>
         <td>Default String if empty (empty or string)         </td>
      </tr>
      <tr>
         <td>default_na = '| STR'         </td>
         <td>Default String if not applicable (empty or string)         </td>
      </tr>
   </tbody>
</table>

Attributes for the &lt;Fields> and &lt;Field>

The &lt;Fields> tag has no attributes, but may contain one or several &lt;Field> tags.

Each &lt;Field> tag has the following attributes:

<table>
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Parameter         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>id         </td>
         <td>This parameter is mandatory and should be the same as the listcat id parameter         </td>
      </tr>
      <tr>
         <td>title         </td>
         <td>Title of the column / line.         </td>
      </tr>
      <tr>
         <td>maxlength : -1 | NUM         </td>
         <td>Max length: -1 means no maxlength         </td>
      </tr>
      <tr>
         <td>minlength : -1 | NUM         </td>
         <td>Min length: -1 means no minlength         </td>
      </tr>
      <tr>
         <td>prefix =' | STR'         </td>
         <td>Prefix (empty or string)         </td>
      </tr>
      <tr>
         <td>suffix =' | STR'         </td>
         <td>Suffix (empty or string)         </td>
      </tr>
      <tr>
         <td>align = left | center | right         </td>
         <td>Field alignment         </td>
      </tr>
      <tr>
         <td>na = '| STR' : default         </td>
         <td>String if empty (empty or string)         </td>
      </tr>
      <tr>
         <td>empty = '| STR' : default         </td>
         <td>String if not applicable (empty or string)         </td>
      </tr>
   </tbody>
</table>

## Parameter descriptions

Use this command to displays the catalog
transfer field values organized either by columns (mode=column) or
by lines (mode=line).

Command syntax: [DISPLAY](../../../command_summary)

<table>
         
         
         
   
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1"><p>Parameter</p>         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1"><p>Description</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>CONTENT         </td>
         <td>Filter to use on the messages written in the active LOG file.         </td>
      </tr>
      <tr>
         <td>DATETIMEMAX         </td>
         <td>Use to display catalog transfers that happened on or before this end date and time according to the transfer record creation (DATEK, TIMEK).         </td>
      </tr>
      <tr>
         <td>DATETIMEMIN         </td>
         <td>Use to display catalog transfers that happened on or after this start date and time according to the transfer record creation (DATED, TIMED).         </td>
      </tr>
      <tr>
         <td>DIAGI         </td>
         <td><p>Define the diagi catalog transfer field display:</p>
<ul>
<li>DIAGI=0: select transfers that have a DIAGI=0</li>
<li>DIAGI=ERROR: select transfers that have a DIAGI other than 0</li>
<li>DIAGI=* : select all transfers (default value)</li>
</ul>         </td>
      </tr>
      <tr>
         <td>DIRECT         </td>
         <td>Transfer direction of the requests.         </td>
      </tr>
      <tr>
         <td><p>EMPTY</p>         </td>
         <td><p>Use this parameter to replace the default output of <span style="font-weight: bold;">Empty</span> values, usually empty string values.</p>
<p>The default string <span style="font-weight: bold;">ANY</span>
means that EMPTY is specified in the model. The default EMPTY used is '-' if it is not defined in the model.</p>         </td>
      </tr>
      <tr>
         <td>FILE         </td>
         <td>Enter file name         </td>
      </tr>
      <tr>
         <td><p>FMODEL</p>         </td>
         <td><p>Complete name or logical name of the XML model file.</p>
<p>This parameter default value is fixed. </p>         </td>
      </tr>
      <tr>
         <td>FOUT         </td>
         <td><span class="bold_in_para">PeSIT</span>
<p>You can extract Transfer CFT messages from the Catalog file, and forward these messages to a specified file using the fout parameter.</p>
<p>The message length for PeSIT ANY profile, when forwarding a message from one CFT to another, has increased from 512 to 4096 bytes. The S/RRUSIZE must be greater than the maximum message length and message information combined (for example, 4127).</p>
<p>The fout parameter enables you to redirect output to a specified file.</p>         </td>
      </tr>
      <tr>
         <td><p>HELP</p>         </td>
         <td><p>Displays help information:</p>
<ul>
<li>FIELDS: Output all the fields name available
for display model creation</li>
<li>MODELS: Output all the models available
in the current model file</li>
</ul>         </td>
      </tr>
      <tr>
         <td>IDA         </td>
         <td>Local transfer identifier assigned by the user or user application.
This identifier may be a search criterion for the catalog entry asso         </td>
      </tr>
      <tr>
         <td>IDF         </td>
         <td>File type identifier.         </td>
      </tr>
      <tr>
         <td>IDT         </td>
         <td>Transfer identifier. Identifies a transfer for a given partner and transfer direction.         </td>
      </tr>
      <tr>
         <td>IDTU         </td>
         <td>Catalog identifier. It is a unique, local reference to a transfer.         </td>
      </tr>
      <tr>
         <td><p>MODE</p>         </td>
         <td><p>This parameter is used to force a model's output mode.</p>
<p>Two modes are available:</p>
<ul>
<li>COLUMN: This mode outputs the catalog fields in
columns with a title bar (see <a href="../brief_catalog_listing">LISTCAT
CONTENT=BRIEF</a>).</li>
<li>LINE: This mode outputs the catalog fields with
one field per line prefixed by its title.</li>
</ul>
<p>The default value ANY means that the mode is specified
in the model. The default mode COLUMN is used if not defined in the
model either.</p>         </td>
      </tr>
      <tr>
         <td><p>NA</p>         </td>
         <td><p>Use this parameter to replace the default output of "Non
Applicable" values.  </p>
<p>A Non Applicable value is a value that does not mean anything
for the concerned transfer. For instance, the message content field doesn't
mean anything for a file transfer, so the NA string will be displayed
instead.</p>
<p>The default string 'ANY' means that the NA is specified
in the model. The default NA used will be '#'  if
not defined in the model either.</p>         </td>
      </tr>
      <tr>
         <td>NPART         </td>
         <td>Network name of the transfer partner.         </td>
      </tr>
      <tr>
         <td>PART         </td>
         <td>The local identifier for the site where the monitor runs.         </td>
      </tr>
      <tr>
         <td>PHASE         </td>
         <td>Refers to the highest level in the transfer flow cycle, for example X (done).         </td>
      </tr>
      <tr>
         <td>PHASESTEP         </td>
         <td>The processing phase step.         </td>
      </tr>
      <tr>
         <td>PIDTU         </td>
         <td>The parent idtu is the idtu of the generic transfer. This means that for a group of files, file collection, or for broadcasting, the child transfers are now linked to the parent via the PIDTU.         </td>
      </tr>
      <tr>
         <td><p>RUSER</p>         </td>
         <td><p>Displays value as defined in the CONTENT parameter.</p>         </td>
      </tr>
      <tr>
         <td>SORTBY         </td>
         <td><p>Use this parameter to display information in an alphabetical/alphanumberic order.</p>
<p>For example, to sort by partner name and identifier, enter:</p>
<p><span class="code">CFTUTIL DISPLAY SORTBY=(PART,IDF)</span></p>
<p>Additionally, you can add a prefix to define the criteria direction. Use <span class="code">+</span> to increase (default) or <span class="code">-</span> to decrease. For example:</p>
<p>CFTUTIL DISPLAY SORTBY=(-IDTU)</p>         </td>
      </tr>
      <tr>
         <td>STATE         </td>
         <td>Defines the transfer request state.         </td>
      </tr>
      <tr>
         <td><p>SUSER</p>         </td>
         <td><p>Displays value as defined in the CONTENT parameter.</p>         </td>
      </tr>
      <tr>
         <td>TYPE         </td>
         <td>Defines the concerned type (object, medium, etc.).         </td>
      </tr>
   </tbody>
</table>

## Examples

Example 1

Displays all the fields described in <span style="font-weight: bold;">listcat</span>
model concerning all transfers.


    DISPLAY     CONTENT 
     = listcat

Example 2

Displays all the fields described in 'listcat' model concerning all
transfers. The COLUMN mode is overridden by the LINE. Moreover, every
invalid field value is replaced by the string '####', and every empty
field value is replaced by the string '&lt;empty>'.



    DISPLAY    MODE 
     = LINE,
    NA 
     = '####',
    EMPTY 
     = '<empty>'

Example 3

This shows an example of a display model file.



    <?xml content='ascii'?>
    <!-- LISTCAT Model : classical CFTUTIL LISTCAT with long 
     IDs -->
    <CFTDisplayFilter id           = 
     'listcat' title_align  = 
     'right'> 
    <Fields> 
    <Field id='PART' title='Partner' /> 
    <Field id='DIRECT' title='Direction' maxlength='1' suffix='' 
     /> 
    <Field id='TYPE' title='Type' maxlength='1' suffix='' 
     /> 
    <Field id='STATE' title='State' maxlength='1' suffix='' 
     />     
    <Field id='ACK' title='Ack' maxlength='1'/> 
    <Field id='IDF' title='IDF' minlength='4' /> 
    <Field id='IDT' title='IDT' /> 
    <Field id='IDTU' title='IDTU' /> 
    <Field id='BLKNUM' title='BLK' /> 
    <Field id='NREC' title='Transmited' align='right' /> 
     <Field id='FREC' title='Total' align='right' />        <Field 
     id='MSG'         title='Msg' 
         maxlength='32' 
     align='center'/> 
    <Field id='DIAGI'     title='Diagi' 
     /> 
    <Field id='DIAGP'     title='Diagp' 
     /> 
    <Field id='REQUSER' title='User' /> 
    <Field id='REQGROUP' title='Group' /> 
    <Field id='IDA'       title='IDA' 
     /> </Fields></CFTDisplayFilter>

The output for this command would resemble the following:



    Partner    DTSA 
     IDF IDT IDTU  BLK 
     Transmited Total  Msg 
      Diagi Diagp 
      User Group 
     IDA
    NEWYORK SFT- TEST1  D1217250 
     00000001 29  # 
       0 
      CP 29% 
     user1 group1 -
    PARIS    RFT- 
     TEST1  D1217250 
     00000002 30  2 
       2 
        # 
       0 
         CP 
     29% -     - 
          -
    PARIS    SFT- 
     TEST2  D1217251 
     00000003 31  2 
       2 
        # 
       0 
        CP 
     29% user1 group1 -
    NEWYORK RFT- TEST2  D1217251 
     00000004 32  2 
       2 
        # 
       0 
         CP 
     29% -   - 
      -
    PARIS   SMT- 
     MESSAGETEST1 D1217261 00000005 33 # # test message 1 0 - user1 group1 
     -
    NEWYORK RMT- MESSAGETEST1 D1217261 00000006 34 # # test 
     message 1 0 -   - 
      -      -
    NEWYORK SMT- MESSAGETEST2 D1217263 00000007 35 # # test 
     message 2 0 - user1 group1 -
    PARIS    RMT- 
     MESSAGETEST2 D1217263 00000008 36 # # test message 2 0 -  - 
      -     -
