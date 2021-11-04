{
    "title": "Use  interactive mode ",
    "linkTitle": "Using interactive mode",
    "weight": "140"
}CFTUTIL can be used in an interactive mode, which consists of several
operating modes that use the same CFTUTIL operations regardless of the operating system.

<span id="Data_entry_in_command_line"></span>

## Data entry in command line

Enter the CFTUTIL commands via the keyboard. The output is sent to the
screen by default, or to a file. For more information see the CONFIG command.

CFTUTIL ‘file\_symb’file\_in file\_out

In this syntax:

-   ‘file\_symb’ designates a character specific to
    each environment. Refer to the Transfer CFT Operating Guide that corresponds
    to your OS

<table>
         
         
         
   
   <th>
      <tr>
<th><p>OS</p>         </th>
<th><p> file_symb</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Windows</p>         </td>
         <td><p>#</p>         </td>
      </tr>
      <tr>
         <td><p>UNIX</p>         </td>
         <td><p> @</p>         </td>
      </tr>
   </tbody>
</table>

-   file\_in is a file
    containing the Transfer CFT commands
-   file\_out is a file
    into which the results of the commands are written

Specifying parameters is optional, the default values are the
standard input and output respectively.

The CFTUTIL module is activated in the Transfer CFT executable file
directory. The file\_in and file\_out designate the complete path or path
relative to the current directory.

On all systems:

-   CFTUTIL standard
    input and standard output are equivalent to:
    -   CFTUTIL ‘file\_symb’
        CFTIN CFTOUT
-   CFTIN and CFTOUT
    are reserved words corresponding to the standard input and output
-   Standard input
    and output to a file: CFTUTIL ‘file\_symb’ CFTIN file\_out
-   File input and
    standard output: CFTUTIL ‘file\_symb’ file\_in CFTOUT
-   File input, file
    output: CFTUTIL ‘file\_symb’ file\_in file\_out

#### CONFIG TYPE=...,FNAME=...

Another way to change the input/output file is to use the CONFIG command with a syntax as displayed
here:

CFTUTIL> CONFIG TYPE=OUTPUT, FNAME=file\_out...> CONFIG
TYPE=INPUT, FNAME=file\_in

See the [CONFIG
command](../../../admin_intro/admin_config_commands/communication_media_concepts).