{
    "title": "Apply a license key",
    "linkTitle": "Apply a license key",
    "weight": "170"
}You need to apply a valid license key to Transfer CFT in the following situations:

-   You perform an initial Transfer CFT installation.
-   A hardware upgrade changes the CPU ID (CPU serial number).
-   After a year passes, to replace an expired license key.
-   To ramp up a Transfer CFT Disaster Recovery instance (for example, on a DR LPAR for z/OS systems).
-   If you are migrating from a version 2.x Transfer CFT to a version 3.x.

## Key management

### Obtain a license key

1.  For a new installation, install Transfer CFT.
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

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>CFTUTIL PARAM(ABOUT)</p>
<p>Host information :</p>
<p>* model = 525 *</p>
<p><span>cpuid</span> = 10A16B2</p></td>
</tr>
</tbody>
</table>

In this example, you would provide the CPU ID 10A16B2.

Use the display system value command to get the serial number, known as QSRLNBR:

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>DSPSYSVAL SYSVAL(QSRLNBR)</p>
<p>System value . . . . . : QSRLNBR</p>
<p>Description . . . . . : System serial number</p>
<p><span>Serial number . . . . </span>: 06890AP</p></td>
</tr>
</tbody>
</table>

In this example, you would provide the CPU ID 06890AP.

<table data-cellpadding="0" data-cellspacing="0">
<tbody>
<tr class="odd">
<td data-valign="top"></td>
<td data-valign="top"><span><strong>Note</strong></span></td>
<td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">Your values will differ from those shown in the examples.</td>
</tr>
</tbody>
</table>
