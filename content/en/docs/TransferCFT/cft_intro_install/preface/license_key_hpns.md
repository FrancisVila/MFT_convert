{
    "title": "Apply a license key",
    "linkTitle": "Apply a license key",
    "weight": "170"
}You need to apply a valid license key to Transfer CFT in the following situations:

-   When you perform an initial Transfer CFT installation.
-   To replace an expired license key (typically after a year).

## Obtain a license key

1.  After completing the installation, or for an existing installation, use the command <span class="code" style="font-weight: bold;">cftutil about</span> to retrieve your system information.
    <table>
       <tbody>
          <tr>
             <td>         </td>
             <td><span><strong>Note</strong></span>         </td>
             <td>Use the ABOUT command to display
    the Transfer CFT product, host, and key information. This command displays the characteristics of the platform
    on which Transfer CFT is installed.         </td>
          </tr>
       </tbody>
    </table>
2.  Contact the Axway Fulfillment team at the appropriate email address to obtain a valid key.
    -   For a US key, contact: <span class="code">fulfillment@us.axway.com</span>
    -   For an EMEA or APAC key, contact: <span class="code">product.key@axway.com</span>
3.  Provide the hostname and system information for the installed or updated Transfer CFT.

## Apply a license key

To apply the license key, enter the Transfer CFT key in the indirection file, which is referred to in the CFTPARM KEY parameter. The file is located at <span class="code">&lt;installation\_directory>/runtime/conf/cft.key</span> .

-   The file can contain one or multiple license keys, but it must have one key per line.
-   On start up the first valid key is used.

<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Note</strong></span>         </td>
         <td>See the <a href="https://docs.axway.com/bundle/TransferCFT_38_UsersGuide_allOS_en_HTML5/page/Content/CFTUTIL/Parameter_index/key.htm">KEY</a> parameter for an example and details.         </td>
      </tr>
   </tbody>
</table>

## About command

Use the CFTUTIL utility to execute the <span class="code" style="font-weight: bold;">about </span>command to find the CPU ID and general system information as demonstrated in this example.



    Host information :
    * model    =
    * hostname = Cgnac1
    * cpuid    = XXXXXXXXXXX
    * sysname  = NONSTOP_KERNEL
    * machine  = NSX-D
    * version  = 02
    * release  = L18
    * distrib  = unknown

The CPUID is fixed, and as demonstrated in this example is typically <span class="bold_in_para"> XXXXXXXXXXX</span>.