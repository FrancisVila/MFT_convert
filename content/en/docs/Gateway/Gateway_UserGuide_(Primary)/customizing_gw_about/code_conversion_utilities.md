{
    "title": "Code conversion and file formatting",
    "linkTitle": "Code conversion and file formatting",
    "weight": "210"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Customizing Gateway Processes

[Overview](#overview)

[Defining code conversion and formatting parameters](#applying_formatting)

[Code conversion](#code_conversion)

[Formatting and padding](#formatting)

[Examples](#examples)

<span id="overview"></span>

## Overview

This topic describes how to use code conversion and file formatting utilities in Gateway. These features enable you to change the data code of file contents or the record size in the file.

<span style="font-weight: bold;">Code conversion</span> involves translating the character code. Use code conversion when you transfer a file between two platforms that support different character codes (for example, UNIX/ASCII to MVS/EBCDIC).

<span style="font-weight: bold;">Formatting</span> involves changing file record:

-   Format (from fixed to variable or vice versa)
-   Size (adding or removing padding characters where necessary)

You define code conversion and formatting requirements when you create an Application or a Transfer Request. Gateway then converts and formats the file dynamically during the transfer.

This topic also describes the two code conversion utilities supplied with Gateway:

-   <span class="code" style="font-weight: bold;">[trncc](#TRNCC)</span> – to compile a text file table
-   <span class="code" style="font-weight: bold;">[trnxcode](#TRNXCODE)</span> – enables you to convert the contents of a file manually

<span id="applying_formatting"></span>

## Defining code conversion and formatting parameters

You define code conversion and formatting parameters in the Application object and in Transfer Requests that do not use an Application.

Gateway dynamically requests code conversion and/or formatting when the following local file attributes are different from the corresponding transfer attributes:

-   Record format
-   Record length
-   Data encryption
-   Padding character

The functions operate differently depending on whether you are sending or receiving a file.

### Sending a file

When you send a file, the *local file attributes* are the file attributes defined by the file management system of the sending platform. Define these attributes in the **Local attributes** section of a Transfer Request or Application.

The *transfer attributes* and the *padding character attributes* are the attributes to apply to the file contents during the transfer. Define these attributes in the **Transfer attributes** section of a Transfer Request or Application.

If you do not specify the transfer attributes, they default to the local file attributes and there is no code conversion or formatting.

### Receiving a file

When you receive a file, the *transfer attributes* are the attributes of the received file. On transfers using PeSIT, the transfer attributes are completed by the protocol. For all other protocols you must define the attributes in the Application object.

You apply the *local file attributes* and the *padding character attributes* to the file on the receiving platform. Define these attributes in the incoming Transfer Request or in the Application object.

If you do not specify the local file attributes, they default to the transfer attributes and there is no code conversion or formatting.

<span id="code_conversion"></span>

## Code conversion

A code is the numeric representation of a character set (alphabet + other symbols). All computers use a given code to represent the characters displayed (ASCII, EBCDIC...). When you transfer a text file between two machines, it is recommended that the character set of the received file corresponds to the code of the receiving machine. If the codes used on the sending and receiving machines are different, code conversion is required.

To convert codes, Gateway uses conversion tables. By default, Gateway supplies the following tables:

-   ascii.ebcdic table (to convert from ASCII to EBCDIC)
-   ebcdic.ascii table (to convert from EBCDIC to ASCII)

Additionally, you can define up to 12 code conversion tables of your own.

The conversion tables are described in the <span class="code">table.trn</span> text file. You can add or change the data contained in this file using a text editor.

Before using conversion tables, use the <span class="code">trncc</span> utility to compile the <span class="code">table.trn</span> text file.

### How conversion tables work

A conversion table maps the hexadecimal representation of characters in the input code to an output code. For example, the ascii.ebcdic table maps <span style="font-style: italic;">41</span> to <span style="font-style: italic;">C1</span> (respectively, the ASCII and EBCDIC codes for the alphabetic character <span style="font-style: italic;">A</span>).

#### Table organization

A table is basically a one-dimensional array. If the value of the character in the input code is <span style="font-style: italic;">n</span>, its value in the output code is in position <span style="font-style: italic;">n</span> in the table. For example the EBCDIC code for <span style="font-style: italic;">A</span> is in position <span style="font-style: italic;">65</span> (41 in hexadecimal) of the ascii.ebcdic table.

### Syntax of code conversion tables

For each conversion table, the <span class="code">table.trn</span> text file contains blocks of information in the following format:


    table  <codein.codeout>
    # comments
    default = 3F,N       # 3F is the ASCII code of the character ‘?’
    fill = 40,N          # 40 is the ASCII code of the character ‘@’
    error = 21,N         # 21 is the ASCII code of the character ‘!’
    data
    [code table]
    end

Where:

-   <span class="code">codein</span> is the input code name

-   <span class="code">codeout</span> is the output code name

-   <span class="code">table</span>, <span class="code">data</span> and <span class="code">end</span> are mandatory keywords

-   <span class="code">default</span>, <span class="code">fill</span> and <span class="code">error</span> are optional keywords

-   The only acceptable code names are:
    -   ascii
    -   ascii1
    -   ascii2
    -   ascii3
    -   ascii4
    -   ascii5,
    -   ebcdic
    -   ebcdic1
    -   ebcdic2
    -   ebcdic3
    -   ebcdic4
    -   ebcdic5
    -   oempc
    -   iso

-   Characters following the hash symbol ( <span style="font-weight: bold;">#</span> ) in a line, contain comment information

-   <span class="code">fill</span>: The value defined in <span class="code">fill</span> represents the code attributed to all non-specified characters. In other words any characters encountered during the transcoding operation that are not defined in the table used.

-   <span class="code">default</span>: The value defined in <span class="code">default</span> represents the code attributed to all characters for which the table assigns the value **,U**.

-   <span class="code">error</span>: The value defined in <span class="code">error</span> corresponds to the code attributed to all characters for which the table assigns the value **,R**.

-   The code table contains 32 lines of eight codes. The beginning of each line gives the offset of the first code in the line.

        <offset> : <line of eight codes>
           00   :  xx  xx  xx  xx  xx  xx  xx  xx        # 1st line of codes
           08   :  xx  xx  xx  xx  xx  xx  xx  xx
           .
           .
           .
           F0   :  xx  xx  xx  xx  xx  xx  xx  xx
           F8   :  xx  xx  xx  xx  xx  xx  xx  xx        # 32nd line
         

In addition to the input codes, the tables can contain:

-   <span class="code" style="font-weight: bold;">,T</span> (Transparent): The character code is not modified between the input and output character sets.
-   <span class="code" style="font-weight: bold;">,U</span> (Undefined): The character code has no equivalent in the input character set. The code attributed corresponds to the value defined in <span class="code">default</span>.
-   <span class="code" style="font-weight: bold;">,N</span> (Normal): The character code corresponds to the value of the character in the input character set. The transcoding is performed in any case, with or without this attribute.
-   <span class="code" style="font-weight: bold;">,R</span> (Error): The character code attributed corresponds to the value defined in <span class="code">error</span>.

#### Example of table using these codes


    table EBCDIC.ASCII1
    # conversion table : EBCDIC --> ASCII
    # ------------------------------------
    default = 3F,N                                             # Gaps are replaced by the character ? (3F in ASCII)
    data
    00   :   ,T    ,T    ,T    ,T    ,U    09,N  ,U    7F,N
    08   :   ,U    ,U    ,U    ,T    ,T    ,T    ,T    ,T
    10   :   ,T    ,T    ,T    ,U    ,U    ,U    08,N  ,U
    18   :   ,T    ,T    ,U    ,U    ,U    1D,N  ,U    ,T
    20   :   ,U    ,U    1C,N  ,U    ,U    0A,N  17,N  1B,N
    28   :   ,U    ,U    ,U    ,U    60,N  05,N  06,N  07,N    # `
    ...
    end

### Conversion table examples

The following examples provide a description of the conversion table from ASCII to EBCDIC and from EBCDIC to ASCII in the <span class="code"> table.trn</span> file (the basic ASCII code set).

You can customize the description to specify codes for undefined characters.

#### ASCII to EBCDIC conversion table


    table ASCII.EBCDIC
    # conversion table : ASCII --> EBCDIC
    # ------------------------------------
    # Attention : 0x13(ASCII DC3) -> 0x15 (EBCDIC NL)
    data
    00 : 00   01   02   03   37   2D   2E   2F
    08 : 16   05   25   0B   0C   0D   0E   0F
    10 : 10   11   12   15   3C   3D   32   26
    18 : 18   19   3F   27   22   1D   35   1F
    20 : 40   5A   7F   7B   5B   6C   50   7D      # ! " # $ % & '
    28 : 4D   5D   5C   4E   6B   60   4B   61      # ( ) * + , - . /
    30 : F0   F1   F2   F3   F4   F5   F6   F7      # 0 1 2 3 4 5 6 7
    38 : F8   F9   7A   5E   4C   7E   6E   6F      # 8 9 : ; < = > ?
    40 : 7C   C1   C2   C3   C4   C5   C6   C7      # @ A B C D E F G
    48 : C8   C9   D1   D2   D3   D4   D5   D6      # H I J K L M N O
    50 : D7   D8   D9   E2   E3   E4   E5   E6      # P Q R S T U V W
    58 : E7   E8   E9   AD   E0   BD   5F   6D      # X Y Z [ \ ]   _
    60 : 2C   81   82   83   84   85   86   87      # ` a b c d e f g
    68 : 88   89   91   92   93   94   95   96      # h i j k l m n o
    70 : 97   98   99   A2   A3   A4   A5   A6      # p q r s t u v w
    78 : A7   A8   A9   C0   6A   D0   A1   07      # x y z { | } ~
    80 : 6F   6F   6F   6F   6F   6F   6F   6F
    88 : 6F   6F   6F   6F   6F   6F   6F   6F
    90 : 6F   6F   6F   6F   6F   6F   6F   6F
    98 : 6F   6F   6F   6F   6F   6F   6F   6F
    A0 : 6F   6F   6F   6F   6F   6F   6F   6F
    A8 : 6F   6F   6F   6F   6F   6F   6F   6F
    B0 : 6F   6F   6F   6F   6F   6F   6F   6F
    B8 : 6F   6F   6F   6F   6F   6F   6F   6F
    C0 : 6F   6F   6F   6F   6F   6F   6F   6F
    C8 : 6F   6F   6F   6F   6F   6F   6F   6F
    D0 : 6F   6F   6F   6F   6F   6F   6F   6F
    D8 : 6F   6F   6F   6F   6F   6F   6F   6F
    E0 : 6F   6F   6F   6F   6F   6F   6F   6F
    E8 : 6F   6F   6F   6F   6F   6F   6F   6F
    F0 : 6F   6F   6F   6F   6F   6F   6F   6F
    F8 : 6F   6F   6F   6F   6F   6F   6F   6F
    end

In the ASCII--->EBCDIC table above:

-   ASCII hexadecimal character 20 is converted into hexadecimal 40 in EBCDIC
-   ASCII hexadecimal character 21 is converted into hexadecimal 5A in EBCDIC

#### EBCDIC to ASCII conversion table


    table EBCDIC.ASCII
    # conversion table : EBCDIC --> ASCII
    # ------------------------------------
    data
    00 :   00   01   02   03   00   09   00   7F
    08 :   00   00   0A   0B   0C   0D   0E   0F
    10 :   10   11   12   00   00   00   08   00
    18 :   18   19   00   00   00   1D   00   1F
    20 :   00   00   1C   00   00   0A   17   1B
    28 :   00   00   00   00   60   05   06   07      # `
    30 :   00   00   16   00   00   1E   00   04
    38 :   00   00   00   00   14   15   00   1A
    40 :   20   00   00   00   00   00   00   00
    48 :   00   00   00   2E   3C   28   2B   00      #      . < ( +
    50 :   26   00   00   00   00   00   00   00      # &
    58 :   00   00   21   24   2A   29   3B   5E      #    ! $ * ) ;
    60 :   2D   2F   00   00   00   00   00   00      # - /
    68 :   00   00   7C   2C   25   5F   3E   3F      #    | ,N% _ > ?
    70 :   00   00   00   00   00   00   00   00
    78 :   00   00   3A   23   40   27   3D   22      #    : # @ ' = "
    80 :   00   61   62   63   64   65   66   67      #  a b c d e f g
    88 :   68   69   00   00   00   00   00   00      # h i
    90 :   00   6A   6B   6C   6D   6E   6F   70      #  j k l m n o p
    98 :   71   72   00   00   00   00   00   00      # q r
    A0 :   00   7E   73   74   75   76   77   78      #  ~ s t u v w x
    A8 :   79   7A   00   00   00   5B   00   00      # y z    [
    B0 :   00   00   00   00   00   00   00   00
    B8 :   00   00   00   00   00   5D   00   00      #    ]
    C0 :   7B   41   42   43   44   45   46   47      # { A B C D E F G
    C8 :   48   49   00   00   00   00   00   00      # H I
    D0 :   7D   4A   4B   4C   4D   4E   4F   50      # } J K L M N O P
    D8 :   51   52   00   00   00   00   00   00      # Q R
    E0 :   5C   00   53   54    55  56   57   58      # \   S T U V W X
    E8 :   59   5A   00   00   00   00   00   00      # Y Z
    F0 :   30   31   32   33   34   35   36   37      # 0 1 2 3 4 5 6 7
    F8 :   38   39   00   00   00   00   00   00      # 8 9
    end

### How Gateway applies code conversion tables

When you start a Transfer, Gateway detects whether the code of the local file attributes is the same as the code of the transfer attributes in the Application or in the Transfer Request. If the codes are different, Gateway initiates conversion based on the table specified in the Application.

#### Example

The Application includes the following parameters:

Local file attributes

-   Data encoding: ASCII

Transfer attributes

-   Data encoding: EBCDIC

When you send a file using this Application, Gateway converts it from ASCII to EBCDIC using the ascii.ebcdic table.

When a file is received using this Application, Gateway converts it from EBCDIC to ASCII using the ebcdic.ascii table.

<span id="TRNCC"></span>

### Compiling conversion tables: TRNCC

<table>
         
         
         
   
   <tbody>
      <tr>
         <td>Syntax         </td>
         <td><p><strong>trncc table.trn</strong></p>         </td>
      </tr>
      <tr>
         <td>Description         </td>
         <td><p>Use the <span class="code">trncc</span> utility to compile a text file table, in order to obtain binary tables that the code conversion module can use.</p>
<p><span class="code">trncc</span> creates one compiled table per text conversion table. Each compiled table is named:</p>
<p>TRN&lt;code_in&gt;&lt;code_out&gt;</p>
<p>Where: <span class="code"><br />
&lt;code_in&gt;</span> and <span class="code">&lt;code_out&gt;</span> are hexadecimal values of the initial and resulting data codes (for example, TRN0102).</p>
<p><span class="code">table.trn</span> can contain several conversion tables. The compiled tables are created in the sub-directory defined by an environment parameter (<span class="code">$p_database</span> for UNIX-like platforms).</p>         </td>
      </tr>
      <tr>
         <td>Return value         </td>
         <td><ul>
<li>0 = Compilation completed successfully</li>
<li>Any other return value = Error</li>
</ul>         </td>
      </tr>
      <tr>
         <td>Diagnostic         </td>
         <td><ul>
<li><span style="font-style: italic;">file open fail</span>: File opening failed</li>
<li><span style="font-style: italic;">compiler fail</span>: File compilation failed</li>
<li><span style="font-style: italic;">table write fail</span>: Cannot save the compiled table</li>
<li><span style="font-style: italic;">bad name</span>: Incorrect name</li>
<li><span style="font-style: italic;">table not found</span>: Table not found</li>
<li><span style="font-style: italic;">read input error</span>: Buffer read error</li>
<li><span style="font-style: italic;">write output error</span>: Buffer write error</li>
</ul>         </td>
      </tr>
   </tbody>
</table>

<span id="TRNXCODE"></span>

### Converting files: TRNXCODE

<table>
         
         
         
   
   <tbody>
      <tr>
         <td>Syntax         </td>
         <td><p><strong>trnxcode  &lt;codein.codeout&gt;  &lt;infile&gt;  &lt;outfile&gt;</strong></p>         </td>
      </tr>
      <tr>
         <td>Description         </td>
         <td><p>This utility is used to convert a file before or after a transfer.</p>         </td>
      </tr>
      <tr>
         <td>Parameters         </td>
         <td><p><span class="code">&lt;codein.codeout&gt;</span> indicates the conversion table to use (see example below). This conversion table was compiled using the <span class="code">trncc</span> utility.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">&lt;infile&gt;</span> indicates the file to be converted</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">&lt;outfile&gt;</span> is the file resulting from the conversion. The output file is created with the converted content of the input file</p>         </td>
      </tr>
      <tr>
         <td>Return value         </td>
         <td><ul>
<li>0 = Conversion completed successfully</li>
<li>Any other return value = Error</li>
</ul>         </td>
      </tr>
      <tr>
         <td>Diagnostic         </td>
         <td><ul>
<li><span style="font-style: italic;">file open fail</span>: File opening failed</li>
<li><span style="font-style: italic;">compiler fail</span>: File compilation failed</li>
<li><span style="font-style: italic;">usage trntrns...</span>: Cannot save the compiled table</li>
<li><span style="font-style: italic;">bad name</span>: Incorrect name</li>
<li><span style="font-style: italic;">table not found</span>: Table not found</li>
<li><span style="font-style: italic;">read input error</span>: Buffer read error</li>
<li><span style="font-style: italic;">write output error</span>: Buffer write error</li>
</ul>         </td>
      </tr>
      <tr>
         <td>Example         </td>
         <td><p>The following command converts an ASCII file (named inascii) to an EBCDIC file (named outebcdic):</p>
<p><strong>trnxcode ascii.ebcdic  inascii  outebcdic</strong></p>         </td>
      </tr>
   </tbody>
</table>

<span id="formatting"></span>

## Formatting and padding

### About formatting

The purpose of <span style="font-weight: bold;">formatting</span> is to change the format of a file, that is, to change the structure of the records in the following ways:

-   Convert fixed length records to variable length records or vice versa
-   Change the record size
-   Convert stream files to fixed record format files

### About padding and truncating

<span style="font-weight: bold;">Padding</span> involves adding characters at the end of each record in a file to make the record a specified fixed size.

The padding function enables you to convert fixed or variable size records into larger fixed size records.

<span style="font-weight: bold;">Truncating</span> is the inverse of padding. Truncating involves removing characters from the end of each record to convert a padded fixed file into a non-padded variable file. To remove characters, set the final record size to a size equal to or smaller than the initial size. The records are first truncated and then the padding characters at the end of the record are deleted.

In the transfer file attributes you can:

-   Enter a hexadecimal value to specify the padding character
-   Specify whether truncating is allowed

### Controlling the file format

#### Via command line interface

To control file format, set the following parameters in the <span class="code">[peladm create\_appli](../../transfers_start_here/parameters_start_here/applications_start_here/working_with_applications_cli#peladm_create_appli)</span> or <span class="code">[peltrans](../../transfers_start_here/submitting_transfer_requests_start_here/working_with_transfers_cli#peltrans)</span> commands:

When sending a file, use:

-   <span class="code">-rec\_fmt</span> and <span class="code">-rec\_len</span> parameters to control the initial format (variable, fixed or stream) of the file stored on the system
-   <span class="code">-x\_rec\_fmt</span>, <span class="code">-x\_rec\_len</span> and <span class="code">-x\_padding</span> parameters to control the format (variable, fixed or stream) of the file being transferred
-   <span class="code">-truncating\_allowed</span> to allow truncating of characters at the end of records

When receiving a file, use:

-   <span class="code">-rec\_fmt</span> and <span class="code">-rec\_len</span> parameters to control the final format (variable, fixed or stream) of the file you want to store
-   <span class="code">-x\_rec\_fmt</span>, <span class="code">-x\_rec\_len</span> and <span class="code">-x\_padding</span> parameters to control the format (variable, fixed or stream) of the received file
-   <span class="code">-truncating\_allowed</span> to allow truncating of characters at the end of records

#### Via the GUI

Control file format via either of the following objects:

-   Transfer Request: <span style="font-weight: bold;">Attributes</span> tab
-   Application: <span style="font-weight: bold;">Physical file attributes</span> tab and <span style="font-weight: bold;">Transfer attributes</span> tab

Complete the fields on these tabs as follows:

-   In the <span style="font-weight: bold;">Local file attributes</span> section, use the <span style="font-weight: bold;">Record format</span> and <span style="font-weight: bold;">Record length</span> fields to control the initial or final format (Variable, Fixed or Stream) of the file
-   In the <span style="font-weight: bold;">Transfer attributes</span> section, use the <span style="font-weight: bold;">Record format</span> and <span style="font-weight: bold;">Record length</span> fields to control the format (Variable, Fixed or Stream) of the transferred or received file
-   In the <span style="font-weight: bold;">Format</span> section, use the <span style="font-weight: bold;">Padding character</span> and <span style="font-weight: bold;">Truncating allowed</span> fields to specify the padding character to use and whether to allow truncating of characters at the end of records

### Changing the record format to fixed length

When changing the record format to fixed length:

If the output record length is greater than the input record length, Gateway adds padding characters to the input record until it equals the length of the output record

If the output record length is smaller than the input record length and:

-   The option <span class="code">truncating\_allowed</span> is set to <span style="font-style: italic;">Yes</span>, the input record is truncated to the length of the output record
-   The option <span class="code">truncating\_allowed</span> is set to <span style="font-style: italic;">No</span>, Gateway returns an error

### Changing the record format to variable length

When changing the record format to variable length:

Gateway removes all trailing characters from the input record

If the resulting record length is greater than the output record length and:

-   The option <span class="code">truncating\_allowed</span> is set to <span style="font-style: italic;">Yes</span>, Gateway truncates the record
-   The option <span class="code">truncating\_allowed</span> is set to <span style="font-style: italic;">No</span>, Gateway returns an error

### Text format files

Text file records end with a line-feed (LF) character (and possibly an additional carriage return character). Since the line-feed character differs between platforms, the following processes take place:

-   <span style="font-weight: bold;">File sending</span>: the records are sent without the line-feed character. On the receiving platform, the file is then reconverted to text format by adding the line-feed character at the end of each record
-   <span style="font-weight: bold;">File reception</span>: if the local file is defined as a text file, the line-feed character is added at the end of each record

Set the <span class="code">text file</span> attribute in either the Transfer Request or the Application.

### Changing file format from stream to fixed

When you send a stream format file, you can change the file format from *Stream* to *Fixed*. Define the following attributes in either the Application or the Transfer Request:

Local attributes

-   Record format = Stream
-   Organization = Sequential

Transfer attributes

-   Record format = Fixed
-   Record length = required length between 1 and 32 000 bytes
-   Padding character = required padding character
-   Organization = Sequential

<span id="examples"></span>

## Examples

In these examples, the exact names of the parameters depend on whether you use the GUI or online commands.

### Send request

Enter the following values:

Local file attributes

-   Record format: Variable
-   Record length: 80
-   Data code: ASCII
-   TEXT file: yes
-   Padding character: 32

Transfer attributes

-   Record format: Fixed
-   Record length: 90
-   Data code: EBCDIC

#### Results

The format of the file stored on the local disk is variable with a maximum record length of 80 characters. It is a text file in ASCII code.

When Gateway sends the file, it converts it to EBCDIC using the ascii.ebcdic table. It deletes the line-feed characters and pads each record with hexadecimal character 32 up to a fixed length of 90 characters.

### Receive request

Enter the following values:

Local file attributes

-   Record format: Variable
-   Record length: 90
-   Data code: Ascii1
-   TEXT file: yes
-   Padding character: 32

Transfer attributes

-   Record format: Fixed
-   Record length: 90
-   Data code: EBCDIC

#### Results

The file sent by the Remote Site is fixed, has a record length of 90 characters and is in EBCDIC code.

On reception, Gateway converts the file into ASCII via the ebcdic.ascii table. It removes the hexadecimal 32 padding characters at the end of each record to reconvert the file to a variable file.

In addition, since it is a text file, Gateway adds the line-feed character at the end of each record.

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
