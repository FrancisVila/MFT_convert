{
    "title": "Apply a\u00a0license key ",
    "linkTitle": "Apply a\u00a0license key ",
    "weight": "200"
}## Check your authorization

Verify that you can access Sphere by going to [support.axway.com](https://support.axway.com/) and logging in. If you do not have an account, follow the instructions in your welcome letter.

Log in to download or access:

-   The product installation package
-   Your product license key
-   Product documentation
-   Product updates, including patches and service packs
-   Product announcements
-   The case center, to open a new case or to track opened cases

You can also access other resources, such as articles in the Knowledge Base, and documentation for all Axway products.

You need to apply a valid license key to Transfer CFT in the following situations:

-   You perform an initial Transfer CFT installation.
-   A hardware upgrade changes the CPU ID (CPU serial number).
-   After a year passes, to replace an expired license key.
-   To ramp up a Transfer CFT Disaster Recovery instance (for example, on a DR LPAR for z/OS systems).
-   If you are migrating from a version 2.x Transfer CFT to a version 3.x.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">You require  as many keys as instances of <span>Transfer CFT</span> running at same time, including when running in multi-node. For example, two Transfer CFT instances cannot run at the same time, on the same server, using the same license key.         </td>
      </tr>
</table>

## Obtain a license key

1.  For a new installation, install Transfer CFT.
2.  After completing the installation, or for an existing installation, use the command **cftutil about** to retrieve your system information. For details see the examples below.
3.  Contact the Axway Fulfillment team at the appropriate email address to obtain a valid key.
    -   For a US key, contact: **`fulfillment@us.axway.com`**
    -   For an EMEA or APAC key, contact: **`product.key@axway.com`**
4.  Provide the hostname where Transfer CFT is to be installed or updated.
5.  Provide the list of characters in the CPU ID.

## <span id="Apply"></span>Apply a license key

To apply the license key from the Axway Fulfillment team, enter the key(s) in the indirection file. Place the character # before the path name of the indirection file. For example, enter **KEY=#prefix..UPARM(PRODKEY)** in the CFTPARM definition. Note:

-   The file can contain one or multiple license keys, but there must be one key per line.
-   On start up the first valid key is used.

Transfer CFT in multi-node architecture can use a single key for a multi-node installation; as either:

-   The hostname must not be defined for the key, or
-   The hostname defined for the key matches the hostname of one of the hosts that composes the multi-node instance

Additionally, the key must have the cluster option.

### Examples

Enter the license key in the following format.

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>CFTPARM    ID       = IDPARM0 ,<br/>…<br/>KEY      =  #%ENVCFT%.UPARM(PRODKEY),</p>
            <p>
<br/>…</p>
         </td>
      </tr>
   </tbody>
</table>

Access the &lt;TARGET>.INSTALL library, and run the JCL called **CFTABOUT**. Near the bottom of the CFTABOUT output, the **`cpuid `line is displayed.**  

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>* cpuid   = 000000000ABC1234</p>
         </td>
      </tr>
   </tbody>
</table>

In this example, you would provide the CPU ID **000000000ABC1234**.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">Your cpuid will differ from those shown in the examples.         </td>
      </tr>
</table>
