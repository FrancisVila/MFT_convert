{
    "title": "Using CFTUTIL Transfer CFT IBM i specific commands",
    "linkTitle": "Using CFTUTIL IBM i specific commands",
    "weight": "290"
}## Line-mode commands

The Transfer CFT utility CFTUTIL can accept line-mode commands. Enter the command at the `CFTUTIL > `prompt and press ENTER to validate. To exit CFTUTIL, enter the` /end `command.

Examples

-   In an command line, enter the command CFTUTIL and press ENTER.

    Enter the selection or command at the prompt.

-   Enter the command `LISTCAT `and press ENTER to confirm.

-   Enter the command` /end `and press ENTER to exit CFTUTIL.

## Files and individual parameters

CFTUTIL can accept commands passed either as individual parameters or in a command file.

### Command passed as a parameter

The command line is passed as a CFTUTIL parameter using the following syntax:

CFTUTIL PARAM(‘command’ ‘parameter=value, parameter=value,..’)

**Examples**

### File passed as a parameter

The following command runs the CFTUTIL utility, which reads the commands to be executed in the `scen.cft` file and displays the results.

Example
