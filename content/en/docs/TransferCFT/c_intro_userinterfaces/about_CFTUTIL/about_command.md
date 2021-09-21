{
    "title": "ABOUT - Displaying computer characteristics",
    "linkTitle": "ABOUT - Displaying computer characteristics",
    "weight": "210"
}## Use the ABOUT command

Use the ABOUT command to display
the Transfer CFT product, host, and key information. This command displays the characteristics of the platform
on which Transfer CFT is installed.

**Syntax**

\[ [COMMENT](../../command_summary/parameter_intro/comment)
= string \]

\[ [TYPE](../../command_summary/parameter_intro/type)
= { ALL
| HOST | CFT } \]

\[ [KEY](../../command_summary/parameter_intro/key) = { <u>FIRST</u> | ALL } \]

Parameters

<table cellspacing="0">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Parameter</th>
         <th>Description</th>
      </tr>
   </thead>
      <tr valign="top">
         <td colspan="1" rowspan="1" width="29.338%">
            <p><a href="../../command_summary/parameter_intro/comment">COMMENT</a>
</p>
         </td>
         <td colspan="1" rowspan="1" width="70.662%">
            <p>Free comment. </p>
            <p>This comment is displayed and can be used to indicate a 
 specific item of information, such as the customer name. </p>
            <p>This information is then used to determine a software license key.</p>
         </td>
      </tr>
      <tr valign="top">
         <td width="29.338%"><a href="../../command_summary/parameter_intro/type">TYPE</a>
         </td>
         <td width="70.662%">Displays 
 the Transfer CFT product, host, and key information.         </td>
      </tr>
      <tr valign="top">
         <td width="29.338%"><a href="../../command_summary/parameter_intro/key">KEY </a>
         </td>
         <td width="70.662%">Defines the number of keys that display.         </td>
      </tr>
</table>

Example

This command displays the following type of information:

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>CFTU20I</p>
            <p>CFTU20I CFT Windows</p>
            <p>CFTU20I Version 3.3.2 20140423</p>
            <p>CFTU20I (C) Copyright AXWAY 1989-2018</p>
            <p>CFTU20I ====&gt; Starting Session on 28/04/2014 Time is 18:54:31</p>
            <p>CFTU20I Parameters file    :C:\AxwayCFT332\Transfer_CFT\runtime\data\cftparm</p>
            <p>CFTU20I Partners file      :C:\AxwayCFT332\Transfer_CFT\runtime\data\cftpart</p>
            <p>CFTU20I Catalog file       :C:\AxwayCFT332\Transfer_CFT\runtime\data\cftcata</p>
            <p>CFTU20I</p>
            <p>CFT information :</p>
            <p>* product  = CFT Windows</p>
            <p>* version  = 3.3.2</p>
            <p>* level    = SP1</p>
            <p>* upgrade  = 7595</p>
            <p>* target   = win-x86-64</p>
            <p>Host information :</p>
            <p>* model    =</p>
            <p>* hostname = MACH-A10229</p>
            <p>* sysname  = Windows</p>
            <p>* machine  = AMT_X8664</p>
            <p>* version  = 6.1.7601</p>
            <p>* release  = Seven Service Pack 1</p>
            <p>* distrib  =</p>
            <p>Axway information :</p>
            <p>* product           = <span>AMPLIFY</span> Transfer CFT</p>
            <p>* version           = 3.3.2_SP1.0</p>
            <p>* applied-patches   =</p>
            <p>* forbidden-patches =</p>
            <p>Key information :</p>
            <p>* idparm                     = IDPARM0</p>
            <p>* key                        = Lxxxxxxxxxxxxxxxxxxxxxxxxxx588S</p>
            <p>*                              CI97S</p>
            <p>* type                       = DATE</p>
            <p>* expire                     = 2018/04/14</p>
            <p>* sysname                    = win-x86-64</p>
            <p>* Nb Transfers               = 999</p>
            <p>* Nb CPU                     = 2</p>
            <p>* Nb Partners                = Max</p>
            <p>* In/Out Bandwidth           = Unlimited</p>
            <p>* In/Out Transfer activation = Unlimited</p>
            <p>* Edition                    =</p>
            <p>* Options                    = BWP CLU FIP ACC ODT CLP CLP XSR SSL SSL</p>
            <p>*                              XTF WBS</p>
            <p>CFTU00I ABOUT    _ Correct ()</p>
         </td>
      </tr>
   </tbody>
</table>

## <span id="CFTTELL"></span>Use the cfttell program

UNIX and Windows only

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

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>C:\projects&gt;<span>cfttell target</span><br/>win-x86-64         </td>
      </tr>
   </tbody>
</table>

 

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>C:\projects&gt;<span>cfttell version</span><br/>3000         </td>
      </tr>
   </tbody>
</table>

 

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>C:\projects&gt;<span>cfttell hostinfo</span><br/>CFT version            : 3010<br/>Target                 : win-x86-32<br/>Processor architecture : x64<br/>Processor type         : Intel/AMD X8664<br/>Processor ID           :<br/>Number of processors   : 2<br/>OS release             : Windows Seven Service Pack 1<br/>OS version             : 6.1.7601<br/>Host name              : ITEM-12345         </td>
      </tr>
   </tbody>
</table>