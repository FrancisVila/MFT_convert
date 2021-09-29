{
    "title": "CFTTELL - Retrieve system information",
    "linkTitle": "CFTTELL - Retrieve system information",
    "weight": "290"
}UNIX and Windows only

This executable file retrieves system information, for example information needed to request a key. To use cfttell:

-   Navigate to the &lt;CFTDIRINSTALL>/bin directory
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

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td>C:\projects&gt;<span>cfttell target</span><br />
win-x86-32</td>
</tr>
</tbody>
</table>

 

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td>C:\projects&gt;<span>cfttell version</span><br />
3000</td>
</tr>
</tbody>
</table>

 

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td>C:\projects&gt;<span>cfttell hostinfo</span><br />
CFT version : 3010<br />
Target : win-x86-32<br />
Processor architecture : x64<br />
Processor type : Intel/AMD X8664<br />
Processor ID :<br />
Number of processors : 2<br />
OS release : Windows Seven Service Pack 1<br />
OS version : 6.1.7601<br />
Host name : ITEM-12345</td>
</tr>
</tbody>
</table>
