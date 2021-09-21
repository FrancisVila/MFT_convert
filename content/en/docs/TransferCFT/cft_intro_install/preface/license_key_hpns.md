{
    "title": "Apply a license key",
    "linkTitle": "Apply a license key",
    "weight": "170"
}You need to apply a valid license key to Transfer CFT in the following situations:

-   When you perform an initial Transfer CFT installation.
-   To replace an expired license key (typically after a year).

## Obtain a license key

1.  After completing the installation, or for an existing installation, use the command cftutil about to retrieve your system information.

    <table cellpadding="0" cellspacing="0">   <col/>   <col/>   <col/>      <tr>         <td valign="top">         </td>         <td valign="top"><span><b>Note</b></span>         </td>         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">Use the ABOUT command to display 
 the Transfer CFT product, host, and key information. This command displays the characteristics of the platform
 on which Transfer CFT is installed.         </td>      </tr></table>

2.  Contact the Axway Fulfillment team at the appropriate email address to obtain a valid key.
    -   For a US key, contact: fulfillment@us.axway.com
    -   For an EMEA or APAC key, contact: product.key@axway.com

3.  Provide the hostname and system information for the installed or updated Transfer CFT.

## Apply a license key

To apply the license key, enter the Transfer CFT key in the indirection file, which is referred to in the CFTPARM KEY parameter. The file is located at &lt;installation\_directory>/runtime/conf/cft.key .

-   The file can contain one or multiple license keys, but it must have one key per line.
-   On start up the first valid key is used.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">See the  <a href="https://docs.axway.com/bundle/TransferCFT_38_UsersGuide_allOS_en_HTML5/page/Content/CFTUTIL/Parameter_index/key.htm">KEY</a> parameter for an example and details.         </td>
      </tr>
</table>

## About command

Use the CFTUTIL utility to execute the about command to find the CPU ID and general system information as demonstrated in this example.

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>Host information :</p>
            <p>* model    =</p>
            <p>* hostname = Cgnac1</p>
            <p>* cpuid    = XXXXXXXXXXX</p>
            <p>* sysname  = NONSTOP_KERNEL</p>
            <p>* machine  = NSX-D</p>
            <p>* version  = 02</p>
            <p>* release  = L18</p>
            <p>* distrib  = unknown</p>
         </td>
      </tr>
   </tbody>
</table>

The CPUID is fixed, and as demonstrated in this example is typically XXXXXXXXXXX.