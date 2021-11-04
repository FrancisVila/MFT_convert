{
    "title": "Apply a license key",
    "linkTitle": "Apply a license key",
    "weight": "160"
}You need to apply a valid license key to Transfer CFT in the following situations:

-   You perform an initial Transfer CFT installation.
-   A hardware upgrade changes the CPU ID (CPU serial number).
-   After a year passes, to replace an expired license key.
-   To ramp up a Transfer CFT Disaster Recovery instance (for example, on a DR LPAR for z/OS systems).
-   If you are migrating from a version 2.x <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> to a version 3.x.

## Key management

### Obtain a license key

1.  For a new installation, install <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span>.
2.  After completing the installation, or for an existing installation, use the command **cftutil about** to retrieve your system information. For details see the examples below.
3.  Contact the Axway Fulfillment team at the appropriate email address to obtain a valid key.
    -   For a US key, contact: **`fulfillment@us.axway.com`**
    -   For an EMEA or APAC key, contact: **`product.key@axway.com`**
4.  Provide the hostname where Transfer CFT is to be installed or updated.
5.  Provide the list of characters in the CPU ID.

### Apply a license key

Apply the license key(s) that you received from the Axway Fulfillment team as follows:

-   Navigate to the CFTPROD library, and edit the 'KEY' file.
-   Edit the CFTPROD/KEY(KEY) member by entering (writing in) your key.

Examples

Use the CFTUTIL utility to execute the ABOUT command to find the CPU ID.


    CFTUTIL PARAM(ABOUT) 
     Host information :
     * model = 525 * 
    cpuid = 10A16B2

In this example, you would provide the CPU ID <span class="spanboldinpara">10A16B2</span>.

Use the display system value command to get the serial number, known as QSRLNBR:


    DSPSYSVAL SYSVAL(QSRLNBR)
    System value . . . . . : QSRLNBR
    Description . . . . . : System serial number
    Serial number . . . . : 06890AP

In this example, you would provide the CPU ID<span class="code"> 06890AP</span>.

<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Note</strong></span>         </td>
         <td>Your values will differ from those shown in the examples.         </td>
      </tr>
   </tbody>
</table>
