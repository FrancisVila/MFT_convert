{
    "title": "key",
    "linkTitle": "key",
    "weight": "1770"
}### <span id="key"></span>key

#### ABOUT

\[ KEY = { <u>FIRST</u> | ALL } \]

Defines the number of keys that display.

-   FIRST: Displays the first valid key in the product key file.
-   ALL: Displays all of the keys in the product key file, regardless of if they are valid. Note that there is a one second pause between each displayed key in error. Additionally, expired keys display their expiration date.

#### CFTPARM

\[ KEY = { string 80 } \]

The Transfer CFT user key. You can enter a string of up to 80 characters, which is comprised of the indirection character and file name (file containing the key).

<table data-cellpadding="0" data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td data-valign="top">         </td>
         <td data-valign="top"><span><strong>Note</strong></span>         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">You do not directly set the key with this parameter.         </td>
      </tr>
   </tbody>
</table>

Enter the name of the indirection file (preceded by the &lt;file-symb> character specific to each system) that contains the set of keys associated with the Transfer CFT. The post-installation default values are:

-   Unix and HP NonStop: @conf/cft.key
-   Windows: #conf/cft.key

The key is associated with the contractual conditions for using the software. It is specific to the product host operating system, and the hostname or the CPU ID of the machine (depending on the OS).

The key also limits the following for a Transfer CFT:

-   Maximum number of simultaneous transfers (MAXTRANS parameter limit)
-   Maximum inbound/outbound bandwidth value
-   Maximum inbound/outbound transfer activation value

[Return to Command index](../)
