{
    "title": "Using CFTUTIL Transfer CFT IBM i specific commands",
    "linkTitle": "Using CFTUTIL IBM i specific commands",
    "weight": "290"
}## Line-mode commands

The Transfer CFT utility CFTUTIL can accept line-mode commands. Enter the command at the CFTUTIL &gt; prompt and press ENTER to validate. To exit CFTUTIL, enter the /end command.

Examples

-   In an Transfer CFT IBM i command line, enter the command CFTUTIL and press ENTER.

    Enter the selection or command at the prompt.

    <table data-cellspacing="0">
       <tbody>
          <tr class="odd">
             <td>&gt; CFTUTIL         </td>
          </tr>
       </tbody>
    </table>

-   Enter the command LISTCAT and press ENTER to confirm.
    <table data-cellspacing="0">
       <tbody>
          <tr class="odd">
             <td>            <p>1:Input :</p>
                <p>&gt; LISTCAT</p>         </td>
          </tr>
       </tbody>
    </table>

-   Enter the command /end and press ENTER to exit CFTUTIL.
    <table data-cellspacing="0">
       <tbody>
          <tr class="odd">
             <td>            <p>1:Input :</p>
                <p>&gt; /END</p>         </td>
          </tr>
       </tbody>
    </table>

## Files and individual parameters

CFTUTIL can accept commands passed either as individual parameters or in a command file.

### Command passed as a parameter

The command line is passed as a CFTUTIL parameter using the following syntax:

CFTUTIL PARAM(‘command’ ‘parameter=value, parameter=value,..’)

**Examples**

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>CFTUTIL PARAM('LISTCAT’ ‘TYPE=ALL')</p>
CFTUTIL PARAM('LISTCAT’ ‘CONTENT=DEBUG,DIRECT=SEND')
            <p>CFTUTIL PARAM('SEND’ ‘PART=LOOP,IDF=TEST')</p>
            <p>CFTUTIL PARAM('LISTPARM’ ‘TYPE=RECV')</p>         </td>
      </tr>
   </tbody>
</table>

### File passed as a parameter

The following command runs the CFTUTIL utility, which reads the commands to be executed in the scen.cft file and displays the results.

Example

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>CFTUTIL PARAM('#CFTPROD/UTIN(SCRIPT)')</p>         </td>
      </tr>
   </tbody>
</table>
