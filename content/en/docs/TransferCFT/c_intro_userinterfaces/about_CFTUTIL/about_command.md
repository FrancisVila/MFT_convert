{
    "title": "Display product information",
    "linkTitle": "ABOUT - Displaying computer characteristics",
    "weight": "200"
}## Use the ABOUT command

Use the ABOUT command to display
the Transfer CFT product, host, and key information. This command displays the characteristics of the platform
on which Transfer CFT is installed.

**Syntax**

\[ [COMMENT](../../command_summary/parameter_intro/comment)
= string \]

\[ [TYPE](../../command_summary/parameter_intro/type)
= {
| HOST | CFT } \]

\[ [KEY](../../command_summary/parameter_intro/key) = { <u>FIRST</u> | ALL } \]

Parameters


           | Parameter  | Description  |
 --- | --- | --- |
|  <a href="../../command_summary/parameter_intro/comment">COMMENT</a>  |  Free comment.<br/>This comment is displayed and can be used to indicate a specific item of information, such as the customer name.<br/>This information is then used to determine a software license key.  |
| <a href="../../command_summary/parameter_intro/type">TYPE</a>  | Displays the Transfer CFT product, host, and key information.  |
| <a href="../../command_summary/parameter_intro/key">KEY</a>  | Defines the number of keys that display.  |


Example

This command displays the following type of information:

<span id="CFTTELL"></span>

## Use the cfttell program

UNIX and Windows only

This executable file retrieves system information, for example information needed to request a key. To use `cfttell`:

-   Navigate to the` <CFTDIRINSTALL>/bin` directory
-   Run cfttell

Options:

-   -l, -L each bit of information is displayed on a new line, this is the default option
-   -s, -S values are listed on a single line, separated by spaces using the format key=value, this option is valid for target, version, and uid.
-   -h display this help

Keys:

-   TARGET: lists the target platform
-   VERSION: returns the Transfer CFT version if Transfer CFT is installed
-   HOSTINFO: lists the OS, Transfer CFT version, and related host and machine details
-   UID: Generates a unique id.
-   HOSTINFO: Display information used in key generation.

Examples

 

 
